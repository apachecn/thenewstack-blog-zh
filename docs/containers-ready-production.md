# LinuxCon 2016:为生产工作评估容器

> 原文：<https://thenewstack.io/containers-ready-production/>

容器可能是当前最热门的技术之一，但是尽管它们对于某些事情来说是很好的解决方案，但它们并不是每个实现的完美解决方案，您仍然需要仔细考虑容器如何适应您的整个基础架构，并仔细考虑如何在生产中开发、管理、监控、部署和保护这些容器。

ContainerCon 是本周在多伦多举行的 LinuxCon North America 的一部分，在 container con 上，有很多宣传容器优势的演讲，还有一些关于使用容器的挑战和注意事项的演讲，尤其是在生产中使用容器的时候。

Linux 容器和像 LXC 这样的技术已经存在了一段时间，但是它们并不容易使用。换句话说，早期的容器“不是为普通人准备的”，正如红帽公司的[文森特·巴茨](https://twitter.com/vbatts)在他关于容器标准的演讲中提到的。

现在的不同之处在于，最近的许多容器项目都非常注重使容器易于使用，结果，容器变得非常流行。大家都听说过 Docker。正如[科里·奎因](https://twitter.com/quinnypig)在他的“码头工人教会中的异端邪说”的演讲中所说，“码头工人的第一条规则就是永远不要闭嘴。”迄今为止，Docker 已经获得了 1.8 亿美元的资金，当然也有它的宣传份额。

伴随着这种易用性和流行性而来的是大量的挑战，尤其是在将容器部署到生产中的时候。换句话说，Quinn 说 devo PS plus 容器不会让在你的笔记本上工作的东西神奇地在生产中工作。在将容器投入生产之前，您真的需要花一些时间来理解容器可能发生故障的方式。这些故障或其他问题可能发生在堆栈中的任何地方:容器本身、容器中运行的应用程序、安全性、网络等。您确实需要查看这些层中的每一层，以了解故障并解决问题。

目前正在向基于微服务的架构转变，这种架构具有小型、模块化的独立流程和可扩展的开发模型，并且与环境无关。最终，从三层架构迁移到微服务架构会带来很大的复杂性，并且每个部署都可能以独角兽告终，Quinn 用这个模型描述了这一点:

Quinn 还谈到了容器并不是配置管理的死亡，以及向不可变基础设施的转移并不意味着配置管理的终结。尽管你可能在其他会议上听到过，但 Docker 并不是一个替代配置管理的快速解决方案，因为会议讨论倾向于关注成功，而不是悲惨的失败。

在米切尔·斯维奇的演讲中，“集装箱企业准备好了吗？连接传统和敏捷 IT，”他表达了在生产中小心使用容器的类似担忧，但是从一个稍微不同的角度。传统的 IT 和更新的、敏捷的方法使用容器不应该是全有或全无的心态。在您的环境中，保留一些应用程序(OpenStack、Oracle SAP 等)可能是有意义的。)在更传统的非集装箱化的环境中。对于其他应用程序，部署在容器中的敏捷方法会更合适，但是这些容器和映像需要像在生产基础设施中运行的其他任何东西一样，进行仔细的监控、修补和保护。

另一个挑战是容器标准仍在形成中。Batts 谈到了容器标准化是如何在几个不同的领域发生的:打包、运行时、网络和云。也有很多可用的工具，所以真正思考和定义您的用例很重要，而不是仅仅使用某些东西，因为它是本周最受关注的热门新容器工具。他还建议确保您的容器集成接触点保持通用，以避免局限于特定的解决方案，尤其是在标准仍在开发中的时候。

容器可能是基础设施解决方案的重要组成部分，但它们显然不是万能的完美解决方案。需要仔细考虑如何使用它们，尤其是在您的生产环境中。

[码头工人](https://www.mirantis.com/software/docker/kubernetes/)和[红帽](https://www.openshift.com/)是新堆栈的赞助商

特色图片由 Paul Townsend， [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>