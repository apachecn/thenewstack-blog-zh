# 集装箱化领导者探索可能的标准化数据存储接口

> 原文：<https://thenewstack.io/containerization-leaders-explore-possible-data-storage-interface-initiative/>

来自每一个领先的容器编制器制造商的一组工程师已经聚集在一起，虚拟地，围绕一个计划来探索基于容器的数据存储的公共词汇。容器存储接口倡议最初是由 Mesosphere 的 Benjamin Hindman 提出的，目前，该倡议基本上是 GitHub 的一个文档，正在探索社区及其用户是否会受益于一个用于寻址和管理存储卷的标准化 API。

Goelzer 在该组织的序言中写道:“该标准的目标是拥有一个由所有编排器共享的单一集群级卷插件 API。”"因此，举例来说，为 Docker 编写的一致性存储插件可以在 Kubernetes 中不加修改地运行(反之亦然)."

Goelzer 继续解释了该倡议的起源——与此同时，该倡议继续使用不幸的缩写“ [CSI](http://www.cbs.com/shows/csi/) ”:“我们来自 Docker、Kubernetes、Mesosphere 和 Cloud Foundry 的大约八个人基本上只是坐在一个房间里，起草了这个提案。现在，我们正在从我们各自的开源社区寻求反馈，以改进该提案。”

## 关于第一步的争论

如果该小组的目标得以实现，任何存储供应商或持久存储容器制造商都将能够构建一个插件，以与任何 orchestrator 相同的方式运行。参与者指出，就目前的情况而言，不愿意在多个实施之间分配支持的存储供应商通常被迫选择一个——Kubernetes、Swarm、DC/OS、Diego——并将他们的测试操作限制在这一个上。否则，他们可能会在市场冲突的早期“袖手旁观”，等待一个冠军出现，这样他们就可以支持市场指定的一个平台。

像大多数 Google Docs 文档一样，CSI 提案草稿被设计为由任何和所有成员标记，并在空白处附上他们的评论。使用 [gRPC 语法](https://thenewstack.io/cncf-adds-googles-grpc-remote-call-project-big-tent/)，该文档给出了四个命令的原型，Goelzer 和他的合作者可能认为这四个命令是任何标准存储容器系统中的主要动词: **create** 、 **delete** 、 **attach** 和 **detach** 。

但是这个最基本的决定引发了这个非官方组织的第一次大辩论。争论的焦点是编排者或调度者是否应该承担数据容器或数据量生命周期管理的角色。带头反对的是 Portworx 的工程副总裁 Venkat Ramakrishnan，他生产基于容器的数据服务平台。

在该计划的“非目标”标题下，Ramakrishnan 插入了两个要点:一个是关于*数据放置*，另一个是关于*数据生命周期管理*。他写道，数据放置“真的不是调度程序的工作。[*]调度程序可以给出提示，但数据放置最好留给数据路径软件，因为数据的生命周期与应用程序数据相关，不受调度程序控制。”*

 *“我们真的认为，存储决策更多地是由应用程序的需求而不是调度程序的需求驱动的，”Portworx 首席执行官 Murli Thirumale 谈到新的堆栈时说。“因此，作为 Portworx 的存储管理人员*和*，我们不仅能够以编程的方式直接与应用程序的需求进行沟通，这样我们就可以决定哪些节点服务于哪些应用程序，哪些节点服务于哪些容器。”

Thirumale 提供了这个例子:假设一个应用程序基于 MySQL，另一个基于 WordPress。他指出，面向内容管理的应用程序通常需要大块内存和存储，但不需要速度。MySQL 应用程序的配置文件正好相反。他说，Portworx 对运行这两种应用程序的数据中心的底层数据结构的管理，已经根据它们各自的配置和数据使用历史，划分出了最适合这两种配置文件的存储卷。调度程序可能无法访问这些简档。

“所以是我们在做决定，而不是时间表，”Thirumale 说。

Ramakrishnan 还向我们提出，消费服务是现代云原生应用程序的角色。[借助融合或超融合架构](http://www.datacenterknowledge.com/archives/2017/03/20/isnt-hyperconvergence-converging/)，计算、存储、内存和网络结构以服务的形式呈现给应用程序使用，当自动化归结为非常简单的经济性时，业务流程编排者可以更轻松地对其进行扩展和缩减。

“存储只是我们的一部分，”Ramakrishnan 说。“我们所做的是利用旧的底层存储，将它们分离出来，并将其打包为单个容器的服务。像 MySQL 这样的数据库容器可能需要高水平的可用性和数据保护。他们可能会创建大量副本，并需要容错能力。因此，他们可以订阅高水平的 HA[*高可用性*服务。如果您是一个数据库，您可能希望每隔几个小时备份一次。然而，如果你是一个网站，你可能需要每隔几天备份一次。”

从 Portworx 的角度来看，如果计划者或编排者不打算承担数据生命周期管理的全部角色，那么假设他们应该有权为应用程序创建存储节点是没有多大意义的。毕竟，存储空间从来都不是完全同质的，就像一盒香草冰淇淋。Portworx 认为，如果存储系统最终依赖于“创建/删除/附加/分离”系统所需的更基本的数据管理视图，容器数据提供商将不得不将其配置限制在一种最低的共同标准。

Ramakrishnan 在 CSI 在线文档的几条评论中表达了这一观点。在一条评论中，他补充道:“老实说，这是在开倒车，我不知道为什么这个规范是基于存储供应商的需求。这应该基于应用程序希望在其基础架构中看到什么(自上而下)，而不是自下而上。”

## 谁应该引用什么？

这引来了谷歌高级工程师兼 Kubernetes 联合创始人蒂姆·霍金的评论:“我不理解这种情绪。我们有一些基准功能，存储提供商必须提供这些功能才能在任何编排系统中运行。这是自上而下的趋同进化——所有主要的编排者都进化出了非常相似的 API。

“我们现在的情况是，”Hockin 继续说，“存储提供商必须单独决定哪些平台足够重要，需要得到支持，这意味着覆盖范围不一致，测试可能不稳定。我们想要的是一个单一的插件，提供商可以根据参考“主机”构建和测试，并相信所有主要的 COs[*容器编排器*都将工作。”

在周三的评论中，Hockin 补充说，CSI 的成功实现可以想象成为 Kubernetes 的 Flex 版本 2。他指出，Flex 的当前版本“不完整，不应该用来证明设计决策的合理性，这就是我们重新审视这个问题的原因。”

从 Hockin 的角度来看，Kubernetes(和其他 conatiner orchestrators)需要更多地考虑寻求实现它们的存储供应商的需求。如果没有基线参考实现，供应商可能会自行试验，谁知道他们的结果会如何。他告诉 Ramakrishnan，最终的 CSI 将需要解决“相对愚蠢的后端系统”的需求，以及更细粒度的特定存储结构提供商，如 Portworx。因此，一个基本的词汇“创建/删除/附加/分离”可能不仅是必要的，而且是不可避免的。

在 Portworx 与我们的讨论中，Ramakrishnan 认为面向容器的工程师也许应该避免考虑更笨的后端系统的需求，特别是来自传统存储供应商的需求。他认为，毕竟他们的目标不是构建横向扩展系统，甚至不是完全容器化他们的应用程序。

“以我们在 Portworx 所处的位置，以及我们拥有的各种客户，”他告诉我们，“我们坚信，容器不适合传统的存储架构。”

Ramakrishnan 补充说:“我们是当今行业中一些最大的容器部署的容器数据结构，我们希望确保社区了解容器化的应用程序如何真正关注存储和存储服务。”“在这方面，我认为容器存储接口倡议实际上需要更多一点的帮助，这就是为什么我们试图帮助社区。”

Cloud Foundry Foundation、Cloud Native Computing Foundation 和 Mesosphere 是新堆栈的赞助商。

特写图片:由苏·王茂林在知识共享 2.0 许可下，在英国柴郡朗康的一座高架桥的拱门内建造的一座教堂。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*