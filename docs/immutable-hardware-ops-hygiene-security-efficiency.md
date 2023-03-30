# 不变的硬件:安全性和效率的运营卫生

> 原文：<https://thenewstack.io/immutable-hardware-ops-hygiene-security-efficiency/>

编者按:罗布·希施菲尔德是

[RackN](http://rackn.com/)

。RackN 通过多基础设施协调为混合企业 IT 创建了统一的运营控制系统。通过开放的数字 Rebar 平台，RackN 可移植性条款可在从云到金属的任何基础设施上扩展 Kubernetes、Docker Swarm 和其他平台。

使用自动化来减少周期时间并消除所有*操作组件的手动干预有明显的好处。这对硬件和软件都是如此。*

RackN 首席技术官 Greg Althaus 和我在**讨论[jérme Petazzoni 的 ContainerCon 2015 安全演示](http://www.slideshare.net/jpetazzo/containers-docker-and-security-state-of-the-union-linuxcon-and-containercon-2015)，他主张限制集装箱的使用寿命作为安全预防措施。**我们意识到，这种短命容器的论点通常也适用于虚拟和物理基础架构。

我以前和乔希·麦肯蒂一起写过关于强迫离职(“蜉蝣”)的文章。想象一下这样一种云，其中的服务器在使用一周后自动退役。这将迫使基础设施中的资源不断变动。云将能够非常[优雅地重新平衡负载](http://robhirschfeld.com/2015/04/20/mayflies-research-schedule/)并处理破坏性管理操作，因为工作负载是为变动而设计的。

Greg 和我一致认为，频繁地更换系统可以增强安全性(和运营卫生)。

基本思想是，如果您的环境不断地被 [破坏，并从](https://www.chef.io/blog/2014/06/23/immutable-infrastructure-practical-or-not/)[不可变基础设施](https://highops.com/insights/immutable-infrastructure-what-is-it/)源 中重建，那么它就更难成为入侵的目标。容器或虚拟机映像并不是重建原始环境的唯一方式:也可以完全自动化金属生命周期，以合理的速度清洗、刷新和重新映像服务器。事实上，这种方法对于超大规模提供商来说很常见。

如果不可变基础设施的目标是通过创建一次性基本配置来消除不确定的配置，那么就有可能在金属上重新创建这种环境。这种方法的关键属性是能够自动循环并将环境重置回受控环境。更快、更可靠地推动这一循环意味着更强大的基础设施。

除了改善卫生和可重复性之外，不可变的基础设施还会对安全性产生影响。

在快速循环中，没有稳定的着陆点来发起攻击，没有人为的后门或配置漏洞，加上频繁的更新和补丁应用。大多数攻击利用可能在物理环境中存在的旧漏洞，因为操作员将变化视为风险。

实际上，像容器或虚拟机那样真正销毁和重新映像服务器可能不太现实。Greg 定义了物理不变性的三个层次来指导实现讨论:

1.  **重新分配**:重新分配擦洗和重新部署。在这种类似云的模型中，机器被放回池中进行随机重新分配。不仅原有的配置和数据会丢失，而且节点和其他节点之间的基础架构特定关系也必须更新。这种实践通过确保清理现有的服务来实施良好的操作行为。由于必须预料到大规模故障，因此缺乏清洁可能会耗费运营时间来寻找丢失或被移除的系统。如果您有许多通用系统或者计划重新平衡工作负载分配，那么这个模型特别有吸引力。
2.  **重建**:重新部署刷洗&重建。在这种(重新)配置模式中，机器被完全重置，但目标工作负载被重新应用到同一系统。这将允许许多配置设置(如 IP 地址)被保留并重新应用于系统。重建周期的另一个价值是高可用性的“混沌猴”验证。总的来说，这有利于卫生，但不如 REALLOCATE 坚固和灵活。
3.  **刷新**:重新部署 Scrub OS，同时保留数据。重建的一个不太极端的版本关注系统的衰退部分(操作系统和应用程序)，同时保持数据完整。对于存储和大数据节点，恢复数据可能会带来巨大的开销、性能影响和风险。如果我们假设数据驱动器是安全的或者不受操作系统管理，那么将数据留在原处的安全风险就更小。

这些不变的基础设施概念可以在物理操作中实施，对安全性、利用率提高和整体卫生状况有显著的好处。我们很想听听您对这种类似云的运营基础架构的看法和担忧。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>