# 微服务定价:全部成本是多少？

> 原文：<https://thenewstack.io/microservices-pricing-whats-it-all-going-to-cost/>

随着企业引入容器和微服务来更新其 IT 基础架构，他们在部署和开始使用它们时想知道的一件事是，将微服务添加到组合中需要多少成本。

不过，到目前为止，提前计算出这些成本被证明是一个挑战。这在很大程度上是因为成本在很大程度上取决于企业想要做什么、他们现有的基础架构是如何构建的，以及将影响最终成本和估计的无数其他问题。

然而，计算出微服务从集成到运营的成本，对于确定它们是否值得，以及计算出它们是应该用于迁移现有应用程序还是构建新应用程序至关重要。

为了尝试完善围绕微服务的定价可能性，New Stack 与几位 IT 顾问、行业分析师甚至一些微服务公司进行了交谈，以获得一系列关于企业如何尝试评估该技术的长期使用成本的建议。

甚至他们也承认在这一点上他们没有所有的答案。

Kubernetes 集装箱集成供应商 [Heptio](https://heptio.com/) 的首席技术官和联合创始人[乔·贝达](https://twitter.com/jbeda)说:“我不认为任何人已经把这归结为一门硬科学与金钱数字”。

## 为什么微服务值得令人头疼的定价问题

微服务的吸引力在于，它们可以简化试图对由各种组件、技术和应用程序构建的庞大、笨重的整体 IT 系统进行更改的复杂问题。通过使用容器和微服务将单块系统中的服务和流程分割开来，较小的应用程序组件可以独立运行，自给自足，允许它们在不影响其他相关代码的情况下使用。通过使用微服务，IT 管理员不必担心现有架构变更带来的问题，因为变更仅发生在较小的子系统或容器中设置的微服务内部。

总部位于英国的云咨询公司 [Amido](https://amido.com/) 的高级顾问 [Chris Priest](https://twitter.com/cjrpriest) 说，这也是很难量化成本的原因。“这在很大程度上取决于你在做什么，”他说。“微服务的持续成本远低于整体式系统。我认为你的成本可以轻松降低 90%。这要看一开始有多糟糕。”

Priest 说，但是节省不仅仅来自于使用诸如 Kubernetes 这样的容器系统。这种节约也来自于开发者文化的改变。

他说，有了单一的基础设施，一家公司可能会有 100 名开发人员在同一代码上工作，这可能是一场噩梦，因为他们的变化与其他人的变化不一致，增加了复杂性和问题。但在微服务方法下，开发人员可以独立工作于代码的不同部分，这允许以更少的重叠和复杂性完成更多的工作，他说。

“将团队切换到微服务的工作方式，您可以获得更高的工作效率，”Priest 说，但同样，很难估计这样一个有益的举动带来的节约。

总部位于拉斯维加斯的云咨询公司 [Kumulus Technologies](https://kumul.us/) 的创始合伙人兼云顾问 Robert Starmer 表示，在尝试确定微服务成本时，可以从将微服务视为 DevOps 的一部分开始，然后分解这些成本以得出估计值。他说，从公司的发展环境开始。

“如果你已经有了容器，你应该知道你的系统如何扩展，这样可以帮助计算微服务的成本，”Starmer 说。“我们已经和几家公司合作过了。”

他说，接下来，看看每个开发人员在访问测试和开发服务器或虚拟机方面的固定成本，然后加上其他相关的开发成本。“你实际上可以对它建模，”基于应用程序的规模，有多少开发人员将致力于这个问题和其他因素。

他说，尽管如此，大多数 IT 领导最终不会采取这些措施。

“这也是人们一致认为很难说在 Kubernetes 上部署微服务的成本的部分原因，因为在应用程序规划过程中缺乏严格性，”Starmer 说。

为了帮助简化这些计算，Starmer 表示，他正在开发一种应用程序，可以在未来用于向 IT 领导者提供这种估计，因为他们看到了微服务在其运营中的好处。

[容器平台供应商 Docker 的营销总监 Suzanne Panoplos](https://twitter.com/spanoplos) 表示，使用 Docker 运行微服务的成本取决于公司服务器和计算基础设施的规模，而不是基于使用的容器数量。

“这是由客户来决定是否需要更多或更少的容器，”她说。“Docker 企业版平台在定价上与环境中运行的传统或微服务容器没有区别，因为它支持这两种应用程序类型。”

## 好建议:从小处着手

Heptio 的首席技术官兼联合创始人贝达表示，开始跟踪和评估微服务成本的另一个好方法是从小处着手，以开放的心态推进。

“中断一两个服务将有助于理解特定应用程序和环境的权衡，”他说。“正如人们所理解的那样，进一步投资微服务将变得更加合理。”

他补充说，避免创建过于微观的服务也是明智的。“每个新服务都有开销，应该考虑到这一点，并根据架构分离速度的优势进行权衡。像 Kubernetes 这样的工具可以帮助减少开销，并补充微服务方法。”他说，与此同时，使用容器平台而不仅仅是原始虚拟机也可以提高效率和降低成本。“本质上，这不是微服务，但通常与这种类型的架构搭配使用。利用率从不到 10%下降到不到 50%并不罕见。这可以通过减少硬件、数据中心或云的使用以及降低管理成本来节省大量成本。”

Beda 说，与此同时，一定要记住基于微服务的架构的成本节约优势，它允许开发人员更快地行动。“这意味着更快的应用上市时间、更快乐和更高效的开发人员，以及更好的竞争定位。”

## 向供应商索要客户证明

恩德勒集团的首席分析师[罗布·恩德勒](https://twitter.com/Enderle)说，随着这一过程的继续，不要忘记寻找传统的客户证明。

“显而易见的问题包括从供应商那里找到像你一样的客户，然后要求采访他们，从他们的经历中学习，”他说。“最终，有了微服务，IT 部门就拥有了最终的解决方案，他们既需要具备构建该解决方案的必备技能，也需要在项目失败的情况下，能够容忍除了自己之外没有其他瓶颈。”

Enderle 说，最终，当谈到正确有效地使用微服务时，它归结为 it 团队的核心技能。“如果你不知道该问什么问题，你可能不具备让微服务发挥作用所需的核心技能，如果有完整的解决方案会好得多。这让我想起了那些询问自己造车的人。如果他们有技能，他们知道该问什么问题。如果他们不这样做，一本书的问题不会让他们获得所需的技能。”

阅读本系列的下一篇文章[站点可靠性工程在微服务中的作用](https://thenewstack.io/the-role-of-site-reliability-engineering-in-microservices/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>