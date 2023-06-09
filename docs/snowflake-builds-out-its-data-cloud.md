# 雪花构建了它的数据云

> 原文：<https://thenewstack.io/snowflake-builds-out-its-data-cloud/>

周二在拉斯维加斯举行的年度[峰会](https://www.snowflake.com/summit/)上，云数据 rockstar [Snowflake](https://www.snowflake.com/) 发布了一系列公告，表明其打算超越其惯常的数据仓库专业化，并在数据和分析领域涉足众多其他类别。这些包括数据湖、操作数据库、流数据和数据科学用例。该公司甚至打算提供一个应用平台。显然，雪花正在采取措施，使其[数据云](https://www.snowflake.com/data-cloud/)愿景不仅仅停留在口头上。

我将涵盖大部分公告，从我认为最具变革性的三个开始:用于内部存储的外部表(现在在私有预览版中)、对基于 [Apache Iceberg](https://iceberg.apache.org/) 的表的支持(正在开发中)和面向行的存储(也在私有预览版中)。我还将涉及一系列面向开发者的披露，甚至还提供一些合作伙伴公告的摘要。开始了…

## 数据云出诊

要介绍的第一个公告——内部数据的外部表——描述起来相当简单。它允许雪花查看和查询存储在其权限之外的对象存储中的数据。任何亚马逊 S3 兼容的对象存储都可以与 Snowflake 联合，这包括内部存储。虽然 S3 可能会让你想到亚马逊网络服务和公共云，但现实是 [S3 API](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html) 已经成为通常安装在企业数据中心的企业对象存储平台的标准——存储在那里的任何数据现在都可以通过雪花访问。这显然不仅包括查询数据的能力，还包括管理数据的能力。

这样的能力并不是雪花独有的。大多数操作数据库已经有提供类似功能的外部表工具。微软甚至在其旗舰数据库的下一版本 SQL Server 2022 中为其外部表工具添加了 S3 API 兼容性，该版本现已公开预览。许多拥有外部表的平台都将其作为查询客户数据湖的桥梁。在雪花案例中，您可以这样使用外部表，但是该公司通过另一个新特性将这种能力提升到了一个新的水平:Apache Iceberg 表。

## 冰山一角

在上周给分析师的一份特别简报中，雪花的产品高级副总裁克里斯蒂安·克莱纳曼(Christian Kleinerman)说，“会议上最重要的宣布之一可能是推出冰山桌。”虽然它仍在开发中，雪花说，它将很快在私人预览，坦率地说，甚至宣布 Apache 冰山支持是耐人寻味的。Iceberg 是一项开源技术，用于将事务/ACID(原子性、一致性、隔离性和持久性)逻辑添加到以开放文件格式存储的数据中，如 [Apache Parquet](https://parquet.apache.org/) 。它还提供了时间旅行功能，因此您可以在执行某些更新、插入或删除之前看到数据的先前状态。冰山是提供这种功能的三种主要技术之一，另外两种是[三角洲湖](https://delta.io/)和[阿帕奇胡迪](https://hudi.apache.org/)。

事实证明，雪花将使 Iceberg 成为数据库中表的一流存储选项——有效地使其成为雪花查询引擎原生支持的附加存储格式。表面上，客户可以选择 Iceberg 作为逐个表的持久性格式，支持传统表支持的几乎所有操作，包括标准的 DML(数据操作语言)和 CRUD(创建、读取、更新和删除)操作，以及加密、复制、治理、压缩、市场兼容性和集群，所有这些都具有 Snowflake 所说的可与传统表媲美的性能(在个位数百分比内)。

同时，由于 Iceberg 是一种开放格式，其中的数据也可以通过一些开源的数据湖技术进行查询，包括 [Apache Spark](https://spark.apache.org/) 、 [Hive](https://hive.apache.org/) 和 [Flink](https://flink.apache.org/) 以及 [Presto](https://prestodb.io/) 和 [Trino](https://trino.io/) 。同样重要的是，它也可以在数据科学环境中使用。Iceberg 支持本质上是 Snowflake 在自己的平台上展示了 data lakehouse 范式，它与 Snowflake 的许多面向开发人员的增强功能联系在一起，我们稍后将对此进行介绍。

## **优利商店**

在我们讨论新的开发特性之前，让我们先来看看雪花的另一个重要声明:Unistore 和混合表。这些技术共同实现了面向行的存储选项，这将首次允许雪花承担*运营*数据库工作负载。

将给定行中的所有值存储在一起对于添加新的数据行，或者查找特定的行，然后更新或删除它们非常有效。但是，如果您正在进行分析，其中您通常在一个巨大的行数组上聚合一个或两个列中的值，那么最好将这些列值存储在一起，以便可以快速计数。

这就是为什么操作数据库本身使用行存储技术，也是为什么大多数数据仓库本身使用列存储技术。这也是为什么近年来许多运营数据库在其行存储领域中增加了列存储技术，以承担所谓的运营分析工作负载。

在雪花的 Unistore 和 Hybrid 表的情况下，我们有相反的情况:一个添加行存储技术的列数据仓库平台，以便承担操作负载。顾名思义，混合表允许数据库中的一个表以两种格式存储，这样所有的工作负载都可以使用它。混合表也可以在查询中与传统表连接，Snowflake 将负责实现这一点的必要机制。

雪花承担运营工作负载的最大原因之一是因为大多数业务应用程序在运营环境中工作。雪花希望开发者在雪花的数据云中运行这些应用。

## 开发者优势

开发前沿发布了几个公告，其中很多对 [Python](https://www.python.org/) 社区特别有意思。其中最大的一个是围绕着 Snowflake 称之为原生应用框架的东西，现在在私有预览中。诚然，对原生应用程序的完整愿景和今天的预览版之间存在差距，但这个想法很有吸引力。原生应用程序框架最终将促进全功能应用程序的开发，开发人员可以构建和销售这些应用程序，雪花客户可以购买这些应用程序并在自己的雪花环境中运行。这将允许这些应用程序创建和维护的数据确实非常本地化，从而提高性能。它还将减轻开发者以这种方式部署他们自己的应用程序的任务，但将确保开发者不会直接访问客户的数据。因此，本地应用框架将一举解决客户的性能、安全性和合规性问题，甚至允许小型开发人员提供这些保证。

目前，原生应用将真正提供一种机制来打包和部署雪花资产，如存储过程、用户定义的函数和外部函数。您是否应该考虑将这些资产的集合构成一个真正的应用程序，这是一个值得讨论的问题。但是情节会变得更复杂。这是因为雪花今年早些时候收购了 Web 应用开发平台 Streamlit T1。雪花表示，它正在努力将 Streamlit 集成到其平台中，从而集成到原生应用框架中。除了上面提到的雪花服务器端资产之外，这将支持使用 Python 开发应用程序前端。此外，混合表和 Unistore 的可用性将意味着这些应用程序实际上可以运行，而不仅仅是提供分析功能(尽管这也是可能的)。

Snowflake 表示，它之所以这样做，是因为它已经注意到了客户在单个 SaaS 应用程序中有多少数据，以及将这些数据引入仓库所涉及的痛点，无论是通过数据管道还是数据虚拟化。雪花说，基于云的应用程序的流行本质上“重新存储”了数据。因此，原生应用程序框架计划旨在通过将应用程序及其数据直接放入客户的雪花环境中来消除这些数据的孤岛。

## 通过流式传输和安全性进行强化

雪花还通过一个名为 Snowpipe Streaming 的功能，增加了对无服务器接收流数据的支持，该功能目前正在私人预览中。该公司还有一个仍在开发中的附加功能，称为物化表，它将提供一种机制，用于对输入的数据进行声明性转换。

在一份有点相关的公告中，雪花表示，它将增加对网络安全工作负载的支持，这将允许对大量结构化、半结构化和非结构化日志数据进行密集分析。

## 蟒蛇变色龙

站在开发前沿，Snowflake 正在全力开发 Python 技术。除了前面提到的将使用 Python 的 Streamlit 平台直接集成到 Snowflake 之外，作为与 [Anaconda](https://www.anaconda.com/) 合作的结果，该公司还宣布在其 [Snowpark](https://www.snowflake.com/snowpark/) 开发者框架上公开预览 Python 作为受支持的语言。Snowflake 还将支持使用来自 Snowpark for Python 环境的一系列开源 Python 包和库。

还有更多。一个名为 Snowflake Worksheets for Python 的新功能(现在处于私有预览版)允许用 Python 编写管道、ML 模型和应用程序，并直接在 Snowflake 的用户界面中开发， [Snowsight](https://docs.snowflake.com/en/user-guide/ui-snowsight-gs.html) 。目前正在开发的大型内存仓库将为大量内存密集型任务提供便利。例如，数据科学工作负载(如功能工程或训练模型)将能够直接在雪花中的大型数据集上执行，有适当的内存资源进行备份，而无需将数据提取到不同的环境中，这两者都有助于提高性能。

一旦这些模型经过训练，非数据科学家将能够在完全不使用 Python 的情况下对它们进行预测。这是因为雪花将添加一个名为 SQL 机器学习的功能(目前在私下预览中)，让拥有 SQL 技能集的开发人员直接在他们的查询中嵌入针对 ML 模型的预测。

## 数据合作伙伴

如果所有这些来自雪花本身的声明还不够，许多合作伙伴的声明也将在雪花峰会上宣布。以下是其中几个的摘要:

*   [Informatica](https://www.informatica.com/) 宣布了一个新的企业数据集成器，它将在雪花数据云中集成来自一系列来源的数据；该公司还为雪花发布了一个新的免费数据加载器，并在 Informatica 的云数据治理和目录服务中发布了新的雪花特定数据治理功能的私人预览。
*   [Fivetran](https://www.fivetran.com/) 宣布了一种新的高容量连接器以及其雪花集成范围内的新功能。
*   ALTR 宣布了一个新的策略自动化引擎，用于管理雪花和其他平台中的数据访问控制。
*   [StreamSets](https://streamsets.com/) 宣布其最新引擎[stream sets Transformer for snow flake](https://streamsets.com/products/dataops-platform/transformer-engine-snowflake/)全面上市，据称该引擎基于 Snowpark 打造
*   主数据管理供应商 [Semarchy](https://www.semarchy.com/) 上周宣布了针对雪花的 xDI，它增加了雪花特有的功能。
*   [数据可观察性/数据质量提供商 Acceldata](https://www.acceldata.io/) 上周宣布了自己与雪花的集成，以实现“雪花环境的洞察、控制和支出智能”，具体围绕数据、处理和管道编排。
*   [Rockset](https://rockset.com/) 宣布自己与雪花整合，为开发者提供对包括[阿帕奇卡夫卡](https://kafka.apache.org/)、 [AWS DynamoDB](https://aws.amazon.com/dynamodb/) 和 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 等来源数据的访问，并将其与雪花中的数据相结合。

## 铲雪

这里有很多东西需要吸收，重要的是要记住，大多数宣布的技术都处于预览阶段或仍在开发中。但是他们来了。一旦他们来到这里，他们将大大增加雪花试图竞争的战线的数量。尽管该公司一直认为自己不仅仅是一个数据仓库，但事实仍然是，它以前一直非常专注于分析领域，并在那里进行了非常激烈的竞争。

雪花峰会上宣布的举措极大地改变了游戏，并将公司置于一些非常拥挤的领域——如运营数据库和应用程序开发——有时竞争是一场底部竞赛。这样一家热门公司将如何应对这些新的竞争领域可能带来的艰难困苦？我们走着瞧。但那些可能做空该公司的人应该预先得到警告:雪花的管理团队的集体行业经验是令人生畏的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>