# 为什么中间层，包括 Docker，对我们大多数人来说并不重要

> 原文：<https://thenewstack.io/why-the-middle-tier-including-docker-wont-matter-to-most-of-us/>

云计算的兴起(按 API 理解:虚拟机、容器、裸机)给各地的企业带来了巨大的好处:我们现在可以用比以往更少的工人更快更好地交付产品。我们看到，从监控工具到容器和 Docker，人们对改进云计算第一次迭代的技术有着一致的兴趣。但是，下意识地关注云计算的改进版本忽略了一个事实，即云计算正在被基于云的服务所破坏，最终将使这些改进与大多数组织和开发人员无关。

中间层正在被云服务抽象化。开发人员不必处理管理应用程序的所有复杂问题。管理应用服务器、容器、监控和其他一切的是服务提供商，而不是用户。开发厚 AngularJS web 应用程序的用户只需调用该服务。他们不必真的担心托管和中间层带来的所有后端复杂性。他们只是希望服务能够正常工作。这是用户最关心的问题。

中间层随着软件即服务的爆炸式增长而出现(SaaS)。大约从 10 到 15 年前开始，过去被编写为运行在本地托管的数据库上的胖桌面客户端的应用程序，开始被构建为运行在中央托管的数据库上的 web 浏览器前端。因为 web 浏览器前端不能可靠地运行复杂的代码，并且不可信(从安全的角度来看)，所以出现了一个“中间层”，处理前端和数据库之间的通信。这个“中间层”变得相当厚，导致了像 Ruby on Rails 这样的框架来帮助管理庞大而杂乱的代码库，这些代码库基本上完成了应用程序的所有工作。

但随后 iPhone 出现了，很明显移动应用将是一件大事，这导致许多人宣布应用应该“首先构建移动应用”在许多情况下，移动应用程序的用户体验优于移动网络，因此公司意识到要最有效地接触客户，他们需要应用程序。此外，客户端 web 浏览器的功能也得到了显著的改进，允许基于浏览器的用户使用“单页应用程序”(spa)获得更好的体验，这些应用程序使用 Javascript 使浏览器的工作方式更像一个胖客户端应用程序。

但是厚中间层的构建并没有考虑厚客户端代码(app 或 SPA ),所以这两者有一段时间的婚姻很尴尬。直到像 [Parse](https://www.parse.com/?gclid=CIao1dTX2MQCFYdgfgodJ08AQQ) 和 [Firebase](https://www.firebase.com/) 这样的服务出现，使得移动应用和 SPA 开发者能够构建面向客户端的出色应用，而完全不需要中间层。相反，这些“后端即服务”( [BaaS](https://en.wikipedia.org/wiki/Mobile_Backend_as_a_service) )处理一切。甚至用中间层构建的应用程序也开始接受这些新的胖客户机。因此，中间层的规模正在缩小。

中间层也在缩小，因为应用程序使用数据库和数据存储的方式发生了巨大变化。存储所有数据的传统单主关系数据库(想想 SQL Server、Oracle、MySQL)正在被一组专门构建的数据存储所取代:用于保存文件(和大型文本块)的对象存储和高可用性文档/键值存储通常被选为应用程序的主要数据库，因为它们能够提供高可用性。甚至关系数据库也正在被托管关系数据库服务所取代，比如亚马逊的 RDS。

两种不同的客户驱动的需求正在降低中间层的规模:更好的用户界面(更厚的客户机)和数据存储端更高的可用性和速度(更厚的数据库服务)。很难看到中间层再次增长——随着我们获得越来越好的云服务，我们减少了花费在非核心业务特定功能上的时间、精力和代码。像许多情况下的中间人一样，应用程序的中间层正在被破坏。

这就把我们带到了云计算——具体来说，就是在亚马逊的 EC2 上运行虚拟机之类的计算单元，或者在谷歌的容器引擎上运行容器。云计算不运行前端代码(而是驻留在客户端)，并且越来越多地不运行数据存储，数据存储可能是托管的 NoSQL 服务，如 DynamoDB 或 Orchestrate.io，或者是托管的数据库服务，如 RDS，或者仍然是一个强大的裸机服务器上的关系数据库，以正确处理负载。

因此，对我们大多数人来说，云计算主要是运行应用程序的中间层——即将消失的中间层。

所有这些都意味着纯云计算(例如 Docker)的下一次迭代将主要与运行基于云的服务的人相关，就像发电厂使用的工具只与为发电厂工作的人相关，而与消耗发电厂生产的能源的大多数人无关。

换句话说:外包工作负载的巨大好处不会随着从本地数据中心的虚拟机转移到公共云计算上运行的容器而结束。普通公司没有内在的理由需要担心单个服务器。都说把服务器当牛比当宠物好，但是一点牲畜(服务器)都没有不是更好吗？就我而言，如果我可以完全摆脱云计算实例，我就没有优化它们的内在需求。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>