# 混沌工程:它意味着什么，为什么它很重要

> 原文：<https://thenewstack.io/chaos-engineering-what-it-means-why-it-matters/>

Gremlin 赞助了这个播客。

如今，混沌工程无疑引起了人们的极大兴趣，尤其是当组织越来越依赖可以跨多云和本地环境扩展的广泛分布的数据基础架构时——在这种环境中，故障风险呈指数级增长。虽然许多人同意混沌工程在某种程度上涉及规划，但一个被广泛接受的定义仍然难以捉摸。

对于首席执行官兼联合创始人[科尔顿·安德鲁斯](https://www.linkedin.com/in/kolton-andrus-77315a2)、[小妖精](https://www.gremlin.com/)来说，混沌工程“是我最喜欢辩论的话题之一”，并且“是混沌工程听起来有趣和令人兴奋的原因”

在本期 [The New Stack Makers](/podcasts/makers) 播客中，Andrus 定义了混沌工程，并描述了组织如何让它为他们服务。《新书库》的创始人兼发行人亚历克斯·威廉姆斯主持了这一集。

[Kolton Andrus，首席执行官兼联合创始人，混沌工程的小精灵](https://thenewstack.simplecast.com/episodes/kolton-andrus-ceo-and-co-founder-gremlin-on-chaos-engineering)

一想到混乱——以及 IT 组织对混乱的接受——就会让许多人产生恐惧。“[混沌工程]吓走了一些老派人士，他们对环境中的这种混乱感到不舒服。因此，大多数人认为混沌工程是随机破坏东西，看看会发生什么，”安德鲁斯说。“我认为混沌工程是深思熟虑的、有计划的实验，它让我们了解我们的系统，其中一个关键概念是‘爆炸半径’的概念。”当我们进行这个实验时，我们会影响谁？因为我们的目标是防止停机，而不是造成停机，我们也不想无意中给客户带来痛苦。我们从来不希望因为我们的方法漫不经心而导致停机。"

安德鲁斯给这场辩论带来了这个问题的深刻背景。在创立 Gremlin 之前——作为混沌工程的先驱之一——and RUS 大量参与帮助避免服务中断，首先是在亚马逊，然后是在网飞。“当停机发生时，它非常耗时且昂贵。这有损你的品牌，”他解释道。“如果你在亚马逊或网飞这样的地方工作，一次宕机会造成数十万到数百万美元的损失，因此防止每次宕机和防止每分钟停机都是值得投资的。”

虽然他在亚马逊的工作更注重基础设施，但他在网飞的任务是作为 API 团队的一部分，专注于应用程序级故障注入，包括在特定服务或功能中注入故障或延迟，如管理客户身份、推荐或最近观看的电影。

“如果其中一个失败了，会发生什么？嗯，说实话，如果我不能获得你最近观看的电影，我可能不应该让应用程序崩溃——我们可以优雅地降级，给你一个演员名单，或者只是不给你看，你可以继续，”安德鲁斯说。“所以这让我们能够非常、非常精确地了解我们想要在哪里进行这些实验。”

他解释说，网飞的一个主要收获是商业案例，比如理解客户看到了什么，以及“系统的正确行为是什么”。“然后我们可以去解决问题，这样当出现问题时，客户就看不到了，他们就可以做他们想做的任何事情。”

Gremlin 实验背后的核心技术基础设施主要依赖于其代理，而“我们要去的地方的未来”正在帮助“人们衡量他们服务的可靠性，并评估发生的潜在风险。”安德鲁斯说，Gremlin 的团队将“甚至为他们运行这些实验，并告诉他们他们的系统是否正确运行，或者给他们一组没有正确处理的事情，这样他们就有了一个需要修复和改进的事情的清单”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>