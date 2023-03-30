# 我们希望我们的客户了解 DevOps

> 原文：<https://thenewstack.io/what-we-wish-our-clients-knew-about-devops/>

企业公司通常会陷入依赖工程师来构建面向用户的产品的怪圈，当最终用户对产品不满意并拒绝使用时，他们就会感到沮丧。

通过在产品周期的最开始优先考虑开发运维及基础设施，您的团队可以确保随着越来越多的用户采用该解决方案，它将按预期运行。通过考虑一些关键因素，你可以开发出一个稳定的、可伸缩的、甚至有用的产品。

## 第一步:了解 DevOps 是什么，不是什么

 [艾哈迈德·阿里

Ahmed Aly 为 Umbrage 开发软件。他在 Umbrage 的主要职责是为全球企业和消费者品牌提供离线优先、移动优化的应用程序。他利用自己在 Java、Kotlin 和 Javascript 方面的经验，为 Bose、Sumitomo Corporation、Green Mountain Energy 等客户创建了解决方案。他拥有机械工程和计算机科学的理学学士学位。](https://www.linkedin.com/in/ahmed-aly-68915b81/) 

[DevOps](https://www.gartner.com/en/information-technology/glossary/devops) 捕捉构建、迭代、交付、支持和改进数字解决方案的 360 度视角。整体观点确保了新功能、产品展示的统一性，并抓住了业务的真实需求。在[umbrange](https://www.umbrage.com/home)，我们经常看到不成功的产品，因为它们太专注于工程。

我们最初的发现过程几乎总是表明，当产品最初构建时，它是由开发人员单独构建的。开发一个 app，需要的不仅仅是开发者。作为一名开发人员，我知道我既不是设计冠军，也不是产品冠军；没有这些工艺的拥护者，我不可能成功。

但是成功的产品开发还有另一个重要的方面——devo PS。

DevOps 专注于构建成功解决方案的过程。它不是为了挖掘业务问题或管理向新用户的推广而设计的。这是一种为核心业务问题构建解决方案的强大方法，通过利用 DevOps 思维模式，您可以为您的产品和用户的成功做好准备。

## 第二步:为成功做准备

当您的团队将开发运维作为优先事项时，它使每个人都能为成功做好准备。您的全球团队采用了该解决方案，它可以跨您创建的基础架构进行扩展。但是，由于产品流程通常由 IT 团队负责，因此成功的准备工作不会发生。这里有一个我们经常看到的场景:

开发人员被要求构建一个工具。因此，开发人员构建了一个数据库实例，并在其上放置了一个轻量级 UI。如果他们被告知这是一个优先事项，他们也会把一个移动应用程序放在一起。由于总部团队只使用了其中一个特性，一切看起来都运行得很顺利。但是当全球团队试图部署它时，它就崩溃了。代码不可扩展，云服务没有配置为支持离线功能，修复代码意味着完全重写，因此产品被搁置，回到旧系统。

听起来熟悉吗？

我们发现，花必要的时间去理解对许多用户的限制，这些用户使用应用程序的条件，他们在世界的什么地方使用它，等等，是很重要的。这些因素应该告知基础设施和开发人员如何构建应用程序。

## 第三步:建立你的 DevOps 基础

我们还成功地将[基础设施用作代码](https://channel9.msdn.com/Shows/DevOps-Lab/On-Prem-To-The-Cloud-DevOps-ing-Everything-As-Code-episode-5) (IaC)。这通常意味着使用 Terraform 将我们的基础设施部署到我们正在使用的云服务。如果没有 IaC，IT 团队需要在您使用的任何云控制台中手动调整基础架构的配置。

这就产生了可扩展性、速度和责任性的问题。通过使用 IaC，您的所有配置都包含在一个代码存储库中，开发人员和开发人员可能会访问该存储库。这也弥合了两个领域之间的差距，有助于双方更加协调一致地工作。

另一个成功的例子是集装箱化。我们已经使用 Docker 和 [Kubernetes](https://thenewstack.io/category/kubernetes/) 在不同的容器中分离关注点，这些容器可以伸缩。这使我们能够扩展每个容器，而不是整个代码库。这就是所谓的水平缩放。您可以扩展包含代码片段的单个容器，而不是扩展运行代码的整个服务器。如果一个容器没有看到巨大的负载，就没有必要扩展它。您只需支付扩展最常用区域的费用。

## 步骤 4:衡量 DevOps 课程

构建、交付和扩展数字解决方案是一项艰巨的任务。识别用户真正需要的关键特性，构建一个团队容易使用的应用程序，并在它发展和推出时支持它，这些都依赖于对成功的理解。

以 DevOps 为先的心态，能够收集特定于开发流程的 KPI，如部署时间、部署失败率和计划外工作。此外，您可以在部署应用程序后跟踪数据，如使用统计、服务器性能或错误跟踪。和业务组 KPI/okr 也可以考虑在内。

让团队围绕[交付一个能让整个公司兴奋不已的数字解决方案](https://www.umbrage.com/home)是一项艰巨的任务。但是通过利用一个可靠的 DevOps 方法，您可以拥有满意的用户和开发团队。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>