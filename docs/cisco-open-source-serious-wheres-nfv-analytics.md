# 思科:在 NFV 虚拟化网络之前，它需要更好的遥测技术

> 原文：<https://thenewstack.io/cisco-open-source-serious-wheres-nfv-analytics/>

周三，思科首席技术官兼首席架构师 Dave Ward 在旧金山[开放网络峰会](http://events.linuxfoundation.org/events/open-networking-summit)的主题演讲中告诉与会者，在有人——无论是开源社区，还是像思科这样的网络公司——找到如何产生适当的遥测技术之前，电信级工作负载在数据中心架构上的协调不会发生。

![160316 Dave Ward 01](img/5d414e72f42e1040ee10ed5e653b51e6.png)

思科首席技术官兼首席架构师戴夫·沃德

“我们已经花了很多年和很多时间来讨论服务协调以及控制器配置和供应网络本身，”沃德说，他已经脱下鞋子，以便能够舒适地在舞台上踱步。“我们忽略了这个轮子的另一面:在网络上推动遥测……事实上，网络数据分析平台尚未成为开源项目，或者我们已经开始标准化的方面。”

沃德承认，软件定义网络( [SDN](https://thenewstack.io/defining-software-defined-networking-part-1/) )分析的协议确实存在，尽管他认为，从以运营商为中心的网络功能虚拟化( [NFV](https://thenewstack.io/de-ossify-the-network-with-function-virtualization/) )技术集中收集遥测数据的能力在实践中尚不存在。

## 四根绳索形成一条辫子

但沃德发表评论的前一天，开放网络实验室首席架构师拉里·彼得森向同样的观众解释说，他的团队目前的项目名为[Central Office Re-architected as a data center](http://sdn.ieee.org/newsletter/november-2015/cord-central-office-re-architected-as-a-datacenter)(CORD)，包含一个旨在实现网络服务监控的重要分析组件。

电信工程师和架构师的目标是协调流量和管理可重新配置的网络，就像 Docker 用户协调应用和交互式工作负载一样，只是规模更大。彼得森周二告诉 ONS 的与会者，CORD 是一个协调虚拟路由器和交换机的平台，但使这些组件像应用程序工作负载一样可寻址和可管理。

彼得森认为，正如在智能手机或平板电脑上运行的移动应用程序客户端不需要知道网络如何工作才能向服务器请求服务一样，网络服务客户端也不需要知道电信网络的架构如何才能请求网络服务(一个常见的例子是观看视频频道)。

![160315 Larry Peterson 01](img/7c3d501c09f8ac3616273d51d18b4298.png)

开放网络实验室首席架构师拉里·彼得森

“你认为路由器不是一个物理盒子，而是一项服务。您成为该服务的租户，并要求从该服务进行路由，”Peterson 解释道，并将这样的请求与运行在云平台上的应用程序如何请求存储即服务进行了比较。虽然有些网络服务在设计上是可信的，但是。实验室主任继续说，一些第三方服务将不得不被信任。

原因有很多，但最主要的是，任何基于软件的协调网络操作的平台都需要能够为虚拟网络中的每个容器、虚拟机或“节点”生成详细的遥测数据。

CORD 在设计时考虑了三种使用情形——住宅(R-CORD)、移动(M-CORD)和企业(E-CORD，其中包括以太网方面的规定)。R-CORD 的贡献者本周展示了基于云的管理平台如何使服务提供商能够使用网络内外的开源软件实时管理整个大陆的通信服务。

然而，正如 Peterson 周二所说，他的团队也在为第四个新兴用例 A-CORD 构建参考实现，以满足电信级 NFV 基于丰富遥测技术的分析需求。他的目标是让所有四个用例的参考实现变得足够完整，以便开源开发者开始实地试验。

## 没有接头的电线？

因此，本周在英国国家统计局,“分析”这个词并不是一个外来物。思科认为这次讨论到底遗漏了什么？

“这是网络的反应部分，当我们可以获得网络的配置和供应时，这种进出平台的遥测技术，然后它们之间的总线对网络做出反应，”沃德周三解释道。业界需要从在控制器层提供服务转向在平台层提供服务，这样开发者和网络消费者会感觉更舒服。

换句话说，网络服务需要为客户提供服务视图，沃德说，这是基于客户需求而不是网络能力。Ward 认为“平台层”对应于工作负载编排堆栈顶部的应用层；控制器层对应于堆栈中更底层的基础架构。

“我们必须意识到这是一个工作流程，”沃德说，他指的是图表上虚拟组件之间的流量进展。以及具有与网络术语、安全所需的特定功能或服务级别协议相关联的特定拓扑的工作流，这就是策略视图。”

与企业数据中心一样，策略是自动化服务管理的脚本化规则，尤其是在拒绝或允许访问资源的情况下。过去，策略应用于用户，但在现代企业数据中心，它们应用于应用程序以及允许用户访问的内容。

思科的沃德认为，服务提供商堆栈上的应用层“实际上是我们还没有讨论过的东西，但它是开源领域的一个巨大进步，并与网络直接相关。”他解释说，通用云工作负载和虚拟化网络功能都与各自类别中的其他节点进行通信。

“作为一个行业，我们还没有将虚拟化网络功能、基于组的策略或意图推进到行动的地方。许多人讨论了“整个堆栈”开发人员的概念。实际上，我是无堆栈开发人员的忠实拥护者。我想要运行我的工作负载，我想要一个负载平衡器或防火墙，[然后]开始。”

沃德说，编排平台应该提供通过分析来轻松确定所请求的服务执行效率或成功程度的方法。他接着说，在今天的云铸造平台上，客户可以要求计算、内存和存储资源，但还不能要求带宽。

“最后……你实际上并不了解，我的工作流程发生了什么，”沃德说。“移动到[*平台*层，并意识到这是公共云目前提供这些服务的地方——作为一个行业，我们需要到达那里，我们需要以开源方式到达那里。”

思科是新堆栈的赞助商。

斯科特 m 富尔顿三世的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>