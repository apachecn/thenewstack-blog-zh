# Kubernetes CI/CD 管道说明

> 原文：<https://thenewstack.io/kubernetes-ci-cd-pipelines-explained/>

为了快速构建和交付健壮的产品，并从自动化和高效协作中获益，软件团队依赖于持续集成/持续交付(CI/CD)管道。为云原生应用实施 CI/CD 使交付周期更加稳健，同时简化了开发和部署工作流。

让我们来谈谈 Kubernetes CI/CD 管道的关键组件，如何优化这些管道，以及一些推荐的最佳实践和工具。

## 是什么造就了 Kubernetes CI/CD 渠道

Kubernetes 平台和 CI/CD 工作流都旨在提高软件质量，以及自动化和提高开发速度。因此，公司受益于与 Kubernetes 一起使用 CI/CD 管道。

以下是基于 Kubernetes 的 CI/CD 管道的一些关键组件:

*   Docker 等容器有助于实现应用程序组件的封装，同时支持运行时的无缝集成。
*   **操作集群**一旦 CI/CD 工具批准了容器，就为您的软件构建部署容器。
*   **配置管理**存储与基础设施设置相关的所有细节，并识别系统中任何新引入的变更。
*   **版本控制系统(VCS)** 是维护代码变更的统一源代码库。这将为 CI/CD 工具生成触发器，以便每当有新的变更被推送到它的存储库中时启动管道。
*   **图像注册表**存储 Docker 容器图像。
*   **安全测试和审计**通过确保管道免受潜在的安全威胁，在应用的快速开发和安全性之间保持平衡。
*   **持续监控和可观察性**通过提供对应用生命周期的全面了解，开发人员可以获得可操作的见解和指标。

## 提高管道效率的关键考虑因素

CI/CD 位于 DevOps 实践的核心，支持可持续模式来简化和加速生产发布。全面理解工作流是构建有效的 CI/CD 管道的基础，同时评估企业需求以帮助选择正确的框架。

以下是提高渠道效率的一些关键考虑因素:

*   **一体化 CI/CD 工具与特定案例解决方案:**与基础设施设置类似，根据使用案例、技术要求和组织目标认真评估可用的 CI/CD 工具至关重要。

*   **内部与托管与混合 CI/CD:** 每种 CI/CD 管道类型都有其自身的有效性，具体取决于您的需求和基础架构。决定选择 CI/CD 管道类型的因素包括易用性、易于设置、基础设施和操作系统支持。

*   **代码测试和验证:**有效的验证和自动化测试框架是 CI/CD 管道的核心组件之一。这确保了稳定的构建，没有代码质量问题，同时突出了潜在的失败场景。
*   **回滚:**这些帮助组织重新部署以前稳定的应用程序版本。在 CI/CD 中实施精心规划的回滚机制对于在出现故障或安全事件时保护应用程序至关重要。

## 定义基于 Kubernetes 的 CI/CD 管道

在定义基于 Kubernetes 的 CI/CD 管道时，您可以选择下面两个主要范例中的一个。

### 基于推送的管道

像配置项管道这样的外部系统会生成构建触发器，以便在基于推送的管道中向版本控制系统存储库提交之后，将更改部署到 Kubernetes 集群。在这种模型中，Kubernetes 集群凭据暴露在集群域之外。

### 拉式管道

每当在基于拉的管道中将新的映像推送到注册表时，Kubernetes 操作人员就在集群内部部署更改。

## 一些最佳实践

以下是构建有效的 Kubernetes CI/CD 管道的一些建议。其中包括一些有用的最佳实践。

### 避免在容器中硬编码秘密和配置

您应该将配置存储在`configmap`**中，而不是硬编码在容器中。这提供了在不同环境中部署相同容器的灵活性，而无需对其进行环境特定的更改。**

 **还建议您将秘密保存在容器之外，并加密后存储在 Kubernetes Secrets 中。这可防止凭据通过 CI/CD 管道中的版本控制系统暴露。

### 使用头盔进行部署

使用 Kubernetes 应用程序部署的 Helm 包管理器跟踪版本或逻辑分组。

### 启用基于 Git 的工作流

为了允许所有基础设施配置都存储在 git 中，CI/CD 管道应该遵循 GitOps 方法。它使开发人员更容易访问基础设施代码，让他们在部署之前检查更改。

Git 还提供了统一的源存储库和集群快照。开发人员可以很容易地根据需要进行引用，并在出现故障时将应用程序恢复到最后的稳定状态。

### 使用淡黄色/蓝绿色部署模式

与正在运行的生产实例并行，运行蓝绿色的实例模式允许您测试更改，并在测试完成时切换流量，消除了部署期间停机的需要。

### 缓存和重用容器图像

使用 Docker 容器图像的缓存和重用功能来最大限度地减少容器构建时间，并降低在新构建的容器图像中引入缺陷的风险。

## Kubernetes CI/CD 管道工具

### 一体化配置项/光盘工具

[**GitHub Actions**](https://github.com/features/actions) 是一款开源的 CI/CD 工具，支持自动化构建、测试和部署管道。当源代码库是 GitHub 时，它是首选的 CI/CD 平台。

[**GitLab CI/CD**](https://docs.gitlab.com/ee/ci/) 方便了软件应用的持续构建、测试和部署，无需第三方集成。

[**Jenkins**](https://www.jenkins.io/) (包括 Jenkins X)是一款开源的自动化服务器，可在不同级别的集群复杂性中提升 CI 和 CD，使开发人员能够跨混合/多云设置无缝地自动化应用构建、测试和部署流程。Jenkins X 是一个升级版本，它为云原生容器化应用程序和编排工具(如 Kubernetes 或 Docker)提供了自动化 CI/CD。

### CI 工具

[**Circle CI**](https://circleci.com/) 是一个基于云的 CI 工具，它使用 API 来促进 Kubernetes 的自动部署。它非常注重在部署之前通过各种方法(如单元测试、集成测试等)测试新的提交。因为它具有实现复杂管道的特性，比如缓存和资源类，所以它是 Kubernetes 生态系统中最流行的轻量级集成工具之一。

[**Drone CI**](https://www.drone.io/) 是一款完全基于 Docker 构建的开源 CI 工具，采用容器优先的方法。Drone 的插件、组件和管道阶段作为 Docker 容器部署和执行。该平台为使用不同的工具和环境进行构建提供了广泛的灵活性，但是您必须将其与 git 存储库集成。

### CD 工具

[**Spinnaker**](https://spinnaker.io/) 是一个开源的持续交付工具，集成了多个云提供商。由于该平台不依赖于 GitOps 模型，配置文件可以存储在云提供商的存储器中。

[**Argo CD**](https://argo-cd.readthedocs.io/) 是一个声明性的 GitOps 连续交付工具，它是轻量级的，易于配置，并且是专门为 Kubernetes 构建的。该平台认为 git 是事实的来源，它增强了安全性，使得访问控制和权限管理更容易管理。

### 自动化和基础设施配置工具

Hashicorp 的 Terraform 是一款开源的基础设施代码工具，可帮助开发团队通过配置文件以编程方式提供和管理基础设施。

[**Red Hat Ansible**](https://www.redhat.com/en/technologies/management/ansible) 是一个开源自动化平台，可实现跨云、虚拟和内部环境的配置、配置管理和基础架构部署的自动化。

### 协作和问题管理工具

[](https://www.atlassian.com/software/jira)**由团队实现，用于软件协作、缺陷跟踪和工作管理。该工具提供可定制的功能，如直观的仪表板、优化的工作流程、高效的搜索、过滤和缺陷管理。吉拉是为支持项目管理的各种用例而专门构建的，例如捕获需求、测试用例管理和实时跟踪任务。**

 **[**Zendesk**](https://www.zendesk.com/in/) 是一个基于云的客户支持平台，使组织能够通过不同的协作渠道与客户互动，包括电话、电子邮件、聊天和社交媒体。Zendesk 为跨职能协作和客户沟通提供了一个易于使用的平台，从而帮助组织更好地管理客户查询并快速响应。

### 安全性

[**开放策略代理(OPA)**](https://www.openpolicyagent.org/) 是一个开源策略引擎，支持高级声明语言，允许开发人员将策略指定为代码。该平台旨在对不同组件实施粒度级策略，包括 CI/CD 管道、微服务、Kubernetes 集群等。

[**Kube-bench**](https://github.com/aquasecurity/kube-bench) 是一款开源工具，用于在 Kubernetes 集群上运行 [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes) 测试。这确保了 Kubernetes 集群是安全的，并根据基准文档中的安全建议进行了部署。

### 监控工具

[**Foresight**](https://www.runforesight.com/) 是一款针对 CI 管道和测试的可观察性产品，可实现对 CI/CD 管道的安全、实时监控。除了跟踪指标、跟踪和日志之外，该平台还提供实时调试功能，以便更快地解决故障。

[**Prometheus/Grafana**](https://prometheus.io/docs/visualization/grafana/)是开源的事件监控工具，实现了高维数据模型，并将指标和时间戳一起存储在时序数据库中。Prometheus 提供了一种灵活的查询语言，是复杂 Kubernetes 集群最流行的警报系统之一。基于 Prometheus 生成的指标，Grafana 为高效的查询和分析提供了内置的可视化支持。

## TL；速度三角形定位法(dead reckoning)

快速交付高质量的软件并不容易维持和扩展。如果您现在开发现代应用程序，CI/CD 位于软件开发过程的核心，因为它提供了灵活性，降低了生产衰退的风险，并确保了质量。为快速工作流执行建立有效的 CI/CD 管道通常被认为是至关重要的。这样做需要勤奋的技术分析，大量的计划和选择正确的工具。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>****