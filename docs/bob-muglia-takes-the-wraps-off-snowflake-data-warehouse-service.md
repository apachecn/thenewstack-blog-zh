# 雪花，一个新的数据仓库服务，由前 Windows 服务器主管 Bob Muglia 领导

> 原文：<https://thenewstack.io/bob-muglia-takes-the-wraps-off-snowflake-data-warehouse-service/>

前微软服务器和工具业务负责人、前 Juniper 高管鲍勃·穆利亚(Bob Muglia)终于谈到了他和 T2 几个月前作为首席执行官加入的初创公司[雪花](http://www.snowflake.net/ "Snowflake")。雪花是一个数据仓库即服务产品，允许用户组合结构化和半结构化数据。雪花完全支持标准 SQL，从头开始构建，具有一些独特的功能，旨在使其比其他选项便宜得多，并且不仅仅是数据科学家可以访问。

成本节约的部分原因是雪花巧妙地将计算和存储分离开来。结果是，分析师可以在早上上班，实例化一个虚拟仓库，并让它全天运行。分析师在当天离开之前关闭虚拟仓库，这样公司就不必为过夜支付费用。

“没有任何东西丢失，因为数据在 S3，”Muglia 说。"当你重新启动它时，它会动态地自我重建."

他说，这与大多数其他数据仓库技术使用的模型不同。“如果你看看 Hadoop 或其他产品，你要做的第一件事就是将所有数据加载到集群上。那需要几个小时。有了我们，你可以在几分钟内运行一个虚拟仓库，”他说。

结果是既容易启动又节省成本。雪花对虚拟仓库的使用和存储分别收费，这比亚马逊对 S3 的收费略高。

但是节约成本并不是雪花的主要驱动力。该服务旨在让企业将结构化和半结构化数据结合起来，并提供更易于使用的服务。

多年来，企业一直在使用传统的数据仓库收集结构化的交易业务数据，Muglia 将其描述为关于发生了什么的数据。在过去十年左右的时间里，许多公司已经开始使用 Hadoop 收集机器生成的数据，通常来自应用程序。他说，这些数据是半结构化的，回答了“如何”的问题。

“如果你能把“是什么”和“如何”放在一起，你就能获得一种否则不可能获得的理解水平，”穆格利亚说。但是这样做很难。“今天，传统的数据仓库不能处理机器数据，Hadoop 也不能很好地处理结构化数据，”他说。

除了结合结构化和半结构化数据，雪花的设计比其他数据仓库产品更易于使用。Snowflake 使其产品更易于使用的一种方式是将其作为服务交付。“如果您在内部或云中运行 Hadoop，您就是在自己运行环境。你在维护它，不得不备份它，照顾它。我们会为你处理所有的事情，”他说。

穆利亚认为，亚马逊网络服务的红移可能是云中雪花最接近的比较，但即使是它也更难管理。“AWS 使创建红移星团变得容易，但一旦你创建了它，你就得自己管理它，”他说。他将 Redshift 描述为更多的基础设施服务，而雪花旨在成为软件即服务。

其结果是，雪花用户可能不必争夺难以找到的人才。例如，为了运行 Hadoop，企业通常需要一名数据科学家和 Hadoop 运营人员。“我们接触过的每家公司都表示，几乎不可能找到这样的人，”雪花公司营销副总裁乔恩·博克说。“在这种情况下，你会开始说，‘鉴于找到那些人有多么困难，我不能做我想做的一切’。”

要启动并运行数据库，企业必须弄清楚数据库分布和数据库索引，确保每个队列都有资源，并重写工作不佳的内容。“所有这些都是我们关心的事情，”博克说。

该公司建立了完全支持标准 SQL 的服务。“我们从 c++和 Java 编译器开始，编写代码，”Muglia 说。

Snowflake 认为 SQL 的使用将使企业更容易使用它的服务。Bock 在 LinkedIn 上搜索了一下，发现许多人在他们的简介中提到了 Hadoop。他找到了 5 万人。对 SQL 进行类似的搜索，得到了 150 万个配置文件。

此外，因为雪花是为 SQL 构建的，所以它更容易与 Tableau 等数据可视化工具进行交互。他说，这种工具通常很难适应 Hadoop，因为 Hadoop 本身不支持 SQL。

雪花目前在 AWS 上运行，但被设计成能够在不同的公共云中运行。“这就是我们现在所处的位置，因为我们的客户数据就在那里，”Muglia 说。

目前，雪花与 Tableau、Informatica、Microstrategy 和 Excel 合作。Muglia 说，与这些工具的集成“相对简单”，但需要一些工作。

雪花并不是唯一一个试图让企业更容易地将结构化和非结构化或半结构化数据结合起来的公司。 [ExtraHop](https://thenewstack.io/extrahop-adds-mongodb-to-make-it-easier-to-combine-wire-data-with-other-corporate-data/ "The New Stack") 一直在说类似的想法。

穆利亚在 6 月份刚刚透露他已经加入了雪花公司。他之前在 Juniper 工作了几年，[去年年底](http://www.networkworld.com/article/2172638/lan-wan/juniper-evp-muglia-abruptly-quits.html "Network World")公司任命新 CEO 后，他离开了公司。然而，他更为人所知的是他在微软工作了 20 多年。在[离开软件巨头](http://allthingsd.com/20110110/head-of-microsofts-servers-and-business-unit-leaving-this-summer/ "All Things D")之前，穆利亚负责服务器和工具业务。当他离开微软时，他把火炬交给了现在已经成为微软首席执行官的塞特亚·纳德拉。

雪花今天宣布这项服务目前对测试用户开放。包括 Adobe、Accordant Media、White Ops 和 VoiceBase 在内的早期客户已经在测试这项服务。

雪花还宣布从红点风险投资公司、萨特希尔风险投资公司和 Wing 风险投资公司获得 2600 万美元的投资。该公司表示，计划将这笔投资用于产品开发和追逐客户。

图片来自 [Flickr](https://www.flickr.com/photos/miheco/ "Flickr") 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>