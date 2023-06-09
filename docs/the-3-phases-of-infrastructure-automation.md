# 基础设施自动化的 3 个阶段

> 原文：<https://thenewstack.io/the-3-phases-of-infrastructure-automation/>

传统的内部数据中心不会有任何发展，但曾经主导它们的工作流正在迅速过时。在基础设施即服务(IaaS)平台出现与数据中心竞争之前，组织习惯于静态基础设施。资源通常一次性调配，长期持有，并由中央 IT 团队使用票务工作流来控制。

 [陈

Melar 是位于旧金山的 HashiCorp 公司 Terraform 的产品营销经理。当不考虑组织如何利用最新技术实现业务现代化时，你会发现她在户外探索。](https://www.linkedin.com/in/melar/) 

时代变了。现在，组织将他们的数据和应用程序部署到云中，利用按需资源配置的强大功能。但是，在多云环境中调配和维护基础架构(每个环境都有自己的工作流)会带来一系列新的挑战，从管理不同的工作流和基础架构蔓延，到应对分散在不同孤岛中的团队和关键技能差距。考虑到这一点，基础设施自动化的采用通常分为三个不同的阶段:

1.  采用和建立供应工作流。
2.  标准化工作流程。
3.  大规模运营和优化。

## 生活在一个多云的世界

组织和团队继续在多样化的公共云和私有云环境中发现显著的业务优势，使用那些最适合其独特情况和手头任务的环境，并利用根据使用需求上下旋转资源带来的效率。根据 [2021 HashiCorp 云战略状态调查](https://www.hashicorp.com/state-of-the-cloud)，76%的组织已经在使用多种云，86%的组织有望在 2023 年实现这一目标，多云环境的主导地位才刚刚开始。

这对 IT 团队来说是个好消息，因为他们现在在云基础架构中有了更大的灵活性来增强业务运营并帮助实现目标。但缺点是，多个用户和多个云可能会创建一个复杂的生态系统，并增加风险，因为没有合规性和安全性的集中执行，并且对[资源使用和成本](https://thenewstack.io/is-cloud-waste-inevitable-as-companies-move-to-the-cloud/)的洞察较少。

## 多工作流、多云环境中的基础架构问题

现实情况是，旧的配置和工作流规则不再适用于当今的多云环境。组织必须考虑对多个云进行资源调配，而云的动态特性意味着基础架构可以不断修改。云也向更多用户开放了基础设施的创建。

在这种日益复杂的环境中构建、维护和保护基础架构带来了四大挑战:

1.  **不同的工作流:**在一个组织内，一些用户选择特定于云的工作流，而另一些用户选择与云无关的工作流。一些人希望继续在私有数据中心使用基于 GUI 的工作流。这可能导致同一组织内有多个工作流。
2.  **基础架构蔓延:**多个团队和最终用户在整个组织中调配基础架构(有时没有告知更大的组织他们在做什么)，很容易导致重复或未使用的资源，因为没有简单的方法来获得所有基础架构的整合集中视图。无序蔓延、不受控制且未知的基础架构可能会产生组织可能都没有意识到的安全漏洞。
3.  **孤立的团队:**不同的工作流和基础设施的蔓延通常会导致团队使用不同的工具和不同的工作流和流程。这限制了合作。团队可能甚至不知道其他团队在做什么，所以他们不必要地重复工作，并与已经解决的问题搏斗。
4.  **技能差距:**使用多个云需要多个工作流的专业知识。个人可能会专注于特定的技能，而不会跨越所有的工作流程。因此，团队可能不具备调配和管理其所有基础架构所需的所有技能，或者因为团队可能不共享公共参考点而在协作方面遇到困难。

## 基础设施自动化的三个阶段

采用多云策略只是第一步，下一步是成功管理和优化它。这意味着依赖基础架构自动化和通用配置工作流。

组织通常在其基础架构工作流和自动化之旅中经历三个阶段:

### 阶段 1:采用并建立供应工作流

在不同的云或内部数据中心中，每天多次从不同的来源手动配置和更新基础架构，使用大量的工作流会导致混乱。团队将很难协作，甚至很难共享组织基础设施的视图。为了解决这个问题，组织必须采用一种基础架构配置工作流，该工作流对于任何云、服务或私有数据中心都保持一致。工作流还需要通过 API 连接到工作流中的基础设施和开发人员工具的可扩展性，以及跨多个提供商查看和搜索基础设施的可见性。

基础设施即代码(IaC)提供了一种在您的所有基础设施中一致地配置基础设施的方法。这提供了基础架构记录和资源调配工作流，以便作为一个团队进行协作。

### 阶段 2:标准化工作流程

接下来，您希望在整个组织中标准化配置工作流，确保它提供足够的安全性并最大限度地提高效率。传统的、基于票证的基础架构调配方法使 IT 成为看门人，他们充当基础架构的管理者，但同时也制造了瓶颈并限制了开发人员的工作效率。但是，允许任何人在没有检查或跟踪的情况下调配基础架构，会使组织容易受到安全风险、不合规和成本高昂的运营效率低下的影响。

为了避免这些问题，组织需要对工作流进行标准化，以最大限度地减少冗余工作，并包括适当的安全性、合规性和运营一致性防护。关键要素包括将基础架构的可重用组件发布为已由中央 IT 部门验证和批准的代码的能力、将策略和防护栏定义为代码的能力、策略和防护栏的验证和实施、与用于 SSO 的中央 IT 和 ops 工具的集成、审核日志记录、通知，以及通过基于角色的访问控制(RBAC)管理用户和团队的能力。

### 阶段 3:规模化经营和优化

然而，即使是标准化的工作流程也是不够的。为了获得基础架构自动化的全部优势，组织必须能够持续优化其基础架构，并大规模管理和运营基础架构和资源。这意味着将自动化的自助式基础架构供应扩展到开发人员，并提供适当的策略和防护，以及补救策略违规的方法。这意味着每当基础架构发生变化时，就会根据预先确定的参数自动触发警报和通知。它还要求能够使用数据收集见解来优化您的基础架构，例如查看整个组织的云支出以避免过度配置，快速取消未利用或未充分利用的资源的配置，以及创建策略来强制实施最佳实践以避免未来的过度配置。

这种单一的事实来源让组织更容易理解云支出、了解基础架构变化并提供持续的管理和治理，从而为组织提供良好的服务。

基础架构自动化之旅的最后一个阶段允许组织以他们无法实现的方式进行扩展，因为票证批准的速度决定了团队成员可以处理的项目，工作通常是多余的，并且工作流是完全不同的。所有这些都减少了跨平台的麻烦，同时获得了利用多个云的好处。

## 一个工作流程来管理它们

最大限度地发挥基础设施自动化的优势不仅仅是创建和标准化工作流。它是关于简化工作、降低成本和确保组织能够实现云的承诺，从更高水平的灵活性和创新到提高开发人员的工作效率和加快新数字产品和服务的上市时间。

[HashiCorp Terraform](https://www.hashicorp.com/products/terraform) 通过工作流为基础设施自动化提供内置功能，以代码形式构建、组合、协作和重用基础设施。Terraform 具有可扩展性，可与组织的所有基础架构和工具配合使用，并在配置后提供基础架构生命周期管理功能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>