# 可观察性是新的库伯内特

> 原文：<https://thenewstack.io/observability-is-the-new-kubernetes/>

"如今，可观测性就像库伯内特一样受欢迎."

这就是主持人、 [DataStax](https://www.datastax.com/?utm_content=inline-mention) 的[Raghavan“Rags”Sri nivas](https://twitter.com/ragss)在今年的 [KubeCon+CloudNativeCon 北美](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)上启动欧盟可观测状态小组的方式。的确， [OpenTelemetry](https://opentelemetry.io/) 是继 Kubernetes 之后[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的第二或第三大项目。这是有原因的。Kubernetes 使复杂的系统更容易以一种更加分布式的方式创建。这本质上要求更多的[可观察性](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/)，以便理解你的系统的“未知-未知”行为。

Kubernetes 的广泛采用也带来了一定程度的标准化，促进了围绕服务编排和标准化的通用语言和数据。服务网格允许测量服务之间的请求流。这些结合起来使得拥抱可观察性的实践更加容易。现在的问题是如何处理所有的数据——以及随之而来的日益昂贵的遥测技术带来的巨大成本。以及如何开始这一切。

加入斯里尼瓦斯的还有 [Honeycomb](https://www.honeycomb.io/?utm_content=inline-mention) 的 [Liz Fong-Jones](https://twitter.com/lizthegrey) 、 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 的 [Bartek Plotka](https://twitter.com/bwplotka) 、Google OpenTelemetry team 的 [Josh Suereth](https://twitter.com/jsuereth) 和 Polar Signals 的 [Frederic Branczyk](https://twitter.com/fredbrancz) 。Fong-Jones 也是 OpenTelemetry 治理委员会的成员，而 Plotka 和 Branczyk 是 Prometheus 的维护者。这篇文章融合了小组讨论的观点，以及在充满活力的 CNCF 可观测性松弛频道继续进行的对话，都是关于如何聪明地进行可观测性以及还需要发生什么。

## 多少才算知识过剩？

在现场聊天和 Slack following 中导致许多其他人的问题来自 Srinivas:“数据太多了吗？可观测性会变得非常昂贵。什么时候太多太多？当试图将信号从噪音中分离出来时，你如何确保你没有丢掉隐藏的含义？我们在自动化方面取得了哪些进步？”

高质量、精细的可观察性与计算和存储相关成本之间的矛盾是真实存在的。说真的，我们需要知道你的应用程序中发生的所有事情吗？

Fong-Jones 认为，抽样是一种非常有效的方法，可以确保你保留每一个错误，但每 100 或 1000 次成功中只有一次。

她还指出了经常发生的大量重复:将数据发送到日志记录、跟踪和度量平台。"拥有更少的高质量信号比试图得到所有信号要好."

她还建议使用跟踪或结构化日志，而不是非结构化日志，以将标记限制在度量协议中，并且不要集中索引日志——将它们保存在本地机器上，但是使用采样跟踪和度量作为您的集中索引类型。

Fong-Jones 继续说，可观察性和特征标记的协同作用非常强大。这允许您将功能标志值附加到属性，并且您还可以标记更详细的跟踪事件。

随着这一特定的对话深入到 CNCF 的 Slack 聊天中，Suereth 说“可观察性信号是有成本的，在某种程度上，这取决于你能合理地做多少压缩/采样。度量(便宜于)[采样]跟踪(便宜于)日志。您可以只使用结构化日志，并从中推断出所有其他可观察性信号，但您可能会付出很高的摄取/处理代码的代价。”

Branczyk 附和道:“我认为重要的是不要沉迷于一种类型的数据——或者收集机制、协议甚至查询语言。专注于你提出的问题，然后选择正确的工具。现实情况是，每种类型的数据往往擅长某一方面，因此要为工作选择正确的工具！”

Plotka 认为开发人员甚至不应该做决定，而是应该与系统管理员和标准工具协商。“理想情况下，一切都是动态的。我喜欢引入日志度量和跟踪信号的想法——减少重复，所以只做其中之一。

“使用，信号，网络组件——最终你有一致的统计数据可以依赖，但这并不意味着你需要知道过去的每一个信号功能，”普罗特卡说。

Fong-Jones 补充说，如果它确实是高容量的，您可以在单独的线程或连续分析中使用度量和导出计数器。

Branczyck 将持续剖析定义为“对代码正在执行的内容进行采样”。幸运的是，像 eBPF 这样的仪器技术已经使集合部分变得相当轻量级，所以需要解决的只是“存储”问题。”

## 那么，如何开始可观性呢？

更多的数据，更多的学习曲线。即使普罗米修斯和其他工具允许您几乎开箱即可开始观察，即使有工具允许您打开和关闭事物，您也不一定有历史数据。一般的可观察性新手不会理解这些数据。

Srinivas 要求 KubeCon 小组成员提供方法，让人们新的可观察性行走，甚至还没有运行。这一切都始于您的服务水平协议或 SLO。Suereth 说，设置您的日志和指标或日志和跟踪——而不是所有三个——来监控 SLO，以开始了解事情进展缓慢的地方，然后深入到根本原因。

你必须先爬，然后才能跑。他将爬行定义为基于 ops 的反动行为——当系统崩溃时，我能处理吗？与跑步相比，我能否评估某项功能是否改善了我的业务？

Suereth 关于可观察性的啊哈时刻是当他的团队向谷歌的一位副总裁演示时，一切都运行得笨拙而缓慢。为什么那个设备特别慢？他们使用可观察性来识别大规模子系统系统中的子组件，因为他们能够识别隐藏在统计数据中的特定类型用户的特定行为。

重要的是，团队要尽可能早地达到那个啊哈时刻。

对 Fong-Jones 来说，这意味着“不必编写新代码，也不必洞察前进道路上发生的事情。我们如何回答最初编写代码时没有预料到的问题。”

她说，实际上任何可观察性的成功都是在生产中完成的，所以第一步必须是缩短发布周期。

后来，随着谈话转向 Slack，她建议从微服务的覆盖范围开始，只从一两个服务开始——你还不需要完全覆盖。

“我们建议从尽可能靠近用户/入口的地方开始，并根据需要增加新的跟踪跨度，以诊断堆栈中更深层次的问题。”

一位与会者还在 Slack 中问，是否有一种方法可以自动缩小数据的范围，以自动检测问题，就像机器学习一样。是的，这听起来确实很理想，但是这将会使很多学习过程自动化。

Branczyk 在持续的 Slack 对话中回应道，“事实是，理解你的数据比任何类型的机器学习或类似的东西都要有效得多。从简单开始，从我们负载均衡器上的错误和延迟 SLO 开始。对于许多组织来说，这足以引起警惕。以此为起点，然后将其从负载平衡器扩展到应用程序级别。”

## 左移:可观察性的下一步

那么，在未来的两到五年里，可观测性将走向何方？

Fong-Jones 表示，下一步是支持开发人员在代码中添加工具，表示需要在易用性和开箱即用以及每个用例的注释和定制之间取得平衡。

Suereth 说，OpenTelemetry 项目在未来五年内将对应用程序开发人员有用，因为仪器可能特别昂贵。

“目标开发人员为操作提供可观察性，而不是相反。这是通过稳定性和协议实现的。”他说现在的可观察性，就像普罗米修斯一样，更关注于操作而不是开发者语言。“我认为我们将开始看到应用程序将可观察性作为其自身配置文件的一部分。”

Suereth 继续说，OpenTelemetry 开源项目的目标是通过一个简单的拉动就拥有一个包含所有跟踪、日志和指标的 API，但它仍然需要确定应该附加多少数据。“是不是一切都应该尽可能从一开始就能够抽象？但是你不想打开它。向前迈进,(需要)一个对每个标准问题都足够好的基线。”

Fong-Jones 指出，这是左移以缩短反馈周期的下一步。虽然她担心像 DevOps 一样，可观测性的概念会变得淡化。

Branczyk 说，标准化协议对于边缘情况来说非常强大，下一步是开放标准和有线协议的标准化。

他认为最大的挑战是文化。“可观察性肯定还在增长。在许多公司，甚至当我与 Kubernetes 领域的人交谈时，他们中的许多人甚至都没有进行监控——我们处于泡沫之中，需要进行大量的市场教育。”

Branczyk 继续说，对于旧的可观察性帽子，虽然日志度量和跟踪是非常有用的信号，但仍然有更多的数据存在。

“我们正在谈论集群，但有时它们非常小，运行在全球各地的物联网设备中，”他说。“我们也需要工具来处理这些情况。”

很多潜在的可观察性仍然是未知的，但这就是问题的关键，不是吗？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>