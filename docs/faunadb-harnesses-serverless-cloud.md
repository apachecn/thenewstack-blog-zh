# FaunaDB 利用无服务器云

> 原文：<https://thenewstack.io/faunadb-harnesses-serverless-cloud/>

如果您可以在开始创业时采用一个数据管理系统，它会随着您的成长而成长，从而消除添加另一个系统的需要，那会怎么样？

这是 FaunaDB 的目标，它将自己描述为一个全球性的、一致的和快速的自适应操作数据库。这家总部位于旧金山的初创公司刚刚推出了 [FaunaDB 无服务器云](https://fauna.com/blog/faunadb-serverless-cloud-launch-day)，它使开发人员能够在没有容量规划或供应的情况下实施和弹性扩展云应用。目前处于测试阶段的内部版本将在几个月后上市，同时还提供私有云版本。

在博客[的帖子](https://fauna.com/blog/faunadb-serverless-cloud-launch-day)中，首席执行官[埃文·韦弗](https://github.com/evan)宣称了几个“第一次”:

*   为无服务器应用程序构建的第一个数据库
*   第一个全球复制的数据库即服务
*   第一个面向公众的事务性、高度一致的多区域数据库

它还吹嘘自己是第一个跨亚马逊网络服务和谷歌云平台实时无缝复制数据的云数据库。它计划在今年晚些时候增加对微软 Azure 的支持。

## 因挫折而生

Weaver 和他的团队在为 Twitter 构建数据库的过程中遇到了挫折，于是他们创建了 Fauna。还记得“失败鲸”的盛行吗？

韦弗解释说:“当时 Twitter 陷入了进退两难的境地，因为 Twitter 是移动优先应用的先锋。

“在近三年的时间里，每当我们开发新硬件时，潜在的需求几乎会立即给我们划上红线，因为人们对 API 以及这段时间内用户的持续增长非常不满。

“我们构建的系统非常高效，但存在可扩展性和性能问题。它们非常不灵活，因为它们是单点解决方案。…我们真的很沮丧，因为在一家产品公司，运输货物和灭火的产品都有最后期限，我们永远无法达到逃逸速度并建立一个可重复使用的平台…这对产品团队来说是一个很大的拖累，”他说。

在离开 Twitter 成立新公司后，他们发现，对于寻求解决大规模灵活数据问题的公司来说，基本上没有什么变化，特别是灵活的运营数据。

他们看到了一种模式:公司会安装无数不同的数据库。

“他们会从 SQL 开始，然后是一些他们需要扩展或提高性能的数据的键值。然后他们会[使用]一个图表系统或地理空间的东西。然后他们会添加一个像卡夫卡一样的信息总线来把它们联系在一起。然后会有两个或三个或四个分析的东西。数据集将被复制 15 或 20 次，他们的工程团队将花费大部分时间来忙乱这个底层基础设施并试图集成它，产品速度将会停滞不前。这和我们在 Twitter 经历的是一样的，但它发生在各个层面，”他说。

“你现在可以在云中获得大型机器，所以你可以比我们在 Twitter 时更大程度地扩展单个工作负载，但基本上你不能安全地修改它，”韦弗说。“与相同数据集交互的团队越多，一些团队就越有可能引发问题。人们害怕更改模式或添加新的数据集。性能变得不可预测。因此，所有这些与规模相关的事情都还没有完全解决。”

“这就是我们开始动物学要解决的问题，”他说。

Weaver 和他的团队着手建立一个完全可重用的通用安全运营数据平台，让一家小公司以非常低的成本在无服务器云中起步，然后随着增长，其数据系统也将增长，而不必添加其他系统或重构应用程序来保持业务运行。

## 回到 80 年代？

在无服务器云上，用户不需要操作任何东西，只需为他们的活跃使用时间付费。它是关系型的，但不是 SQL。它是自适应的，因为它允许您动态地改变您的基础架构占用空间。

Weaver 将其描述为 80 年代 SQL 系统的一种倒退，当时有一个大型的整体系统，如大型机以及与之集成的一切。

云改变了这一点。他说，现在人们试图部署到商用硬件、分布式集群、多数据中心设置、混合云、私有云，并扩展到更高水平的吞吐量、可用性和数据规模，因此拥有一个大型大型机的生产力优势在 NoSQL 和单点解决方案中消失了。(他说人们正在逃离 NoSQL。)

所以动物群是云的整体模型，他说。您可以创建任意数量的子数据库。

他说，交互模型使用开发人员熟悉的现代应用程序开发模式。

“你插入文件，并在其上建立关系。所以你不需要去规格化任何东西。你也不需要像 SQL 系统一样扁平化。您可以从 SQL 中获得您想要的所有功能，如事务、唯一索引、复合索引和视图，但您也可以获得所有这些对现代应用程序开发非常有用的功能，如图形查询、临时功能，您可以及时查看您的数据库是如何变化的，为任何查询构建一个更改源。

FaunaDB 是用 Scala 和 Java 实现的，可以在任何现代操作系统上运行，包括 Linux、Windows、BSD 和 OS X。为了便于移植，它在 JVM 上实现，并通过类型安全的嵌入式 DSL(如 LINQ)进行查询。

MongoDB 用户将熟悉服务的文档模式，以及将所有这些索引组合在一起的能力。他说，用户可以在文档上建立一个常规索引，或者制作一个代表图形的不同索引，连接、相交以获得文档的时间视图，这样它就可以被输入到社交网络主题中，并补充说该公司计划扩展到更多的查询领域，如搜索和地理空间。

在其网站[上的示例 JavaScript 查询](https://fauna.com/product)返回城市犯罪观察报告的变更提要。它同时说明了图形查询、多级连接、索引和临时性。韦弗吹嘘说，其他语言的表达也同样简单。

## NVIDIA 的支持

该公司成立于 2012 年，过去四年一直在研究 FaunaDB。它已经筹集了 761 万美元，投资者包括太阳微系统公司的创始人[斯科特·麦克尼利](https://twitter.com/scottmcnealy)和数据狗公司的创始人[奥利维尔·波梅尔](https://twitter.com/oliveur)。

最近，Couchbase 的联合创始人克里斯·安德森(Chris Anderson)被任命为开发者体验总监。Fauna 还与 Serverless，Inc .合作，改善开发人员对无服务器架构的体验。

NVIDIA 是在私有云中为其多项服务使用动物群的企业客户之一。去年，它在多个数据中心推出了由动物群支持的 [GeForce Experience 3.0](http://www.pcworld.com/article/3117775/software-games/nvidias-faster-better-geforce-experience-30-launches-with-mandatory-registration.html) 【用于配备 GeForce 显卡的电脑的软件】。Weaver 表示，它一直在“大力推进企业故事”:运营、性能和功能集。

其他较小的客户包括服务业务软件供应商[Breezeworks](https://www.breezeworks.com/)； [Longform](https://longform.org/) ，一个策划文章的网站；还有 [ThinAir](https://www.thinair.com/) ，一家终端安全厂商，提供保护企业商业机密和知识产权免遭泄露的服务。

“为了满足客户的安全需求，我们经常需要快速、轻松地从云迁移到内部数据中心。FaunaDB 无服务器云独特地支持这些需求，”ThinAir 工程总监 [Cliff Moon](https://www.linkedin.com/in/cliffmoon/) 说。

特征图片:[动物园](https://www.flickr.com/photos/69709362@N00/14027379060/)由 [Ibinic](https://www.flickr.com/photos/69709362@N00/) 出品，授权于**CC BY-SA 2.0T9。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>