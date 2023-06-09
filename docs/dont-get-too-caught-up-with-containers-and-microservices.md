# 不要太沉迷于容器和微服务

> 原文：<https://thenewstack.io/dont-get-too-caught-up-with-containers-and-microservices/>

大多数人现在都明白了:云——更多的是公共云，而不是私有云——是我们应该使用的东西。对于我们经常使用的许多软件(例如 Google Apps、Office 365)来说是这样，对于我们为他人运行的软件来说也是这样。但是太多的用户和评论家将云视为终点，我们正在编写的软件的最终目的地。几乎没有关于构建和部署软件的下一个重大战略改进的评论；相反，我们没完没了地关注如何在云上进行战术改进，比如[容器](http://developerblog.redhat.com/2014/05/15/practical-introduction-to-docker-containers/)和[微服务](http://martinfowler.com/microservices/)。写作和思考技术的人花太多时间思考纯粹的技术创新，而几乎没有时间考虑技术带来的战略利益。在本专栏中，我将概述我理解接下来会发生什么的框架。

云的真正好处是业务敏捷性。具体来说，云有助于更快地将软件即服务(SaaS)推向市场，并减少发布更新所需的时间。一开始，SaaS 需要一个数据中心，这是一项巨大的资本投资，并且需要大量的支持人员。然后出现了主机托管和托管，这减少了资本投资和必要的员工数量。但在所有情况下，在云出现之前，都需要人来分配机器进行开发、测试、质量保证和生产。公共基础设施即服务(IaaS)将需求从人变成了信用卡，企业很乐意交出信用卡。

与业务目标保持一致的工程师发现了云的业务灵活性优势——这让他们变得缓慢，他们正在寻找一种更快的方式。但是对我来说，工程师和业务之间的一致性对于业务敏捷性的下一次重大改进来说是否如此接近还不清楚。

原因如下:技术人员只是想要更多的技术。他们沉迷于技术。这不是技术的难易程度。他们只是在制造更多的技术:容器、容器管理、监控等等。维护任何云都是一件痛苦的事情，即使是公共云。最先进的、最佳实践的云管理方式似乎是[永无止境的](http://www.informit.com/articles/article.aspx?p=2263503)；我们摆脱了死记硬背的系统管理员和网络工程师，但现在我们需要非常难找的 DevOps 工程师。这不是我们真正希望的业务敏捷性。

如果你相信我——重要的是优化业务敏捷性——那么很容易看到最终状态是什么:产品经理能够直接从产品愿景构建软件。虽然没有任何设计人员或开发人员，很难看到这种情况发生，但这是一个了解我们应该优化什么的有用结构。我们应该优化的是一个组织发布新产品和产品更新的能力，尽可能快，尽可能少的执行风险。这个焦点与其说是次要的，不如说是我今天读到的许多鼓吹新技术的文章中完全没有的。

当前的最佳实践公共云不是最终状态；这只是人生道路上的又一步。我们在某个地方呆久了，那里太乱太丑了。在传统技术领域(容器、微服务、监控)发生的讨论更能反映出随着时间的推移将会发生的变化。

相反，我关注的是那些已经实现了实质性业务敏捷性的技术，这些业务尽可能少地将他们的产品需求付诸行动。我看到 [Snapchat 在谷歌应用引擎](http://www.businessinsider.com/snapchat-is-built-on-googles-cloud-2014-1)上的构建和 [Yo 在 Parse](https://www.quora.com/What-are-some-creative-uses-of-Parse) 上的构建，以及[你通常可以在几个小时](http://www.businessinsider.com/you-can-use-this-startup-to-build-a-copy-of-billion-dollar-app-instagram-in-a-half-hour-2012-7?IR=T)内构建大规模可扩展的社交网络应用，然后做很少的工作来维护后端。这并不是说这里的技术很完美(但是想想 2009 年的公共 IaaS！)，但它提供了下一个级别的业务敏捷性。

太多的科技初创企业来自于“来自(网络规模公司)的工程师，他们构建了一个供外部使用的内部工具版本。”不要误解我的意思——我们已经通过这种方式获得了许多优秀的工具——但是我们更有可能通过仍然需要大量工程人员的产品看到渐进式的变化，而不是看到使业务更加敏捷的革命性变化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>