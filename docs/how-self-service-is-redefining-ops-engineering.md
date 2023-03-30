# 自助服务如何重新定义运营工程

> 原文：<https://thenewstack.io/how-self-service-is-redefining-ops-engineering/>

[Pivotal](https://tanzu.vmware.com/) 赞助了这篇文章。

 [尼尔·麦卡利斯特

1982 年，作为一名年轻的程序员，Neil 的第一个文本编辑器是一沓纸(后来出现了计算机)。从那以后，论文方法对他很有帮助，因为在 IT 和软件开发领域工作了几年后，他继续为 SFGate、Web Techniques、InfoWorld、PC World 和 The Register 等出版物编辑和写作。他目前是 Pivotal 的高级产品营销经理。](https://www.linkedin.com/in/neilmcallister/) 

你不需要在日本呆很长时间就能注意到它一定是自助服务的世界之都。这个国家无处不在的自动售货机，实际上是一个国家机构，排列在大大小小城市的街道上。据估计，这个国家有 550 万个这样的餐馆——每 23 个人就有一个——它们提供从冷饮到热午餐的一切。

更重要的是，日本的 DIY 采购趋势近年来有所扩大。如今，便利店完全无人化，每个货架都是自动化的。甚至餐馆也在尝试自助点餐。

对西方人来说，这可能听起来很奇怪——但不应该。想一想:你第一次使用自动柜员机而不是与银行出纳员打交道是在多久以前？还有很多例子。我们已经从在自动售货机里买邮票发展到了 iPhones。在某些美国市场，麦当劳甚至效仿欧洲，尝试让顾客用巨型触摸屏点汉堡。不要再问“你想配薯条吗？”

考虑到这些趋势，在企业 it 的高科技世界中，自助服务的需求同样在增长也就不足为奇了。事实上，它正在迅速成为数字化转型的催化剂和关键驱动力。

## 自助服务？但是…那是无政府状态！

想想 20 年前糟糕的旧时光吧，那时是中央集权统治。当一个业务部门需要新的基础架构时，通常需要几个月的时间才能调配好。难怪应用交付的瀑布模型占据主导地位；每个人都有充足的时间。

随着软件创新步伐的加快，事情需要改变。进入 DevOps。这个想法是打破集中的 IT 和嵌入产品开发团队的操作工程师，开发人员可以更快更有效地满足他们的操作需求。然而，尽管这种模式对 Spotify 这样的科技公司——它帮助开发了 devo PS——很有效，但对许多其他公司来说，它并不完全正确。特别是在大型企业中，开发运维很难在不增加成本的情况下[扩展](https://content.pivotal.io/intersect/why-devops-in-enterprise-is-dead)。

AWS、Azure 和谷歌等“超大规模”云提供商的崛起提供了一种不同的模式。这些供应商提供 IT 服务的菜单，从计算和存储到后端软件实例，只需点击几下鼠标即可订购。事实上，“*aaS”中的“服务”也可以代表“自助服务”。企业开发团队越来越渴望这种自助服务模式。

然而，真正自由放任的自助服务往往会导致混乱。所谓的流氓 IT 的许多危险包括成本超支、重复工作、不兼容的平台和标准、不一致的安全策略、跨项目的不良集成、僵尸实例等等。

## 现代自助服务是什么样的

那么，我们如何交付当今开发团队想要的东西呢？不出所料，谷歌给了我们一块拼图。谷歌以近乎不可思议的规模运营，其运营必须支持真正不计其数的团队和项目。[传统的开发运维方法](/tag/DevOps)永远无法扩展以满足其需求。它需要一个新的模型，谷歌称其开发的模型为[站点可靠性工程(SRE](https://landing.google.com/sre/books/) )。

从广义上来说， [SRE 与 DevOps](https://content.pivotal.io/intersect/scale-and-velocity-are-driving-the-next-generation-of-devops) 相关，因为可靠性工程师将软件工程的原则和实践应用于操作任务。有时，他们可能会提供新的基础架构，如存储、备份系统或负载平衡。他们的主要关注点是可靠性——确保开发人员部署应用的系统和平台尽可能地可用、可扩展和高效。

然而，SRE 与 DevOps 的不同之处在于，sre 并不嵌入产品团队。相反，他们同时服务于多个产品团队。但与旧的集中模式不同，他们通过交付可由多种产品消费的解决方案和服务来实现这一点。通常，他们的工作是找到将现有解决方案应用于新问题的方法。

这个难题的另一部分是“[平台作为产品](https://content.pivotal.io/blog/in-2019-put-a-platform-as-a-product-strategy-in-place)的概念在这个模型中，可靠性工程师专注于交付一个平台，开发团队可以在这个平台上构建和部署他们的软件。他们通过考虑他们的产品的平台来做到这一点，就像其他团队生产产品一样——只是在这种情况下，他们的“客户”是其他内部开发团队。

这一概念的关键是，该平台不能一刀切。像其他现代软件一样，平台必须以连续、迭代的方式交付，不断响应开发人员-客户的需求。

## 最终结果

如果您现在还没有猜到，DevOps 自助服务出现的核心主题是自动化。我们的目标是让尽可能多的手动流程实现自动化，这有两个主要原因。

首先，自动化使可靠性工程师能够有效地工作。在 DevOps 模式中，嵌入式操作工程师通常在等待新版本发布时无所事事，而自动化则允许可靠性工程师以高效且同样重要的标准化方式为多个产品团队提供服务。

第二，自动化操作允许开发团队在他们想要的时候得到他们想要的。就像日本的无人便利店一样，他们可以请求所需的工具、基础设施和服务，最有可能的是通过某种类型的服务目录，而不会给运营工程师造成积压。当这些请求以标准化、自动化的方式处理时，基于云的、面向所有人的免费自助服务的混乱局面就可以避免。

如果您认为实施这些实践听起来像是对传统 IT 操作的重大改革，那么您没有错。这种对自助服务的需求实际上只是数字化转型需求的一种基层表现，这一次不是来自首席信息官的办公室，而是来自产品团队本身。

通过认识到这种需求并采取行动，自助服务不仅可以成为数字化转型的结果，还可以成为数字化转型的驱动力。越来越多渴望现代化的 IT 和 DevOps 组织可能会发现他们的盟友比他们想象的要多。

## 会面和协作

了解更多和探索这些概念的一个地方将是 Pivotal[spring one Platform 2019](https://springoneplatform.io/)大会。精选演讲包括“[更多开发人员，没有问题:支持自助访问 Kubernetes](https://springoneplatform.io/2019/sessions/more-devs-no-problems-enabling-self-service-access-to-kubernetes) ”和“[企业中的大规模 K8s:通过角色视图自助服务](https://springoneplatform.io/2019/sessions/k8s-at-scale-in-the-enterprise-self-service-through-the-view-of-personas)”等等。会议于 10 月 7 日至 10 日在奥斯汀会议中心举行。

特写:尼尔·麦卡利斯特

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>