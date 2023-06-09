# 利用微服务实现和谐的流程编排

> 原文：<https://thenewstack.io/achieving-harmonious-orchestration-with-microservices/>

微服务的指数级增长令人震惊。它甚至催生了一个最近才达到病毒式传播顶峰的笑话。Twilio 的开发人员教育家 Joe Nash 开玩笑说，几个有影响力的工程师讨论一个新兴的微服务就足以让它迅速成为更广泛的技术社区的中流砥柱。他想出了 AWS 的一个虚构的新散列服务 Infinidash 来说明他的观点。乔是对的。关于 Infinidash 的讨论主导了社交圈子，最终在流行的消息应用 Signal 发布的一则笑话中达到高潮，该笑话将 Infinidash 称为他们生态系统的核心组成部分。

围绕这种虚构产品的笑话引发了笑声和热议，但除了批评炒作周期的善变本质之外，这件事的要点是显而易见的。虽然微服务能够为开发人员实现快速的功能迭代，并为公司缩短交付周期，但它们可能会很快变成一团乱麻，需要投入大量的时间和金钱。事实上，随着微服务从一种小众的方法发展成为一种标准，它们也变得越来越难以管理和治理。

 [杰西卡·克莱格

Jessica 是 LaunchDarkly 的一名开发人员倡导者，她在那里谈论变化，并撰写关于工程决策对人类的影响的文章。她还为一些科技出版物撰稿，并与黑人女性一起工作，以提高科技行业内的平等和公平代表性。](https://www.linkedin.com/in/jessicacregg/) 

平台工程的艺术和科学已经越来越受欢迎，部分原因是为了理解这个复杂的生态系统。在任何给定的时间里，一个团队可能运行数百个微服务，甚至更多的实例，以及数千次检查，这并不是不可想象的。一个恰当的例子是，Monzo 在一个现在很有名的关于其网络隔离项目的博客 pos t 中详细介绍了其 1500 项微服务。

平台工程从头到尾检查整个软件开发生命周期。这一发现过程的结果为抽象和自动化框架的设计、构建和维护提供了信息，该框架旨在支持应用程序开发生命周期。典型的工作流可能包括一个连接到持续集成系统的源代码控制系统，该系统随后被部署到产品中。

但是随着越来越多的团队配备了自助服务平台，平台的需求可能会迅速发展。应用程序开发团队通常需要不同的工作流来进行持续集成(CI)、持续交付(CD)和部署。随着复杂性的增加，解决方案也在增加。除了您可能遇到的令人头痛的问题之外，当我们考虑到错误配置的可能性时，完全由微服务组成的架构可能会变得非常昂贵，并且是一个很大的风险源，更不用说在发生事故时您可能会发现自己面临的不和谐的警报了。

## 这完全是时间问题

在一个分布式系统中，尽管看起来是对整体的反对，服务从来都不是完全独立的。你还必须解决延迟问题。假设您有一个从数据库中读取数据的服务，那么您现在还需要考虑额外的依赖关系以及异步调用。假设你的团队没有考虑这些电话的方式和顺序。当你完成桌面纸牌游戏时，你会很快积累一堆通知，就像你看到的获胜动画一样。

使用微服务时，您必须严格考虑监控策略，以创建一个您当前团队可以支持的系统。抵制为未来设计的诱惑，关注可伸缩性和现实的可维护性。

## 创造一个有意义的高潮

基于微服务的架构的相互依赖性也使日志记录变得复杂，并使日志聚合成为成功方法的重要组成部分。[金融时报的技术总监 Sarah Wells](https://twitter.com/sarahjwells?lang=en) 监督她的团队将 150 多项微服务迁移到 Kubernetes。在这个项目之前，在创建一个有效的日志聚合系统时， [Wells 引用了](https://www.infoq.com/news/2017/04/avoid-alert-overload-services/)有选择地选择标识事件的度量和命名属性的需要，以及作为事件一部分发生的所有周围事件。关联相关的服务确保系统被设计成在真正有意义的问题发生时标记它们。

在她最近在 QCon 的演讲中，她还提到了在构建日志聚合时理解速率限制的重要性。正如她指出的，当谈到日志时，你通常不知道你是否丢失了重要的记录，直到为时已晚。

一个很好的方法是实现一个将任何情况转化为请求的过程。例如，下一次你的团队发现自己在寻找一条它认为有用的信息时，不要只是满足请求，要将它与你的下一个团队的过程回顾一起记录下来，看看你是否可以扩展你的报告度量。

## 秩序的重要性

同样的事情也发生在你收到的警报上。你有信心理解它们吗？这绝不意味着是一个“号召”，而是一个旨在帮助你停下来思考和重新思考你的方法的问题。如果你不理解一个警告，你可能不是团队中唯一不清楚的人。确保您的团队使用共享的词汇来划分重要性等级，最重要的是，为基础架构的不同领域分配特定的所有者，以保持清晰的报告关系。

最后，不要让事情变得太大。碰巧的是，人们喜欢使用微服务。这些发现在 O'Reilly 去年的[微服务采用调查](https://www.oreilly.com/radar/microservices-adoption-in-2020/)中得到证实，在该调查中，92%的受访者表示微服务取得了一些成功，超过一半(54%)的受访者表示他们的体验“非常成功”

我们固有的偏好很容易导致微服务成为分布式的单片。为了标准化工作方法，团队可能会发现他们的灵活性在努力适应个人偏好时受到了损害。有一套严格的要求来证明某样东西符合目的，同时有一定程度的自动化来防止服务超出容量，这将有助于阻止大量过于急切的采用。

通过特性标志，工程团队可以完全控制不断增长的微服务。将微服务包装在功能标志中，可以在最需要的时候重新路由服务，并在灾难发生时隔离问题。

您是否从事平台工程，并有自己的故事，讲述您是如何实现自助服务抽象、与站点可靠性工程师合作，甚至是如何创建一个解决方案来弥合硬件和软件基础架构之间的差距的？如果是这样，我们希望您能参加我们的第三届年会，[轨道](https://trajectoryconf.com/)，会议将于 11 月 9 日至 10 日举行。[点击此处查看今年活动的关键主题](https://www.cvent.com/c/abstracts/73b6dabe-8ec1-4da2-82a4-cb045f6901d1)，并浏览阵容的最新更新。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>