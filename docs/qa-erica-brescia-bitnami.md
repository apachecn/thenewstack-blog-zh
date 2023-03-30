# 与 Erica Brescia、Bitnami 的问答:生产规模的持续部署

> 原文：<https://thenewstack.io/qa-erica-brescia-bitnami/>

也许没有人比 [Bitnami](https://bitnami.com/) 更了解持续集成和持续部署。该公司目前维护着超过 137，000 个独特的云和虚拟机映像，涵盖开源和专有应用程序、库、框架和操作系统。大多数主要的云提供商依赖 Bitnami 软件包来更新他们提供给客户的软件副本，许多企业也是如此。在这个漏洞更新和安全修复频繁的时代，这不是一个小任务。在许多情况下，Bitnami 甚至可以在他们的云提供商修补他们的系统之前就获得软件的修补版本。

为了更多地了解 Bitnami 的运营，我们在公司的旧金山办公室采访了联合创始人兼首席运营官 [Erica Brescia](https://twitter.com/ericabrescia?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) 。该公司计划发布用于重建和部署应用程序包的框架，该框架将被称为 Bitnami Enterprise，这对许多维护自己软件的组织来说无疑是非常有用的。我们谈到了保持开源软件更新和打包的挑战，Bitnami 运营背后的机制，以及公司的工具 [Stacksmith](https://thenewstack.io/bitnami-announces-stacksmith/) ，它允许最终用户为定制应用程序生成 Docker 文件。我们也忍不住询问布雷西亚该公司如何看待新兴云市场的发展。

Bitnami 的创意来自哪里？

布雷西亚:非常有机。我们从一个名为 [InstallBuilder](http://installbuilder.bitrock.com/) 的跨平台安装工具开始，我们仍然以 BitRock 品牌在世界各地销售它。因此，像英特尔、三星和通用动力这样的公司购买许可证，用它来打包他们的软件，并从多个平台运送安装程序。

TNS: 这一直是独立软件提供商的事情？

布雷西亚:是的，是的。我们一直专注于安装和部署，尤其是跨多个平台的安装和部署。使用 InstallBuilder 可以做的一件很酷的事情是为 Linux 构建一个安装程序，它可以在几乎任何 Linux 发行版上安装和配置您的完整堆栈。它确切地知道在哪里安装东西，以及权限和其他东西如何在所有不同的操作系统上工作。你说，“给我建一个平台的安装程序”，它就会这么做。你不必知道每个操作系统工作的所有特定方式。所以，如果你想一想安装程序到底是什么，它是一个跨平台的配置引擎，对不对？

**TNS:** 正是。

**布雷西亚:**这成为我们所做的一切的基础，本质上是关于软件配置和部署。所以我们开始与商业开源软件供应商合作，像 SugarCRM，MySQL，Jaspersoft，Alfresco，Zenoss，当这些人开始建立业务的时候。有一个开源公司获得资助的巨大浪潮，我们真的成为这些公司向最终用户交付软件的标准解决方案。

他们面临的挑战是，开源软件开始更多地进入主流，并从中间件上升到应用程序级别。当你到了那个层次，你就不再是卖给开发商了；您正在向一个不知道如何安装和配置 Apache 的业务人员销售。Bitnami 可以使用我们的安装程序交付整个 SugarCRM 堆栈，并在 Mac 或 Windows 笔记本电脑上提供可点击的安装体验。这允许较少的技术人员来评估软件。当然，当他们决定需要它时，it 部门可以去安装它，使用我们的 Linux 安装程序，并将其安装在服务器的某个地方。

这就是我们真正看到提供这种预制造、预集成和随时运行的软件堆栈的影响的地方。我们将与安装相关的支持请求减少了 50%以上，因为一切都以正确的方式设置。

这真的是比特纳米的起源。我们看到了构建这些软件堆栈对这些公司的益处，以及我们如何帮助他们发展业务。所以我们决定更上一层楼，打包更多的开源软件。

多年来，我们已经非常非常擅长打包大量的软件。我们建立了一个完全自动化的系统来监控我们包装的所有东西。

我们从本地安装程序开始，然后虚拟机变得更受欢迎。所以我们开始运送虚拟机。然后，所有的云平台都上线了。早在亚马逊还没有市场的时候，我们就开始为亚马逊建立 AMIs(亚马逊机器映像)。我们成为那里最受欢迎的应用程序提供商。一旦其他云供应商开始建立他们的市场，他们在亚马逊上看到 Bitnami 应用程序，他们自然开始来 Bitnami，因为我们是这个领域的专家。

我们现在有亚马逊、Azure、谷歌、甲骨文、VMware、CenturyLink、1&1 和 GoDaddy，还有一堆其他的云平台在路上。在几乎每一个供应商的情况下，当然是所有的主要供应商，他们甚至在推出市场之前就来找我们，因为你不想有我们所说的“空云综合症”，对吗？你不想有一个没有内容的市场。

Bitnami 向云供应商提供的不仅仅是内容，而是始终保持最新的内容。Bitnami 经常更新其映像，并以比云供应商修补其操作系统映像更快的速度将其推送给云供应商。去年，我们推动了 2.35 亿小时的云计算使用，如果我们计算核心时间而不是简单的计算时间，这将是一个更大的数字。我希望今年至少能翻一番。

Bitnami 处于一个非常独特的位置，可以帮助下一波云的采用。当用户来到 Bitnami 时，他们知道他们得到的东西可以安全使用；包裹里没有邪恶的东西。无论您是在笔记本电脑上部署 Drupal，还是在 Amazon 或 Azure 上部署，他们都能获得一致的部署体验和完全相同的堆栈。这使得在不同环境之间移动变得非常容易。我们的堆栈在整个 Bitnami 应用程序库中配置一致，使基础架构更易于管理。因此，使用 Bitnami 对用户有很大好处，它简化了从本地到云环境的过渡。

是的，你是怎么做到的？

**布雷西亚:**自动化。这是我们内部拥有的一个完整平台。我们将在今年晚些时候发布一款企业产品，将我们所构建的一切产品化。

因此，系统接受更新并开始构建和测试过程。一切都完全自动化了。我们跟踪简历，然后我们有一个叫 Bitnami 机器人的东西，它基本上抓取我们打包的所有东西，并说，“哦，这个应用程序有一个更新。它需要包装。”

这个过程中有一些人的参与，但不多。例如，应用程序包在发布之前要经过人工检查，但是所有剩下的工作几乎都是自动完成的，除非软件的部署方式发生了巨大的变化，然后我们必须改变我们的系统来更新它。

https://youtu.be/mfimauzFQvY

**TNS:** 你们最近引进了一些新高管。

布雷西亚:是的，我们有！去年，我花了相当多的时间打造我们的高管团队。我们最近雇佣了[里克·斯潘塞](https://www.linkedin.com/in/rickspencer3)，他是 Ubuntu 的工程副总裁。他在那里工作了九年多，管理了整个 Ubuntu 工程。我们还聘请了来自 VMware 的[西蒙·班尼特](https://www.linkedin.com/in/simonpbennett)，他是我们的产品副总裁、[戴尔·布朗](https://www.linkedin.com/in/dalerbrown)，我们威瑞森云平台业务开发副总裁、[菲利普·史密斯](https://www.linkedin.com/in/philipsmith)，我们的首席财务官和[大卫·丹尼斯](https://www.linkedin.com/in/davidpdennis)，我们的营销副总裁。我们还在运营和工程方面引进了一些杰出的技术人才。例如，我们请来了我们的高级 IT 运营总监 Ian Kallen。

我们正在有机增长，去年这个时候我们大约有 35 人，可能还不到那个数字。我们现在大约 70 岁，到今年年底我们将接近 100 岁。

**TNS:**Bitnami 是否开始使用 Docker 容器作为打包机制？

**布雷西亚:**是的！我们正在 Bitnami 研究许多围绕集装箱的有趣的东西。我们在 Docker Hub 中放置了一些组件的容器，供人们使用。这是同样的价值主张。一切都是一致配置的，可插拔的，总是最新的。它们旨在开箱即用地协同工作。所以你有所有正确的库和它们应该在哪里，MySQL，MariaDB，Rails。现在，我们正在打包许多语言、框架和数据库。

11 月，我们推出了一个名为 [Stacksmith](https://thenewstack.io/bitnami-announces-stacksmith/) 的新工具，它将从 Bitnami 构建和维护的已知良好的组件中为您构建一个 Docker 文件。最酷的是它完全是 API 可寻址的，可以通过 Webhooks 获得。您可以将它挂接到您的 CI/CD 系统中，如果您正在构建的任何组件有更新，Stacksmith 会主动通知您。

我们对此感到非常兴奋，这将是我们今年晚些时候推出的更大产品的一部分，名为 Bitnami Enterprise，它将允许人们再次建立在 Bitnami 已知良好的组件之上，并使用我们的许多工具来打包和部署他们自己的应用程序。

**TNS:** 这对公司来说还是有意义的，因为这样他们就不必将所有的专业知识都整合到包装中。

**布雷西亚:**正是，打包打补丁。开发人员和 IT 运营人员应该能够将他们的专业知识和精力集中在对他们的组织更有价值的其他事情上。

**TNS:** 你认为你服务的用户群正在转向云计算吗？

**布雷西亚:**我们确实看到很多人搬家。毫无疑问，人们开始行动了。我想说，这是非常稳定、坚实、稳健的增长。我们也经常驾驶它。我的意思是，有很多人对他们的内部 IT 部门感到沮丧，希望通过 Bitnami Enterprise，我们能够帮助 IT 部门解决这一问题，并通过为他们提供一种自助方式来启动和运行应用程序，从而让他们的用户满意。

Bitnami 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>