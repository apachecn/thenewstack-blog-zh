# 这里没有嘘:Ticketmaster 对容器化、集成和变化的热情

> 原文：<https://thenewstack.io/choke-points-ticketmasters-take-containerization-integration-change/>

我们经常谈论新堆栈的创新——容器化、并行化、弹性——好像它们是所有信息技术发展中不可避免的进步。我们通常将它们描述为开发人员领导的革命的原则，这场革命不仅重塑了软件的架构，也重塑了 IT 工作场所的文化。

但是我们观察的是原因还是结果呢？周二下午晚些时候，在柏林 KubeCon 会议的主题演讲中，一个小组讨论揭示了一些真实世界的用例，这些用例让我们的革命性论点听起来有些刺耳。特别是， [Justin Dean](https://twitter.com/justinmdean) ，现场活动访问提供商 Ticketmaster [ *上图右上方* ]的平台高级副总裁，讨论了他的公司自上而下的方法，将容器化作为其开发团队的一项政策。

这是一个没有人能够预料到的对话方向:一个高级管理人员决定执行向容器化的全面过渡的故事，以及一个从他们的角度来看不能很快改变他们旧的编码习惯的开发人员的故事。

## 速度与激情

“几年前，就像所有其他行业一样，我们开始意识到速度是游戏的名字，”Dean 说。“我们需要变得更快，否则我们将开始把大量业务拱手让给竞争对手。我们需要能够比小公司更快地交付软件。作为一家大公司，要想变得敏捷，推出新产品和新功能来与一家初创公司或车库里的两个人竞争，真的非常非常困难。”

迪安没有说这个词，就像霍格沃茨的学生从来不会说“拉尔夫·费因斯”一样，但他指的竞争对手是 StubHub。这是易贝的门票转售部门，据许多人估计，它是世界上最大的赛事门票二级市场。易贝在 2007 年收购 StubHub 后，开始重建其电子商务平台。虽然花了几年时间，但 StubHub 最终赢得了世界的关注，包括 2012 年[将分析应用于打击欺诈](http://www.sloansportsconference.com/content/stubhub-eliminating-fraud-through-analytics/)的新颖方法。

StubHub 的软件开发人员在开源领域声名鹊起，至今仍在 GitHub 上维护着几个项目。2013 年，一位名叫[阿克谢·维亚斯](https://www.linkedin.com/in/akshayvyas21/)的 StubHub 开发者在一次移动网络开发者大会上共同展示了一个主题为“移动网络应用开发趋势”的会议维亚斯兴风作浪，旁观者做着笔记。如今，Vyas 是 Docker Inc .的 UI 工程主管。

据《彭博商业周刊》2015 年初发表的一篇文章称，StubHub 在美国转售了约 30 亿美元的音乐会和体育赛事门票，而同年该市场的年估值预计仅为 50 亿美元。然后在 2016 年 2 月， [StubHub 宣布开发一个完整的、全新的售票管理平台](https://venturebeat.com/2016/02/08/stubhub-takes-on-ticketmaster-with-new-platform-for-both-primary-and-secondary-tickets/)，包括一个全新的移动应用。从网络空间到法庭，它在各条战线上与 Ticketmaster 作战。

Ticketmaster 需要一个全新的、重新焕发活力的平台。昨天就需要了。

## 变形金刚(电影名)

“十年前，我们为公司开发了许多令人惊叹的工具，”Ticketmaster 的院长解释道。“我们有私有云，一切都由 NFS 掌控。我们有自己构建的配置管理系统，它能为你做各种各样的好事……它让[*开发人员*]非常非常容易地与无数的依赖关系捆绑在一起。”

这些开发人员的生计似乎已经被一个本土的工具链的存在所确保，这个工具链是业务中的一切所依赖的。如果 Ticketmaster 的领导人启用核选项:立即废除并替换现有的平台，他们舒适的、有资格的地位将受到威胁。事情就是这样。不仅仅是整个平台被抛弃，开发人员的剩余部分也被告知要保持小规模和敏捷。每个人都被赋予了对自己的粒度代码项目的责任——责任意味着完全的所有权。

> Ticketmaster 一度维护着 150 个并发的持续集成管道。

在所有这些当中，Ticketmaster 选择了 Docker 容器，随后选择了 [Kubernetes](/category/kubernetes/) 容器编排引擎来将混乱变得有序。但后来，高管们决定将其应用部署在公共云上——而不是出于你通常认为的原因。

迪恩表示，采用公共云意味着“迫使每个团队真正解决他们软件的所有基础问题。”他告诉 KubeCon 的与会者，离开开发者为自己建造的舒适的自建巢穴，进入这个集装箱化的新世界的决定完全是由高层决定的，并且是自上而下推动的。

他承认这对整个公司来说是一个挑战。“所有这些事情，你必须自己弄清楚，”Dean 说 Ticketmaster 的开发者被告知。

“所以进入门槛相当高。当你偶然发现这是一种全新的语言时——如果你不太注意的话，所有这些技术都是相当新的。如果你在一个开发团队中，并且你现在正在编写商业软件，这就像，'哦，现在我必须学习所有这些行话，并且弄清楚我要怎么做！'从最终用户的角度来看，您必须了解一个相当大的障碍，即能够成功地将一个遗留应用程序放入一个容器中，而不受所有限制，然后将它放入一个构建管道并继续运行。"

## 直截了当

他说，将项目从私有开发/测试环境过渡到公共生产环境，迫使开发人员坚持一种方法。他接着说，如果没有这种单一方法的承诺，Ticketmaster 就不会筹集资金投资这个新平台。

这是一个你可能听不到的论点，甚至来自你自己的组织，但它实际上可能是真的:部署到公共云迫使开发团队规范他们的过程。在私人空间中，开发人员通常可以自由支配工作流和过程，多个团队可以对如何开展工作进行无限的排列。Dean 告诉观众，Ticketmaster 一度维护着 150 个并发的持续集成管道。

将这些渠道缩小到更舒适的几十个左右，意味着 Ticketmaster 的高管不得不停止关心某些细节，以加强他们对那些他们认为会产生结果的细节的关注。

![](img/79ab92ed4f22628e07152171bd5a63ef.png)

“目前，你如何构建你的软件并不是这个特殊运动真正关心的，”迪恩说。“它在某种程度上假设你正在使用你正在使用的任何东西来达到某一点。为了进入我们世界的集群，我们正试图通过 [GitLab CI](https://about.gitlab.com/gitlab-ci/) 进行标准化，并以非常严格的方式强制一切通过。它必须在 Docker 容器中，必须在 GitLab CI 中。[现在有了赫尔姆](https://thenewstack.io/update-kubernetes-helm-package-manager-simplify-app-deployment/)，我们试图更加符合交付的标准模板。

“但我想说，它仍然——我不知道——不太成熟。他继续说道:“有很多团队在做他们所使用的任何‘当前日’活动。“我要说的是，我们还有一些工作要做，才能达到真正的连续交付、连续部署等等。但是进入这个世界的唯一方法是如果你来自 GitLab CI 世界。所以至少我们把它作为我们的瓶颈。”

贾斯汀·迪恩(Justin Dean)为 KubeCon 观众绘制的开发工作流程包括尽可能缩小开发人员的选择范围，重复使用包括“标准”、“严格”和“强制”在内的词语，并引用装配线工程领域的一个令人惊讶的短语——“瓶颈”——来证明他的论点，即 Kubernetes 可以通过将开发人员的部署选项缩小到一个来使企业 IT 部门的生活更加轻松。然而，如果你想让你代码通过瓶颈，那就去做吧。

“要让你的容器世界恢复正常，你能做的最重要的事情之一就是，强制‘禁止访问’它，”他一度说道。对于“禁止访问”，他的意思是消除对活动容器的 SSH 登录，从而像最初设计的那样加强它们的进程隔离。他说，开发人员的本能是在这里或那里做出快速的改变，或者凭自己的心血来潮进行测试。“当你消除这一点时，你会迫使你的技术栈进行大量的预先思考和大量的成熟，”他说。

他继续说，消除了窥视容器并查看发生了什么的选项，迫使开发人员利用合成监控工具、时序数据和更复杂的警报，使容器变得更智能，以便它们能够照顾自己。

## 蓝雷

Ticketmaster 的故事讲述了一场紧急的商业生存运动，旨在将其开发者的心态从专有天堂转变为开源集市。这场运动远未结束。其他大型企业是否应该向 Ticketmaster 学习？或者把全有或全无的过渡思维强加给他们的开发者会有危险吗？

新的堆栈将这些问题交给了 IBM 自己的两位主要开发人员。

“如果你能首先在企业内部获得支持，那就太好了。我不一定不同意这个观点，”IBM 杰出的软件工程师 [Andre Tost](https://www.linkedin.com/in/andretost/) 回应道，他已经在公司工作了 28 年。“我只是觉得不太现实，尤其是对我们谈的企业来说。没有钱，‘让我们保持一种观点’，这意味着我们需要从字面上理解数百个现有的企业应用程序，并对它们进行重构和重新转移到容器中。”

托斯特和他的同事[凯尔·施洛瑟](https://github.com/kyleschlosser)(任职于混合云首席技术官办公室)是容器化的长期倡导者，他们帮助客户将现有的 *n* 层软件过渡到容器化环境。他们推荐的一种方法是将这些遗留应用程序的代码期望看到的中间件真正容器化——这种方法意味着一种更加渐进的、多阶段的容器流失方法。

“我看到的危险是，这种做法有点半生不熟，人们期望你会从中获得所有好处。但是，因为你只是简单地做了一个“提升和转移”，你仍然需要像以前一样管理它们，因为它们并不真正意味着以[微服务](/category/microservices/)的风格运行。”

但这不是 Ticketmaster 选择的路线:它想要微服务、可扩展性和并行性，并与传统进行斗争。也许它避免了托斯特预见的危险。

“从我们交谈过的所有客户中，我们看到许多人选择了，而不是将工作负载转移到基于容器的系统，”施洛瑟说，“采取提供正确类型的集成的方法，以便我们可以在这些系统之间进行交互。在很多情况下，这意味着从现有系统中公开 API，以便可以从微服务中使用它们——以此作为连接这两个领域的一种方式。”(新的堆栈将在即将到来的关于容器化中间件的特性中展示更多来自 IBM 的施洛瑟和托斯特的内容。)

但正如贾斯汀·迪恩所说，共存不是一个选项。Ticketmaster 正在与一个平台竞争，这个平台最大的优势是没有遗留问题。如果你仔细想想(你不用想太久)，这种情况可能适用于这个星球上几乎所有行业的领先公司。采用 Ticketmaster 的激进方法——加快削减开支，并通过在工作流程中建立瓶颈来强制实现标准化——将是这些领导者考虑的一个选项。

我们喜欢把开源描绘成你的选择。当这是别人的选择时，我们并没有谈论太多。

云本地计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>