# Istio 是有史以来最新一代的防火墙吗？

> 原文：<https://thenewstack.io/is-istio-the-most-next-gen-next-gen-firewall-ever/>

微分段和隔离的概念是一种基本的网络安全最佳实践，很少有人会对此提出异议。[微分段](https://www.networkworld.com/article/3247672/virtualization/what-is-microsegmentation-how-getting-granular-improves-network-security.html)通过遏制潜在危害并减小其“爆炸半径”来帮助降低风险如果做得好，攻击者很难仅仅通过破坏环境中的一个组件就在环境中移动。

实现微分段的技术工具可以追溯到物理交换机上的 VLANs，并且是软件定义网络(sdn)的一项基本功能。所谓的“下一代”防火墙(NGFWs)除了具有第 7 层协议意识之外，通常还非常强调隔离场景。然而，微分段的实际采用和使用远远落后于对其优势的认识。

其原因主要是由于复杂性和操作负担。很难手动配置 SDN 和 VLAN 架构，使其与您应用的实际拓扑紧密对应。随着时间的推移，随着应用程序的发展，维护它们变得更加困难。例如，大多数组织都提供一些基本的分段，例如为面向互联网的流量、内部流量和存储流量提供单独的网络。然而，很少有人将分段应用到应用本身，并为环境中的每个工作负载实施真正的“最低权限”分段。例如，虽然大多数组织会通过 DMZ 将面向公众的应用程序的前端连接到互联网，但很少会将该前端后面的流量分开，例如缓存、队列和存储流量的分段区间。

 [约翰·莫雷罗

Morello 是 Twistlock 的首席技术官，领导该公司与战略客户和合作伙伴的合作，并推动其产品路线图。此前，他是财富 500 强全球化学公司雅宝的 CISO。他在微软的咨询服务和产品团队工作了 14 年。他负责在 Windows、Azure 和 Office 365 中发布安全技术的功能团队，并担任美国混合云咨询团队的首席架构师。他与妻子和两个年幼的儿子住在路易斯安那州。作为一名热情的渔夫和潜水者，他也是恢复路易斯安那海岸联盟的主席。](https://www.paloaltonetworks.com/prisma/cloud) 

[云原生](https://www.twistlock.com/2018/08/23/preparing-cloud-native-world/)应用架构的兴起既是最大的挑战，也是解决这一问题的潜在出路。考虑到一个典型的遗留应用程序，当被重构为微服务时，实际上可能有数量级更多的离散组件，并且这些组件将比过去更频繁地更新。如果组织在处理少量虚拟机时疲于应对微分段，那么当同一应用程序在 24 个容器中运行并每天更新时，他们还有什么希望对其进行分段呢？幸运的是，支持以高度自动化的编排方式运行这些应用的可编程基础设施的相同概念也支持以声明性的编程方式定义分段和隔离。

这是一项关键的创新，它使一组称为服务网格的技术能够将网络拓扑和路由从基础架构层中抽象出来，并将其构建到应用程序本身中。服务网格允许开发人员使用基于声明性模型的方法轻松地将微服务链接在一起，该方法位于底层基础设施中的物理甚至传统 SDN 层“之上”。例如，服务网格可以让开发人员构建他们的前端组件，只需连接到缓存“服务”，而无需硬编码到特定的 IP 地址、主机甚至云提供商。服务网格确保该服务始终可用，可以管理对它的访问，为服务之间的流量提供默认加密，并支持高级负载平衡场景，如 canary 部署和 A/B 测试。服务网格的例子包括 [Istio](https://www.twistlock.com/2018/06/21/securing-istio-twistlock/) 和 [Linkerd](https://linkerd.io/) 。

虽然服务网格为一般应用部署和管理提供了重要功能，但它们也为实现微分段提供了潜在的解决方案。使用遗留工具进行微分段的核心问题是提供分段的工具和其组件被分段的应用程序之间的脱节。如果用来做微分段的规则不完全正确，你会破坏应用程序；如果它们不够精确和具体，你就失去了细分的潜在优势。此外，随着应用程序的发展，你必须确保这些规则始终与应用程序完全同步。想想大型组织拥有的成千上万个应用程序，以及不断发生的争夺它们注意力的安全事件，很容易理解为什么大多数组织采取非常粗粒度的方法来进行细分。

服务网格通过将细分定义移出基础设施并将其放在应用本身旁边来解决这个问题。不再需要手动配置基础架构来与应用程序保持一致。相反，由于该解决方案完全在软件中，并且完全由用于运行应用程序的 orchestrator(如 Kubernetes)运行，开发人员可以直接将安全性声明为其应用程序部署的一部分。开发和测试中使用的相同网格模型可以完美逼真地跟随应用程序进入生产。这使得隔离每个单独的微服务变得切实可行，而没有以前在需要手动基础架构配置时阻止大规模使用的摩擦。

像 NGFWs 一样，像 [Istio](https://www.twistlock.com/2018/06/21/securing-istio-twistlock/) 这样的服务网格也可以强制协议合规性(比如确保实体之间只允许 HTTP 流量)和传输协议的加密。然而，与 NGFWs 不同的是，配置并没有脱离应用程序，也不需要单独管理。相反，每次构建应用程序时，它都可以根据生产中使用的相同网格策略进行验证，并且可以在任何存储库中进行版本控制，如 GitHub。同样重要的是，因为服务网格是纯软件，所以相同的配置是完全可移植的，即使在不同的云提供商和内部部署之间也是如此。

服务网格提供的不仅仅是微分段，它们还让微分段首次大规模成为现实。正如 Kubernetes 从硬件和操作系统中抽象出底层计算能力一样，服务网格也从底层网络中抽象出路由和连接。一旦路由和连接从基础设施中分离出来，并可以被视为代码，就可以采用真正为应用量身定制的、权限最低的微分段方法。

如果你对这个话题感兴趣，并且你正在参加 Kubecon + CloudNativeCon NA，我将深入探讨这个话题，并在[我的会议](https://kccna18.sched.com/event/Grad/is-istio-the-most-next-gen-next-gen-firewall-ever-created-john-morello-twistlock)期间进行演示。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>