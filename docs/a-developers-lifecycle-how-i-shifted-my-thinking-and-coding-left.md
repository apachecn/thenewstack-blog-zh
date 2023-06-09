# 一个开发人员的生命周期:我是如何将我的思维和编码向左转移的

> 原文：<https://thenewstack.io/a-developers-lifecycle-how-i-shifted-my-thinking-and-coding-left/>

## I. W **我们已经在这里**

 [梅丽莎·麦凯

Melissa McKay 是 JFrog 的开发者倡导者。她活跃于开发人员社区，是持续交付基金会下的互操作性 SIG 的主席，是一名国际公共演讲者、作家、Java 冠军、Docker 队长和安全编码的啦啦队长。](https://www.linkedin.com/in/melissajmckay/) 

在我的职业生涯中，我有各种各样的经历，从低级实习生到首席工程师，基于能力水平的期望大相径庭，以及小公司/小团队与大公司/大团队之间的差异。我很感激有机会从一个职位开始，在那里我学会了如何戴几顶不同的帽子。我很早就知道了竞争情报的好处——大约 15 年前！我接受了极限编程的培训，这让我进入了冲刺规划、结对编程和回顾的世界，从规划到发布的整个过程中都看到了特性和错误修复。

我在这种环境中茁壮成长，但回过头来看，我可以诚实地说，与我今天看到的相比，我们的开发管道相对简单。那时候的我，从来不参与释放后发生的任何事情。在那之前我没有处理过任何安全相关的事情。我认为这是在管道末端的操作或安全工程师的手中，甚至可能在部署之后。如果发现了什么，我们将重新开始在开发周期中进行更新的计划阶段。似乎有点晚了，不是吗？

在过去的几年中，许多开发人员在加入 DevOps 团队时已经看到了很多变化，他们应该期待更多的变化。感觉越来越多的责任在转移我们的方式。我不认为这仅仅是更多的工作和更高的期望，而是更多的授权来对我们开发的软件做出更好的决定——更聪明地工作。

开发商正被要求打破各自的小圈子。将代码更改抛在墙上并期待最好结果的日子已经一去不复返了。尽管编码和软件设计的细节总是在我们的专业领域内，但我们也必须承认交付和部署过程中的细节。这包括我们的管道知识和基本的安全概念。更好地理解我们的软件在部署过程中所经历的过程，我们就能更有效地设计实现这一过程的方法。

几年前，我参加了一个面向开发人员的安全培训项目。其中大部分是重复负责任的编码，负责我写的代码，并确保我没有为攻击者制造任何明显的欢迎垫。培训内容包括常见攻击媒介的防御性编码技术，如跨站点脚本、SQL 注入和泄露凭据。有人提到要注意包含已知漏洞的包和库，但是回过头来看，这一点强调得还不够。

然后是 2017 年的 Equifax 漏洞，然后是各种依赖注入攻击，比如网络安全管理软件产品黑客、log4shell、spring4shell 和流氓开发者(仅举几例)破坏自己的开源包！

## **二。我们在哪里**

已经收集了大量关于个人的信息，旨在为公众提供更高效、更高性能的应用程序——社交媒体上有大量个人信息，现在，在线登录您的银行账户以获取最新余额是对优质服务的最低期望。

这类信息的数量和细节对犯罪分子很有吸引力。只要有可能接触到它，攻击者的注意力就不会消失。软件漏洞现在被大肆宣传，如果发现可预防的措施没有被优先考虑或被忽略，这对于组织来说是一种尴尬。在过去的几年中，对消费者的影响稳步增加。简而言之，现在有一个非常个人的成本给开发者，因为我们也利用今天的技术和软件来进一步增强和享受我们自己的日常生活。

安全漏洞已经变得越来越常见，或者至少在媒体上公布得越来越频繁。很明显，当涉及到强化的安全实践时，我们的大部分软件都缺少这个标杆。当被指责的手指四处飞舞寻找谁该受到责备时，预计有几个会落在开发商的方向上。

我们能做什么？仅仅满足于我们开发的软件**能够工作**已经不够了。我们现在需要确保它负责任地运转**。**

 **首先，让我们了解一下我们今天处于这种困境的几个原因。随着大量个人信息的存在，以下因素也起了作用:

*   为了缩短部署时间，我们实现了管道自动化。这根本不是负面的。然而，对速度和自动化的渴望不能也不应该取代测试我们应用程序的努力。看起来我们已经失去了一些测试的艺术，除了“快乐路径”之外的路径有时会暴露我们的应用程序。
*   随着向云原生应用程序开发的转移，开发人员更多地参与将应用程序打包成映像。虽然已经开发了一些工具来简化这一过程，但是当使用开源和其他第三方图像时，对细节的混淆使得一些主要的攻击媒介暴露无遗。
*   鼓励开发者不要重新发明轮子。第三方库的可用性及其数量之多导致了我们经常在应用程序中引入的依赖性的激增。

我们已经认识到，在开发过程的早期关注安全缺陷会带来巨大的不同。我们可能无法预测未来的漏洞，但我们肯定可以使用从以前的攻击中获得的知识来防止由于相同的问题而导致的重复渗透。格言“愚弄我一次，可耻的是你；愚弄我两次，我感到羞耻。当我们得到信息时，我们没有借口。

这并不意味着责任完全在开发者身上。我们非常依赖我们的安全工程师和运营人员，不仅要帮助将安全措施放在适当的位置，还要从一开始就帮助收集和整理安全信息。有人知道吗？

然而，我主要担心的是，随着开发人员越来越多地参与构建云原生应用程序并将他们的应用程序打包到容器中，我们正在增加无意中打包现有漏洞的可能性。我们不仅习惯于引入我们已经熟悉的框架和相关的依赖项，还习惯于从公共资源中引入父映像和基础映像！

更糟糕的是，有些是通过有意隐藏这些细节的插件在幕后自动发生的。意图是好的，主要是试图减轻开发人员的工作流程，但我们真的需要对我们正在做的事情更加了解和小心。我的思绪游走到那个无辜地躺在人行道上的随机闪存盘上。

## **三世。我们需要去哪里**

在过去几年中，安全领域发生了巨大的变化和改进。漏洞数据库持续增长，并提供我们需要的信息-像美国政府的 NVD 和基于风险的安全的 VulnDB，以及其他公共安全漏洞和 CVE 追踪器的来源是非常宝贵的。

使用这些资源的组合，以及提高我们对我们的软件是如何依赖、开源和其他第三方资源构建的认识，将使我们有很长的路要走，以改善我们的保护。许多这种责任都直接出现在开发人员面前。我们处于一个很好的位置，可以直接从我们的开发环境开始漏洞过滤和检测过程！

知识就是力量。这是不可否认的。但是如果你不知道如何处理它，它也会变得非常可怕。收集信息后的下一步是分析信息，这是做出重要决定的时候。现在可供我们使用的数据量是巨大的。现在是时候专注于整理这些数据，然后根据分析提出合理的建议了。

例如，在审查一系列漏洞时，认为我们能够消除所有漏洞是天真的。基于零漏洞策略阻止每次签入或使每次构建失败是不健康的做法。相反，我们需要能够继续前进，并根据以下问题的答案做出合理的决策:

1.  漏洞是否适用于我的软件，被利用会有什么后果？
2.  是否有针对此漏洞的修补程序，实施和/或进行必要的升级需要多少努力？
3.  该漏洞是否严重到足以导致停产？

我认为其中一些决策最好由安全专家而不是开发人员做出，这就是可靠的安全策略发挥作用的地方。作为一名开发人员，我所期待的是更多关于何时敲响警钟的指导。帮助我们衡量严重程度的 CVSS 评分是一个良好的开端，但这是一项正在进行的工作(CVSS v2 对 CVSS v3？)，还有很多事情要做。

总而言之，我们正朝着正确的方向前进。我看到越来越多的漏洞扫描工具是为我们管道最左边的区域——开发人员——设计的。我将拥抱这些工具，它们帮助我在构建软件时做出更明智的决策，尤其是那些我可以直接整合到我现有的开发环境中的工具。

透明而轻松地检测漏洞是很好的第一步。但是现在我看到了那些警告我有危险的红线…接下来我该怎么办？

![KubeCon EU 2022](img/3a946f86447e1f058ffa27e8553342db.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**