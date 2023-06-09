# 站点可靠性工程是一种魔法

> 原文：<https://thenewstack.io/site-reliability-engineering-kind-magic/>

[](https://www.broadcom.com/info/aiops/docker-monitoring)

 [彼得·沃特豪斯

彼得·沃特豪斯是 CA 技术公司的高级策略师。他是一名商业技术专家，在开发、战略、营销和行政管理方面拥有 20 多年的经验。通过他在 CA 的日常工作，Waterhouse 涵盖了 DevOps、移动性、云和物联网等关键趋势。](https://www.broadcom.com/info/aiops/docker-monitoring) [](https://www.broadcom.com/info/aiops/docker-monitoring)

网站可靠性工程师(SRE)可以被认为是 IT 界的奇才，或者像谷歌的 SRE 安德鲁·威多森(安德鲁·)描述的那样“就像是世界上最激烈的维修站工作人员的一部分……在一辆时速 100 英里的赛车上换轮胎。”

那么，站点可靠性工程师(SRE)与传统的 IT 运营有什么不同呢？一门起源于网络规模、云原生独角兽世界的学科能否适用于稳定的企业 IT 状态呢？

是的，可以。横向扩展确实是管理企业 IT 的新方法。企业 IT 闭门造车的观念已经不复存在。现在，创造和开展大规模业务的唯一途径是通过以前所未有的方式管理工程可靠性。对移动体验的需求和复杂云架构的出现转移了运营重心。这不再是让灯亮着的问题。而是关于性能。应用程序必须运行良好，体验良好，背后的基础设施需要持续监控。

可靠性就像任何特性一样，不是部署后就能翻新的东西；它是随着软件的开发、测试和发布而建立和增强的。这意味着建立一门新的学科，谷歌最初的 SRE 负责人本·特雷诺(Ben Treynor)将其描述为“当一名软件工程师被赋予以前被称为运营的任务时会发生什么”

## 令人清醒的现实

很容易再抛出另一个三个字母的首字母缩写词，并声称它是运行复杂 It 系统所涉及的所有问题的灵丹妙药。事实上，将可靠性工程化到具有数千个容器化应用程序和微服务的分布式系统中是一项艰巨的任务。不仅仅是因为所有的移动部件，还因为任何关于可预测系统行为的先入为主的概念都不再适用。

以监视现代软件应用程序为例。这可能包括用多种语言编写的业务逻辑，并链接到遗留的 ERP 系统(定制或打包，或者两者都有)。还会有大量的数据库——传统的用于事务支持的关系型数据库，是的，但更有可能是 NoSQL 数据存储的大杂烩——无论是内存、图形还是文档——也许是最近采用的 Node.js

其中一些组件将是内部的，一些将被容器化并迁移到公共云——这可能意味着 AWS 上的 Docker 和 Kubernetes，但可能是 Azure 和 Mesos——见鬼，为什么不两者都实现一些混合风格的弹性呢？

但就像老蒙提·派森的小品一样，如果这就是你所要管理的全部，那你就很幸运了。根据业务的性质，还会有大量的第三方服务——包括支付处理和对账。更不用说所有新的 web 和移动应用程序通过 API 网关与核心业务系统进行交互，可能还有 Hadoop 和 ElasticSearch 等公司提供的一些分析能力。要保持这种性能，需要大量的操作技巧。

## 命运偏爱勇敢的人

在今年早些时候的一次精彩演讲中，来自 Stripe 的 [Julia Evans](https://www.linkedin.com/in/jvans/?ppe=1) 描述了管理当今复杂分布式系统的现实。她的演讲令人耳目一新的是她公开承认她经常发现工作很难，以及总是有大量的新东西要学。正如她在摘要中所说，她并不总是觉得自己像个巫师(呼应了哈利·波特的抗议)。

这种诚实说明了作为一名 SRE 人的令人兴奋之处。像上面描述的系统会引起许多棘手的问题，只有好奇和勇敢的人才能让生意走上正轨。成为一名 SRE 并不适合胆小的人或者满足于救火现状的人。它是为我们队伍中那些容易感到无聊的人准备的——那些不断询问可靠性问题、精心改进的超级侦探——并且边走边学。

因此，如果我们考虑一个可能影响我们现代应用程序的典型业务关键型问题，比如说某个延迟问题导致越来越多的移动应用程序用户放弃预订服务？团队如何解决这个问题？像这样的问题可能会被忽视一段时间，或者可能会有大量的警报。即使确定了问题，团队在哪里找到根本原因？是新代码发布的问题还是 API 网关的问题？这是因为一些奇怪的微服务自动扩展问题吗？我们认为早期的 CPU 增加是正常的，但实际上非常糟糕吗？

采用 SRE 式的方法，关键业务问题永远不会下意识地得到解决。通过在应用性能管理和应用分析等领域使用现代工具，SREs 可以观察应用的实时行为，系统可以收集和关联来自所有相关组件的信息。这些解决方案不是在事后做出反应，而是不断识别异常模式(如那些移动应用程序放弃)，并将它们与历史趋势进行比较，这意味着 SRE 在业务受到影响之前就得到预警。

但是除了揭露新的正常应用程序的怪异和“未知-未知”，现代工具也鼓励和刺激更多的 SRE 侦探工作——真正有价值的东西。这些工具不会只是检测异常，然后让团队手忙脚乱地在大海捞针。相反，他们会分析性地收集所有证据，并以基于事实的方式带领团队找到解决方案。例如，使用 SRE 启发的监控服务来检测新软件版本引入的性能异常，然后跟踪导致问题的实际代码。

像哈利·波特一样，操作专家可能很难接受他们是巫师。但是问问你自己——你想继续做一个被持续的救火工作弄得筋疲力尽的傻麻瓜吗？当然不是，这是职业限制，很烂。那么，是时候让一些 SRE 魔法——获得采用容器和微服务等新技术所需的技能和工具——成为你的业务面向未来的重要组成部分了。

[![](img/5ab520429f605a02ada8436402231784.png)](https://www.pagerduty.com/summit/)

[CA Technologies](https://www.broadcom.com/info/aiops/docker-monitoring) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>