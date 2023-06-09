# 与 Docker 下一波浪潮对话的五家存储公司

> 原文：<https://thenewstack.io/five-storage-companies-that-speak-to-dockers-next-wave/>

随着向集装箱转移的成熟，存储等以前被搁置的问题开始凸显出来，并将成为本周在旧金山举行的 DockerCon 上讨论的话题之一。例如，Docker 有一些新闻，新成立的公司 Portworx 也有一些新闻。还有其他几家公司也在参与，包括 Datawise.io、Joyent 和 EMC。

“不仅仅是存储，围绕基础设施的一切，包括网络，都是事后才想到的，它们被视为附加功能，”Portworx 首席技术官 Gou Rao 说。

“这与虚拟化出现时的发展没有什么不同。…每当您在如何部署应用程序方面遇到颠覆性技术时，基础架构都需要应对。”

Docker 将宣布一个新的存储卷和网络插件模型。

“分布式应用世界中的存储必然也是需要分布式的东西。Docker 企业营销副总裁 David Messina 表示:“实现容器分布式存储的第一步实际上是创建分布式多主机网络，我们将在周一宣布这一点。"那么你需要的是存储选项的可插拔性."

他说，ClusterHQ 的 Flocker 将成为其第一个存储合作伙伴，但预计其他公司将很快利用其存储卷插件。

以下是一些公司解决集装箱存储问题的方法。

## 波特沃克斯

硅谷初创公司 [Portworx](https://portworx.com/) 通过推出其首款带有 PWX 开发者预览版的产品而崭露头角，这是用于在 Linux 容器中托管有状态应用的下一代存储软件。

Portworx PWX 公司为 Docker 容器提供本地弹性横向扩展块存储，允许容器化应用程序直接在存储基础设施上执行，并允许容器在机器和云之间流动地持久化和调度。

其创始人、首席执行官 Murli Thirumale、首席技术官 Gou Rao 和首席架构师 Vinod Jayaraman 曾在 Ocarina Networks 共事，该公司于 2010 年被戴尔收购。Portworx 成立于去年 11 月，由梅菲尔德基金(Mayfield Fund)和迈克尔戴尔(Michael Dell)投资 850 万美元(金额未披露)。

容器和数据在多个节点之间不是固有的可移植或持久的；没有为容器调整存储性能；据该公司称，快照和复制等存储功能不是特定于容器的。

[![Gou Rao](img/4e2cfe948907d64de182a2e25094c4ff.png)](https://thenewstack.io/wp-content/uploads/2015/06/Gou-Rao.jpg)

苟饶

Rao 解释说，无状态应用程序需要大量的计算，但对存储的要求较少。他们不关心持久性，而是依赖有状态的服务，比如 SQL 数据库、键值存储或消息队列。有状态应用程序的数据需要持久化，并且您关心快照和复制。两者有不同的打包和部署要求。

“容器有更多的方式来描述这种环境，并以各种方式打包它们，这样做比以虚拟机为中心或以厨师为中心的部署更有意义，”他说。

该公司的愿景是以软件定义的方式调配基础架构。这需要两样东西:Linux 容器和软件驱动的方法来定义容器应用程序的基础设施。

“我们真的没有看到像 Chef 和 Puppet 这样非常以机器为中心的复杂脚本作为供应应用程序和基础设施的方式，”Rao 说。“我们看到像 SQL 数据库这样的应用程序以一种统一的方式配置其基础架构。

“今天，它们是两个不同的步骤。要调配应用程序，我必须首先调配存储，我必须知道应用程序的用途，然后单独安装和调配应用程序。

“在以容器为中心的世界中，只要基础设施知道如何按照这些软件意图行动，容器和它需要的资源将被同时部署和供应。这为运营人员提供了管理和扩展数据中心的灵活性，”他说。

它的产品 PWX 运行在商用 X86 服务器上。它由一个名为 PRX orchestrator 的调度程序组成，该调度程序可以感知您的数据中心环境，并可以在具有适当资源的适当机器上调度应用程序；以及附加到每个容器化应用程序的 PXC 横向扩展块存储。

“对于每个有状态的应用程序，我们都附加了自己的虚拟逻辑存储设备。无论应用程序在哪里运行，它的存储总是持久的。你的所有存储功能，如复制和快照，几乎都是在每个容器的软件中完成的，”他说。

它使用 CoreOS 来提供 Linux 发行版和 Docker 作为运行时。

Rao 说，编排层与任何人都会使用的任何其他编排工具兼容。

“在向客户交付产品时，我们采取了非常企业化的生产质量观点。他们期望的是 VMware vSphere 风格的体验，而不是 OpenStack 的自助式体验，”他说。

## Datawise.io

与此同时，另一家成立于 2014 年、仍处于隐身状态的公司 Datawise.io 将于本周在 DockerCon 上预览其 Project 6。首席执行官兼创始人 Jeff Chou 及其团队是 Cisco、Veritas 和 VMware 的资深员工。

Chou 表示，该公司专注于网络和存储方面的集装箱市场空白，但项目 6 只是该公司所做工作的一个子集。他对大部分细节守口如瓶。然而，可以在 http://www.datawise.io/project-6.html.找到项目 6 的预览

[![Jeff Chou](img/8a491da5c727a8ac409ba2b7190e16ad.png)](https://thenewstack.io/wp-content/uploads/2015/06/Jeff-Chou.jpg)

周杰夫

“网络和存储，我们认为它们是同一个东西，它们都是 IO。很难分别解决这些问题；我们认为这些问题需要整体解决，”他说。

“Docker 和 containers 对于应用程序的移动性非常有用，但缺少的是数据移动性。数据移动涉及网络和存储。

“通过 Project 6，我们希望展示如何在集群中管理容器，同时考虑网络和存储等资源。我们想做的一些事情是对 Docker Swarm 或 Google Kubernetes 进行一些增强，以便允许插件考虑应用程序的网络和存储需求。我们觉得这是一个创新时机已经成熟的领域，”他说。

Project 6 旨在简化内部环境中裸机容器的网络和存储管理，他认为这将是未来的趋势。

周说，该公司将在今年晚些时候谈论更多的计划。

## Joyent

与此同时，Joyent 首席技术官布莱恩·坎特里尔(Bryan Cantrill)坚持认为，其 Manta 存储服务在集装箱存储市场上遥遥领先。

“Docker 对无状态服务最有吸引力，因为它完全是暂时的——这很好。但是有很多应用程序需要持久存储，你应该能够在一个容器中运行。

“如果你想运行一个数据库，那就需要持久存储。你不能把它放在一个容器里的想法是可笑的。我们已经在集装箱里做了十年了。

[![Bryan Cantrill](img/6090fe7a1b53ffb6f9db09aa2f6cf69e.png)](https://thenewstack.io/wp-content/uploads/2015/06/Bryan-Cantrill.jpeg)

布莱恩·坎特里尔

“在 Triton 和[容器优化的 Linux](https://thenewstack.io/joyent-and-cannonical-offer-a-linux-flavor-ubuntu-containers-on-a-bare-metal-platform/) 中，有直连存储。你的容器有一个持久的 ZFS 文件系统。所以如果你想在容器中运行 Postgres，你可以。表演棒极了。”

他说，问题在于“Linux 文件系统的故事一团糟”，Linux 社区还没有接受 ZFS，这是 Sun Microsystems 在 2005 年与 OpenSolaris 一起推出的。“我认为 ZFS 是最好的开源存储平台，就这样，”他说。

“现在，当你有大量数据时，人们会四处晃动这些数据——他们会将这些数据放入公共云上的[亚马逊] S3 等光学商店，或者在本地放入 SAN 或 NAS 设备。他们把它放入一些东西中，这些东西的唯一目的是可靠地存储和检索数据，”他说。

“从理论上来说，容器可以让您在存储所在的位置加速计算。所以如果你想对数据进行操作，如果你想查询数据，如果你想有效地扫描你的数据，你想把你的数据拉出来。它需要移动到其他可以在其上进行计算的元素，这是一种荒谬的资源浪费，因为你的数据在某个地方的计算机上。它有一个中央处理器，可以工作。

“容器允许非常简单的抽象，允许您在数据所在的位置加速计算，但它需要您重新思考您的存储基础。出于多种原因，您不能对 S3 这样做，也不能对 NetApp 文件管理器或 EMC SAN 这样做。你必须重新思考你进行权威存储的方式。”

坎特里尔说，乔因特就是这样对待蝠鲼的。他认为市场还没有理解 Manta——他认为很少有人真正理解 Docker 和企业存储。

他说，主要的企业存储供应商并不专注于以容器为中心的存储，事实上，他们在维持现状方面有既得利益。

## EMC 和集群总部

与此同时， [EMC 与 ClusterHQ](http://siliconangle.com/blog/2015/06/18/the-container-front-heats-up-as-emc-throws-its-weight-behind-flocker/) 合作，将 EMC 增长最快的两条产品线与 Flocker 集成:其 XtremIO 系列全闪存阵列和 ScaleIO 软件平台，后者将服务器中的直连存储整合到统一的容量池中。

Flocker 提供了一种更可靠的方法来为有状态应用程序利用数据，这是 EMC 一直在努力的事情——它在今年早些时候发布了一个开源工具包。

在其新的 1.0 版本中，Flocker 还支持其他存储选项，包括 OpenStack Cinder 和亚马逊 EBS。

Silicon Angle 报告称，预计 Flocker 在帮助组织将 XtremeIO 系统和 ScaleIO 设备的闲置容量用于开发项目方面最为有用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>