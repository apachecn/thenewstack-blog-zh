# 30 岁的 Linux:它对 Kubernetes、云和 Edge 的影响

> 原文：<https://thenewstack.io/linux-at-30-its-impact-on-kubernetes-cloud-and-edge/>

[](https://www.linkedin.com/in/jkriggins/)

 [詹妮弗·里金斯

詹妮弗是一名自由作家，她利用讲故事、写作、营销、播客主持、公共演讲和品牌来跨越技术、商业和文化的鸿沟。因为如果我们正在建设未来，我们需要更多地考虑我们正在建设的未来。](https://www.linkedin.com/in/jkriggins/) [](https://www.linkedin.com/in/jkriggins/)

今年 8 月，Linux 迎来了 30 岁生日。开源 Linux 内核的决定意味着成千上万的开发者和操作者直接或间接地为它做出了贡献——这可能是最重要的代码库。从 Linux 桌面到 Windows 操作系统，再到 Android 设备，再到 edge，它的统治地位是如此之大，以至于据估计世界上大约一半的人口被认为是 Linux 用户，尽管他们中的大多数人甚至没有意识到这一点。

是什么让 Linux 成为现代软件的支柱？为什么，在一个技术老化的时代，它的覆盖范围和可扩展性只会越来越大？它不仅是传统系统的未来，也是 Kubernetes、边缘计算和物联网的未来？它如何应对日益分散的系统的安全问题？

我们采访了两位 Linux 爱好者和 SUSE 的同事: [Alan Clark](https://www.linkedin.com/in/alanhclark/) 来自 SUSE 的 CTO 办公室，从事新兴技术和开源工作，以及 [Matthias Eckermann](https://www.linkedin.com/in/meckermann/) ，SUSE 的 Linux 平台产品管理总监。他们反思了自己从事 Linux 工作的职业生涯，以及为什么 Linux 是开放的未来。

【cloud native 和 Kubernetes 等现代技术趋势如何依赖于 Linux 操作系统？

 [马蒂亚斯·埃克曼

Matthias 是 SUSE Linux 平台产品管理总监。](https://www.linkedin.com/in/meckermann/) 

**埃克曼:**从一开始就有很多东西建立在 Linux 上，我们现在也在用。如果你说一切都是云原生的，那只是游戏的一半，因为有数十亿安装和使用的 Linux 系统不是云原生的。我看到的是非常传统的工作负载的连续体，直至极端的云原生。有趣的是，所有这些都可以在一个能够向多个方向扩展的操作系统的基础上实现。扩展 Linux 不仅仅意味着内存大小或 CPU 大小。根据您可以整合的系统数量以及您所服务的人员数量，它可以扩展不同的体系结构。

Linux 允许完全不同的用例，从网络设备到 Linux 可能提供的裸机容器主机。这个容器主机中有许多功能—安全性、工作负载隔离、容器隔离、提供存储容量、为所有这些数百万个容器进行正确的调度。这在传统工作负载和云原生工作负载之间是共享的。

**如果有 35 亿潜在的 Linux 用户，人们在这一点上离 Linux 内核有多远？**

 [艾伦·克拉克

Alan 来自 SUSE 的首席技术官办公室。他领导 SUSE 行业标准和新计划项目，负责 SUSE 战略并参与全公司的新计划、行业标准和开源组织。](https://www.linkedin.com/in/alanhclark/) 

克拉克:这取决于他们是谁。

一个操作者非常想知道盖子下面是什么；他们想知道，但他们希望它易于管理。他们知道他们运行的是 Linux，他们知道什么版本，什么补丁，但是他们希望操作简单。所以，我们想简化他们的生活。正如 Matthias 所说，我们希望在各种架构和规模等方面进行简化。我们想带来一致性。这就是我们如何简化他们的生活。

我们今天正在做的一个方法，当然，是在 Kubernetes 用这些集装箱化的模型。这就是 Kubernetes 如此成功的原因。它使我能够在所有这些环境中保持一致性，并让我对自己的世界有一个简单的看法，因此我可以协调和管理它。

从开发人员的角度来看，我希望我的代码可以在任何地方运行。我真的不想知道那个环境的细节。让接线员处理那件事。然后，我处理编写代码、运行服务或应用程序以及部署它们的简单性。所以，给我一个简单的开发部署模型。让操作员弄清楚在哪里以及如何处理的编排。运营商已经从我这里抽象出来，这样我就可以让我的生活变得简单。我们简化了双方操作员的生活。所以这是一个双赢的局面。

即使 Linux 是不可见的，不为它上面的更高层所知，Linux 的好处是它在一方面是可配置的。但另一方面，有如此多的人从事这项工作，他们有着不同的兴趣，因此所有这些不同的工作负载都可以在它的基础上实施，或者使用它或进一步开发它。

**开源经常有这个臭名昭著的安全问题，因为它通常由用户来运行补丁，而他们经常** [**没有足够快地运行它们**](https://thenewstack.io/open-source-developers-are-securitys-new-front-line/) **。Linux 社区是如何解决这个问题的？**

**埃克曼:**问题是用户和人的行为。不幸的是，即使容器提供了更多的抽象，容器也不一定会变得更好。从 Linux 的角度来看——我把 Linux 社区和所有合理的、免费的和商业的 Linux 发行商放在同一个桶里，因为我们在幕后一起工作——每个人都非常专注于尽可能快地、尽可能合理地提供更新，并做出协调一致的响应。这些修补程序是及时可用的，并且以可供所有这些用户使用的方式可用。对于所有主要发行版来说都是如此。

所以打补丁的问题是客户运营的问题。在这里，我们看到了旧世界和云原生世界之间的真正区别。这可以归结为抽象。

在传统世界中，操作系统之间有着非常紧密的联系:低级应用程序、中间层和高级应用程序。如果您已经正确地建立了系统管理，公司会以每周或每月更新一次的方式进行管理。您的系统需要运行一年或更长时间；您可以少打一点实时补丁，但仍然是安全的。

在云原生世界中，我认为有一个机会，从我的角度来看，这是云原生方法的一个重大承诺，因为你有真正明确的分离。首先是主机，它一方面为您提供硬件抽象、安全性、调度、容器和工作负载的隔离。中间层，或 Kubernetes 和 Kubernetes 管理层，位于第二层。第三层是应用层。我绝对不关心主机，因为那是 Linux 所在的地方，是 Linux 好的地方，是你可以使用最小的、高度安全的、非常专注的 Linux 操作系统的地方。然后是所有功能和堆栈的中间层，包括 Kubernetes 集群管理。然后是第三层。所有的应用程序都在这里。

> “随着时间的推移，我看到这些容器的质量在下降，因为没有人考虑过容器的生命周期。”

我目前看到的最大挑战是在第三层，因为我们每天生产大量的集装箱。而且只要容器和方法是新的，就非常容易，一切都是安全的。但是我看到随着时间的推移，这些容器的质量在下降，因为没有人考虑过容器的生命周期。我认为这是我们今天面临的最大问题，容器的生命周期面临着我们过去在传统世界的操作系统堆栈上看到的同样的挑战。这是每个实现容器的人都需要注意和解决的问题。这意味着 CI/CD 工具具有适当的源代码管理。与您的容器和 Kubernetes 管理的适当集成是必不可少的。

所以 Linux 已经老到可以竞选美国参议员了。马提亚斯，Linux 的未来是什么？

**埃克曼:**我没有看到它变老，因为有很多想法。具体来说，我们看到 edge 带来了许多新技术和新思想、新硬件的出现、对纵向扩展和横向扩展的新要求以及对网络功能的新要求。

另一件事是安全。软件供应链对每个人来说都是一个挑战，我们需要思考未来的 Linux 如何让客户相信它是真正以安全为出发点生产的，以及 Linux——作为发行版或软件包或主机或访客或容器——如何以一种明显安全的方式生产和消费。我们通过我们拥有的安全认证来做到这一点，比如[通用标准](https://www.commoncriteriaportal.org/cc/)。我们甚至用我们的过程做到了这一点，我们生产 Linux 发行版的方式是经过认证的。

安全性的另一面是 Linux 本身——Linux 内核和 Linux 生态系统——是如何发展的。在边缘，我们将把诸如安全设备的使用视为当务之急。这意味着像 SUSE 这样的公司与硬件合作伙伴一起工作，将硬件关于操作系统的概念和操作系统关于硬件的概念更紧密地结合起来，以便从安全的角度来看是可管理的。

另一方面，我们将拥有更多像增强的 Berkeley 包过滤器这样的技术，在 Linux 内核本身的安全性和其他方面给予我们更多的灵活性。我预见，我们将会看到在 Linux 内核的这种能力之上开发另一个层次的应用程序，这将把 Linux 提升到性能、监控甚至更多方面的下一个层次——同时它正在向一种新的能力发展。

艾伦，你认为 Linux 在第四个十年将走向何方？

克拉克:我们现在已经 30 岁了，Linux 并没有死——恰恰相反，它在成长，在变化。如果你听马蒂亚斯描述的所有事情，它会告诉你它非常活跃。对它做出贡献的人的数量，给它注入新思想的人的数量，告诉我它非常有活力，并且它的使用和扩散继续急剧增长。

未来是广阔的。所有的新想法和它将被使用的地方 Linux 的未来非常光明。

![](img/f620400d3f58d723440a85aa65739860.png)

*要了解更多关于 Linux 和其他云原生技术的信息，请考虑参加 10 月 11 日至 15 日举行的 [KubeCon+CloudNativeCon 北美 2021](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>