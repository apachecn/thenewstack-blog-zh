# Magma 为无线网络带来了一种系统方法

> 原文：<https://thenewstack.io/magma-brings-a-systems-approach-to-wireless-networking/>

[](https://www.linkedin.com/in/bruce-davie/)

 [布鲁斯·戴维

布鲁斯是一位计算机科学家，因其在网络领域的贡献而闻名。最近，他与拉里·彼得森(Larry Peterson)共同创立了 Systems Approach，LLC，生产开源书籍和教育材料。他是 VMware 亚太区的前副总裁兼首席技术官。在此之前，他是思科系统公司的研究员，领导着一个负责多协议标签交换(MPLS)的架构师团队。Davie 拥有 30 多年的网络行业经验，并参与撰写了 17 份征求意见稿(RFC)。他于 2009 年被认可为计算机械协会(ACM)会员，并于 2009 年至 2013 年担任 ACM SIGCOMM 主席。](https://www.linkedin.com/in/bruce-davie/) [](https://www.linkedin.com/in/bruce-davie/)

对于我们大多数人来说，无线网络是一种无处不在的技术，我们认为这是理所当然的。WiFi 遍布我们的家庭、办公室和咖啡店，而蜂窝网络允许我们在许多其他环境中保持连接。当然，一旦你离开了人口稠密的地区，任何形式的网络接入都不那么普遍了。事实证明，让网络无处不在需要一些关于无线网络如何构建的新想法。这种全新的方法已经在一个名为 [Magma](https://www.magmacore.org/) 的开源项目中实现，我们稍后会谈到这个项目。

互联网架构比实际的无线数据网络早了几十年。然而，无线连接被无缝地集成到了互联网中，因为互联网从架构的其余部分中抽象出了链路层的细节。对于许多网络人来说，无线网络只是另一个链路层，我们可以在很大程度上避免考虑它们。他们提供了一种便捷的方式将数据包从 A 传送到 B，但我们的网络架构并不需要真正改变。

虽然互联网架构足够通用以适应无线网络，但将数据服务引入语音网络却是另一回事。在过去的 20 年中，电信行业已经开发了一个完整的并行体系结构来将数据网络引入蜂窝网络，蜂窝网络最初是为了支持语音服务而推出的。自从第一次被添加到 2G 中以来，数据已经逐渐成为蜂窝架构的核心，但它作为为语音构建的网络的一部分的历史已经产生了挥之不去的影响。

互联网架构和蜂窝网络架构之间最显著的区别之一是接入技术的抽象，或者说缺乏抽象。如果您通过以太网、WiFi 甚至蜂窝网络访问互联网，互联网的核心不会因您的访问技术而改变。核心路由器没有与接入技术相关的特征或状态。然而，如果你看看移动网络的核心，你会看到一套完全不同的组件，这取决于接入技术是 3G，4G 还是 5G。因此，部署移动网络意味着一旦你选择了无线电技术，就会有很多其他技术可供选择。这使得蜂窝网络的部署变得非常复杂。根据您可以获得的频谱，您可以选择无线电技术，这将推动您的网络核心中的许多其他技术选择。如果你有不同区域的混合光谱，这种复杂性遍布核心。

这又把我们带回了岩浆。Magma 的开发是为了解决使网络接入更加普遍的问题，特别是在蜂窝技术可能是将网络带给服务不足的人口的最佳方式的地区。Magma 的一个原则是，像互联网一样，接入技术应该只影响边缘。因此，Magma 被设计为一种移动核心解决方案，它尽可能靠近无线电边缘，终止特定于特定无线技术的协议。这适用于各代蜂窝技术(4G/LTE/5G)或未经许可的频谱，如 WiFi。Magma 的核心软件实现与无线电技术的细节完全隔离。

Magma 做出了许多其他设计决策，这些决策与现代云原生系统的构建方式一致，并与传统的电信架构形成对比。一个这样的决定是使用一个集中的控制和管理平面，该平面为网络的配置和管理提供一个单一的北向 API。这与[软件定义的网络](https://sdn.systemsapproach.org/)转变数据中心运营的方式非常相似:集中式控制器允许将网络作为单个实体进行管理，而不是作为一组单独管理的设备进行管理，中央 API 支持一种模式，在这种模式下，更高级别的软件可以自动配置网络服务和策略。对于试图以经济高效的方式将网络连接扩展到服务水平低下的社区的运营商来说，自动化和易于管理是至关重要的要求。

运行在商用硬件上的开源软件是使网络具有成本效益的重要因素，但重要的是要认识到这些本身是不够的。如果一个运营商要运行一个由开源组件组成的网络，它需要可靠且易于管理。Magma 采用了云原生技术，例如使用小型故障域和可独立重启的服务，来实现可靠的移动核心实施，并且可以在不关闭网络的情况下进行增量升级。系统的每个部分都配备了大量仪器，以便于故障排除和其他网络操作。

Magma 仍然处于相当早期的阶段，但已经在允许农村社区获得网络接入方面产生了影响，当经济状况对更传统的方法提出挑战时。例如， [Muralnet](https://www.muralnet.org/) 正在使用 Magma 将网络接入扩展到美洲土著社区，而 [Brisanet](https://www.bnamericas.com/en/news/brisanet-brings-connectivity-to-remote-areas-in-the-northeast-with-magma) 也类似地将其部署到巴西的偏远地区。在网络架构方面，Magma 正在为移动和无线网络领域带来一种[系统方法](https://systemsapproach.substack.com/p/defining-a-systems-approach)，这是朝着简化网络部署迈出的重要一步，而网络部署在历史上是最难构建和运营的。

随着我们进入一个数十亿设备连接到“边缘”的网络时代，Magma 代表了一个将互联网和云网络的最佳实践带到边缘的机会，因此网络变得真正无处不在。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>