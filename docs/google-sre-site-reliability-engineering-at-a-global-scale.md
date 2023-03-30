# 谷歌 SRE:全球范围的网站可靠性工程

> 原文：<https://thenewstack.io/google-sre-site-reliability-engineering-at-a-global-scale/>

当 [DevOps](/category/devops) 在 2009 年左右诞生时，其目的是打破开发和 IT 运营之间的孤岛。DevOps 已经成为运营团队的可靠性需求和开发人员的速度目标之间的拔河游戏。[网站可靠地工程](https://thenewstack.io/the-evolution-of-the-site-reliability-engineer-sre/)成为了平衡器。

正如谷歌 SRE 项目的设计者本杰明·特雷诺·斯洛斯所说:“当你让一个软件工程师设计和运行操作时，就会出现 SRE。”

SRE 团队已经成为如何大规模构建系统的答案，实现了速度、可维护性和效率之间的平衡。

今年的 [DevOps 企业峰会](https://events.itrevolution.com/)想要邀请谷歌 SRE 领导层来剖析谷歌是如何运作的，这是唯一合乎逻辑的。毕竟，拥有超过 20 亿行代码的谷歌生产环境是有史以来最复杂的集成系统之一。它的互联性和正常运行时间为 DORA metrics 设定了标准，但也带来了全球范围的挑战。它写了关于现场可靠性工程的[书](https://sre.google)。

当然，谷歌之外的几乎所有人可能都不会从事这种规模的工作，但是，由于越来越多的分布式系统不断与其他系统集成，随着复杂性的增加而扩展的挑战是普遍的。解决这些问题的方法也是如此。

## 一个团队统治他们，但不是统治

谷歌的网站可靠性工程团队被视为一个中央有机体，横跨内部网络和开发工具，以及面向客户的工具。每个服务生命周期阶段都有不同的需求，SRE 项目的类型也各不相同。

“它们的共同点是都围绕着 SRE 的任务:可靠性、速度、可维护性和效率。和一套共同的原则，”谷歌 SRE 项目工程负责人 Christof Leng 博士说。他在慕尼黑领导三个横向的 SRE 团队，并负责维护谷歌的 SRE 参与模式，即围绕 SRE 和开发者协作的政策和原则的集合。

谷歌有 3000 多名工程师，分属于不同的产品领域，每个领域有 50 到 300 名工程师。这使得它成为世界上最大的，如果不是最大的*SRE 团队的话，也是最大的团队之一，然而它仍然比开发团队小得多。冷说，这让 SREs 专注于他们的核心任务。并且它限制了开发人员可以卸载到 SREs 上的工作量。*

此外，SRE 的支持不是自动的，也不是对谷歌的所有开发团队都是如此。SRE 仍然是一种有意的稀缺资源。SRE 团队由开发团队资助——由总监或副总裁决定——每个团队至少由六名 sre 组成。开发和 SRE 团队必须同意开始一个约定，任何一方都可以结束它。但它通常是长期的。

“生产卓越是一项多年的投资，因此不会孤立地考虑参与，而是在 SRE 产品领域的水平上，”谷歌 SRE 教育总监、[原版 SRE·奥莱利指南](https://sre.google/sre-book/table-of-contents/)的合著者詹妮弗·佩托夫博士解释道。

“建立对团队所负责的服务的深刻理解需要时间。”

## 谷歌 SRE-开发者关系的具体范围

虽然管理服务是一项具有共同目标、服务水平目标和错误预算的共同努力，但 Petoff 指出，尽管日常生产由 SRE 团队负责，但最终正常运行时间和可用性责任由开发团队承担。

“提供可靠服务的责任不是卸到 SRE 上，也不是扔到围栏外。SRE 的工作是帮助开发团队实现他们的可靠性和速度目标，并首先满足我们用户的需求，”她说。

事实上，SRE 团队能参与什么，不能参与什么，这一点非常清楚。谷歌 SRE 团队只能从事某些项目——待命团队的存在并不被视为正当理由。他们只能比其他人更有效率地做他们能做的事情。如果开发人员可以做到这一点，这应该仍然是一个开发人员人数。

谷歌 [SRE 参与模式](https://sre.google/sre-book/evolving-sre-engagement-model/)仅涉及生产，包括:

*   系统架构和服务间依赖关系
*   仪器、指标和监控
*   应急响应
*   容量规划
*   变更管理
*   性能—可用性、延迟和效率

根据设计，SREs 的工作也必须“对 SRE 团队来说是有趣的、有影响力的和具有挑战性的”，Petoff 说。这不是放弃传呼机的职责。“SRE 不会成为行动小组的成员。我们的任务不是处理操作，而是通过工程改进系统的固有可靠性。”

SRE 团队的目标是通过回答什么出了问题、如何修复以及如何确保问题得到永久修复来减少运营工作量。

对于 sre 来说，总有比时间更多的工作要做，所以他们所有的工作都应该有一个明确的范围和联系，以支持用户。用户可能看不到这些好处，如基础设施更新，如向标准平台聚合以提高功能速度。标准化还通过减少认知负荷使 SRE 团队受益。

最后，SRE 的一个重要角色是教师，传授生产知识。佩托夫说，这是防止 SRE 团队成为生产中的人类抽象层的唯一方法。“你不能建一堵墙，然后抱怨一种‘把它扔过墙’的心态。”

## 谷歌 SRE 在实践中是如何运作的

是的，SRE 团队可以在应用或服务生命周期的任何阶段加入开发团队。但是它们从一开始就是最有效的，当你向左移动时带来了可靠性。

冷说，在设计阶段，“你做出了许多难以置信的困难或实际上不可能改变的决定——架构、技术、故障转移能力。”他继续说，“当生产专家在会议上有发言权时，你可以在问题实际发生之前解决它们。”

然而，这种情况并不常见。例如，[SLO](https://thenewstack.io/automate-user-satisfaction-with-this-gitops-friendly-spec-for-service-level-objectives/)通常在实现完成后才讨论，但是已经选择的架构应该扩展到预期的 9。否则，要么整个系统不得不重新设计，以免让用户失望，要么你走了另一条路，投资于过于复杂的架构，以至于无法满足用户的需求。

也不是每个 SRE 项目都是一样的。Leng 将其分为三个按需类别，涵盖了人员预算和项目时间承诺:

*   基线支持—战术性和反应性的临时支持，如办公时间或咨询项目，开发人员根据收到的建议执行，或在大规模停机时作为事件响应团队的一部分
*   协助参与——SRE 提供战略性、前瞻性、以产品为中心的咨询服务，拥有专门的 SRE 联系人和共享的生产路线图；这可以是一个临时嵌入到关键产品开发团队中的 SRE，而 SRE 可以是一个力量倍增器
*   全力支持— SRE 是生产的实际所有者，随叫随到，解决不太明显和复杂的生产问题—目标是 SRE 在 18 个月内自动完成工作。

“越高不一定越好。它的成本更高。尤其是在生命周期的早期阶段，变更率很高，较低层次的参与可能更有效。”冷说，约定可以随着时间的推移而扩大或缩小，但不是所有的服务都需要这样。

一切都因情况而异。如果一个 SRE 团队专注于核心基础设施，他们可能会为一些不同的项目提供全面的支持，但是如果他们正在进行早期的实验性项目，他们可能会进行几个基线项目。

## 当事情出错时

仅仅因为它是谷歌，并不意味着它是完美的……[无论如何](https://thenewstack.io/alphabet-workers-union-tests-the-appetite-for-tech-industry-unionization/)。但是，谷歌网站可靠性参与模型希望最好的情况，并为最坏的情况做准备。这可能是任何事情，从操作过载到对开发人员不再做他们该做的事情的方向不一致。

这是他们在战略层面应用事件管理最佳实践的时候。从寻找根本原因开始。开始[寻求开发合作伙伴和关键依赖方的认同](https://thenewstack.io/how-engineering-leaders-drive-cross-functional-collaboration/)。如果无法达成一致，请向开发和 SRE 管理链上报。然后宣布“黄色代码”——解决问题所需的工作胜过所有其他项目工作。

当所有这些都失败时，不要做英雄，不要做一个永远的消防员——要意识到什么时候是时候交出你的呼机了。但这没关系，因为冷说，谷歌的服务工程师之间的流动性通常非常高。

“这不是通常会发生的情况。每个人都明白 SREs 也需要保持快乐，你不能把他们扔到公共汽车底下。开发商也明白他们从中获得的价值，”冷说。

最后，正如他对同事们说的，“无论你做什么，记住英雄主义是不可持续的。你不能永远不生产。你也不能没日没夜地工作，这是不可持续的。通过智能工程解决问题，而不是蛮力。”

团结就是力量。分裂你会堕落。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>