# 向 Kubernetes 介绍开源零信任

> 原文：<https://thenewstack.io/introducing-open-source-zero-trust-to-kubernetes/>

越来越多的组织正在使用云原生和开源技术来快速实现现代化。

 [凯尔·亨特

凯尔是拉菲系统公司的产品营销主管。他在信息传递和定位、竞争差异化、走向市场战略和思想领导力方面有着出色的表现。](https://www.linkedin.com/in/kylehunter) 

2022 年第一季度，全球在云基础设施上的支出是 2019 年第一季度的两倍(根据 [Statista](https://www.statista.com/statistics/967292/worldwide-cloud-infrastructure-services-market-revenue/) :分别为 559 亿美元和 275 亿美元)。在这些转变中，随着更多的用户、数据和应用程序增加了风险，安全性成为一个关键的考虑因素。组织必须严格审视谁负责安全，以及他们是否真正准备好迎接挑战。

组织为更好地解决安全问题而采取的一种方法是零信任。零信任不会自动将网络的一部分视为可信网络并要求对其他活动进行身份验证，而是假设所有网络流量都是恶意的。零信任就像一个入侵已经在进行中一样，让整个网络中的每个人对每个操作或请求进行身份验证。这很快成为网络安全的最佳实践。

让我们来看看零信任的要求，将零信任应用到 Kubernetes 所面临的挑战，以及可以帮助缓解这些挑战以保持应用程序现代化的开源解决方案。

## 零信任的必要条件

到达并危及一个端点就足以触及敏感数据，这是许多攻击者的终极目标和高价值目标。零信任通过消除可传递的信任，并在授予跨网络的访问权限之前不断进行识别和验证，防止攻击者在入侵后横向移动。

可信网络每天都被用来发起攻击和提升权限，这意味着假设信任的模型始终容易受到入侵者的攻击。越来越多的应用程序意味着安全漏洞比以往任何时候都多。随着越来越多的内部人员(开发人员、架构师、承包商等)访问网络。—许多用户可以访问比他们应该访问的更多的数据和网络资源。零信任将网络用户限制在其角色所需的访问权限内。

## Kubernetes 面临的零信任挑战

尽管许多组织认识到零信任的价值，但他们通常不知道如何或从哪里开始。在已经建立的安全实践中实施零信任原则可能会留下一些空白，因此向零信任模型的转变需要利益相关者的支持和准备。

Kubernetes 有很多可移动的部分，比如 pod、副本集和有状态集等等。其中许多都是短暂的，因为它们经常被创造和破坏。Kubernetes 固有的复杂性使得以标准化的方式应用零信任原则具有挑战性。

默认情况下，kubectl 不提供基于角色的访问控制(RBAC ),用户帐户不会记录执行的命令。通过防火墙访问资源也很困难，并且监督多个集群变得复杂且容易出错。

理想情况下，访问控制应该集中在所有集群中。这降低了向零信任和 Kubernetes 过渡的复杂性。

如果做得好，零信任允许团队以一种变革性的、简单的、低成本的和无负担的方式获得安全。为了利用这些优势并减轻挑战，组织可以转向开源平台寻求支持。

## 开源零信任解决方案

开源解决方案的一个例子是 [Paralus](https://www.paralus.io/) 。Paralus 专为从单个集群到数千个集群的多集群环境而设计，为团队提供了管理资源访问以及威胁识别和响应的安全方法。

它源于 Rafay 的零信任访问服务，包括自定义角色、身份提供者(IdP)支持和允许管理员创建具有不同权限的自定义规则等功能。通过一个工具，平台团队可以管理所有集群、位于任何位置的用户以及托管在本地或云中的集群的访问。

## 并行访问管理

使用 Paralus 的 Kube API 代理功能，kubectl 工具可以访问和管理 Kubernetes 集群，而不会丢失功能。Paralus 根据预定义的访问策略验证经过身份验证的用户，并相应地授予他们对 Kubernetes 集群中资源的访问权限。

本质上，Paralus 易于使用，可以帮助任何规模的组织解决 Kubernetes 中的安全挑战。作为一款开源应用，Paralus 可以免费部署和使用。团队可以定制 Paralus，并为零信任框架和实践做出贡献，以实现持续改进。

处于应用程序现代化进程中的组织正在经历一段复杂而充满挑战的时期。为了实现现代化，Kubernetes 必须参与其中，但是随着应用程序数量的激增，保护所有敏感数据的安全是一项艰巨的任务。组织应该实施零信任框架和最佳实践来保护数据，这需要假设访问您网络的每个人都是潜在的威胁参与者。采用像 Paralus 这样的开源工具可以帮助简化零信任的实现，并减少一个挑战。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>