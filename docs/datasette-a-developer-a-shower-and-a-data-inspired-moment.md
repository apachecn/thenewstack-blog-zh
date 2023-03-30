# 数据集:开发者、淋浴和数据启发的时刻

> 原文：<https://thenewstack.io/datasette-a-developer-a-shower-and-a-data-inspired-moment/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

我们倾向于认为开源是一个社区，甚至是一种利他的努力。但是有时候一个项目可以“积极地开源”，正如 [Datasette](https://datasette.readthedocs.io/en/stable/) 创始人[Simon Williamson](https://twitter.com/simonw)所说，因为一堆“非常自私的原因”威廉森在他的职业生涯中写过大量的开源(例如， [Django](https://www.djangoproject.com/) 的联合创始人)和专有(例如， [Lanyrd](https://en.wikipedia.org/wiki/Lanyrd) 的联合创始人)软件，但他说他将开源作为一种“创造性的出路”，让他保持一定程度的独立性，即使全职工作可能会限制它。

你没听错:开源并不总是需要拯救世界。如果它拯救了个体开发者的理智，那就足够了。

当然，许多其他人确实受益于 Willison 的开源贡献。但即使他们不这样做，威廉森也会继续开源他的代码。为什么？因为这促使他写出更好的软件，即使它帮助他跟上各种各样的项目——285 个存储库和统计中的 285 个——他为之做出了贡献。这是一种非常高效的建造方式。威廉森说，他喜欢开源的一点是，对于他解决的每一个问题，他都不必再去解决它。“代码将永远存在，”他说。

事实上，威廉森的开源方法提供了关于如何建立一个社区利益最大化的项目的深刻见解——即使是一个人的社区。

## 淋浴和蒸汽

正如威廉森在一次采访中解释的那样，他在 2009 年为英国报纸《卫报》工作时，就清楚地意识到自己需要 Datasette，一种探索和发布数据的工具。在那里，他帮助创办了数据博客，这是一个发布《卫报》故事背后的数据的地方。尽管威廉森最终使用 Google Sheets 作为发布底层静态数据集的方式，但他渴望一种更好的方式来发布和查询这些数据。

几年后，他有了自己的数据集“淋浴时刻”

“那确实是一瞬间，我真的在洗澡，”他说。

首先，他推断，云提供商让托管动态代码变得便宜而容易。其次，他可以在通常没有数据库的地方插入 [SQLite](https://www.sqlite.org/index.html) ，一个广泛使用的公共领域关系数据库。

“如果我得到 SQLite，然后导出数据，我将它与 Docker 容器捆绑在一起，该容器带有一个小应用程序，可以为您提供一个界面和东西……也许这是一个值得探索的真正有趣的空间，”他说。

的确如此。Datasette 出生了。

但是 Datasette 不仅仅是解决一个技术问题。这也是威廉森表达自己和保持独立的一种方式。在他的职业生涯中，威廉森发现自己在更大的组织中。这种雇佣带来了特权，但也限制了开发商的建设能力。他说，他创办 Datasette 的部分原因是为了有一个创造性的出路。

“对我来说，这是一个再次深入技术领域的机会，”他解释道。“我想要一个项目，在那里我可以决定建造什么，并把它作为我自己的个人空间。这几乎是一种发泄情绪的方式。”

## 一个人的开源维护组

今天 Datasette 大约有 30 个贡献者，但大部分工作都是由威廉森完成的。他没意见。事实上，这很好，他说，因为外界的贡献并不是纯粹的好事。

“有一个梦，你有一天早上醒来，有一个美丽的，闪闪发光的新功能拉请求，但实际上，如果这种情况发生，这是一种压力，”威廉森说。“因为你必须仔细检查代码，以确保它符合你试图构建的更广泛的模型。”

他说，一种替代方案是插件架构，他几乎从一开始就将这种架构整合到 Datasette 中。

“插件的美妙之处在于，我不需要给任何人权限来加载你的插件，他们甚至不需要和我说话，”威廉森解释道。他说，他可以在某天早上醒来，Datasette 将拥有一个全新的功能，而无需他做任何事情。他说:“如果质量差或者不太好用，也不会对核心造成任何伤害。”

这种插件架构不仅可以保护 Datasette 内核免受其他人的不良代码的影响，还可以保护内核免受 T2·威廉森的不良代码的影响。“我有很多疯狂的想法，我不想把它们放入核心，因为它们可能是糟糕的想法，但把它们放入插件对我来说没有任何坏处，”他说。

他的梦想是变得有点像 WordPress，他为 Datasette 建模了 WordPress 的插件架构。“WordPress 是一个非常不错的 CMS，有 7000 个插件，这意味着它可以做任何事情。“我希望 Datasette 成为一个‘体面的引擎’,拥有 7000 个插件，用于数据分析和探索，这意味着如果你想要一张地图或图表或所有这些不同的东西，它都可以为你所用，”威廉森说。

## 出于“非常自私的原因”开放源代码

如果威廉森的插件方法保护他自己和其他人免受糟糕代码的影响，那么他对开源的拥抱可能是他发现的确保他首先写出好代码的最好方法。

“Datasette 积极开源有很多原因，”威廉森说。“大部分都是很自私的原因。”

他解释说，首先，他在职业生涯中写了很多封闭源代码，包括在 Lanyrd 时，他和他的联合创始人/妻子娜塔莉·唐恩[把它卖给了 Eventbrite](https://blog.natbat.net/post/61658401806/lanyrd-from-idea-to-exit-the-story-of-our) 。然而，一旦你离开了那个雇主，你以后就不能再使用那个软件了，威廉森说。

他指出，即使你是自己写软件，而不是为你的雇主写软件，如果它不是开源的，你就不会真的想让其他人使用它，这意味着它可能会过时。相比之下，在户外工作时，威廉森说，“它迫使我写出好的代码。它迫使我写真正好的文档。”更不用说伟大的单元测试了。

那些文档，包括相关的注释，有助于讲述他的代码的故事。虽然这对外部贡献者来说可能是有用的，但 docs 也帮助 Willison 继续他的工作。威廉森维护着 73 个开源项目，他说你能维护 73 个项目的唯一方法是你对待每一个项目就像你不是核心维护者一样。每个人都必须有一个自述，测试和详细的问题线程讨论他在做什么。“因为这样你就可以在六个月的间隙后重新投入其中，并与他们一起提高工作效率，”他说。

“我是一个只有一个人的开源维护团队，”威廉森说。“我把我在 Eventbrite(一个 600 名工程师的组织)中学到的经验应用到一个只有一名工程师的组织中。”

对威廉森来说，现在是关键时刻了。在过去的一年里，他是斯坦福大学约翰·s·奈特新闻研究员，拿着报酬修补他的 Datasette 梦想。他目前的想法是使用 Datasette 进行自由开发，为各种组织解决与数据新闻相关的有趣问题，他说这可能是一种很好的方式来找出软件应该做什么。

你有兴趣帮助威廉森塑造数据新闻业的未来吗？访问[dataset 页面](https://datasette.readthedocs.io/en/stable/)，贡献代码、想法、文档等。

*如果你或你认识的人在不同的开源项目上需要帮助，请访问 [AWS 开源](https://aws.amazon.com/opensource)网站，了解开源项目如何[申请 AWS 推广积分](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/)。*

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>