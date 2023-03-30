# 微服务:入门时的四个基本清单

> 原文：<https://thenewstack.io/microservices-four-essential-checklists-getting-started/>

微服务本可以赢得 2014 年的年度流行语。关于这个主题，网上有无数的演讲、会议讨论和文章。然而，很少有组织使用微服务，许多人都在谈论它，但 FUD 仍然是人们如何感知和采用这项技术的云。

耐克、网飞和 Twitter 等公司率先采用微服务。去年，在 AWS re:Invent 会议期间，耐克的故事被广泛分享和引用，作为企业潜在颠覆性技术的一个例子。

[https://www.youtube.com/embed/h30ViSEZzW0](https://www.youtube.com/embed/h30ViSEZzW0)

视频

尽管如此，采纳者们一直在大声声明:使用微服务并不能立即解决单一应用程序的问题。然而，随着时间的推移，微服务的采用确实提高了组织的效率，允许比以前更快的交付和反应。

微服务需要纪律、新的工具集和涵盖组织所有方面的团队动态变化。一些值得探索的参考资料包括[马丁·福勒的微服务](http://martinfowler.com/articles/microservices.html)、[弗雷德·乔治的 Slideshare](http://www.slideshare.net/fredgeorge/micro-service-architecure) 和萨姆·纽曼的“[构建微服务](http://shop.oreilly.com/product/0636920033158.do)”。

我想看一下四个基本清单，它们帮助我驾驭了这一技术趋势，并在考虑采用微服务时提供了有用的指导。有一些与单片应用程序相关的常见症状可能会触发微服务的采用，我将它们称为“基本单片讨厌列表”查看是否可以在您的项目中找到其中的一些:

## 清单#1:基本的单一憎恨列表

1.  团队对某项技术的决策畏缩不前(这是应用程序中大多数问题的起因)。)如果在此阶段发生技术变更，可能会导致更多的回归时间并影响业务；因此，避免了技术的改变。
2.  当进行持续集成和变更部署时，团队等待大型单元的部署。这延迟了反馈并导致计划的延迟。
3.  渐进的设计变更被推迟，以利于特性的推出，因为设计变更需要与架构师和产品经理进行更多的协调。
4.  一个新团队需要很长时间才能适应并开始为现有的代码库做出贡献。这减缓了团队轮换，并导致对现有团队成员的强烈依赖。
5.  当推出一个变更时，必须集合多个团队来确保变更不会破坏上游或下游的系统。这导致了许多会议、长时间的决策以及最终延迟交付商业价值。
6.  系统某个部分的故障会导致整个应用程序的降级，从而导致停机。这些故障很难识别和隔离。这将导致整个系统衰退，而不是部分可用的系统，因为故障不能局限于系统的一个功能或方面。
7.  部署在云平台上的应用在处理云实例故障时，会产生更高的运营成本和系统设计复杂性。这导致对云平台普遍缺乏信心，并最终导致技术团队在考虑云部署应用程序时意见不一。

为了处理这些症状，我们需要一个更加模块化的系统，它是松散耦合的，可以部分地更改或维护，以防止故障期间的停机。微服务提供了实现这一目标的方法，基于大量成功采用案例的描述，出现了一些常见的模式。我称之为“必备微服务”

## 清单 2:必备微服务

1.  最好从少量粗粒度但自包含的服务开始。随着时间的推移，随着实现的成熟，可能会出现细粒度的实现。
2.  微服务引入了许多以前在单片系统中不存在的移动部件。因此，与整体应用相比，初始资本支出相对较高。
3.  对于在单片集成电路方面有丰富经验的开发人员、操作人员和测试人员来说，基于微服务的系统是一个新的现实；因此，他们需要时间来适应这种新的转变。重要的是不要操之过急——给团队足够的时间来加速。
4.  服务组合可能基于多种因素:几乎没有共享功能的自包含业务功能、使用的技术或需要使用的集成端点。
5.  需要添加到堆栈中的强制工具集:粒度监控、日志聚合和仪表板、应用程序指标、自动化部署和系统仪表板。
6.  需要逐步改变团队结构和动态，需要团队中更多的所有权和跨职能技能。不再有开发人员、QA 人员、运营孤岛…
7.  需要标准化的服务模板，为开发提供样板。这将减少开发团队的开发喋喋不休和初始加速时间。此外，它将为 ops 团队引入标准化。
8.  不要马上放弃这个单一的应用程序。取而代之的是，让它与新的微服务共存，并在单块应用程序中反复摒弃类似的功能。

上述清单清楚地表明了微服务采用的底线。这并不容易，需要对人员和流程进行大量投资。与任何技术一样，最好避免大爆炸式的方法，并在一头扎进去之前找到让你的脚趾弄湿的方法。

我已经确定了一些快速成功的清单，这将使一个组织开始起步，同时避免大爆炸的方法。我称之为“基本微服务启动器”

## 清单#3:基本微服务启动器

1.  确定必须添加到整体应用程序中的新特性，并将它们开发为微服务。或者，如果不能识别新的特性，最好替换掉单一应用程序中“不太关键”和更“独立”的特性
2.  就单片应用程序和新微服务之间的标准通信接口达成一致。
3.  新的微服务需要是自包含的，因此必须有自己的运行时环境。该服务还需要部署在独立的基础设施上，该基础设施在物理上或逻辑上与整体应用程序隔离。
4.  指派一个管理团队，负责微服务的开发、维护和操作，该团队独立于管理整体应用程序的团队。该托管团队必须是跨职能部门的，并且必须对这些服务拥有完全的所有权。
5.  如果单片中的现有功能被新的微服务取代，那么单片必须被改变以适应功能切换。可能有必要让同一功能的多个版本共存于旧的功能整体版本和新的微服务中。特性切换将允许在使用新服务和单片应用程序中的现有代码之间进行切换。这很有用，因为您可能希望有一个后备，并安排一个优雅的负载切换到新服务。
6.  创建一个服务样板作为开发和部署新服务的模板。这个服务样板应该封装支持基于微服务的系统所需的公共成分:监控、日志收集、度量和安全机制(比如超时、断路器)。这个服务样板必须考虑多语言技术，包括应用服务器、数据库、编程语言等…
7.  同意构建更活跃或更频繁使用的粗粒度服务，而不是一堆细粒度服务。粗粒度服务将减少整体应用程序和微服务之间的网络调用。一般来说，服务规模选择就是在决定粒度时，在系统中选择适当的折衷方案。

这些想法将允许一种安全的方式来试验微服务和增强现有的单片应用程序。另一个想法是，在采用微服务架构的最初几周，强制要求所有非关键服务都基于微服务架构。这个想法是给这个新的范例时间来适应组织内部，并让团队能够应对运行混合模型的挑战。随着使用这些服务的团队逐渐成熟，关键功能可以通过完全构建为微服务来实现。

任何技术的采用都有缺陷，微服务也是如此。当处理将单片应用程序迁移到基于微服务的架构时，这一点更加明显。在我的“基本微服务陷阱”列表中，我捕捉到了其中的一些问题

## 清单 4:基本微服务陷阱

1.  服务蔓延，需要对各种活动服务及其特定版本进行适当的簿记
2.  处理不再使用的失效或过期的服务和端点，并使用该信息淘汰适当的服务
3.  在特定微服务中进行更改后执行集成测试
4.  开发运维活动在传统上反对开发运维的团队中成为主流
5.  确定合适的服务规模——既不太大也不太小
6.  投资重写服务或划分现有服务

以上大部分问题很大程度上是传统的软件开发整体思维的错误。有一些可用的工具和实践可以处理大多数问题，并为开发创建一个可持续的环境。

当您选择开始试验微服务的各个阶段时，上述基本清单是一个很好的开始反思您所处位置的地方。像所有诞生时的技术趋势一样，微服务正处于大规模采用的早期阶段，随着围绕它的文献越来越多，它将很快在企业 it 中变得司空见惯。

Vivek Juneja 是首尔的一名工程师，他专注于云服务和微服务。他于 2008 年开始从事云平台工作，是 AWS 和 Eucalyptus 的早期采用者。他还是一名技术布道者，在印度的各种技术会议上发表演讲。他写过@ www.cloudgeek.in 和 [www.vivekjuneja.in](http://www.vivekjuneja.in/) ，热爱梳理技术社区。你也可以通过电子邮件联系到他:vivekjuneja@gmail.com。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>