# 启动并运行开放策略代理

> 原文：<https://thenewstack.io/getting-open-policy-agent-up-and-running/>

[](https://www.linkedin.com/in/anderseknert/)

[Anders Eknert](https://www.linkedin.com/in/anderseknert/)

[Anders 是 Styra 的一名开发人员，在主要分布式环境的软件开发、安全和身份系统方面有着长期的背景。不在电脑前时，他喜欢看足球、烹饪和比利时啤酒。在推特上关注他，地址是@ anderskernt](https://www.linkedin.com/in/anderseknert/)

如今，越来越多的组织使用开放策略代理(OPA)作为跨云原生体系实施策略的事实标准。作为云计算原生计算基金会(CNCF)的毕业项目，OPA 有数十个用例——从 Kubernetes 护栏、微服务授权到基础设施即服务控制——可供数百万用户使用。

无论一个组织的目标是[大规模的 OPA 用例](https://blog.styra.com/blog/scaling-opa-how-sugarcrm-atlassian-and-netflix-unified-authorization-across-the-stack)，比如那些来自[网飞](https://www.youtube.com/watch?v=R6tUNpRpdnY)或者[亚特兰大](https://www.youtube.com/watch?v=nvRTO8xjmrg&list=PLJHPZt__YGKeCg3Lew3jvCOuyiUhW25Sk&index=3&t=1s)的用例，还是想要从一个单独的 OPA 实例开始，团队都需要先走后跑。在这里，我们讨论公司如何为 OPA 创建一个健壮的策略即代码生命周期，从而允许公司创建可跨团队、集群和云扩展的可重复流程。这不是深入 OPA 的技术细节，而是建立一个框架，团队可以用它来组织和运行 OPA。

## 创建策略即代码生命周期

在任何组织中推行“策略即代码”的关键是理解它只是代码。这意味着您使用 OPA 实施的策略应该与您组织中的其他软件享有相似的生命周期(以及一等公民的地位)。这样的流程不仅有助于初始 OPA 策略的创建，还允许团队更轻松地跨其他团队和流程扩展 OPA，例如他们可能会使用 CI/DC 或 DevOps 流程。

以下是健壮的策略即代码生命周期的基础。第一步是确定您的需求——在哪里以及如何实施 OPA。这包括决定您的域和执行点，如 Kubernetes 准入控制或作为特使微服务边车。它还包括确定您将使用 OPA 执行的真实世界的组织安全和法规遵从性策略—通常存储在 pdf 中或只是存储在人们的头脑中。下一步自然是了解您的集群或应用程序中的数据依赖性，这对于使用 OPA 实施这些策略是必要的。

接下来是为您的用例部署和配置 OPA。OPA 有许多可能的配置——例如，在集群的前端，或者作为微服务的代理侧柜分布——因此，您可能希望尝试不同的[部署选项](https://thenewstack.io/5-opa-deployment-performance-models-for-microservices/),以获得满足您需求的最佳延迟性能。与此同时，还需要将现实世界的策略转换成减压阀的版本控制策略，这是 OPA 的策略语言。幸运的是，有许多资源可以帮助新用户掌握减压阀并开始制定模块化的政策，从充足的[减压阀文档](https://www.openpolicyagent.org/)到[施蒂拉学院的培训课程](https://academy.styra.com/)。

## 确保一致的 OPA 生产

虽然流程的第一阶段是 OPA 所独有的，但是下一阶段，我们可以称之为“生产”，对大多数开发人员来说是熟悉的。在这里，团队将利用典型开发运维或 CI/CD 工作流中的标准流程来完善策略即代码生命周期。

例如，您将首先建立一个 CI 和测试阶段，在此阶段，您将把 OPA 策略组装到一个单一的存储库或库中，并对策略执行单元测试和 QA，以验证它们在实际环境中是否能按预期工作。这不仅在构建新策略时创建了一个安全网，而且在安全性和合规性团队中提高了 OPA 的可信度。此外，这允许您创建策略构建工件或包，然后可以作为常规流程的一部分轻松地将其推送到 OPA 部署。

在部署阶段，您只需将您的策略代码部署到 OPA，并确定每个 OPA 实例刷新其数据的频率，以便做出决策。同时，您还将为依赖于该特定库的每个 OPA 实例部署公共库，从而允许每个实例做出良好、一致的决策。

在倒数第二个阶段，您将针对 OPA 运行状况、策略版本和数据版本监控和协调您的 OPA 部署，就像您对组织中的任何其他软件或服务所做的那样。最后，您将记录 OPA 决策以供审计。将决策日志记录与普通的应用程序日志记录分开，意味着重要的决策(如围绕授权所做的决策)不会淹没在常规应用程序事件的噪音中。通常，团队会将 OPA 决策日志提供给其他安全和法规遵从性管道工具，帮助证明 OPA 做了它应该做的事情，并且以组织的非技术成员可以理解的方式进行。

## 在您的组织内扩展 OPA

通过在您的 OPA 部署的早期构建策略即代码生命周期，您不仅可以确保您的项目顺利进行，还可以通过一个明显健壮的过程在关键利益相关者中建立信誉。此外，这种流程为真正大规模管理 OPA 提供了所需的基础，例如，通过简化与 GitOps 等流程的集成，允许为非技术用户创建策略库，以及支持集中式 OPA 策略部署，最终将通过中央 OPA 管理平台实现。

虽然每个 OPA 项目都是一次旅程，但它们都从同一个地方开始——具有强大的策略生命周期，并通过在组织内灌输策略即代码作为一等公民。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>