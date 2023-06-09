# 可观测性数据增长失控！

> 原文：<https://thenewstack.io/the-growth-of-observability-data-is-out-of-control/>

[](https://www.linkedin.com/in/martinmao/)

 [马丁·毛

马丁·毛是 Chronosphere 的联合创始人兼首席执行官。他之前在优步，领导开发和 SRE 团队，创建和运营 M3。在此之前，他是 AWS EC2 团队的技术负责人，也曾在微软和谷歌工作过。他和他的家人住在我们的西雅图中心，他喜欢在业余时间踢足球和吃肉馅饼。](https://www.linkedin.com/in/martinmao/) [](https://www.linkedin.com/in/martinmao/)

在不抵押你的业务的情况下，基于可观察性数据的爆炸获得正确的结果，现在是 Twitter 的热门话题。

软件工程师 Elan Hasson [在一篇关于可观测性领域一些大玩家的帖子中插话](https://twitter.com/ElanHasson/status/1512408672147673090?s=20&t=4P_8fE09epabriqsE3AlfQ)“为日志和指标支付比运行你的应用支付更多的费用仍然让我着迷。

值得注意的是，这种情况非常普遍，组织为他们的可观察性数据(通常是指标、日志、跟踪，有时是事件)支付的费用比他们为生产基础设施支付的费用多。

又是为了什么目的？如果这些组织可以从更多的数据到更好的结果(更高的可用性、更满意的客户、更快的补救、更多的收入)画一条直线，这种权衡可能是有意义的。

但在很多情况下，这是不正确的。社区同意——在帖子的后面，Hasson 补充道，“为日志/指标/跟踪支付更多费用并不等同于积极的用户体验。考虑可以产生和传输多少数据。$$$.你仍然需要优秀的人才来将数据转化为行动。”

我完全同意。

[云原生应用](https://thenewstack.io/category/cloud-native/)和基础设施正在产生越来越多的可观察性数据，根据 ESG 的数据，71%的公司认为他们的可观察性数据(指标、日志、跟踪)正在以令人担忧的速度增长，但结果却是越来越差，而不是越来越好。

我们怎么知道？

根据来自[page duty](https://www.pagerduty.com/?utm_content=inline-mention)的[研究](https://www.pagerduty.com/state-of-digital-ops/)，从 2019 年到 2020 年，整个平台的关键事件量上升了 19%，并且还在以越来越快的速度继续上升。因此，如果可观测性数据继续以不可持续的速度增长，而结果却越来越糟糕，那么是时候重新思考我们控制可观测性数据的方法了。下面是[我们可以开始解决这个问题的四种方法](https://chronosphere.io/learn/observability-data-growth-to-reach-tipping-point-this-year/):

保留期:大多数公司默认将所有数据保留 13 个月。但是在现代云原生架构中，我们一天要部署多次，一个容器只存在几个小时，大量的现代可观察性数据不需要保留 13 个月。减少数据占用空间的一个策略是为每种数据类型设置最佳保留期。例如，如果您的实验室环境被拆除并每两周重建一次，那么您可能只需要保留两周的可观测性数据。

分辨率:这是指发出数据的频率——例如，每 10 秒跟踪一次 CPU，每分钟跟踪一次，每小时跟踪一次。与保留类似，一种解决方案并不适合所有人。在持续集成/持续交付(CI/CD)用例中——您进行自动化部署，因此每秒或每 10 秒进行一次跟踪是非常有意义的。相比之下，其他使用情形(如容量规划或长期趋势分析)不需要精确到每秒的数据。这里的一个小变化可能会产生很大的影响:每 10 秒测量一次与每分钟测量一次相比，需要产生和存储的数据量相差 6 倍。

高效存储。许多关于可观测性的数据是时间序列数据——这意味着它是对一段时间内某件事情的度量。使用关系数据库、键值存储或 blob 存储不是存储这些数据的有效方式。相反，您需要一个专门为此类解决方案构建的存储解决方案，如时序数据库。

数据聚合。可以说，这是抑制数据增长最有效的策略。公司之间的一个常见模式是发出大量数据，这些数据也有很多维度(也称为高基数)。我们的目标是能够根据这些维度对您的数据进行切片和切块，以快速找出问题发生的位置。这提供了巨大的优势，但也产生了大量低价值的数据。通过聚合提供有用见解的维度组合，同时丢弃大量原始基础数据，组织可以显著减少其数据占用空间。

在一个可观察性数据大规模增长的时代，能够有效利用数据来推动积极成果的组织将脱颖而出。虽然组织不需要一次解决所有这四种方法，但是这些行动将为实现这一目标奠定坚实的基础。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>