# 在图形数据库中行走及其含义

> 原文：<https://thenewstack.io/walking-in-a-graph-database-and-the-meaning-it-holds/>

图形数据库还是不太懂。就此而言，我们仍在适应一个后关系世界——一个与应用程序架构日益水平和分布式的本质相关的新时代。但是还有更多东西需要理解，那就是数据库影响我们日常生活的方式。直到我们看到服务如何改变我们看待生活和工作的方式，我们才能真正理解图形数据库的意义。

以地图为例:它上面有任意数量的点。代表陆地和陆地上“事物”的无限“节点”。直到最近，这些东西之间的联系对我们来说毫无意义。杆子是杆子是杆子。但现在不是了。极点可以更好地理解为可以在在线地图上查看的数据对象，或者现在越来越多地被理解为连接其他事物的东西。这就引出了下一个问题:

## 这如何改变我们对数据库的看法？

到目前为止，数据库被认为是管理银行记录、收据、账单、关于人和动物的数据等的工具。但是对于图形数据库，这有点像我们在数据库本身。我们能看见一根柱子。我们可以看到一盏路灯。但是我们很快就能在其他多维度上看到它们。当我们行走时，数据会随着路径上各种对象的不同关系而变化。这有点像在图表中穿行，通过数据结构将我们与每个节点联系起来。

透过这个镜头，我们对应用有了新的认识。我们开始看到构建数据基础设施的公司如何在数据中找到上下文，并使用它来构建新的应用程序。这个过程是一个无限循环。收集、分析数据，发现模式，开发应用程序。图形数据库通过连接看似不相关的信息点来加速这一过程，例如银行欺诈，去年春天菲利普·拉思勒在新的堆栈中描述:

与大多数其他显示数据的方式不同，图表旨在表达关联性。图形数据库可以揭示使用传统表示(如表格)时难以发现的模式。越来越多的公司正在使用图形数据库来解决大量互联数据问题，包括欺诈检测。

网络被许多技术专家视为一个数据库。现在，数据库正在发生翻天覆地的变化，将自己暴露在现实世界中。正如 Matt Asay 在 [ReadWrite](http://readwrite.com/2014/11/28/internet-of-things-nosql-data) 帖子中指出的那样，关系数据库可能适用于处理以隔离方式管理的结构化、高度统一的数据集，他提到了[玛奇纳研究](https://machinaresearch.com/report/research-note-why-nosql-databases-are-needed-for-the-internet-of-things/)关于物联网的一份报告。随着“数以百万计的传感器、设备和网关”的出现，需要新型数据库来处理电线杆、房屋或树木的含义。

对此想得太多会让人掉进无尽的兔子洞。今天的工作是开发创造未来的数据库。这意味着坚持考虑分布式架构的现实，以及图形数据库如何在这些环境中运行。

## 分布式平台中的图形数据库

在过去的几个月里，很明显，分布式、互联世界的动态正在产生新一代的图形数据库提供商。此外，还出现了将数据平台与图形数据库技术连接起来的混合体。从分布式的角度来看，用分布式平台连接图形数据库是有意义的。随着图形数据库的扩展，解决能够大规模处理大容量读写操作的问题将是成熟市场的下一个挑战。

例如，将 [Cassandra 的 NoSQL 平台](http://cassandra.apache.org/)与 [TitanDB](https://www.quora.com/Titan-graph-database) 、最近从 [Aurelius](http://thinkaurelius.com/) 收购的图形数据库 [DataStax](http://www.datastax.com/) 整合，用它建立一个横向扩展的节点网络，你会开始看到这种混合版本的出现。

Cassandra 采用无主架构，旨在承受数据中心中断而不中断服务。DataStax 的客户网飞使用亚马逊网络服务(AWS)。2012 年，在一场大风暴中，AWS 的一个数据中心发生了宕机。网飞的客户没有一个失去服务，这在一定程度上归功于 Cassandra 的平台能力。有了 Cassandra，TitanDB 可以跨任何数据中心实施，为客户提供了稳定性，他们可以将此作为其运营的一部分。

TitanDB 旨在跨分布式集群进行横向扩展。对于 Cassandra，它有一个分布式存储引擎，可以在添加节点时扩展数据库。相比之下，领先的图形数据库 [Neo4j](http://neo4j.com/) 具有主/从架构，需要更强大的机器来扩展。跨集群存储是 TitanDB 的优势所在。

Neo4j 的创始人 Emil Eifrem 说，Neo4j 和 Titan 采取了完全不同的方法。他说，出于性能和可靠性的原因，他们决定从头开始建立一个图形数据库。当在不是为图形构建的数据库之上构建图形数据库时，需要权衡利弊。Neo4j 建立了他们自己的关系数据库管理系统和一个查询语言。声明一下，该公司本周宣布了 Neo4j 2.2，其中[增加了读写可扩展性](http://www.datanami.com/2015/03/25/neo-tech-cranks-up-speed-on-upgraded-neo4j/)。

TitanDB 采用另一种方法，在另一个数据库的基础上构建一个非原生的图形数据库。Eifrem 说，像 Cassandra 这样的数据库在处理大容量和吸收大量数据方面非常出色。但他质疑查询运行的速度，以及它们在多大程度上满足了实时业务需求。

OrientDB，根据它的网站，有一个混合文档图形引擎。它构建在 SQL 之上，但添加了支持树和图形操作的扩展，同时还提供了多主和共享架构，以克服写操作中的主从瓶颈。他们的网站对 Orient 和 Neo4j 的区别有详细的对比分析。

## Appbase:图形数据库即服务

与此同时，新的数据库竞争者 [Appbase](https://appbase.io/) 希望其图形数据库即服务(DBaaS)产品将吸引应用程序制造商在为搜索和实时社交网络产品构建数据引擎时使用其服务。

Appbase 提供了一个 DBaaS 产品，允许开发人员快速扩展实时数据库和后端服务，通过单一 API 访问数据。Appbase 认为它存储数据的方式是独一无二的:以图表的形式。这意味着数据不是由行和列组成，而是由顶点和边组成。

Appbase 创始人西达尔特·科塔里说:“如果你要在 SQL 数据库中建立一个社交网络模型，实时完成是不可能的。”。“在两个不同的表中捕获对象是不可能的。当您将整个数据模型视为一个网络时，顶点适用于多少行。边意味着每个对象都由一条边连接。所以随着你的成长，你需要更多的顶点和更多的边。”

Kothari 说，Neo4j 认为图形数据库是一个计算层。Appbase 试图做的是把一个图想象成一个数据结构。

Kothari 说，这项服务与服务器和客户端的方法无关。使用 Appbase 的开发人员可以编写一个 Javascript 代码，并且不需要设置服务器。

虽然允许灵活性和快速扩展，Appbase 的产品也有一些权衡。首先，作为 DBaaS，Appbase 将自己决定如何存储最终用户的数据。正如他们的网站所说，用户不能自己选择数据库:“我们的目标是创建一个抽象底层内部的数据库服务，这样我们就可以选择最好的东西，并将其作为一个单一的、一致的 API 提供。同时，我们保持堆栈的透明度，并提供最适合它的数据建模指南。”

类似的服务，如 GrapheneDB，是在 Neo4j 的开源工具上作为 DBaaS 构建的，这意味着业务用户可能会感觉对这种决策有更多的控制权。

## 市场准备好使用图形数据库了吗？

搜索趋势无疑表明人们对图形数据库的兴趣越来越大。

但是像 Orchestrate 这样受人尊敬的行业服务对其图形数据库搜索查询的兴趣比一些人预期的要少。

“图表工作负载将是应对不断扩展和多样化的数据集的组织感兴趣的领域。图形数据库提供了查询数据的方法，这些数据可以支持推荐引擎等受欢迎的功能。Orchestrate 的首席技术官 Ian Plosker 说:“它们也可以用于更普通的用例，比如描述项目之间的关系。”Orchestrate 自 2013 年以来一直在其数据库即单一 API 服务上提供图形搜索查询功能。“我们提供了一个可靠的 graph API，可以满足绝大多数用户的需求，但老实说，graph 是我们的开发人员社区最少要求的功能。我们最大的客户和工作负载为我们的 JSON 面向文档的模型编排了强大的搜索和时序查询，这是大规模“物联网”项目所需的查询类型。

“开发人员利用我们的图形 API 来描述项目之间的关系。例如，图关系可以用来描述两个用户之间的友谊，或者一个用户对一个文档的所有权。这允许开发人员查询用户的所有朋友，或者用户拥有的所有文档。我们对数据集中的关系数量没有限制。”

Techstars 的毕业生 Appbase 目前发现，其他初创公司和企业家也在使用它的产品。但是，如果他们要巩固他们在市场中的地位，他们需要超越初创企业用例，进入企业。

科塔里说:“创业公司是最快抓住新趋势的，他们也是更快意识到这些问题的人。”“但企业更像是筒仓；我们将如何接触他们还没有计划好。我们对有机食品更感兴趣。”

尽管还没有一个开源路线图，Kothari 确认最终用户不会被锁定在 Appbase 上。可以通过 REST API 访问数据。该公司没有任何数据库内置的导出机制，但程序员可以访问它。

## 走向成熟的图形数据库

虽然图形数据库市场正在壮大 Forrester 等领先分析师预计，到 2017 年(T1)，该行业的占有率将达到 25%——但在成为成熟的数据库产品之前，还有很长的路要走。

数据库专家[科特·莫纳什](http://www.monash.com/index.html "Curt Monash")是一名行业分析师和莫纳什研究公司的创始人，该公司发布行业博客 [DBMS2](http://www.dbms2.com/ "DBMS2") 。虽然乐观，但他仍然认为图形数据库还有很长的路要走，Neo4j 具有原生图形存储和原生图形处理，而 TitanDB 可以跨分布式基础架构使用，以处理更大容量的数据。

> “最接近标准图形语言的是 SPARQL，它只适用于有限的图形和图形用例集，”Monash 说。"所以，是的，很高兴看到在一种更具表现力的图形语言上达成一致."

图形数据库的相对年轻表明了 TinkerPop 的重要性，这是一个新的 Apache 基金会孵化器项目，它标准化了图形数据库。参与的成员包括 Neo4j、Titan、MongoDB 和 FoundationDB。正是这种努力将帮助图形数据库发展得更加成熟。

一般来说，Monash 寻找的两样东西是:

*   数据类型——或者实际上是文档类型——标记节点和边的灵活性。
*   丰富的操作集——中心性、路径长度等等。

未来是可以预测的，但是只有当我们了解到不同的信息点是如何联系在一起的时候。如果没有这种能力，浏览数据将是一种混乱、繁琐的体验。

图片[通过](https://www.flickr.com/photos/genista/6898950/in/photolist-BmPq-h8SMwA-asR9We-hANqky-6ZQ1ia-7gHY78-6b2mvv-HUu3n-c31keN-krGpEg-8D2xu1-5jqFVg-2PLYK-6z2FGd-5kjC5x-d4XVmq-9Q9sUZ-cqiFUw-eiZiTb-a5xQp6-9gLLmi-hiiggS-fxRvun-4GiNs4-64fGf6-dj5ZW5-hH6zMu-hiiia3-5HajLP-fKkEcr-9M2QU4-4CffYr-8v3k3Q-piRD7s-jhermP-4vSJoy-5JxTBh-cvhE2y-2mpRbt-fcFao-4fAVs4-2vVkpu-4jPTyW-a8pM1R-7L3UB8-dmhmrv-dPcqJ1-bN496n-73oHgx-8kJq43) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>