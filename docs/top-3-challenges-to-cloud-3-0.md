# 云计算 3.0 的三大挑战

> 原文：<https://thenewstack.io/top-3-challenges-to-cloud-3-0/>

云 1.0 侧重于基于虚拟化构建的基础设施即服务(IaaS)。Cloud 2.0 引入了云原生服务，如大数据、AI/ML、可扩展的中间件服务，以及基于容器化等概念的开发。

云下一步将走向何方？我相信云 3.0 将专注于大规模的任何地方的计算——想象一个“去中心化的世界计算机”，它完全分布在云到边缘，生活在多个位置，永远不会死亡。

## 为什么权力下放很重要

 [天力福

Tenry Fu 是 Spectro Cloud 的联合创始人兼首席执行官。他拥有 20 多年解决企业 IT 问题的经验。在他的前公司 CliQr 被思科收购后，他最近领导了思科 CloudCenter 套件和思科容器平台的架构。CliQr 的技术支持应用程序可以跨公共云和私有云更高效地运行。他在可扩展分布式系统、企业系统管理和安全性领域拥有超过 15 项专利。他喜欢在业余时间阅读历史书和建造立体声系统。](https://www.linkedin.com/in/tenryfu/) 

如今，像 AWS、Azure、GCP 这样的公共云大多是集中式的。虽然公有云有多个区域，但每个区域基本上仍然是一个数据中心。托管在这样一个区域中的应用程序将以典型的客户端服务请求/响应方式为来自远程位置的客户端提供服务。

随着越来越多的数据在边缘生成，由于“数据重力”，计算自然会向数据所在的位置靠近 5G 等技术可以最大限度地减少网络延迟和带宽限制，但不能解决边缘处理的需求。例如，如果一家零售商店想要捕获客户的照片进行图像识别，以便向客户的手机进行一些推送促销，那么最好在商店本地处理图像，而不是通过 WLAN 将图像发送到集中的云区域。也有需要更多本地用户交互的用例，例如 AR/VR。

云的分散方法的另一个优势是参与者可以在需要时互相提供资源。资源孤岛可以被打破，这样整个世界在基础设施方面的过度配置就会大大减少。

我们已经看到公共云提供商将他们的业务扩展到更接近边缘的地方。这些位置和投资跨越多个云和数据中心，为真正的全球化提供了坚实的基础设施存在点基础。

## 差距和挑战

虽然“云 3.0”可能是一种自然的演变，但我们才刚刚开始解决需要企业采用的问题:

**1。安全和控制必须是首要考虑的因素。**这类似于早期的私有云与公共云之争。企业花了十多年才接受公共云。云提供商必须证明他们在安全性、运营效率、工作负载和网络隔离方面做得更好。即便如此，企业仍然是混合云或多云的；没有人想把所有的鸡蛋放在一个篮子里，有些云更适合某些工作负载。

企业很难接受完全分散的全球“公共”云，特别是如果他们的工作负载将在不可见的不可信计算环境中运行。网络和数据的物理隔离几乎是不可能的，因为一切都是分布式的。转变到逻辑隔离需要思维方式的改变。

企业将更喜欢专用的“私有”分散式云，即覆盖在现有公共云和私有云之上的云，它利用自己的公共云帐户和本地基础架构，以便获得控制和信任。

**2。要求重写应用程序会降低采用速度。**早期的分散式计算平台要求开发人员使用专有编程语言或 PaaS 服务来创建可在其平台上运行的应用。例如，CDN 提供商提供 FaaS，以太坊提供类似 Javascript 的编程语言 [Solidity](https://solidity.readthedocs.io/en/v0.6.6/) ，Synadia 为应用程序提供分散的 NATS 消息总线服务。这对于充分利用平台和隐藏幕后的一些互连可能是必要的。然而，这抑制了采用——重写应用程序不仅是一项巨大的投资，而且对于企业来说，选择赢家也是有风险的。

这让我想起了 2009 年伯克利云计算观点中的预测。它描述了云的两种竞争方法:基础设施即服务(例如 AWS EC2)和平台即服务(例如 Google App Engine)。它预测 PaaS 将会腾飞，因为它将隐藏基础设施的复杂性，并提供简单的编程接口来消费服务。当[2019 年发布无服务器计算](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2019/EECS-2019-3.pdf)的 Berkeley 视图时，作者承认:“市场最终接受了亚马逊的低级虚拟机云计算方法，因此谷歌、微软和其他云公司提供了类似的界面。我们认为低级虚拟机成功的主要原因是，在云计算的早期，用户希望在云中重新创建与他们在本地计算机上相同的计算环境，以简化他们向云迁移工作负载。很明显，实际需求比单独为云编写新程序更重要，尤其是在不清楚云会有多成功的情况下。”

如今，AWS 同时提供 IaaS 和 PaaS 服务。两者都很重要，但 IaaS 首先被采用，因为它更好地理解了最初如何使用它。成功过渡到云 3.0 将建立在当今熟悉的开发工具和平台上，如 containers 和 Kubernetes，但以多云和多集群的方式。随着时间的推移，将会开发更多的分散式服务和平台。

**3。罗马不是一天建成的，去中心化的云也不会。**企业采用和迁移到分散式云不会一蹴而就，而是一个过程。此外，服务仍将存在于内部或公共云上，因此与它们的互操作性将非常重要。

当迁移到分散式云时，第 2 层或第 3 层站点到站点 VPN / VPC 对等设置将不再可行。大多数服务访问控制必须转移到应用服务级别的第 7 层。服务网格将发挥重要作用，并扩展到其他集群，以及与现有的遗留服务互连。

为了使一切无缝，计算平台需要编排和放置额外的服务网格网关来自动化服务可访问性控制。

虽然完全去中心化的普适计算平台的概念很有趣，但要实现它还有许多事情需要解决。新的使用案例和实施——我们将在未来几年看到许多发展。

亚马逊网络服务是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>