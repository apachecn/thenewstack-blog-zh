# 撇开邪恶的机器人不谈，自主的动力看起来很有希望

> 原文：<https://thenewstack.io/evil-robots-aside-the-drive-to-autonomy-looks-promising/>

[InfluxData](https://www.influxdata.com/) 赞助了这篇文章。

 [Evan Kaplan，InfluxData 首席执行官

Evan Kaplan 是一名企业家和技术领导者，担任首席执行官近 20 年。他的经历涵盖了从自家车库到纳斯达克上市公司的领先创业公司，年收入近 2 亿美元。在担任 InfluxData 首席执行官之前，Evan 是 iPass 的总裁兼首席执行官，iPass 是全球领先的企业、电信和服务提供商 WiFi 接入提供商。在 iPass，他领导了从传统拨号提供商到全球 WiFi 接入领导者的转变。Evan 之前还担任过 Aventail Corporation(现在是戴尔公司的一部分)的董事长、首席执行官和创始人。他还在 1996 年与人共同创立了 Aventail，并率先实现了基于 SSL 的虚拟专用网络(SSL VPN)的首个商业实施，以及业内首个受管外联网服务，这是早期的基础设施即服务(IaaS)产品之一。](https://www.influxdata.com/) 

科幻电影中一个流行的情节是自主机器的概念，也许是机器人或超级计算机，发展出类似人类的智能水平和有感情的角色。因为这是一部电影，观众想要一个令人兴奋的情节，机器发展出一种叛逆的意识，意图反抗它的人类创造者。这个故事情节构成了一部伟大的夏季大片。

冒着听起来陈词滥调的风险，现实生活开始模仿艺术。

事实上，许多人类设计的系统的最终目标是自治；即系统独立于其人类创造者学习和行动的能力。在今天由人工智能支持、软件驱动的世界中，最终目标越来越现实。但幸运的是，对我们人类来说——至少目前是这样——这些设备不太可能很快变得有感知能力和失控。相反，他们从我们的算法训练中学习，以完全独立地操作。

制造、汽车、医疗保健、信息技术等行业都在竞相实现这些自主系统。也许今天最著名的例子是自动驾驶汽车。随着特斯拉、优步、Waymo 和苹果等公司努力将完全自动驾驶汽车带到开放的道路上，它们正在迅速成为现实。与此同时，部分自动驾驶的汽车就在我们身边，具有自动紧急制动和自动停车等有用的功能，提高了安全性和便利性。

虽然无人驾驶汽车听起来很酷，但自主系统在其他行业也很重要。在信息技术领域，大趋势是应用容器和虚拟化，其中服务器和微服务根据需要自动启动和关闭，以支持不同的工作负载。在制造业，“工业 4.0”是新的工业革命，它利用信息物理系统的自动化和数据交换来创建智能工厂，其中包括基于生产参数为自己做出决策的机器。例如，生产线上偏离质量规格(即有缺陷)的产品可以在没有人工干预的情况下从生产线上移除。

这些只是一些早期的例子，它们将成为下一代经济增长的决定性力量，带领我们超越当前的信息经济。让我们称之为“自动化经济”我认为这个词抓住了从简单的自动化到复杂的控制系统，最终到自我学习、完全自主的系统的必然趋势，这种趋势是由廉价传感器的兴起和计算能力的指数增长推动的。虽然基础技术是可用的，并将随着时间的推移而改进，但开发这些系统的专业知识和技能将使公司和国家有所不同。从根本上说，其中的过程和步骤几乎总是相同的:使用工具、观察、学习、自动化、重复。

## 自治系统的步骤:

### 工具

对于这些类型的系统，仪表化是走向自治的第一步。这意味着在各种物理和虚拟元素上放置传感器或计量器，以捕获时间点数据。测量和理解这些系统中成千上万的单个元素随时间的变化是至关重要的。汽车行驶速度有多快？离前面的车辆有多近？路面是湿还是干？这些和数百万其他数据点是自动驾驶汽车的关键输入。更重要的是，只要机器还在运转，数据就必须不断流入。

在虚拟或软件世界中，基础设施、微服务或容器的工具同样重要。有多少可用的磁盘空间？队列深度是多少？有多少内存是空闲的？微服务的响应率如何？这些以及数百万其他数据点是创建自修复和自扩展系统的关键输入。

### 观察

接下来就是观察了。实时观察系统是至关重要的，因为复杂系统的行为和故障本质上是不可预测的。我们观察系统，识别我们所看到的，如果我们装备良好，正在收集正确类型的数据，然后理解这些数据，我们就有了学习的基础。我们在乎前面的车是不是蓝色的吗？胎压低意味着什么？队列深度真的很重要吗？事情会随着一天、一周或一个月的时间而变化吗？观察是决定如何处理数据的关键。我们应用从工具中监控到的洞察力，并观察指标的影响。然后，我们需要从观察中学习，并尝试从中采取一些行动。

### 学习

在学习过程中，我们希望教会系统这些数据意味着什么。我们观察趋势，并从这些观察中提供学习到的(或预期的)行为，但是过一会儿我们希望系统自己学习。自我学习是自主性的一个关键因素，因此机器学习是系统内的一项基本技术。例如，如果路面光滑，轮胎充气不足，我们希望车辆能够自己学习施加多大的刹车压力。人类不能参与这种瞬间的决定。

### 使自动化

自主或自动化是一个旅程。可以基于 IP 请求进行扩展的系统是自治的一个层次，但我们总是想要更多。我们希望这个系统能够自我修复和自我学习。在现实世界中，自动驾驶仍然是一个目标，但防滑技术是一种相当成熟的自主形式。

当然，所有这些数据都需要快速消化，以便进行分析，并在它们仍然重要时采取措施。一台真正自主的机器——尤其是一台做出生死决定的机器，比如是刹车还是撞上水泥墙——必须快速了解当前状况，决定采取什么行动，然后采取行动。

## 走向自治的记录平台

正如你所想象的，转向自治有一些复杂的技术需求。有一些专门构建的平台是为处理自治系统的非常明确的需求而设计的，这些需求无法用通用工具正确地解决。

在设计这些系统时，必须首先考虑存储什么数据是重要的，以及您希望收集数据的频率:例如，如果您需要自治系统自动缩放队列深度，您需要存储这些数据。这允许存储每个离散时间元素的许多测量值的能力。记录的频率也很重要，我们称之为精度，我们支持纳秒级的精度，主要用于网络监控和一些算法交易应用。但是，如果您想在 99.999%的正常运行时间内提供自动化，那么您的精度必须至少达到第二级，因为您一年只能承受 5 分钟的停机时间。自然，您需要考虑将这种功能集群化，以提供冗余来支持高可用性。

由于自主系统的每个方面都配备了传感器和仪表，技术平台必须能够以极快的速度处理大量数据。这需要一个能够立即接收和存储数据的基础架构。此外，平台必须能够压缩数据，以免很快耗尽所有存储容量。

时间是任何为实现自治而构建的平台的基本组成部分。每个数据点都有一个时间戳，因此系统可以准确地了解测量时间或事件发生时间。应用程序需要支持基于时间的功能，例如计算数据的移动平均值，或者比较一个数据点与在不同时间段进行的相同测量相比有何不同。

系统必须能够对数据进行下采样；也就是说，在一段时间后去掉一些(但不是全部)数据点。现在，以非常精细的级别查看最新的数据可能很重要，但随着时间的推移，如此多的数据的价值会逐渐减少。不太尖锐的数据适合观察一段时间内的趋势，删除不必要的数据点可以节省存储空间和成本。

该平台必须能够实时解释和分析数据，以便在仍然有意义的时候采取行动。等待十分钟来应用自动驾驶汽车的刹车以避免碰撞是不可行的；一旦数据显示可能即将发生碰撞，就必须立即采取行动。

最后，该平台必须为控制型功能而设计。您希望使用您的关键时间戳数据来做一些事情，例如应用车辆制动以避免碰撞。只有当你能够控制接下来会发生什么的时候，对一个情况的了解才是有用的。

## 外卖

我们正处于一个新经济时代的尖端——自动化经济时代。各行各业的机械化系统正通过自我学习、自我修复和自我行动的过程迅速向自治方向发展。需要考虑需要多大的时间窗口来提供数据。例如，在自动缩放系统中，黑色星期五的负载可能比其他任何一天都高，但是您需要一年前的历史记录来做出精确的决策。

基础信息技术和人类的知识和专业技能正在融合，引领自主机器的发展，旨在让我们的生活更美好，并做人们根本无法做到的事情；比如探索我们周围的星球，或者去这个星球的海洋深处。抛开叛逆的机器人不谈，迈向自主的动力看起来确实非常有希望。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>