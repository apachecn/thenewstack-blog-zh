# 问与答:Eventbrite 的 Pat Poels 关于构建一个可快速伸缩的事件驱动架构

> 原文：<https://thenewstack.io/qa-eventbrites-pat-poels-on-building-a-rapidly-scalable-events-driven-architecture/>

[![](img/c462c657fed4074effb37e3e17f6bc43.png)](https://en.wikipedia.org/wiki/Pat_Poels)

Pat Poels 在 2005 年世界扑克锦标赛中大获全胜(翻转筹码/LasVegasVegas.com)

夏天就要到了(至少对北半球来说)，伴随着温暖的天气而来的是节日和户外活动。换句话说，对于活动管理和票务网站来说，现在是关键时刻。或者是这家在 180 个国家为聚会提供活动信息和票务的全球性公司面临的众多困难之一。

Eventbrite 负责平台的高级副总裁 [Pat Poels](https://www.linkedin.com/in/patrickpoels/) 已经在该公司工作了六年多，领导着软件工程团队和平台管理，该平台不仅支持 EventBrite 的网站和移动应用程序，还通过 API 支持许多第三方应用程序。

在 EventBrite 之前，Poels 在 Ticketmaster 工作了 15 年，帮助该公司经历了数字化转型的许多阶段。在这两次演出的间隙，Poels】以玩锦标赛扑克为生，在那里他学到了很多关于策略和逻辑的课程。所以我们不得不在那里开始我们的问答。

**所以你们都建立了大型 IT 平台并赢得了大型扑克锦标赛。有数学上的联系吗，或者有什么吸引力？**

是啊，有。当然，数学一直是我的强项，但我也从很小的时候就喜欢拼图。我做了很多来打发时间，拼图游戏，逻辑游戏，等等。

**谈到可扩展计算，肯定有很多难题需要思考，这是肯定的。**

是啊，百分之百。这些追求实际上非常紧密地联系在一起，这可能并不奇怪。

是的，在 Eventbrite 的这段时间里，我认为我们攻击这个行业的方式与我过去在 Ticketmaster 经历的方式有些不同。我认为，我们必须花大量的时间来达到一个我们可以大规模扩展我们所做的事情的位置，这也是我转到这个平台角色的部分原因。但是，随着时间的推移，拥有一家专注于自助服务的公司，以及一家为世界上数量最多的组织者提供最多免费和付费体验的公司，这些领域的可扩展性确实是一个巨大的挑战。

这是我们真正感兴趣的地方。但是，在此之前，也许你可以在一个非常高的水平上勾画出 Eventbrite 的平台？

是啊。我们利用亚马逊网络服务来做大部分事情。像很多人一样，我们有不同的工具用于不同的应用，所以我们所做的大部分都是基于 AWS 的。

我们一直在做的很大一部分工作是试图了解如何通过大大小小的活动来满足一个非常大的市场，自助活动或来自组织者的活动，以及可以以有计划的方式发生的需求，其中你知道这将是一个在几分钟内销售 50，000 张门票的节日，或者可能是有人放在平台上的实际上甚至不是真正的活动。你必须确保你能够区分这些东西，满足那些必须大规模发生的事情，并让那些想以自助方式使用它的人真正简单，还要找到平台上不真实的东西，并屏蔽掉那些东西。

我们所走的道路确实要求我们非常专注于以模块化的方式进行构建，以更加服务化的方式进行构建，并学习 API 和服务架构。我认为我们的第一个公开可用的 API 是在 2009 年推出的，所以这是我们已经研究了很长时间的东西。

我们主要通过当地用户群了解 Eventbrite。他们会建一个 Eventbrite 页面。这对当地社区有很大的好处。但是你们也在做商业活动。

是啊，绝对的。我们满足于更多的自助服务，更小的组织者，因为他们有一个团队，他们需要尝试和聚集在一起，并不一定是他们的职业。他们需要把它作为他们工作的一部分，而不是一直到企业级公司，实际上是把它作为他们的必要手段。他们的业务是出售他们一直在上演的活动的门票。该平台和我们的产品需要能够满足所有这些不同类型的组织者。

去年，我们每周处理超过 300 万张机票。如果你考虑所有不同的库存，这个平台比世界上任何其他平台都有更多的库存，无论是免费的还是付费的体验。

模块化的部分在于，我们有在大楼内部开发很多东西的人，我们有在外面作为合作伙伴进行开发的开发人员和工程师。我们希望确保我们建造的东西能让我们两者都得到促进。

> 你会为某个节日或其他有 50，000 张票的地方出售门票，你会在几分钟内将这些门票销售一空。你不会有 50，000 个请求，你会有 500 万个请求，1000 万或 5000 万个请求，这种情况会非常非常严重。

我们内部建立了一项服务，让我们能够帮助销售门票。这是我们如何赚钱的核心是卖票。我们利用这项服务在我们的网站上售票，我们也利用这项服务通过我们的移动产品售票。我们为与会者提供了一款移动产品，允许他们自助购买门票，我们还为组织者提供了一款产品，允许他们为走到门口的人出售门票。同样的技术，同样的服务，用在两种情况下。但是，在外部，我们已经开始利用这项服务，让我们在分销合作伙伴关系上获得本地购买体验。其中最大的一个是脸书，但我们也在镇上与[乐队合作，我们在那里也有其他的事情要做。](https://www.bandsintown.com/en/)

这让我们可以做到的是，无论消费者身在何处，我们都可以在他们面前获得这些美好的体验。

**你的平台具体包括什么？**

我认为平台这个词用得太多了，有时候很难准确理解它的意思。从我的角度来看，现在处于平台 SVP 的位置，我想到的是驱动我们构建的产品的服务和驱动其他人在外部构建的产品的服务。我认为它是我们的内部 API，我们扩展给自己的开发人员和外部开发人员。它也是我们整合的设计系统，允许人们使用我们的平台来构建产品。

**将新组件或新功能放到平台上的开发流程是什么？**

如果我们谈论对平台进行更新的工作流程，我们会在组织内进行持续集成，以尝试并帮助更新所有这些不同的服务。毫无疑问，我们的分发方式允许我们非常灵活地分发这些东西。

很明显，当你有了 API，有了与平台交互的系统，你必须确保你是在以一种非常聪明的方式做这件事，因为你做出改变，你可能会破坏生产中的东西，不仅仅是你自己的东西，而是其他任何地方的东西。以协调的方式做这些事情对我们来说非常重要，但我们能够快速完成也非常重要。

**现在，当我们谈到可扩展性时，我认为 Eventbrite 是一个大型运营公司，它将持续需要 AWS 资源。它是非常尖的还是交通更有规律，但只是高容量？**

它非常尖。当一个有限库存的活动开始销售时，很多人想去参加那个活动，你会看到公众想要这个非常稀缺的资源的难以置信的强烈本性，并且它都在同一时间发生。但是，由于我们是一家全球性公司，所以交易会持续不断地发生。你可以看到美国的一天是什么样子，但是澳大利亚的一天是什么样子，在某个时间段内是什么样子，但是这是根据他们一天中的时间而偏移的。

你将为某个节日或其他有 50，000 张票的地方出售门票，你将在几分钟内将这些门票销售一空。你不会有 50，000 个请求，你会有 500 万个请求，1000 万或 5000 万个请求，这种情况会非常非常严重。有许多公司不得不处理他们收到的这种请求的尖峰性质，但对我们来说更具挑战性的原因是，它必须在非常非常压缩的时间范围内发生。

那么，你是否经常过度调配，或者总是做好准备是否有其他秘密？

我认为这与智能配置有关。这需要观察你的交通模式，确保你为可能出现的事情做好准备。但同样重要的是，我们要明智地进行缓存，并采取措施确保平台不会完全崩溃。

**有没有计划开源你们自己开发的组件？**

是的，绝对的。我认为，我们，就像每个人一样，从开源的角度利用我们使用的一些伟大的工具，我们也为开源社区做出贡献。我认为，当工程师是你的客户时，你会意识到他们能够获得他们不必自己开发的伟大技术会有多大帮助。我们确实开源了我们所做的一部分，我确信这将是我们随着时间的推移继续投资的事情。

**你如何评价你的开源技术组合？你还在使用商业软件吗，或者它是一个完全开源的堆栈，或者你在这个范围内处于什么位置？**

我认为我们更倾向于使用开源工具。是啊。我们自己编写了很多代码，我们正在使用和构建的以及已经构建的很多东西都是我们自己编写的，但我们也肯定会尽可能地利用开源工具。

**你认为哪些技术即将出现，你可能正在尝试？你现在在关注 AWS Lambda 吗，或者你可能对哪些东西感兴趣？**

是啊，我们绝对是在看 Lambda。我认为，尤其是我们的数据团队，正在花大量时间将它视为我们的一条潜在道路。

我们正在做一件我认为非常有趣的事情，那就是 RFID。因为我们运营的很大一部分是让人们进出大楼，所以我们开始延伸和扩展 RFID 功能，使活动举办者能够轻松地将人们登记到活动中，消费者也能够轻松地使用内置 RFID 芯片的手镯进出活动。

但我认为我们过去做的真正有趣的事情与无现金有关。我认为我们有很多机会以更好的方式利用 RFID 技术。我们已经在几个节日里做了测试。

**所以如果你在节日里喝醉了，你不必担心会丢钱包。只要你有一个小小的 RFID 腕带，你仍然可以获得更多的啤酒。**

我很高兴是你说的，而不是我。

**我们已经在人工智能研究和人工智能模型开发等方面做了很多，但你如何让人工智能进入生产系统？**

我们面临的一个重要领域是欺诈检测。我们希望能够确定一个事件是否是真实的，我们希望能够确定一个交易是否是欺诈性的。

我们做到这一点的最佳方式，或者说实时做到这一点的最有效方式之一，是掌握大量关于真实交易的信息和关于欺诈交易的信息。当你拥有我们平台上的库存和交易的深度和广度时，你就有大量的数据可以查看和分析，并与模型进行对比，这样你就可以非常确定地确定，哪些特征会将你指向不真实或欺诈性的交易。

自从我加入公司以来，我们一直在这条路上投资，整整六年。我们在工程和数据科学方面有专门的资源，让我们自己越来越好地围绕我们的交易数据和事件数据进行机器学习，以帮助确保我们处理的交易是真实的，我们放在平台上的事件也是真实的。

当我早些时候谈到模块化平台时，这是我们已经在内部投入大量资金的领域之一。我们所做的模块化，我们相信我们将能够为外部开发人员带来这一点，并能够分享我们所获得的知识。不仅仅是库存管理，这是我们花了很多时间并且非常擅长的，还有欺诈检测。

<svg viewBox="0 0 68 31" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink"><title>Group</title> <desc>Created with Sketch.</desc></svg>