# 蜂巢:调试、协作变得更容易

> 原文：<https://thenewstack.io/honeycomb-making-debugging-collaboration-easier/>

总部位于旧金山的 observability 软件初创公司 Honeycomb 推出了新功能，旨在帮助 DevOps 和现场可靠性工程(SRE)团队更轻松地分析基于事件的生产数据，并更快地解决问题。

它将这些增强功能称为以高分辨率观察生产的能力。Honeycomb 提供所谓的“下一代”应用程序性能管理，旨在调试实时生产软件，使用任何数据模型从任何来源消费事件数据，并鼓励协作解决问题。

新功能包括:

*   **一个重新设计的主页**专注于让团队中最新或最初级的成员也能访问数据，但能够深入到原始事件来探索问题。
*   **BubbleUp** ，允许用户选择热图中的可疑区域来调查异常行为。
*   **直接从线图、直方图或热图中点击**即可访问分布式跟踪，轻松跨服务导航、检查关键细节并发现延迟、错误或重复。
*   **增加了协作功能**，因此用户可以共享和搜索查询历史，重放调试步骤，为新团队成员管理仪表板等。

“其他公司对 AIOps 的想法是‘我们会为您监视您的系统，如果有问题，我们会通知您。相反，Honeycomb 旨在让开发者或运营商能够提出类似“发生了什么奇怪的事情”这样的问题，而不是“当你认为有事情发生时告诉我”。相反，它让你有能力回答你已经提出的问题，”Honeycomb 首席开发人员 Liz Fong-Jones 说。

除了帮助尽快引入新的团队成员，它还旨在提供一个单一的位置来查看数据，共享分析或您昨天或几周前运行的查询的结果。

客户可以从直方图切换到热图，并在跟踪视图中来回切换。公司[去年 6 月增加了寻人软件](/honeycomb-monitoring-now-combines-tracing-with-event-analytics/)。

Fong-Jones 是这样描述的:

"您可以单击以显示具有此延迟的一个跟踪。我可以查看该跟踪，了解一组 API 调用在下游发生了什么。或者你可以使用 BubbleUp。如果你问，‘这些数据是怎么回事？’我们可以回答问题。

它可能会告诉你，有一个用户正不成比例地遇到问题。或者你可以看到它是一个端点。或者 MySQL 持续时间明显不同于对照组的一组值。它可以在 Honeycomb 和 surface insight 中接收丰富的事件，因此您不必马上知道您在寻找什么。我可以说，“让我看看大家都怎么样了。哦，嘿，那看起来很奇怪。让我们只去看看那一个客户。”

*如果我知道某个客户有不好的体验，那这种体验有多糟糕？我们可以看到，一旦客户使用我们的应用程序，他们就会开始有非常糟糕的延迟，然后放弃并离开。*

*在一个统一的视图中获得这样的见解——能够查看整个画面，查看一个单独的跟踪和中间的所有内容——这就是我们使用 BubbleUp 功能所做的事情。*

通过协作功能，用户可以看到队友运行的查询，而不是处理数据的静态不同副本，可以并行检索查询和调试，然后协作共享结果。

在 InfoQ 的一篇文章中，Fong-Jones 提倡生产所有权，她说这需要改变人、文化和流程，而不仅仅是工具。

展望未来，该公司正在超越其事件响应的核心优势。这包括使用 Honeycomb 进行持续优化，并添加更多历史分析功能，以用作服务级别指标和服务级别目标。

她说，“我们已经从仅仅是为高级用户、大而粗糙的 bug 提供的工具，转变为‘这是一个调试工具，你团队中的任何人都可以使用’”。

在之前的一篇 TNS 文章中，Wojtek Chichon 采访了 Honeycomb 的联合创始人和首席执行官 Charity Majors 关于让开发人员随叫随到的重要性、可观察性驱动开发的概念以及团队中的软件所有权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>