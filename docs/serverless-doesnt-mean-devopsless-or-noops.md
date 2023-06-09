# 无服务器并不意味着无开发或无操作系统

> 原文：<https://thenewstack.io/serverless-doesnt-mean-devopsless-or-noops/>

当选择无服务器和 Lambda 作为云操作的首选架构时，您需要了解固有的限制，以便在应用程序和产品代码的规模和复杂性开始增长时进行扩展。

在构建应用程序代码时，Serverless 是一个快速提升的好选择，但是有一个常见的误解，即 serverless 意味着 DevOpsLESS 或 NoOps，事实并非如此。

更重要的是，有时你必须提前真正投资于设计和架构，以免后来碰壁或招致大量技术债务。在本帖中，我们将概述我们在构建 Jit 时遇到的一些限制，Jit 是一个基于无服务器和基于事件的架构的软件即服务 DevSecOps 平台。

## 无服务器问题快速概述

当您的应用程序开始增长时，如果您没有提前计划，就会很快遇到无服务器模式特有的挑战。我们希望帮助那些探索无服务器的人在开始之前就知道他们需要设计什么样的应用程序(或者如果他们已经开始的话，可能会很快返工)。

### 节流

Lambda 节流是您可以同时运行的实例数量的结果。(本帖解释了[如何克服那个](https://www.infoq.com/articles/aws-lambda-avoid-throttling/))。

默认情况下，AWS Lambda 将此限制为 1，000(您可以请求提高此阈值，但首先需要知道它是存在的)。但是请注意，这涉及到成本问题，因此在检查您的架构设计并确保您确实需要之前，您不应该自动提高门槛。

这意味着你同时运行的事件或服务越多，你碰壁的速度就越快。如果您计划完全在无服务器架构上运行，这是您需要在第一行代码中就考虑的事情。

> 虽然你的设计今天可能在小规模下工作，但你必须很早就考虑这是否会线性扩展。

记住，这个限制的目的是保护你和 AWS 免于错误或糟糕的设计。例如，想象一个 Lambda 在循环中调用自己的情况。如果没有这种内置的保护机制，您可能会遇到数百万次调用。

虽然您的设计目前可能在小范围内有效，但您必须尽早考虑当您拥有数千个租户或客户(或更多)时，这是否会线性扩展。根据您如何设计您的资源、Lambdas 和微服务(以及每个服务的“微”程度)，如果您将您的服务分解成过小的块，您可能会由于太多并行事件的限制而中断整个服务链流程。

这意味着您需要很好地了解您当前处理的流量，以每分钟事件的形式，甚至您的服务处理的峰值和异常流量。所有这些都需要考虑，此外还要考虑每种方法所采用的通信调用方法——同步或异步(我们将在后面更深入地探讨这一点)——在同步调用中，每个服务或系统调用加起来会使系统过载。

重要的是要意识到节流的工作方式是不可预测的。因此，即使您有适当的监控来确保您不会达到 1，000 个并行事件，并且您认为您被覆盖了，这实际上也可能发生在您的第一个峰值，其中节流可能发生在更低的阈值，因为这本质上是意外的行为(但记录在 AWS 文档中)。因此，一个好的实践是以一种能够在发生这种情况时恢复的方式来构建您的系统(比如等幂和重试)。

### 超时设定

顾名思义，无服务器不会在永远运行的服务器上运行，它们提供短暂的运行时间，最多只有 15 分钟的函数运行时间。这可能会影响您的服务可以处理的输入大小。当您从一开始就设计函数，并且输入的大小随着处理时间不断增加时，您可能会在运行时遇到超时。

因此，对于运行时与输入大小成线性关系的服务或函数，推荐的设计模式是将输入分成块或批，并在不同的 Lambdas 中处理它们。在这样做的时候，使用队列来避免节流也是一个很好的做法。

### 事件大小

在基于无服务器的系统中流行的事件驱动设计模式，很多时候需要事件处理链中的各种服务，包括 API 网关、SQS (Amazon 简单队列服务)、事件桥、SNS (Amazon 的发布/订阅服务)，其中每一个都有不同的事件大小限制。您使用的每个资源可能有不同的大小限制，您需要知道，当发送大的有效负载时，沿着链传递数据可能会中断。

> 链中的每个资源都能够处理不同大小的有效负载，这意味着如果不提前考虑这一点，您将会遇到失败事件。

这意味着您不能在资源之间发送无限的负载，并且在构建您的函数和服务时需要意识到这一点。链中的每个资源都能够处理不同大小的有效负载，这意味着如果您没有提前考虑这一点，并确保您的系统服务和资源可以接收到该有效负载，您将会遇到失败事件。

一种解决方案，本质上是一种变通方法，可以通过利用支持有效负载大小的不同资源，将较大的有效负载传递到 S3 桶。[专家提示:搜索“AWS 服务配额”以了解更多有关您使用的资源的信息。这是一个[入门的好参考](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-s3-messages.html)。]

### 幂等性

由于上面列出的所有挑战和原因，并且因为故障总是会发生，所以会出现延迟。Lambdas 和无服务器资源通常建立在重试机制上。这就是幂等性的关键所在。对于给定的输入，服务需要提供相同的结果，无论重试或部分重试多少次(这意味着即使只是重试了流的一部分，结果仍然需要相同)。

您需要提前设计幂等性，以便重试和重放不会影响生产系统的状态。一个好的做法是确保在运行数据时，为每个实例创建唯一的、但不是随机的、确定性的 id。这是一个[正确做这件事的好向导](https://aws.amazon.com/premiumsupport/knowledge-center/lambda-function-idempotent/)。

### 内存泄漏

要理解内存泄漏是如何发生的，首先需要理解运行代码的机制是如何工作的，因为它也有其局限性。当涉及到 Lambda 函数时，同一个 Lambda runner 被一次又一次地重用，直到它死去。也许它完美地运行了 1000 次，但它可能在第 1001 次运行时就开始崩溃，并可能导致您的服务出现问题。

例如，用反复使用的同一个解释器来解释 Python 代码。如果这段代码在每次运行时添加全局内存对象，而这些对象可能会通过不同的运行实例传递，这可能会导致内存泄漏，从而超出实例内存限制。然后你的 Lambda 就会崩溃。

这在使用共享资源和多租户架构时尤为重要。您需要确保不会留下未使用的资源、敏感数据或其他垃圾。当谈到租户隔离时，如果您使用共享内存，您需要非常小心，确保数据不会在实例之间泄漏，因为这样数据就可能在租户之间泄漏。我们在一篇关于数据层的[租户隔离](https://www.infoq.com/articles/serverless-tenant-isolation/)的帖子中分享过，但这同样适用于运行时。

### 同步调用与异步调用

无服务器中的同步调用会导致许多问题(上面提到了一些问题，比如节流)。如果可能，并且不需要立即响应，异步调用模式是无服务器的首选模式。

与同步和有状态相比，无服务器通常被设计为更加异步和无状态，因此最好是发挥该技术的优势。当您确实需要同步调用时，请确保使用正确的防护栏，比如使用 API 网关，并通过适当的日志记录获得可见性。

## 成本和容错护栏

这是一个拗口的问题，可能会让那些探索无服务器基础设施的人望而生畏。也就是说，无服务器非常强大、可扩展和灵活，如果有合适的防护栏，您几乎可以完全避免这些问题。

当然，在无服务器上运行的另一个常见问题是成本，这一点不应该被忽略。您设计和构建应用程序的方式也将直接影响成本。您需要有适当的机制来防止过度超出资源，首先是计费警报和一般的成本意识系统设计，这对于无服务器是非常重要的实践。

> 您设计和构建应用程序的方式也将直接影响成本。

其他完全是博客文章的领域是监控和测试无服务器应用程序。正确的监控、可观察性、日志记录和跟踪对于确保当您编写由 50 个 Lambdas 组成的应用程序时，您可以测试流程是否正常工作，以及在生产运行时是否继续正常工作确实非常重要。

当生产意味着 10，000 个租户时尤其如此。了解无服务器架构在幕后如何工作的另一个好处是，通过遵循这里建议的准则，您将获得显著的成本改进，同时获得更好的系统设计。

## 无服务器应用的弹性和健壮性设计

对于那些希望运行速度更快、专注于交付并推出产品和功能而不需要太多管理和基础架构开销的人来说，无服务器是一个绝佳的选择。当选择运行无服务器时，您需要记住这意味着使用许多不同的 AWS 资源，了解每种资源如何独立工作以及如何协同工作，以及它们的局限性和缺陷是至关重要的。

在我们的下一篇文章中，我们将深入探讨其他推荐的无服务器设计模式，包括租户隔离、数据库连接池和最小特权，以及如何避免租户饥饿、无限循环、低效调用和过大的 CPU 和 RAM 实例等反模式。

请记住，与不可预测的动态云环境中的所有云原生应用程序一样，通过监控和日志记录确保您对应用程序的工作方式有适当的可见性对于无服务器应用程序尤为重要。

在使用共享资源和多租户时，确保安全性和数据隐私以不损害关键数据也是至关重要的。有优秀的 [DevSecOps 工具](https://jit.io)可以帮你做到这一点。当您了解您的技术如何在幕后工作时，您可以优化您的设计、架构和应用程序代码，以获得更好的性能、安全性和容错能力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>