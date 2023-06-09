# 一家小型创业公司如何改变虚拟化格局

> 原文：<https://thenewstack.io/how-one-small-startup-is-changing-the-virtualization-landscape/>

[](https://www.linkedin.com/in/charlesschulz/)

 [查尔斯-亨利·舒尔茨

查尔斯·h·舒尔茨是瓦特公司的战略主管。他是一名技术专家、网络安全专家、自由软件倡导者，并在开源项目和网络安全政策方面工作了多年。](https://www.linkedin.com/in/charlesschulz/) [](https://www.linkedin.com/in/charlesschulz/)

虚拟化无处不在。无论是在内部基础架构、混合基础架构还是云中，无论您运行的是虚拟机还是容器，您都可能依赖于某处的虚拟机管理程序。

但是虚拟化已经成为基础架构中如此常见的元素，以至于虚拟机管理程序的存在几乎已经被遗忘了。这一领域的创新相当有限，而硬件(这是世界上所有基础设施的共同点)却在不断创新。

此外，与某些主要的 IT 部门(例如操作系统)相反，虚拟化主要掌握在开发解决方案的公司手中，这些解决方案是封闭的，一旦在您的基础架构中实施，就很难退出。

因此，在这个行业不再流行，整个技术行业由几家巨头主导的时候，着手开发一个新的虚拟化平台这样的项目似乎很奇怪。但是这并没有阻止 XCP 天然气项目背后的人们。

 [马克-安德烈·佩津

Marc-André是网络营销经理。](https://www.linkedin.com/in/marc-andr%C3%A9-pezin-8b854641/) 

2018 年，我们在法国一家专注于虚拟化解决方案的科技初创公司推出了开源项目 XCP-ng: Xen 云平台——新一代。XCP-ng 来自 Citrix 虚拟机管理程序解决方案，旨在成为基于 [Xen 项目](https://xenproject.org/)的完整虚拟化平台。

项目开始后不到两年，它现在托管在 Linux 基金会的官方 Xen 项目中。在社区方面，该项目取得了巨大成功，因为它拥有一个庞大且非常活跃的用户社区(超过 150，000 次下载，社区论坛上有 3，500 名活跃成员)。在项目的可持续发展方面，2020 年底，法国国家能源与创新局推出了项目的首个 LTS(长期支持)版本:XCP-ng 8.2。我们甚至建议专业支持可以从目前的 5 年增加到 10 年。最后，在技术方面，全职从事 XCP-ng 工作的开发人员团队从 2018 年的三名开发人员增加到 2020 年的七名，并积极参与 Xen 核心项目——最新的 Xen 安全补丁就证明了这一点，该补丁涉及 Xen 处理 PCI passthrough 的一个缺陷。

## XCP 天然气公司成立的原因

那么，一家位于法国阿尔卑斯山格勒诺布尔的小型法国创业公司是如何在虚拟化领域取得一席之地，同时为古老的 Xen 项目带来新鲜空气和新奇事物的呢？嗯，这并不完全是盲目的。

在开发之前，我们在 Kickstarter 上开展了一项活动，通过这项活动，我们确信人们对新的虚拟化解决方案有兴趣，尤其是完全开源的解决方案。虽然该活动需要 6，000 美元才能成功，但该项目在 30 天的活动中筹集了近 60，000 美元，这是一个良好的开端，也证明了虚拟化部门尚未满足所有需求。特别是，Kickstarter 活动主要是由项目之外的公司资助的，这些公司当时无法找到满足其虚拟化需求的满意解决方案。

XCP ng 也不是一个从零开始的项目。该解决方案得益于多年来的发展，不仅是围绕 Xen 项目本身，还有 Citrix 在 XenServer 上的成就。事实上，由于该公司的历史产品 Xen Orchestra 是云中基于网络的管理、备份和行政界面，因此该公司的团队在这一技术上已经训练有素。

因此，XCP-ng 有着坚实和公认的基础。ates 的目标是利用其专业知识和对开源世界的深入参与，为 Xen 项目带来它一直或多或少缺乏的东西——使用和参与项目的活跃用户社区，以及对解决方案进行创新的财务投资，并通过更大规模的推广来重振 Xen 项目。

## Xen 项目和 Citrix XenServer 怎么样？

让我们谈谈 Xen 项目本身。虽然众所周知，但很少有人真正知道这个开源管理程序的多事之秋，以及它与科技行业一些最大的参与者之间的动荡关系。你们中的一些人甚至认为这个项目或多或少处于停滞状态，或者根本不活跃。

Xen Project hypervisor 是一个开源的 type-1 hypervisor(它运行在硬件上！).该项目于 2003 年在剑桥大学诞生，因此它是历史上第一个发明的开源管理程序。自然吸引了很多公司的关注。2007 年，Citrix Systems 收购了 XenSource，并创建了自己的版本:XenServer，增加了 Xen 核心和一个 API (XAPI)。此外，Xen 项目还与当时一些最大的科技公司(包括 Citrix、IBM、HP、Red Hat、Sun Microsystems)成立了顾问委员会。

这花了一些时间，但在 2012 年，Citrix XenServer 也成为了一个开源项目，商业版也可用。但是 XenServer 缺乏一个开发人员社区，缺乏全面检查、沟通，甚至没有关于项目的文档。

到 2017 年底，Citrix 对免费版本引入了更进一步的限制(例如，一个池中的三台主机)，并将许多有用的功能(例如，实时存储迁移和动态内存)从免费版本移至付费商业计划。简而言之，这就是导致创造 XCP 天然气公司的原因。再加上许多特性都被付费许可锁定，开源方面的情况看起来并不乐观。即使在开发层面上，XenServer 中添加的大多数最新功能都在某种程度上依赖于非开源代码；使得用户比以往任何时候都不太可能从源头上使用 XenServer。

Vates 是一家法国科技初创公司，自 2012 年以来一直专注于虚拟化解决方案，因此我们对 XenServer 的未来不太有信心。愤怒的用户从四面八方包围了 Citrix，准备将其基础架构迁移到 VMware 或 HyperV，以应对 Citrix 所做的更改。作为迄今为止的主要产品，Xen Orchestra 是 XenServer 的独家产品，因此 XenServer 的不确定未来意味着 Xen Orchestra 的潜在不确定未来。我们决定是时候采取行动了。XCP-ng 项目在 XenServer 7.4 发布后不到一个月就启动了。

Citrix 选择突然改变 XenServer 定价策略的原因可能永远不会为人所知。然而，我们的两个观点是:Citrix 的战略与开源世界并不一致。我们认为，对于 Citrix 来说，未来是在云中，而不是在“内部”基础架构中。因此，在我们看来，XenServer 只是 Citrix 大梯子上的一个小梯级；只有一步，甚至不是强制性的一步，为其更大的产品 XenDesktop 带来更多客户。

## XCP 天然气项目才刚刚开始

这就是 XCP 天然气项目的过去和现在。在后续的文章中，我们将关注它的未来。我们还将讨论在虚拟化领域还需要做些什么。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>