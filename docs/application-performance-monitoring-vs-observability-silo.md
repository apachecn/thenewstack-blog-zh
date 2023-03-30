# 应用程序性能监控与可观察性筒仓

> 原文：<https://thenewstack.io/application-performance-monitoring-vs-observability-silo/>

[Raygun](https://raygun.com/) 赞助本文。

 [让·突尼斯

Jean 是 Raygun.com 的一名作家，也是一名应用和网络性能工程顾问，自 1999 年以来一直在这一领域工作。](https://raygun.com/) 

最重要的能力是可用性。

这是我从体育评论员那里听到的常见说法。无论运动员是在 [NBA](http://www.nba.com/) ， [NFL](https://www.nfl.com/) 还是 [EPL](https://www.premierleague.com/) ，他们都需要在任何人谈论他们在得分或进球方面有多好之前参加比赛。如果一个人因为受伤总是坐在板凳上，他就不可能成为伟大的球员。

同样的原理也适用于 [监控系统](https://raygun.com/blog/monitoring-microservices/) 。传统上，监控只是简单地对设备执行 ping 操作，以检查系统是启动还是关闭，换句话说，就是它的可用性。在过去，这是我们能得到的，也是我们需要的。即使技术不断进步，IT 系统的最基本要求也是可用性。如果您的用户无法获得您的开发人员刚刚从头开始构建的全功能、云原生 web 应用程序，那么其他一切都无关紧要。

但是今天，传统的监测是不够的。随着软件安装在运行在云基础设施上的容器中，我们需要更多。虽然那些旧的监控系统会告诉你什么时候有东西坏了，但你也需要知道它为什么会坏。

这就是可观察性的来源。

## 变得善于观察

可观察性并不像过去几年它的流行程度让你相信的那样新奇。这个术语，或者它的变体，来源于 [控制理论](https://en.wikipedia.org/wiki/Observability) 和量子物理学。

所以能够观察系统状态的抽象概念可以追溯到几十年前。但是为了实际观察和测量某些东西，系统必须公开它的状态。一旦外部提供了内部数据，就可以对其进行收集、存储和分析。

传统的监控工具无法做到这一点。在当今世界中，云基础架构中的 [微服务](https://raygun.com/blog/what-are-microservices/) 非常复杂，您需要为开发运维团队使用超越传统监控的工具。

但即使这样也在改变。

## 预测:你将需要 APM

监控工具，特别是应用程序性能监控(APM)解决方案，已经适应了多年，能够观察这种类型的数据。Gartner 预测，企业组织使用 APM 工具监控的应用程序比例将从 2018 年的 5%增加到 2021 年的 20%。因此，三年来，您的组织可能将其监控翻了两番。

为什么？越来越明显的是，要取得成功，这些组织需要扩大 APM 工具的覆盖范围，以关注客户体验、业务洞察力和服务健康。

但是您需要 APM 工具做什么呢？你有可观察性。反正 [不是监控死了](https://speakerdeck.com/grepory/monitoring-is-dead) 吗？

监控没有死。它只是改变了。

## 可观察性和监控并不矛盾

[监控和可观察并不相同](https://thenewstack.io/monitoring-vs-observability-whats-the-difference/)，但它们也没有什么不同。监控本质上是可观察性的一个子集。它通过更好的可见性和洞察力、更精确的警报以及更快的根本原因识别和调试，帮助您找出问题发生的原因，从而超越了监控。

所以两者一点都不矛盾。他们就像家人一样。

但这不是他们是否相同的问题。关键是要有正确的策略来确保当某个东西坏了的时候，你会发现是这样的情况，并且能够迅速确定它为什么坏了。

目标是避免或最小化对应用程序用户的影响。

## 战略观察家

为了确保你的软件以最高的性能水平运行，你需要开发一个可观察性策略。让我讨论一下这样做时需要考虑的一些事情。

可观察性包括三个关键方面，在任何观察基础设施的策略中都必须包括这三个方面，尤其是如果您的应用程序是云原生的。一个合适的策略包括这三个方面。少一点，你就只能回去监视了。

### 1.韵律学

您可能熟悉从您的 IT 系统收集指标的过程。大部分类似于传统的监控。回到简单的 [SNMP](https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol) (简单网络管理协议)监控时代，系统已经能够在任何给定的时间点提供各种指标的数据。

您可以收集关于各种指标的数据，例如总请求数和错误数。这些数据通常以时间间隔表示，这让您可以将它们放在 [图表和](https://raygun.com/blog/dashboard/) 仪表板上。指标数据还允许您进行趋势分析和容量规划。

有了度量标准，您将能够看到是否有问题或者是否有些事情没有按照预期的那样工作。一旦出现问题，您可以生成警报并得到通知。

### 2.跟踪

从系统中收集跟踪可以让您从用户的角度看到请求，因为他们的请求在您的应用程序中传递。由于微服务的存在，痕迹在当今的现代应用架构中显得尤为重要。这使您能够看到组成应用程序和相关基础设施的所有服务。

趋势是变得更加以用户为中心。您不仅需要观察系统性能，还需要观察用户如何受到性能的影响。 [痕迹](https://raygun.com/documentation/product-guides/apm/traces/) 有助于查明*问题在哪里*——而不仅仅是存在问题的事实。您可以更快地识别系统中导致问题的组件，并通过应用程序的各个部分监控性能。

### 3.日志

[日志](https://raygun.com/blog/c-sharp-logging-best-practices/) 集合已经存在很久了。您拥有由操作系统、应用程序、基础架构生成的日志，应有尽有。日志通常包含应用程序中发生的事件的详细集合。

拥有日志可以帮助您准确地确定是什么导致了问题。但是挑战在于发现应用程序抛出的异常就像大海捞针一样困难。庞大的数量可能会导致难以找到问题的原因。

对于现代应用程序，您不能仅仅依赖系统记录自己的数据。开发人员能够记录关于他们的应用程序的定制数据，这些数据可以在日志中公开和存储。这也应该是你策略的一部分。

因此，通过日志，您可以找到问题的确切原因。

## 到你适合的地方去

有了这三个关键的可观察领域，监控似乎就不需要了。但事实恰恰相反。监控工具允许收集所有这些数据。

[APM 工具已经收集了指标数据](https://raygun.com/blog/apm-tools/) 。您的开发人员可以通过公开度量数据(如 RED 方法:比率、错误和持续时间)来使他们的软件可见。例如，您可以通过在 [部署测试](https://raygun.com/blog/software-deployment-tools/) 期间捕获登录请求率的指标，并将该信息提供给您的监控工具进行分析，从而提高应用程序的可观察性。

跟踪可用于提供例如用户登录请求所经过的每个微服务的利用率信息。有了这些数据，您的 APM 工具可以帮助您快速识别您的 [云基础架构](https://raygun.com/blog/cloud-monitoring-best-practices/) 中的哪个位置出现了登录速度变慢的情况。

很多 APM 厂商也提供 [崩溃报告工具](https://raygun.com/platform/crash-reporting) 。当与这些类型的工具配合使用时，日志数据的捕获是最好的，这些工具可以向您显示导致某些内容被记录的特定代码。这让您可以更快地调试正在影响用户的问题。

## SLO 风格

保证可观察性的最好方法是开发人员在编写软件时将其构建到他们的代码中。将 APM 工具与您的持续交付渠道相集成，可以确保您的整个系统得到观察，从而在出现问题时更容易进行故障排除。

如果你不确定从哪里开始你的可观察性策略，从 [服务水平目标](https://landing.google.com/sre/sre-book/chapters/service-level-objectives/) 或 SLOs 开始。您的 SLO 定义了您为用户提供的系统性能级别。如果您想让用户满意，那么您应该使用您拥有的任何监控工具，并开始开发这些 SLO。一旦您有了目标，您就可以开始实施可观察性的关键领域——度量、跟踪和日志——并将收集的数据发送到您的监控工具。

## 结论:成为伟大的观察者

在您的可观察性支柱之上运行 APM 工具是一种方法，它将帮助您专注于解决客户体验问题，而不仅仅是应用程序健康问题。但是随之而来的是技术和组织方面的挑战。不是每个人都想打破孤岛。

你想简化你的可观察性策略，但是没有精灵会为你做这件事。这需要努力和时间。你必须花时间尽可能正确地做这件事，遵循任何组织过程。您必须观察您的数据，包括您的 APM 工具，并确保当您的用户遇到问题时，您不仅知道是什么导致了问题，还知道为什么。

现在你观察入微了。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>