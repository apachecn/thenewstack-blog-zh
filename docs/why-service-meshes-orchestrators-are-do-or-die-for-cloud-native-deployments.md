# 为什么服务网格、编排器是云原生部署的成败关键

> 原文：<https://thenewstack.io/why-service-meshes-orchestrators-are-do-or-die-for-cloud-native-deployments/>

[阿斯网](https://aspenmesh.io/)赞助本帖。

 [扎克·乔里

扎克认为，云原生基础设施改变世界运营方式的方式是一种代际转变。作为 Aspen Mesh 的营销主管，他参与推动了该技术的采用。当他不考虑服务网格如何解决微服务运行时的挑战时，他的思维通常会转向满是鳟鱼的蓝色小线。](https://aspenmesh.io/) 

微服务独立、短暂的本质带来了一些严重的好处，但跟踪每一个微服务是一个挑战，特别是当试图弄清楚当一个微服务关闭时，其余的微服务会受到什么影响。最终结果是，如果您在微服务架构中运行或开发，您很可能会花一部分时间思考您的服务到底在做什么。

随着微服务的采用，由于大型系统中存在大量的服务，问题也出现了。像安全性、负载平衡、监控和速率限制这样的问题，曾经必须为一个整体解决，现在必须为每个服务单独处理。

好消息是工程师喜欢好的挑战。几乎就在他们用微服务制造新问题的同时，他们也在用新兴的微服务工具和技术模式解决这些问题。也许微服务的出现只是工程师为了保证工作保障的一个聪明玩法。

今天的云原生宠儿 Kubernetes 缓解了微服务带来的许多挑战。自动调度、水平扩展和服务发现解决了您在使用微服务时会遇到的大多数构建和部署问题。

Kubernetes 没有解决的是几个关键的容器化应用程序运行时问题。这就是服务网格介入的地方。让我们看看 Kubernetes 提供了什么，以及 Istio 如何添加到 Kubernetes 来解决微服务运行时问题。

## Kubernetes 解决构建和部署挑战

Kubernetes 之类的容器编排工具管理着容器化应用程序带来的许多构建和部署挑战。

Kubernetes 支持微服务架构，使开发人员能够抽象出一组 pods 的功能，并通过定义良好的 API 向其他开发人员公开服务。Kubernetes 支持 L4 负载平衡，但它对更高级别的问题没有帮助，如 L7 度量、流量分割、速率限制和电路中断。

## 服务网格解决运行时管理流量的挑战

服务网格有助于解决终端用户使用您的应用程序时出现的许多挑战。如果这些通信是安全的，那么能够监控哪些服务正在相互通信，并且能够控制集群中的服务对服务通信，这是确保应用程序安全且有弹性地运行的关键。

Istio 还通过生成统一的指标来提供整个微服务架构的一致视图。它消除了协调由各种运行时代理发出的不同类型的指标的需要，或者添加任意代理来收集遗留的未装备应用的指标。它增加了跨多语言服务和集群的可观察性，这是任何其他工具都无法在如此细粒度的级别上实现的。

Istio 还增加了更深层次的安全性。虽然 Kubernetes 只提供基本的秘密分发和控制平面证书管理，但 Istio 提供了 mTLS 功能，因此您可以对有线流量进行加密，以确保您的服务到服务通信是安全的。

## 天作之合

将 Kubernetes 与一个类似服务网状的 Istio 结合起来，可以让你两全其美，因为 Istio 是在 Kubernetes 上运行的，所以两者可以无缝地协同工作。您可以使用 Kubernetes 来管理您所有的构建和部署需求，Istio 负责重要的运行时问题。

Kubernetes 已经成熟到大多数企业都使用它来进行容器编排。目前，有 74 家 CNCF 认证的服务提供商，这证明了这是一个巨大且不断增长的市场。我认为 Istio 是 Kubernetes 的扩展，是在一个包中解决更多挑战的下一步。

Istio 已经很快走向成熟，并开始在企业中得到更多的采用。很可能在 2019 年，我们将看到 Istio 成为企业的服务网格标准，就像 Kubernetes 成为容器编排的标准一样。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>