# 自动化:所有的乐趣和游戏，直到出错

> 原文：<https://thenewstack.io/automation-all-fun-and-games-until-something-goes-wrong/>

技术和软件业的故事是一个速度和效率不断提高的故事。*摩擦力更小。一条更快的路。*这不仅仅是一个共享的神话；这可以从市场上出现的产品类型、它们的定位以及它们如何进入工作流和工具链中看出来。

例如: [COBOL](https://thenewstack.io/u-s-unemployment-surge-highlights-dire-need-for-cobol-skills/) 让非专业人士更容易编程。 [DevOps](https://thenewstack.io/the-what-why-and-how-of-devops/) 去除了构建和操作软件之间的摩擦。平台工程正在建造护栏和黄金通道，这样开发人员就可以专注于发布代码。尽管只知道一行代码，低代码使构建东西成为可能。还有 [AI](https://thenewstack.io/data-analytics-and-ai-what-will-happen-in-2023/) …好吧，你就等着瞧吧。

虽然许多创新、技术和工具确实使软件工程的某些部分变得更好，但我们正在向一个终点前进的概念——一个完全自动化的幸福高原，在那里我们任何人都不必做任何事情——当然是异想天开的(客气地说)。通常，在追求效率、简单性和速度的过程中，我们最终会引入意想不到的复杂性和我们没有预料到的新问题。

我们不应该把这种现实仅仅视为一种偶然的异常现象，而应该注意到它们。它们告诉我们一些关于我们的技术经验的重要事情，也强调了我们设计并带到这个世界上的解决方案总是会产生我们意想不到的后果。

## 移动边界

思考自动化挑战的一种方式是认识到不同类型的工作之间总是有一个界限。是一名软件工程师，曾在运营和开发工具部门工作过(最近在 Kong 和 Chef ),她告诉 New Stack，在开发人员生产力的世界里，她看到了一个边界不断移动的过程。

“有些事情更多地落在开发人员身上，有些事情更多地落在像我这样的人身上，他们在特定功能开发之外工作，”Lam 说。

换句话说，每当我们在一个地方自动化某件事或使某件事更有效率时，那总是因为其他地方正在发生某件事。还有人在思考这个问题。

这并没有什么特别独特的地方。为了使问题和过程更容易解决，它们总是被分解成不同的组成部分。然而，当我们需要跨越边界进行交互时，事情就变得棘手了。

“感觉就像我们在移动边界，却不一定能更好地改变人们在边界相遇时发生的事情，”Lam 说。

这个问题的一个很好的证明就是在边界会发生什么？由可靠性工具公司 Stanza 的联合创始人兼产品负责人[玛吉·约翰逊-品脱](https://www.linkedin.com/in/maggie-johnson-pint-a1934023/)提供。

“当我们对事件进行[分析](https://thenewstack.io/top-12-best-practices-for-better-incident-management-postmortems/)以及为什么会发生这些事件或者为什么我们无法解决某个事件时，发生的情况是，原本打算管理该系统的工程师正在通过如此多的自动化层工作，以至于当出现问题时，他们没有明确的方法来修复它，”她说。

在这里，界限是这样的，它变成了一个限制——一个阻止你找到问题解决方案的路障。

> “人们不想要控制权，直到他们想要。”
> 
> **——玛吉·约翰逊·皮特，第七节**

根据 Johnson-Pint 的说法，这不是由糟糕的技术引起的问题，而是具有讽刺意味的是，它的优雅。

她强调了使用前端堆栈 [Vercel](https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/) 的体验，它抽象了后端操作——“这真是不可思议，”她说。但是“当你使用它时，就好像你已经完全脱离了物理计算机存在的概念，你只是运行在一个无限的平台之上。”

这意味着，作为用户，你忘记了你所依赖的东西是必须制造和维护的。

只有当事情出错时，你才会意识到你对某些事情缺乏控制。你对自己系统的掌控感让位于其他东西:如果不是完全无助的感觉，至少是明显的挫败感。

在这一点上，约翰逊-品脱是苦笑:“人们不想控制，直到他们这样做。”

## 坏习惯

效率的逻辑会鼓励坏习惯。

Pint-Johnson 说:“我们在这个行业花费的钱比我们需要的多得多。”她在这里指的是云——现代云系统提供的简单性让人们很容易忘记计算正在某个地方发生。

“人们并没有密切关注开销机架是如何增加的，因为他们不必坐在那里考虑，我是否必须在物理计算上花费更多，并必须添加额外的机架？

“在所有需要解决的与气候变化相关的问题中，这可能不是最大的一个。但实际上，我们不应该烧掉这么多电脑！”

这是很重要的一点。虽然有迹象表明行业开始意识到软件对环境的[影响，但很难想象我们如何在减少摩擦、提高便利性和简化性的同时，妥善解决可持续性问题。](https://thenewstack.io/cloud-lessons-to-help-developers-improve-esg-impact/)

> “有一种观点认为自动化总是比人更好，我认为这是一个我们可以进行更多质疑的立场。”
> 
> **—林漪娸，软件开发人员**

是的，[某些自动化技术](https://thenewstack.io/what-is-cloud-automation-and-how-does-it-benefit-it-teams/)可能有助于识别并最大限度地减少低效和浪费，但这种改变究竟有多大意义仍是个大问题。事实上，有一种危险是，在一个需要认真和持续关注的问题上，这仅仅是一个绷带。

“有一种观点认为，自动化总是比人更好，我认为这是一个我们可以进行更多质疑的立场，”Lam 说。“很多时候，是的，你的自动化会一遍又一遍地做同样的错误事情，你无法停止做错误的事情，直到有人能够以某种方式与他们互动。”

Lam 说的是扰乱系统的错误。但不难看出它也适用于宏观层面的挑战:当我们被埋在层层抽象中时，我们如何开始解决它们？

## 对谁来说没有摩擦？

当谈到效率时，另一个重要的考虑因素是，改进究竟会使谁受益？

与可持续性不同，像可及性和神经多样性这样的问题已经被证明是科技行业声称关心的问题。但是，这在多大程度上符合日益便利和简单的模式，还有待商榷。

根据软件开发人员和可访问性倡导者 Myles le wando[的说法，由于可访问性仍然被视为“最好拥有”而不是一项要求，因此很容易被排除在为开发人员构建护栏和黄金路径的过程之外。](https://www.linkedin.com/in/codemacabre/)

他告诉《新堆栈》,这可能会影响到谁真正能够在这个行业茁壮成长。“对于神经多样化的开发人员来说，一些人可能会被副驾驶或数字配对程序员的吸引力所吸引，”莱万多说。“但这种对效率的强调、期限的缩短、速度的加快，给员工带来了压力，增加了压力和焦虑。”

换句话说，如果我们在没有必要的自我反思的情况下处理效率和生产率的问题，我们可能会发现这个行业变得更加困难——最终完全破坏我们肯定想要实现的目标:为每个人提供更好的工作。

## 我们让一件蠢事变得简单

认识到这些问题在可持续性和可访问性方面的严重影响是很重要的，但是这个问题通常通过最平凡和愚蠢的例子得到最好的证明。

Pint-Johnson 提供了一个很好的例子:有一段时间，她为 Moment.js 做贡献，这是一个帮助开发人员管理日期和时间的 JavaScript 库。当您调用基本 API 时，它将返回您计算机本地时区的日期。如果你想要 UTC，或者协调世界时，你必须在你的代码中明确地声明“moment.utc”。

在一段时间内，这不是一个问题-事实上，大多数 Moment 用户并不太关注 UTC。但 Pint-Johnson 说，随着 Node 的引入，当 JavaScript 开始转移到服务器上时，这种情况发生了变化:“你实际上想用 UTC 做任何事情，因为谁知道用户在哪里。”

随后，这导致了各种项目和产品中的错误。"我们不得不一遍又一遍地解释堆栈溢出！"她笑着说。

“这很有趣，因为你会认为这没什么大不了的，人们会慢慢学会的。但是因为这个库很难搞，而且有数百万的代码库……世界上的每个开发人员都不得不一遍又一遍地尝试同样的东西。”

最终，Moment 团队去了 TC39(ECMA 的一部分，负责 JavaScript 标准的机构)并提议去掉日期默认值，所以开发者必须选择它。Pint-Johnson 说:“我们让一件蠢事变得简单，却让所有事情变得困难。”

## 没有方向地开始

Pint-Johnson 提出的问题很好地提醒了我们，当一件事情很容易——或者，事实上，从视野中消失——我们似乎不需要去了解它。Lam 在产品营销的方式中看到了这种东西:“不管是不是有意的……许多围绕自动化的语言实际上是一种抽象的语言:‘没有人需要知道这些。’"

正如我们所看到的，这影响了我们解决问题的能力，潜在地使我们更加依赖专家。但这只是一个问题:它还改变了我们思考问题的方式——我们只是触及边界，然后等待专家的到来。我们也许不太可能赞同可能有其他方法来解决问题的想法。或者，事实上，问题源于几个月或几年前做出的决定。

Lam 认为，这个问题部分是由于该行业对她所谓的“入门经验”的关注造成的。她指出，对产品开发人员的关注是该行业在过去十年中做得特别好的事情，但她声称现在有“一个巨大的中间缺失”

“从这些东西开始真的很容易，但没有任何东西告诉你在使用它们或你以后可能想做的事情时如何维护你的环境。”她说。“一旦你过了入门阶段，就像从悬崖边上掉下来一样。”

她举了 Docker 的例子——虽然文档很好地告诉了您如何开始，但它没有探究使用它的一些含义和利弊。

“它没有告诉你，‘哦，顺便说一句，这个让你的环境看起来无缝的东西——你正在将数十亿字节的图像下载到你的硬盘上，在某些时候，你可能想清理它们！’"

这可能会对我们产生严重的技术影响——在学会避免供应商锁定的危险后，我们似乎陷入了许多微锁定的情况。

> 自动化会影响我们解决问题的能力，可能会让我们更加依赖专家。但这只是一个问题:它还改变了我们思考问题的方式——我们只是触及边界，然后等待专家的到来。

Lewando 说:“许多工具最终可能更难维护，或者可能有不可预见的限制，需要在以后解决。”[技术债务](https://thenewstack.io/3-sources-of-tech-debt-and-how-to-manage-it/)工具越多，解决起来就越复杂，需要在集成、维护和开发人员培训的时间和财务成本与新工具的潜在优势之间找到一个平衡点

根据 Lam 的说法，我们需要的是心态上的转变，摆脱那种只做一点点、不花太多力气快速行动的冲动。“对我来说，问题是我们如何谈论人们的需求是什么，”她说。“我们如何在这种基础设施中培养一个人——我们如何向他解释？”

## 便利的代价

目前有很多事情要担心。因此，软件业对那些能让人们的生活变得更轻松、更舒适的东西感兴趣是有道理的。

然而，这并不意味着我们应该忽视舒适和便利的成本——即使我们认为我们现在不需要支付这些费用，但我们很可能在未来的某个时候不得不支付。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>