# Spectre 和 Meltdown 对云的影响

> 原文：<https://thenewstack.io/impact-spectre-meltdown-cloud/>

[](https://www.heptio.com)

 [克雷格·麦克卢奇

克雷格是 Heptio 的创始人兼首席执行官，hept io 是一家专注于让生活在云计算世界中的企业能够访问 Kubernetes 的初创公司。在创办 Heptio 之前，Craig 是谷歌的一名产品经理，在那里他创建了 Kubernetes 项目，并与业界合作创建了云原生计算基金会，他也是该基金会的主席。](https://www.heptio.com) [](https://www.heptio.com)

随着两个新的安全漏洞的发布，新的一年有了一个有趣的开始:Spectre 和 Meltdown。最近的研究表明，在过去 20 年中制造的几乎每一个计算机处理器都包含这些基本的安全问题，它们代表了一类世界上从未见过的可被广泛利用的漏洞。大大小小公司的 IT 和安全专业人员都在努力理解这对他们的业务意味着什么。这些问题本质上相当深奥，但却是一个非常真实的威胁。

本文将为这些问题提供一些基本框架。这里的重点不是威胁本身，而是这种新的安全漏洞意味着什么，以及如何开始考虑它，因为它涉及到您的业务，尤其是您的托管环境。可以肯定地说，一些最大的长期影响可能是对云计算架构、成本和安全实践的影响，但这是迄今为止很少有人公开讨论的威胁的一个方面。

## 熔毁和幽灵问题的背景

多年来，科技行业一直在谈论处理器“旁道”攻击。这指的是以前主要是理论上的想法，即你可以编写一段非常安全的代码，但其他心怀不轨的人可以利用运行代码的底层处理器的问题来访问你的信息。

我们现在生活在这个世界上。Meltdown 展示了一种利用底层处理器架构问题的实用方法，Spectre 提供了第二条潜在的途径。

这两种利用都依赖于现代处理器使用的令人难以置信的智能优化算法来做一些他们可能不应该做的偷偷摸摸的事情。这些漏洞依靠这些算法近乎“千里眼”的尝试来预测接下来会发生什么。从处理器的角度来看，这有可能使您的代码运行得更快；对于漏洞，它允许访问他们不应该访问的内容。

在崩溃的情况下，解决这个问题的唯一方法是积极地“解谐”代码，并迫使处理器正确运行。在幽灵事件中，我们还不知道如何减轻它。

## 这有什么大不了的？

崩溃是相当糟糕的，但我们理解它，并有适当的缓解措施。通过改变操作系统，我们可以在事情如何运行方面创造更多的确定性，并确保漏洞不存在。然而，没有人对这种缓解会对性能产生重大影响感到满意。实际的里程数会有所不同，但在一些非常糟糕的情况下，它可能会使代码运行速度降低 30%甚至更低。不管怎样，关键是漏洞被理解了，缓解措施也到位了。这当然感觉像是另一个令人心痛的问题——在许多方面确实如此——但商业是可以适应的，我们会解决这个问题。

> Meltdown 和 Spectre 迫使聪明人真正退后一步，重新思考事情。它侵蚀了人们对系统的信任。

幽灵更糟。不是因为我们知道如何用它来做坏事。还没有。更糟糕的是，我们不知道如何用一种通用的方式来减轻它，因为它证明了熔毁不是昙花一现。威胁依然存在，并侵蚀信任。如果有人设计了一个实用的漏洞，我们确实可以看到它的缓解迅速出现。像谷歌这样的公司的安全研究人员可能会负责任地披露这种利用。但完全有可能的是，敌对的国家行为者会抢先一步，从现在到那时所造成的损害可能相当大，而且难以量化。

作为一个在这个行业工作过一段时间的人，这感觉是一个分水岭时刻。《幽灵党》的寓意并不会让人联想到一场令人心痛的事件。这感觉更像是爱德华·斯诺登披露政府监控的性质和形式时发生的事情。它迫使聪明人真正退后一步，重新思考事情。它侵蚀了人们对系统的信任。

## Spectre 和 Meltdown 如何影响云计算

这在很多地方都有问题。这些挑战不仅存在于我们熟悉和喜爱的英特尔处理器中，也存在于不同处理器架构的范围内。对移动和客户端设备安全的影响可能是深远的。然而，我所在的领域是 IT 基础设施的“幕后”世界，这些利用将面临挑战的最大领域是云计算。

云本质上是多租户的(意味着价值在于与其他人共享相同的资源)，这很可能是那个世界中认知失调的主要来源。

**影响云计算的内在弹性。**云的大部分价值主张都基于云资源的共享特性，以及按需使用这些资源的能力。它允许组织更加动态地运作。基础设施已经从固定资产转变为动态公用事业；亚马逊的领先计算产品被称为“弹性计算云”并非偶然过渡到一个客户需要与潜在的敌对行为者进行严格隔离的世界确实是一个挑战。

随着对安全性的日益关注，我们很可能会看到许多企业的基本消费单元从“虚拟机”转向“完整的服务器”虚拟机仍然是可访问的，并且是运行工作负载和分配单个提供商所消耗的工作的主要方式，但是扩展单元将变得更加粗糙。

今天，一些云产品已经为高度敏感或受监管的工作负载考虑到了这一点，但这很可能成为旁路攻击感知世界的规范。这将给云提供商的运营效率带来压力，因为他们正在努力重组产品以满足这些需求。随着时间的推移，随着整体利用率的下降，这很可能会推高成本。

**云提供商的准入门槛提高。**如果有什么不同的话，我们很可能会看到围绕“三大”云提供商的更多整合。面对虚拟机在何处运行的问题，保持灵活性，同时管理配置完整服务器的更大复杂性，将变得越来越具有挑战性。较小的云企业，无论是在特定地区运营，还是专注于利基应用，都将难以做出同样的调整，并可能会看到对其产品的信任度下降。

虽然总体而言，旁门左道攻击的出现可能会在某种程度上打击企业对云的兴趣，但它也可能会提高有意者的准入门槛，并巩固“三大”云提供商的地位。

这在网络边缘可能更具挑战性，因为那里的整体资源池更小。在更小的本地设施中运行更接近用户的计算工作负载有着巨大的潜力，在这些环境中需要注意确保工作负载的充分隔离。

**代码级保护。鉴于这些漏洞的性质，编译后的二进制文件——被渲染成最低可能形式的机器代码块——变得很可怕。它相对不透明，对于云提供商来说，审查漏洞利用具有挑战性。更高层次的服务包括编译过程，将开发人员编写的代码转换成机器可读的东西，为组织提供了确保不会发生任何意外的方法。**

亚马逊的 Lamba 或 Azure 的功能服务可以用来增加额外的安全措施。通过查看代码，并控制编译过程，这些服务可以变得更加安全，并保持云的灵活性。具有讽刺意味的是，由于 Spectre 和 Meltdown 等漏洞的利用，我们可能会更加重视这些特定类型的高度多租户服务，因为它们可以比在不受控制的环境中运行不透明的二进制文件更安全。

**加强对云提供商实施的审查。**这些安全漏洞的出现带来的另一个影响是，有前瞻性的组织将会加大对云提供商运营方式的审查力度。如果相邻的客户工作负载共享一个处理器，那么不仅相邻的客户工作负载容易受到这些漏洞的攻击，而且运行在相同服务器上的所有其他东西也会受到攻击，从而将它们整合到云提供商的基础设施中。这可能会增加对云提供商额外审计和审查的需求，并可能进一步减缓或抑制云的增长速度。

## 展望未来

看看侧信道攻击的未来会是什么样子，确实会很有趣。既然这种新型的利用方式已经引起了人们的关注，那么可以肯定的是，安全研究人员将会使用更加强大的工具和能力来发现类似的威胁。

我对企业的建议是继续他们的云计算之旅，但是如果需要的话，保持选择在内部运行。现在专注于避免深层次的特定于提供商的锁定，因为我们还不完全知道事情会如何发展，以及在可能的情况下从不太敏感的工作负载开始(这总是明智的)。其中很大一部分将是真正理解工作负载的安全敏感性，并仔细考虑风险容忍度。一刀切的计划可能不是最佳的。

我还主张适度的怀疑，不管是来自那些哭喊天要塌下来的人，还是来自那些说一切都好的人。业界真正理解这一新趋势的含义还需要时间。这些影响很可能是重大的，但我们必须自我教育，花时间真正理解威胁和影响。

由 [Johannes Plenio](https://unsplash.com/photos/GmBT6GQEOs0?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/search/photos/storm?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>