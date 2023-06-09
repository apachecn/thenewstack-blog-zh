# 关于集装箱安全的三个被忽视的教训

> 原文：<https://thenewstack.io/three-overlooked-lessons-container-security/>

上周对我来说是激动人心的一周——我刚刚加入集装箱安全专家 [Aqua Security](http://aquasec.com) ,在特拉维夫呆了几天，了解这个团队和产品。我确信我学到的东西对经验丰富的安全老手来说可能是显而易见的，但对我们其他人来说可能不那么明显！以下是我感兴趣的三个方面，希望您也会感兴趣，即使您以前从未真正考虑过容器化部署的安全性:

## #1:容器图像中的电子邮件地址

我们很多人把联系电子邮件信息放在容器图片里。即使 Docker 文件中的 MAINTAINER 指令被弃用，转而支持使用更通用的标签，也很自然地认为用户会发现能够联系图像作者是有帮助的。

如果你在一家大公司工作，或者你以前在安全部门工作过，你可能会非常清楚你不应该公布单个公司的电子邮件地址，并且你可能会像 Aqua 团队一样在公开的容器图像中发现它们。但这不是我所想的。在开源世界里，我们把我们的名字(或者至少是我们的在线身份)放在我们所做的工作上，这样做似乎很自然。

问题就在这里:如果无名氏在公共容器图像中留下了像 john.doe@giantcorp.com 这样的个人电子邮件地址，任何人都可以很容易地发现(虚构的)巨人公司中有一个叫无名氏的人，他们负责那个特定的组件。这为[鱼叉式网络钓鱼攻击](https://en.wikipedia.org/wiki/Phishing#Spear_phishing)创造了潜在的机会。

当然，如果我们在开源项目上工作，我们仍然容易受到鱼叉式网络钓鱼的攻击，但是在安全性、信任和声誉之间需要达成妥协。如果用户能够看到项目背后的个人开发者，他们会对给定的项目更加信任，而个人通过公开在他们编写的代码上署上自己的名字来建立自己的声誉；这些担忧可能会超过安全风险。相比之下，是巨人公司的品牌声誉激发了客户的信任，在员工的简历上也很好看，所以没有理由把个人的名字放在代码或容器图像上。如果你在做开源代码，你可能会使用个人邮箱，而不是公司邮箱，对吗？

当然，黑客可以在 LinkedIn 上查找巨人公司，并在那里找到许多关于无名氏的信息，所以删除个人电子邮件地址并不能消除总体风险——但它确实减少了攻击面。

因此，如果你为一家公司工作，你应该考虑在公共容器图片中使用通用的电子邮件地址，如 hello@、engineering@或 your-container-name@,而不是你个人的公司电子邮件地址。

## #2:图像扫描并不像看上去那样简单

有很多产品会扫描您的容器图像，让您知道它们是否包含已知的漏洞。Aqua 做到了这一点，但是 [Docker](https://docs.docker.com/docker-cloud/builds/image-scan/) ，CoreOS 的 [Clair](https://coreos.com/blog/clair-v1.html) 以及其他几个人也做到了。他们正在扫描图像，寻找数据库中记录的已知漏洞，如美国国家标准和技术研究所的国家漏洞数据库。听起来很简单，对吧？

但事实证明，在容器图像中检测漏洞的方式非常微妙。

假设有一个虚构的包 mypkg 版本 1.2.7 有一个漏洞(我正在编造)，名为 [CVE](http://cve.mitre.org) -999。mypkg 的维护者修复了该漏洞，并且该修复使其成为 mypkg 1.3.0 的发行版。因此，漏洞数据库可能会说，已知 CVE-999 存在于 mypkg 1 . 3 . 0 之前的任何版本中。

现在，其他几个修复和功能进入了 1.3.0 上游，让我们想象一下被扫描图像的所有者不想要所有这些。相反，她决定只挑选 CVE-999 的补丁。她重新构建了自己的 mypkg 版本，并将其命名为 1.2.7.12345。

根据数据库，漏洞似乎仍然存在，因为 1.2.7.12345 低于已知已应用该修补程序的 1.3.0。但这是假阳性。

它是一个容器图像的事实对这种误报没有任何影响——但是当我们考虑容器层时，也有类似的问题。

假设您有一个包含 mypkg 1.2.7(没有修复)的基础映像，那么我们知道它是易受攻击的。如果扫描程序只是一层一层地报告漏洞，那么问题似乎存在于任何子映像中，即使软件包在不同的层中被版本 1.3.0 所替换。又一个假阳性。

当您部署的代码中存在漏洞时，会出现第三种类型的误报，但只有在与另一个组件交互时才会出现。如果您不使用该组件，该漏洞实际上不会影响您的部署。例如，考虑一个通过网络访问被利用的漏洞。如果容器没有任何网络接口，那么漏洞的存在并不重要。

这些误报不仅仅是令人讨厌——它们让人们很难理解生产中的代码是否真的有问题。人们越习惯于忽略假阳性，当一个重要的真阳性出现时，他们就越不可能注意到并做出反应。

## #3:检测和预防

根据定义，在引入[零日漏洞利用](https://en.wikipedia.org/wiki/Zero-day_(computing))和检测到零日漏洞利用之间存在时间差。在这个间隙中，虽然漏洞是未知的，但图像扫描无法帮助您避免部署该漏洞。套用 [Donald Rumsfeld](https://en.wikipedia.org/wiki/There_are_known_knowns) 的话，我们已经控制了已知的未知，但我们真正需要担心的是未知的未知。

有一天，即使有最严格的政策，您也会将漏洞部署到生产环境中，因为不可能防止部署您不知道是问题的东西。如果该漏洞被利用，它会以某种方式改变您的代码的行为—可能会写入一个不寻常的文件，或者发送意外的网络流量。

![](img/81bf6271305dea9f1d219e051146a800.png)

作者在特拉维夫。

弄清楚什么构成了“正常”行为可能并不简单，但是一个[容器化的微服务架构](/category/microservices/)在这里确实有所帮助。容器中的功能越少，就越容易定义它应该做什么的限制——这给了我们增强安全性的机会。

例如，在容器中运行的微服务通常只使用很少的端口与少量其他服务进行通信。如果您开始注意到相同的代码也试图在完全不同的端口上发送请求，您可能会认为这是可疑的，需要停止并调查。类似地，作为一般规则，您可以预测微服务应该访问的文件或可执行文件的集合。其他任何事情都将是确凿的证据。

检测异常行为意味着您可以发现问题的存在，并且可以进一步禁止意外行为的发生。

## 结论

我刚刚开始触及容器安全中有趣概念的表面，以及我们需要考虑的重要事情，以确保我们的容器化部署尽可能安全。如果有你认为我需要知道的角度，或者你想了解更多的问题，我很乐意[听听你的意见](https://twitter.com/lizrice)。

CoreOS 是新堆栈的赞助商。

图片来自[利兹·赖斯](http://www.lizrice.com/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>