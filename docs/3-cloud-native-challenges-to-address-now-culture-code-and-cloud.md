# 现在要解决的 3 个云原生挑战:文化、代码和云

> 原文：<https://thenewstack.io/3-cloud-native-challenges-to-address-now-culture-code-and-cloud/>

本文是甲骨文赞助的系列文章中的第一篇，概述了云原生挑战以及如何最好地应对这些挑战。

在第一批大型云服务推出十多年后，我们现在正处于开发服务和工具的黄金时代。开发运维实践和云部署现在是新应用和服务的基础。这些工具不仅仅是为预算庞大的初创公司或云公司准备的。

但是并不是每个开发团队都向云或者使用开源云原生技术过渡。我们正处于这样一个时刻，我们必须让云原生方法和模式对每个人和每个项目开放。这意味着为大量企业开发人员带来更多的服务、工具和最佳实践，这些开发人员拥有内部部署，利用 Java 或 WebLogic 等久经考验的平台，并拥有依赖这些技术运行业务的关键应用程序。他们需要一个路线图来将他们的团队和相关的核心业务应用程序带到云上，并带到像 Kubernetes 这样的云本地技术上。

组织向云迁移所面临的最大问题围绕着人员、流程和技术，这带来了与技术债务相关的阻力。重新培训大型开发团队并将其过渡到 DevOps 文化，或者使用新的开源技术为云重新编写现有的应用程序并不容易。虽然迁移到云托管基础架构的选项通常是很好的第一步，但在云中按原样运行应用程序的经济性可能会掩盖更深入地采用云技术带来的好处。但是他们不能放弃这些基础应用。

其他问题包括需要支持多个云、支持更多地理位置或遵守区域数据保护规则，甚至套利成本，将请求发送到最便宜的服务。

## 三个 C:文化、代码和云

Oracle Cloud Infrastructure 开发人员关系副总裁 Bob Quillin 表示，云原生采用挑战分为三个部分:文化、代码和云。这些部分共同决定了组织内新的和现有的应用程序采用云原生的潜在深度和广度。

*   在云原生计算基金会(CNCF) 最近的 2018 年 8 月[调查中，“开发团队的文化变革”被列为当今使用&部署容器的头号挑战。交付现代应用程序所需的文化，同时继续从早期的 DevOps 实践中发展，已经将许多企业开发人员和团队抛在了后面。除此之外，站点可靠性工程师(SREs)等新角色以及将 DevOps 工作流扩展到整个应用生命周期、安全性和产品管理的新工具进一步强调了为企业而非独角兽设计的更好培训和工具的需求。文化变革并不容易，但其结果是一种工作方式，从敏捷性到可靠性都得到了改善。](https://www.cncf.io/blog/2018/08/29/cncf-survey-use-of-cloud-native-technologies-in-production-has-grown-over-200-percent/)
*   推动这些变化的许多开源代码都源自大型超大规模云平台。Google 的 Borg 诞生了 Kubernetes，它被主要的公共云和全球开源社区如此热情地采用，以至于现在超过一半的代码提交来自 Google 之外。随着平台的发展，它增加了管理部署、控制和监控分布式应用程序的工具。通过 CNCF，相同的代码运行在每个人的云上，从 Raspberry Pis 上的 edge 系统，到 OpenStack 和 Oracle Linux 的内部部署，再到大型公共云的托管 Kubernetes 实例。有大量的选择；事实上，有这么多，它可以混淆选择它们，几乎不可能管理和管理自己。
*   云本身是最后一个元素，因为组织利用公共云的大规模数据中心中可用的计算和存储能力来提供资源和一组新的编码抽象。第一次云部署是相同的服务器，现在像开放计算项目这样的开放硬件项目导致了硬件设计的爆炸式增长，混合了定制 CPU、GPU 和用于机器学习的专用硬件，以及混合硬件和软件的 FPGAs。正是基础设施让我们能够大规模、快速地工作，支持大数据、物联网和机器学习等新技术，但这种丰富性也带来了更多的复杂性。

## 云原生创造结果

把这三个因素做好，会给公司带来改变游戏规则的结果，比如 [TravelTime](https://www.traveltimeplatform.com/) 平台。一种地理搜索工具，使用时间边界，TravelTime 按时间绘制地点地图，显示通勤距离和当地服务。

“我们提供按位置进行大规模消费者搜索的工具，回答‘一小时内我能做什么？’这意味着大量复杂的数据处理，包括公共交通、步行和驾驶，”[查理·戴维斯](https://www.linkedin.com/in/charlie-davies-259b6b9/)说，他是旅行时间平台背后的公司 iGeolise 的联合创始人。

最初，该平台仅支持英国，并且过去需要一周多的时间来处理他们服务所需的每次数据更新。随着全球扩张，支持应用程序所需的数据量呈爆炸式增长。

“我们最初使用自己的服务器，”Davies 说，“但通过与 Oracle 全球创业生态系统计划合作，我们被介绍给了 Kubernetes，并开始在容器中构建微服务。这使我们能够并行处理操作，过去需要一周的时间现在只需要不到八个小时。”这给了他们更多的控制权。"我们可以使用 Kubernetes 根据需要上下旋转容器."

Kubernetes 转向 Oracle 容器引擎改变了 TravelTime 的工作方式。“我们消除了开销问题，”戴维斯说，“把更多的时间花在让我们的系统变得伟大的事情上。”由于不必花时间考虑底层基础设施，他能够从根本上改变公司的工作方式，从投资战略到公司如何以及向何处扩张。“你不需要考虑服务器，你只需要成为最擅长做软件的人。”

## 云原生框架帮助组织实现云原生

随着云原生开发的成熟，新的选项变得可用。像操作符、sidecars 和适配器这样的设计模式将允许现有的单片应用程序集成到分布式系统中，同时帮助解构和重构旧代码。这些方法仍然非常新，但是它们已经开始帮助云迁移。

帮助这种转变的工具和服务也刚刚出现。这与构建新的包容性文化携手并进，扩展了 DevOps 运动的工作，以帮助团队了解如何在新兴的云计算世界中构建和操作分布式系统。云领域的竞争意味着计算和存储越来越便宜，但仍然有很多关于锁定的担忧。在一个平台上构建一切都很好，但是如果您的代码不能迁移或者您的数据受到高额出口费用的影响，该怎么办呢？

Oracle Cloud Native Framework 是这个问题的一个答案，它是 iGeolise 用来构建 TravelTime 的。这是一套一致的基于开源的托管服务和软件，基于 Kubernetes 基础和包装，可以在云中、内部或混合环境中运行。它由一组丰富的新 OCI 云原生服务和最近发布的 Oracle Linux 云原生环境组成。它还附带了基于其他 CNCF 项目构建的额外管理工具，包括利用熟悉的 Terraform 供应工具的资源管理器和额外的监控服务。Oracle Functions 增加了开源 Fn 无服务器平台，使其适合与物联网和各种事件驱动的项目一起工作。

现代云解决方案的应用程序生命周期的所有元素都在，从流程编排和配置，到应用程序定义和开发，以及可观察性和分析。

整个解决方案以容器的形式提供，可以在任何有经过认证的 Kubernetes 的地方运行，消除了供应商的束缚。借助按使用付费的计费模式，Oracle 为企业提供了一种通过托管服务利用全新开源云世界的方式。团队不再需要管理他们自己的资源，但是仍然可以熟悉他们的支持结构。

结果是一个完整的解决方案，有一系列可供选择的部分，这是开源和云不可知的。它可以在任何云上支持您的代码，甚至可以跨多个云工作，无论是混合解决方案还是多云操作。

在下一篇文章中，本系列将深入探讨 DevOps 的未来，以及企业[开发团队如何应对当今的文化挑战](https://thenewstack.io/how-to-build-a-culture-bridge-to-the-cloud/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>