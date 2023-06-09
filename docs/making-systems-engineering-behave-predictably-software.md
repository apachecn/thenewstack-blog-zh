# 让系统工程的行为像软件一样可预测

> 原文：<https://thenewstack.io/making-systems-engineering-behave-predictably-software/>

基础设施自动化的复杂性正在迅速增加。不再可能做出简单的改变而不产生意想不到的后果。如果基础设施被视为代码，那么它就是一个软件产品，作为一个软件产品，它必须遵守与任何其他软件相同的可靠性标准。为此，用于使软件产品以可预测的方式运行的相同原则应该应用于系统工程。

## 借用数据库世界

要使基础设施被认为是可靠的，它必须行为一致。基础设施保持自我一致性是不够的，然而，它还必须相对于其上运行的应用程序具有可预测的性能，因为基础设施在应用程序的体系结构中扮演着重要的角色。要做到这一点，我们应该借鉴关系数据库管理系统。模仿[交易逻辑](http://www3.cs.stonybrook.edu/~kifer/TechReports/transaction-logic.pdf)(例如，ACID)的交易基础设施对于促进基础设施产品被认真对待所需的信任级别是必要的。为了实现这一理想，必须满足几个要求:

*   在基础设施的事务方法中，必须能够保证隔离。这不仅要求知道基础架构的当前和所有以前的状态，还要求这些状态是可靠的，也就是说不需要手动更改系统的状态。然而，这个问题几乎很难解决。如果是这样的话，那么怎么可能达到事务基础设施的目标呢？
*   必须使用基础设施的表示来对基础设施整体的当前状态进行建模。给定基础设施的当前状态，必须提供一个或多个转换函数来表示从当前状态到下一个状态的变化。这些功能必须提供自我纠正错误，并提供可逆性保证。也就是说，实现保证事务性方法所必需的所有前置、中间和后置条件断言仍然是不切实际的。
*   不可完成的变更不应该修改当前状态(变更应该是原子的和隔离的)，并且一旦变更已经完成，必须为状态的所有未来观察更新视图(变更应该是一致的和持久的)。如果我们对我们的基础设施进行变更，我们不希望一个畸形的变更请求使我们的基础设施处于断裂状态或陷入暂时状态。传统的配置管理系统通常需要人工干预来解决损坏状态的问题。

## 管理状态变化

进一步类比，理想的情况是能够提出对状态的更改，分析其适用性，并且只有在系统“接受”该更改时才保持该更改。如果我们有多个并发系统管理基础设施的状态，那么这就是某种形式的 MVCC 将被证明有用的地方。一旦先前提议的状态改变被保持，先前提议的状态改变可能在任何时候使较新的提议的改变无效。同时，当提议的变更被序列化和持久化时，变更的提议和验证允许有一致的状态视图。这种方法的主要问题是，在从初始状态到最终状态的转换中可能会应用不确定的逻辑，因为这是一个复杂的分布式系统(一组运行 Linux 发行版的主机，供人们直接使用)，而不是关系数据库。这就是问题所在:几乎所有用来操作我们基础设施的操作系统在设计时都考虑到了用户。它们是为人们直接操作而定制的。

考虑包管理的问题:这是 Linux 生态系统中多次“解决”的问题。安装包被表示为一个转换函数。首先，要求系统的状态是可表示的:软件包已安装，安装尝试失败，安装成功。必须知道所有可能的状态。浏览一下包管理中涉及的状态转换列表，就可以合理地理解这个问题有多么重要:

*   已卸载->正在安装
*   安装->安装失败或已安装
*   安装失败->清除安装失败->卸载
*   安装->卸载
*   卸载->卸载失败，已卸载
*   卸载失败->清除卸载失败->安装，卸载

## 主要行为者

在这个特定的转换功能中涉及到两个主要的角色:配置管理(CM)和包管理。许多包管理系统遵循 ACID 原则，这允许配置管理只关注终端状态(已安装、已卸载)。这是基础设施管理中最容易理解的部分之一，但它仍然被证明是繁琐的，并且充满了错误。此外，这必须发生在分布式系统中的许多主机上，并且 CM 系统缺乏跨多个主机的协调。基础设施管理的“黄金映像”方法可以保证所有系统的状态一致，这是 CM 无法做到的，但有时是不切实际的，或者被完全忽略。

> 如果一切都与理想相差甚远，那么如何可能达到事务性基础设施的目标呢？

构建基础设施的操作系统必须停止将自己视为桌面操作系统。出于各种密集的目的，没有人会在他们的笔记本电脑上运行 Red Hat 那么为什么有必要使用特定的 Linux 发行版作为桌面操作系统呢？删除它们，并简化操作系统，以便作为独立的计算单元进行部署，这些计算单元是集合的一部分。这正是像 CoreOS 这样的 Linux 发行版试图做的事情。

## 隔离可展开的人造物体

CoreOS 是一个 Linux 容器管理程序。直接登录 CoreOS 系统本质上是一种反模式。使用奥马哈更新协议以自动方式更新操作系统，并且更新仅通过重启计算节点来进行。CoreOS 的用户不像传统 Linux 发行版的用户那样在上面运行应用程序。相反，它们在容器中运送和运行应用程序——将所有可部署的构件与系统中的任何其他参与者隔离开来。

CoreOS 提供了一个理想的平台，可以在这个平台上运行分布式系统，比如 Kubernetes 和 Mesosphere。这些平台为开发人员提供了事务性升级他们的应用程序的能力，但是他们的功能集在这方面仍然有些欠缺。如果假设应用程序在测试和生产环境中的行为相同，那么在 Mesosphere 和 Kubernetes 中都有足够的能力。两者都允许服务的“滚动升级”，即只有在成功完成全部或部分升级后，才转换它们各自的分布式单元。两者都允许应用简单的“成功标准”,该标准指示从当前状态到期望状态的成功转换。然而，对于这些平台来说，允许更复杂的前置、中间和后置条件断言来指示状态转换的成功将是理想的。

## 超越

为了做到这一点，必须有适当的机制，允许条件逻辑(有效地为平台提供适应度函数)应用于状态转换的不同阶段。简单地监控应用程序的状态就足够了，但是这需要超越简单的可用性监控。应用程序的行为是否一致并符合预期？除非满足所提供的条件，否则不应认为应用的更改是成功的，从而保证不允许错误的流程持续下去。

这些平台在达到理想的基于交易的系统之前还有很短的路要走。CM 如何或可以处理事务性基础设施？这将意味着一系列的取舍。CM 系统的用户将不得不忍受灵活性的降低，但是将会得到更多的保证，他们所做的改变将会持续下去，并且在整个基础设施中将会有一致性。对于 CM 用户来说，这也意味着范式的转变:人工干预和系统管理必须结束。说服系统管理员不允许用户登录很容易，但让他们停止登录和进行更改则完全是另一回事。

CM 系统必须为资源提供一个一致的接口，允许指定前置、中间和后置条件。此外，在任何这些断言期间，所有资源都必须能够从故障中恢复。大量的工作都落在了那些编写资源和提供者的肩上，但是 CM 必须促进这种类型的资源管理。CM 必须提供基础设施状态的整体视图，并允许跨系统的更新协调。它目前最多只允许最终的一致性，但最终这只会导致最终的不一致性。

交易基础设施将把系统工程的复杂性与提供给客户的服务结合起来。如果将基础设施视为代码，那么没有理由将其归为软件二等公民。如果基础设施是提供给开发人员的一项服务，而开发人员在所提供的基础设施服务之上构建产品，那么基础设施就是产品的一部分，应该如此对待。

CoreOS 和 Red Hat 是新堆栈的赞助商。

专题图片:“你们害怕吗？！torbakhopper 的《人类与自然和银行的交易以及商业的想象构造:液体绘画，斯科特·理查德，旧金山(2015)》获得了 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 的许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>