# 在企业中采用容器

> 原文：<https://thenewstack.io/adopting-containers-enterprise/>

编者按:这是我们的电子书《Docker 和容器生态系统》中的一章。下载电子书，了解更多关于不断变化的集装箱景观。

在大型企业中，颠覆性的新技术和实践通常会经历一个彻底的采用过程。这个过程通常从精心的演示和讨论开始，然后是各种概念验证。当采用发生时，它通常首先发生在构建非关键系统的小团队中，并且主要用于开发和测试工作负载。当技术进入生产阶段时，大量的时间和机会已经过去了。

容器，以及容器化企业工作负载的概念，目前正在许多企业中经历这一过程，这是由容器提供的解决困扰企业中开发人员生产力和应用程序交付的各种问题的承诺所推动的。

## **企业动机**

通过围绕工作负载提供抽象，并使其可移植，容器成为支持各种更有效的开发过程和应用程序架构的基础。

具体来说，企业开发团队和 IT 组织认为 Docker 和 containers 是一种解决以下问题的方法:

1.  **流程低效:**企业中不同的团队通常有他们自己的开发和发布软件的标准。不幸的是，外包开发常常伴随着有限的治理和透明度，这常常加剧了这个问题。许多企业正在探索将容器作为跨团队标准化软件发布过程的一种方式。
2.  **遗留应用程序:**遗留应用程序和系统在企业中很常见。这些系统不断产生操作和维护问题。项目团队努力分配资源来运行随需应变的测试基础设施，结果是经常放弃测试以支持按时发布新功能。从事遗留应用程序工作的团队被容器所吸引，因为它们能够帮助更有效地利用基础设施。
3.  协作:从事大型项目的开发团队必须协调软件发布，这一过程通常需要很长时间。例如，从事持续维护和开发遗留应用程序的团队欣赏容器帮助他们更容易地同步软件发布的能力。基于容器映像的开发方法也有助于鼓励开发和操作团队之间更紧密的交互，从而鼓励 DevOps。
4.  **开发/生产奇偶校验:**生产、开发和测试环境经常会有奇偶校验问题，它们会逐渐分离，导致持续的“在我的机器上运行”问题。容器有助于确保跨各种基础设施的一致的运行时环境，企业开发团队发现这是一个非常有用的特性。
5.  **虚拟机蔓延:**随着企业采用虚拟机，虚拟机往往会蔓延，导致基础架构的利用率降低。企业通常通过建立严格的治理规则(如审批和工作流)来限制蔓延。然而，这些规则逆转了开发人员的弹性和自助服务的优势。由于与容器相关的开销比虚拟机低得多，许多企业对容器作为缓解蔓延的一种方式感到兴奋。
6.  **云原生应用:**微服务和其他云原生应用架构需要与传统设想不同的基础设施视图。在容器中，企业开发团队看到了更容易构建云原生应用程序并利用新兴趋势的机会。

## **集装箱采用策略**

当虚拟机开始在企业中流行时，IT 部门的一个主要卖点是整合未充分利用的基础架构以减少其运营空间和成本的机会。然而，容器和围绕它们的生态系统的采用是由敏捷性驱动的，而不是成本降低。

在评估和采用容器技术时，企业通常会采取一些策略:

1.  **追求唾手可得的果实:**当开发团队不得不努力获得测试环境的供应和可操作性时，他们会损失大量的时间，挫败感也会增加。在开发和测试中解决基础设施可用性问题通常是向容器过渡的良好驱动力。对于不需要专用实例的项目，重用作为链接容器部署的测试环境的 IT 基础设施是一个很好的开始方式，并且可以提供重要的技术操作知识。
2.  **更新构建和部署流程:**需要修改构建和部署基础架构，以便企业充分利用现代基础架构。为了部署到公共云和私有云，一些企业将终端应用程序部署为一组机器映像，从而减少了设置新调配的按需基础架构所需的时间。同样的实践可以扩展到容器图像。在基于容器的部署模型中，构建步骤可以使用环境中预先存在的基础映像来生成新的容器映像。部署步骤可以获取这个映像，并在支持所选容器技术的任何基础设施上运行它。

*****   **采用“容器优先”:**对所有新项目采用容器优先的方法是另一种推动采用的常用方法。这意味着所有的新项目都必须用容器来构建和发布软件，除非有特殊的原因。首先使用容器鼓励开发团队将容器视为他们的应用程序拓扑的一级元素，并刺激容器原生应用程序的开发。此外，使用预容器化的项目环境来培养新的开发团队比使用传统方法要容易得多。这有助于团队快速启动，而没有转换现有项目流程的复杂性。*   **标准化基础映像:**对于运营团队来说，形式化并发布所有项目都可以使用的标准容器映像非常重要。这些定制的基础映像可以托管在开发团队在构建项目时使用的私有注册表中。对标准化基础映像的更改可能意味着注册中心的新版本，然后可以在开发过程中透明地使用。企业习惯于托管防火墙规则和其他数字 IT 资产的私有存储库，因此这对于他们来说应该不是一个奇怪的采用步骤。****

 ****## **面临的关键问题**

当将容器整合到他们的整体 IT 策略中时，企业面临两个关键的挑战:[安全性和缺乏成熟的工具](http://www.theregister.co.uk/2015/01/12/docker_security_immature_but_not_scary_says_gartner/)。

虽然像 Google 和 Twitter 这样的网络规模的公司已经在生产中使用容器很多年了，但是对于开源和专有产品来说仍然是早期。工具成熟度的问题很大程度上是时间和经验的问题。随着更多的采用和需求，工具将不可避免地稳定和改进。

企业 IT 组织正在寻找容器来帮助他们实现更现代的应用程序架构和开发过程，在这个过程中允许他们更快地创新。

另一方面，安全性一直是早期采用者关注的焦点。虽然这是所有在生产中使用容器的公司都关心的问题，但对于在多租户环境中使用具有生产工作负载的容器的公司来说，这是一个更大的问题。

[cyclone slider id = " ebook-1-赞助商-2 "]

眼下的问题是容器隔离。迄今为止，容器并没有表现出强大且经过测试的隔离不同工作负载的能力，这些工作负载已经成为各种虚拟机管理程序的假设。

去年，Canonical 推出了 [LXD](http://www.ubuntu.com/cloud/tools/lxd) ，它实现了围绕更强容器安全性的想法，并通过 Ubuntu 和 OpenStack 集成提供这些想法。像 Hyper 这样的新项目——它使用一个极简的 Linux 内核，称为超级内核，来加载和运行容器——也正在成为单独容器的有趣替代品。正是因为这个原因，VMware 一直在推广传统虚拟化[作为容器](http://blogs.vmware.com/cto/vmware-containers-containers-without-compromise/)的补充。

## **集装箱实习**

随着组织继续推动敏捷性和创新，他们自然会致力于消除低效，如资源约束和流程瓶颈。与此同时，他们正在转向现代应用架构风格，如微服务，以及开发过程，如持续交付，这使得开发人员能够更快地迭代。

去年，ING 的首席架构师在 Dockercon Europe 上讲述了他们如何使用 Docker 来实现持续交付。BBC 新闻还强调了它如何围绕 Docker 构建其持续集成解决方案，并分享了他们在这样做时必须处理的警告和妥协。这两家大公司的展示表明了企业对容器技术的重视有多快。

通过采用本文中概述的一种或多种方法，不熟悉容器游戏的企业可以在启蒙的道路上迈出第一步，知道他们正在走一条以前已经走过多次的路。

Docker 和 VMware 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>****