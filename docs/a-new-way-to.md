# Reflect 将可视化翻译成代码

> 原文：<https://thenewstack.io/a-new-way-to/>

从俄勒冈州波特兰市的 [Twilio](https://www.twilio.com/) 和[条纹](https://stripe.com/)中吸取经验。基于[的 Reflect](https://reflect.io/) 让开发者可以轻松地将数据可视化嵌入到他们的网站和移动应用中。

Reflect 吹捧自己是第一家提供“数据可视化即服务”的公司，这意味着用户不必担心构建和扩展基础架构来提供仪表板、报告和其他数据图形视图，这是一个嵌入式模块。

社交媒体分析公司[simple Measured](http://simplymeasured.com/#sm.0000bv3xanwxed7szo610fuzl4pbn)的联合创始人 Aviel Ginzburg 说:“如今，需要进入可视化层的功能和思想数量非常巨大，我们已经有很多了。

“他们已经建立了一个非常强大的可视化服务，我们可以将它直接插入到我们现有的系统和服务中。”

联合创始人 Brad Heller 和 Alex Bilmes 认为这是一个需要在成本管理供应商 [Cloudability](https://www.cloudability.com/) 工作时解决的问题。

“我们一遍又一遍地建造同样的东西，”海勒说。“我们想，‘需要有人为人们一劳永逸地解决这个问题，这样工程团队就不必(在这方面)投入大量资金。

“越来越多的人在消费分析，但人们真的很难建立这样规模的服务。对于大公司来说，建设这样的基础设施可能要花费数百万美元。”

“我希望我们能够解决所有与基础设施和前端相关的问题，这样我们就可以将数据可视化世界向前推进一点。人们现在正在努力解决数据可视化的基础问题，因此有很多创新被扼杀了。”

该公司刚刚在 DFJ (Draper Fisher Jurvetson)领导的一轮融资中获得了 250 万美元的种子资金。

**你家还是我家？**

该技术涉及一个放置在客户端数据库中的代理，该代理根据用于创建可视化的拖放界面来处理查询和路由数据。可视化然后被翻译成代码，开发者可以嵌入到他们的应用中。它为他们提供了一个层，让他们以易于理解的方式对其分析数据进行建模；同时，它是可组合和可重用的。

用户可以选择一个托管代理，也可以使用一个本地数据托管代理。

“托管服务在 AWS 上运行，但我们已经在 HPE 的数字海洋上运行了。这与云无关。我们使用自己的容器化层，这使得我们无论底层硬件或平台是什么，都可以轻松地进行横向扩展，”该公司的首席技术官 Heller 说。

它支持红移、BigQuery、Postgres、MySQL 等技术。API 使用数据模型将可视化请求转换成对数据库的查询，Reflect.js(一个定制的 JavaScript 可视化库和 UI 工具包)将视图呈现到页面上。

反射代理在加密的嵌入式数据库中维护所有数据库凭证。据该公司称，这些凭证被解密以查询数据库，但它们从未离开代理。

对于像 Simply Measured 这样只使用公开数据的客户来说，这不是问题，但对于处理更敏感数据的客户来说，这可能是个问题。

“我们现在没有一个强有力的合规故事，”海勒说。“在很多情况下，我们的产品可以让你达到 90%。数据流经我们的 API，它本质上是一个路由层——接受一个可视化请求并将其发送到后端。”

他说，该公司正在进一步探索合规要求。另一种方法是将技术打包并部署在客户的云或云帐户中，这样他们可以保持对数据的控制并保护数据。

到目前为止，报告受数据库性能的限制。

“但是我们可以做很多智能的事情，因为我们有这个中间件。我们知道您运行的每个分析查询，我们有相关的日志。我们知道您使用的是什么可视化方式，所以我们可以做很多有趣的事情，比如预热，比如提前运行查询，或者根据我们看到的数据库中的数据变化进行智能缓存，或者预测下一个查询会是什么。这些东西都来了，但现在还很初级，”他说。

**无缝集成**

在去年创建公司后，Reflect 最近参加了 Techstars Seattle '16，超过 1000 家公司请求访问其私人测试版。

“现在，我们专注于帮助人们在正确的时间使用可视化。人们很难选择合适的图表来展示。海勒说:“对于给定的数据集，只有几种‘正确’的方式来可视化数据，这取决于你想要传达的信息。”

它希望扩展它提供的显示选项，比如提供不同可视化的 mashups，但也要解决其他技术挑战。

Heller 说，其最初的迭代涉及让客户推出数据集以反映可视化，但移动数据被证明是采用的一个巨大障碍，它发现这种代理方法更可行。然而，行业中的其他人在努力向外扩展时，正在实施“许多非常复杂的机制”。

简单测量使用 Reflect 为其基于 web 的仪表板提供可视化。他说，这很容易根据他公司的外观和感觉进行定制。

“对我们来说，能够通过真正简单和无缝的集成来利用它们，有助于我们通过专注于事物的分析和数据方面来更快地前进，”金兹伯格说。“他们让我们很容易定制东西，他们有一个功能齐全的路线图，所以每隔几周，我们就可以向我们的客户提供新的功能，同时我们专注于我们平台的其他方面，”他说。

“当您考虑为您的可视化提供支持时，您的选择是要么使用 BI 工具，然后您真的无法控制体验-您只需让事情按照该工具的方式工作-或者您必须从头开始构建一切。[Reflect]提供了这种两全其美的令人惊叹的中间立场。”

数字海洋和 HPE 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>