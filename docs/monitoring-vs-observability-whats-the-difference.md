# 监控与可观察性:有什么区别？

> 原文：<https://thenewstack.io/monitoring-vs-observability-whats-the-difference/>

伊斯梅尔·埃吉尔梅斯

伊斯梅尔是桑德拉公司的业务发展经理。他热衷于销售、营销和发展战略。

现代分布式应用程序无法通过传统方法进行有效监控，传统方法基于处理*可预测的*故障。随着微服务架构现在成为 web 应用程序事实上的标准，有效的调试和诊断要求系统是可观察的，也就是说，可以通过观察其输出来推断其内部状态。

然而，对于开发团队来说，可观察性和监控之间的界限经常是模糊的。在本帖中，我们将讨论监控、可观察性以及二者之间的关系。我们还提到了一些可以用来实现可观察性的工具。

## 监视

采用 DevOps 思维模式的组织通常会开始将应用程序分解为微服务架构，以便获得可操作性，并在发生事故时减少修复时间。但是，随着他们的系统变得越来越复杂，他们必须确保仍然能够看到系统故障，并及时做出反应。

根据谷歌的 SRE 的书，你的监控系统需要回答两个简单的问题:“什么坏了，为什么？”监控允许您使用一组预定义的指标和日志来观察和了解系统的状态。监控应用程序可让您检测一组已知的故障模式。

监控对于分析长期趋势、构建仪表板和发出警报至关重要。它让您知道您的应用程序如何运行、如何增长以及如何被利用。然而，监控复杂的分布式应用程序的问题是生产故障不是线性的，因此很难预测。

话虽如此，监控仍然是构建和运行基于微服务的系统不可或缺的工具。如果监控规则和指标简单明了，并且侧重于可操作的数据，它们将为您的系统健康状况提供一个相当好的视图。虽然监视可能不会使您的系统完全免受故障影响，但它将提供系统行为和性能的全景视图，使您可以看到任何故障的影响以及后续的修复。

## 可观察性

起源于控制理论的可观测性，衡量你从系统的外部输出中了解系统内部状态的程度。可观察性使用仪器来提供有助于监控的见解。换句话说，监控就是你在之后*所做的事情，一个系统是可观察的。没有一定程度的可观察性，监控是不可能的。*

可观察的系统允许您了解和测量系统的内部，以便您可以更容易地从结果导航到原因——即使在复杂的微服务架构中。它帮助您找到以下问题的答案:

*   请求通过了哪些服务，性能瓶颈在哪里？
*   请求的执行与预期的系统行为有何不同？
*   为什么请求失败了？
*   每个微服务是如何处理请求的？

可观察性可分为三个主要支柱:

*   **日志**:带有时间戳的、不可变的离散事件记录，可以识别系统中不可预测的行为，并提供对出错时系统行为变化的洞察。强烈建议以结构化的方式接收日志，比如 JSON 格式，这样日志可视化系统就可以自动索引并使日志易于查询。
*   **度量**:监控的基础，度量是在一段时间内聚集的计数或测量。度量将告诉您一个方法使用了多少内存总量，或者一个服务每秒处理多少请求。
*   **跟踪**:对于单个事务或请求，单个跟踪显示了它在分布式系统中从一个节点移动到另一个节点时的操作。通过跟踪，您可以了解特定请求的细节，确定哪些组件导致了系统错误，监视模块中的流程，并找到性能瓶颈。

## 可观察性与监控的关系

可观察性和监控相辅相成，各有不同的用途。

监控告诉你什么时候出了问题，而可观察性让你明白为什么。监控是可观察性的一个子集和关键行动。你只能监控一个可见的系统。

监控跟踪应用程序的整体健康状况。它汇总了系统在访问速度、连接性、停机时间和瓶颈方面的性能数据。另一方面，可观察性通过提供对特定故障模式的粒度和上下文洞察，深入到应用程序操作的“是什么”和“为什么”。

虽然监控只为已知的问题或事件提供答案，但为可观察性而配备的软件允许开发人员提出新的问题，以便调试问题或了解通常具有不断变化的复杂性和未知排列的动态系统的一般状态。

## 建立一个可持续观察的系统

实现可观测性并不一定很难。您可以从许多与您的应用程序相关的关键指标入手；例如应用程序的 CPU、网络和内存。

系统日志对于确保系统的可观察性也是必不可少的。尽管日志可能会快速增长并变得难以管理——存储起来也很昂贵——但是有一些工具可以提高日志记录的效率。一个例子是 [OpenTelemetry](https://opentelemetry.io/) ，它不仅用于日志记录，还用于度量整理和跟踪。OpenTelemetry 还集成了流行的框架和库，如 Spring、ASP.NET 核心和 Express。

跟踪使您的可观察系统更加有效，并允许您识别分布式系统中问题的根本原因。跟踪可以被视为可观察性实现的最重要部分:理解您的微服务架构中的因果关系，并能够从结果到原因跟踪问题，反之亦然。

持续的自动化可观察性让您在整个软件开发生命周期中保持对任何风险或问题的掌控。它提供了跨整个 CI/CD 管道和您的基础架构的可见性，让您可以随时快速反馈您环境的运行状况，包括生产前阶段。

## 可观察性工具

为了管理分布式系统基础设施，您需要一套专用的工具来可视化您的操作状态，并在出现故障时通知您。这些工具允许您了解系统行为并防止未来的系统问题。

在我们的白皮书“[监控与可观测性”](https://www.thundra.io/whitepaper/monitoring-vs-observability?utm_source=newstack&utm_medium=paid&utm_campaign=WP-Monitoring%20vs%20Observability&utm_content=lp_monitoringVsObservability)中，我们深入描述了三个领先的可观测性平台: [OpenTelemetry](https://opentelemetry.io/) 、 [Jaeger](https://www.jaegertracing.io/) 和 [Zipkin](https://zipkin.io/) 。

还有许多工具可以帮助检测您的应用程序。一个很好的例子是我们自己的工具[桑德拉](https://thundra.io)，它为可观测性提供了一个自动化的即插即用解决方案，同时为与 OpenTracing 兼容的手动仪器打开了大门——并且很快将开放遥测。

## 最后一点:观察和改进

生产中的应用程序会因为各种原因而失败。无论你付出多少努力，总会有出错的地方。如果你不能有效地检测你的应用程序的组件，你将很难[调试生产问题](https://thenewstack.io/platform-agnostic-tracing)。另一方面，即使是一个可观测的系统也没有所有问题的答案。

你需要不断地检查你所拥有的数据，以确定其有用性。可观察性必须有正确的数据来帮助你得到生产中已知和未知问题的答案。您必须不断调整系统的仪表，直到它可以被适当地观察到，直到您可以得到任何问题的答案，以支持您的应用达到您想要的质量水平。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>