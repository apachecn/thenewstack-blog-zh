# 微服务之路:做好准备，提出问题

> 原文：<https://thenewstack.io/path-microservices-getting-ready-asking-questions/>

这篇文章是探索微服务基础的系列文章的第二篇。请每周一回来查看更多的分期付款。

云原生微服务是真正令人兴奋的架构发展，尤其是在构建、部署和管理复杂的分布式解决方案方面。然而，围绕[微服务](/category/microservices/)的大部分讨论都直接指向技术:持续集成和部署、容器、编排器等等。重要的东西，但是还有其他的东西要考虑:

一旦您的组织决定微服务是您项目的正确架构，那些有实施经验的人会强调，问一问同样重要:我们是微服务架构的正确组织吗？

## 你必须这么高才能骑微服

专家表示，评估企业采用云原生微服务与公司的规模、行业甚至实际技术的关系更小，而与企业本身的关系更大。

[Jamie Dobson](https://twitter.com/jamiedobson?lang=en),[Container Solutions](https://container-solutions.com/)的联合创始人兼首席执行官认为，架构的成功实施在很大程度上取决于企业的文化和内部流程。“客户来找我们，希望使用微服务作为技术问题的解决方案，”他说。"实际上，它通常是组织问题的技术解决方案."

他继续解释说，微服务的基本复杂性在于架构本身，而不是计算机。并不是每家公司都处于合适的位置来进行这一转变。“企业中充满了充满智慧和创造力的高管，他们热衷于微服务，部分原因是谷歌和网飞等公司都在这么做。而且好处是实实在在的。但很难理解微服务本身，以及云迁移所需的组织转变，”他说。“当一家专注于云迁移和供应商中立的优秀专业服务公司变得非常有价值时，引入这种理解就变得非常重要。”

有一些场景可以表明，公司在考虑微服务迁移时可能会面临特殊的挑战。专家强调，这并不是说采用这种架构变得不可能，只是这个过程会更长或更复杂。

那么什么时候企业可能不适合微服务呢？

*   **行业敏感性**:某些行业，例如金融服务和医疗保健，面临着需要与新技术相协调的法律、报告和合规性要求，或者可能根本就没有跟上。
*   **脆弱性因素**:一家经营了几十年的全球性公司，尤其是一家平均员工保留时间超过十年的公司，很可能比一个更年轻、更紧凑或更敏捷的组织更难驾驭向全新架构的巨大转变。
*   **【停滞不前】的公司**:多布森描述了一种“停滞不前”的公司文化，即厌恶风险，有很长的决策链和严格的等级制度。最终，一个组织不太适合，甚至可能抵制采用新的响应性微服务范式时所需的快速适应。

多布森说:“企业的固有结构和组织将极大地影响所做的选择，从而影响转变为有利于微服务的环境的能力。”

## 微服务真的是最适合的吗？

一旦您的公司准备就绪，您如何评估您的特定应用程序是否真的会从微服务的诸多优势中受益？

现任 [Netlify](https://www.netlify.com/) 、[的 CTO David cala vera](https://www.linkedin.com/in/david-calavera/)之前曾在 [Docker](https://www.docker.com/) 和 [GitHub](https://github.com/) 从事微服务架构工作，是这种新技术领域的老手。根据卡拉维拉的说法，第一步是评估应用程序已经或将要承担多少责任。接下来是确定这些责任之间的相互联系。

Calavera 说:“评估应用程序组件互连程度的最佳指标叫做[相关性](https://en.wikipedia.org/wiki/Connascence)。如果当你改变其中的一个时，你也必须改变另一个，那么两个或更多的元件被称为共相。

“考虑到这种关系，你可以更好地评估是否值得拥有不同的微服务，或者你应该保留你的整体架构，”卡拉维拉解释说。此外，他说，团队必须记住，将这些组件分成微服务将在它们之间引入网络连接——这不可避免地增加了系统的复杂性。

“你不想以牺牲一个理想的架构为代价，最终增加不必要的复杂性，”卡拉维拉提醒道，并指出他的同事戴夫·切尼的智慧:

https://twitter.com/davecheney/status/967678947172409344

## 准备，稳定…开始？

在确定您的组织本身非常适合向微服务转变，并且您的项目或服务将受益于该架构之后，剩下一个问题:您如何确定您是否已经准备好以这种方式构建应用程序？

根据 Calavera 的说法，需要考虑的关键问题是，您的团队是否准备好处理在生产中运行多个服务而不是一个服务的额外复杂性。“这种复杂性将影响你的团队习惯的所有过程——从你在你最喜欢的版本控制系统中组织你的代码的方式，到你部署你的应用程序的方式，到你在生产中观察和监控它的行为的方式，”他说。

卡拉韦拉总结道，一旦你确定并评估了生产服务的开发、测试和维护所涉及的每一个流程，并准备好了调整或替换它们的具体答案，“你就可以开始认为自己准备好了。”

## 起飞准备

最好的过渡可能是用户永远不会注意到的。除了对现有能力进行诚实的评估之外，团队还能做些什么来为成功迁移的最平稳进展做好准备呢？

专家们一致认为，归根结底，没有那么多:变量实在太多了。

“不幸的是，很难为所有可能的情况做好准备。卡拉维拉说:“当我们谈到通过网络互连的分布式系统时，情况尤其如此。因此，微服务迁移总是计划分阶段进行。

卡拉韦拉说:“出于安全和安保原因，完全跳到微服务是不明智的——当过渡到不同的架构时，请始终记住，保持完整的服务正常运行是您的首要任务。”

实现这种过渡的最佳方法是在迁移的安全性和有效性之间找到平衡。这也被称为[效率-彻底性权衡](https://en.wikipedia.org/wiki/Efficiency%E2%80%93thoroughness_trade-off_principle)(或 ETTO)原则。

“一方面，我们需要确保过渡是完全安全的。迁移过程中的错误可能会导致严重的停机，”卡拉维拉说。“另一方面，无论您对这种迁移做了多少计划，了解它是否有效的唯一方法是将其暴露在生产的复杂性中。”

幸运的是，以前的朝圣者帮助准备了道路，其中主要的是[马丁·福勒。](https://martinfowler.com/)有几种微服务架构模式，它们结合在一起有助于创建一个平稳的流程。简而言之，这些是:

**断路器**模式:[断路器](https://martinfowler.com/bliki/CircuitBreaker.html)对于在发生意外情况时中止代码执行非常有用，例如当网络瘫痪，两个微服务无法相互通信时。

“这种模式迫使我们思考在那种情况下该做什么，并且有几个库用不同的语言实现了这种模式，”卡拉维拉说。

**抽象分支**模式:一种逐步对软件系统进行大规模变更的技术，[抽象分支](https://martinfowler.com/bliki/BranchByAbstraction.html)允许您在变更仍在进行的时候定期发布系统。

“这有助于引入替代逻辑来执行操作，”卡拉韦拉解释说。“在这种情况下，替代逻辑可以是向微服务发送消息，而不是使用我们当前应用程序的逻辑。”有几个库用不同的语言实现了这个模式，包括 [Go](https://github.com/calavera/go-scientist) 和 [Ruby](https://github.com/calavera/scientist) 。

**特性标志**模式:也称为[特性切换](https://martinfowler.com/articles/feature-toggles.html)，它们能够实时改变应用程序内的执行路径。“我们可以实现一个标志，允许我们向我们的新微服务发送一些流量，但不是全部，”卡拉维拉说。同样，存在用不同语言实现这种模式的多个库。

为了观察系统在转换过程中的行为，他补充道，“所有前面提到的库都有某种类型的支持来发出事件、日志和度量，我们可以将它们提供给我们最喜欢的监控系统。”

最重要的是，可以将这些模式结合起来创建一个系统，为过渡到微服务架构提供重要的控制。例如:通过将抽象分支与断路器相结合，可以实现允许将流量导向新微服务的更改，但如果断路器因意外错误而跳闸，系统将退回到旧的应用程序逻辑。

这条路是步行走出来的。

接下来:是时候卷起袖子开始工作了。新堆栈的微服务入门系列的第 3 部分将详细介绍入门！

由 [Adrien Tutin](https://unsplash.com/photos/x8xJpClTvR0?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/search/photos/path?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>