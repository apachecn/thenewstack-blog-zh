# 在云原生平台中为容器编排提供安全的企业功能

> 原文：<https://thenewstack.io/pillars-security-cloud-native-paas/>

Docker 让很多事情变得更简单，但是 Docker 容器没有比虚拟机更容易让 IT 运营受到影响。对于迁移到云的大型组织，开发人员可以从内部数据中心和公共 IaaS 自助访问资源，但中央 IT 部门必须想出新方法来确保容器的安全性和合规性。为容器编排提供企业功能的最新平台需要帮助组织创建一个更加安全、透明和可控的操作环境。

企业平台即服务(PaaS)是下一代中间件，它提供了在大型现有组织中实施容器策略所需的功能，包括 Docker 容器编排、代理、安全性和合规性。

今天的数据中心由各个级别的各种安全支柱定义，从应用隔离和容器化到物理基础架构分区。以下是云原生平台云安全的三大支柱:

*   **限制平台攻击媒介**:无论恶意行为源自内部还是外部，平台都是共享的，默认情况下攻击应该被隔离，并易于锁定。
*   **实施标准**:应用程序设计并不仅限于最后一行代码，平台需要承担起确保安全、补丁、许可和合规性标准的角色。
*   **利用现有运营**:多年来，大型组织已经设计了角色规范和专业知识，以确保合规性和安全性。[新闻不断暗示](http://www.computerworld.com/article/3016216/security/over-680tb-of-data-exposed-in-mongodb-databases.html)也许开发人员并不总是伟大的数据库管理员。此外，运营部门不断投资于同类最佳的工具来增强安全性。云平台需要集成和使用这些功能。

虽然这三大支柱非常重要，但我们必须更深入地解释企业 PaaS 可以做些什么来保护数据中心，以及它如何实现这一目标。

## 企业平台即服务为数据中心带来了什么

采用 PaaS 来配置来宾应用流量(入口、出口和内部)的[加密是数据中心运营商控制和标准化其加密策略的一个机会。这有一个额外的好处，即消除了应用程序开发人员理解和正确实施加密的负担，这是一种通过消除人为错误来减轻 it 组织风险的策略。](https://apprenda.com/blog/how-apprenda-adds-security-to-guest-applications/)

关键程度在数据中心堆栈中继续向下延伸。高度监管环境中的零信任模式通常通过软件定义的网络(SDN)来建立。从本质上讲，这些是网络设备中基于软件的规则引擎，规定数据包何时、何地以及如何在网络中流动。零信任模型的出发点是，除非明确允许，否则任何应用程序工作负载都不能与另一个应用程序工作负载进行通信。这有效地“划分”了应用程序。

当企业平台即服务(PaaS)是应用工作负载在此基础设施上运行的机制时，平台必须了解底层网络拓扑和 SDN 实施的工作负载规则集。PaaS 应利用这一知识来制定应用工作负载放置策略，从而在软件定义的整体放置和流量模型上完成循环。这是通过 PaaS 和 SDN 的直接集成实现的，例如 [Apprenda 与思科以应用为中心的基础设施的集成](https://apprenda.com/blog/apprendaaincisco/)。该策略的最终目标是通过减少攻击面和遏制任何此类攻击来降低风险。

说到受攻击面，强化数据中心的一个可替代因素是操作系统。

我以前写过关于[可信计算基础(TCB)](https://apprenda.com/blog/trusted-computing-base-tcb-gotta/) 的文章，这是一个系统漏洞表面积的有效度量。操作系统在数据中心 TCB 中占有一席之地，供应商一直在努力降低其操作系统风险。

多年来，IT 组织围绕强化服务器操作系统和应用服务器映像以及应用安全补丁改进了流程，旨在解决 TCB 并降低风险。PaaS 与操作系统的关系不应该建立在严格的依赖性上，因为那样会破坏这些努力。

事实上，恰恰相反才是理想的:PaaS 应该从应用中抽象出操作系统和应用服务器的细节，但是如果它本身与操作系统和应用服务器紧密耦合，就不能做到这一点。PaaS 的部分工作是增加组织推出操作系统或应用服务器更新或全新版本的能力，如 RHEL 7、Windows Server 2012 R2、WebSphere、JBoss 和 Tomcat 以及随之而来的安全增强。这也适用于应用服务器级别。

当然，安全是多方面的。虽然它主要集中在环境配置和技术选择上，但安全性的其他方面完全集中在过程控制上。这是数据中心运营的对象、内容、时间、原因、地点和方式。过程控制的目的不仅是为行动建立指导方针，而且是加强责任。

## **通过记录和审计问责**

PaaS 可以直接影响的两种问责机制是日志记录和审计。第一个是日志记录，PaaS 操作人员通过它可以深入了解其环境的运行时。通过将日志集中记录到整个数据中心的通用聚合器中，活动或即将发生的故障的警告、故障排除和事件解决都变得更加容易。

日志记录还为历史分析创建了环境和应用条件的记录。

PaaS 不仅应该记录自己的操作，还应该为其权限范围内的来宾应用程序提供一种统一的方式来主动和被动地参与日志记录，要么通过显式 API，要么通过在应用程序工作负载中植入将信息记录到持久性存储中的功能。

审计平台操作是实施过程控制的另一种方式。大多数组织的安全策略都包括审计规则集，这些规则集定义了需要捕获哪些关于系统状态变化的信息。谁采取了行动，他们采取了什么行动，以及状态之间的差异(实际上是变化)这些参数应该被捕获。这有助于在对操作问题进行故障排除的同时重放操作，并提供关于对环境进行更改的影响的预测分析**。**

## **最后的话**

合理的技术选择、正确的实施和过程控制共同构成了企业中全面安全策略的一部分。PaaS 在云堆栈中的地位不仅给了它机会，也给了它责任，提供工具来解决这一战略的重要部分。

Apprenda 和 Docker 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>