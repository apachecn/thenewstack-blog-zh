# Grindr 建立了一个可扩展的平台，以扩展其服务范围

> 原文：<https://thenewstack.io/grindr-settles-scalable-platform-expand-range-services/>

是什么将一个平台与一堆软件区分开来？首先，一个平台可以让企业轻松地扩展到新的服务和市场，而没有相应的扩展痛苦。

这可能是从移动社交网络服务 [Grindr](http://www.grindr.com/) 如何管理 IT 中获得的经验。Grindr 是一个非常成功的纯移动地理社交网络应用，旨在帮助同性恋和双性恋男子与附近志同道合的人联系，Grindr 正计划将其服务扩展到联系之外，以满足一系列生活方式的需求。想想附近美味餐馆的 Grindr，或者寻找好节目的 Grindr。

有了新平台，由于平台的可扩展性，这种扩展变得更加容易。

“我们有一个巨大的机会。Grindr 首席技术官卢卡斯·斯利卡(Lukas Sliwka)说:“我们正在谈论我们多年来建立的一个庞大的用户生态系统。“我们的愿景是，在接下来的几年里，把我们的平台变成一个地方，让同性恋者不仅可以了解他周围的人，还可以了解他周围发生的事情。”

大约两年前，Sliwka 在那里成立，当时公司只有 4 名软件工程师(现在已经增加到 40 名)。当他第一次签约时，斯利卡最初并不担心拓展新市场。相反，他有一个更紧急的任务:稳定公司的平台，并达到一些 SLA(服务水平协议)。

作为一个社交网络服务，Grindr 是巨大的。这项服务有大约 200 万活跃用户，他们经常使用这项服务。每个用户平均每天花大约一个小时在网站上，比脸书用户平均每天花的时间还多。目前，该公司的使用高峰是太平洋时间周日下午 3 点 30 分左右，超过 100 万用户可以使用这项服务。这可以转化为每秒 10，000 到 20，000 个 API 请求，以及大约 1，5000 到 2，000 条聊天消息。

## 第一项任务:建立 SLA

当 Sliwka 加入时，该平台主要基于 Ruby-on-Rails，并运行“团队从零开始构建的一系列不同的定制技术，”Sliwka 回忆道。

因此，所有这些定制工作相当于“一个管理和维护成本非常高且相当脆弱的基础设施”，斯利卡说。“因为它是定制的基础架构，所以没有定期更新的好处。”

例如，Grindr 作为一种位置辅助服务，需要强大的地理空间算法，这是该公司自己创造的，尽管谷歌提供了非常合适的算法。另一个特性 chat 最初是由 Jabber 拼凑而成的。

> “你不想浪费这些人的周期来管理已经解决的事情”——Lukas sli wka。

Sliwka 的第一个任务是找到那些可以被一些更容易管理的现成技术取代的自制组件。

Jabber 被一个更易管理的[mongoseem](https://www.erlang-solutions.com/products/mongooseim.html)栈取代了，它得到了 Erlang Solutions 的支持。该公司还引入了 [ObjectRocket](http://objectrocket.com/) ，它基本上将 MongoDB 打包为服务，因此可以轻松部署。

在一年之内，在重构客户端并向“拥挤率”或最大可能的流量调整后，团队能够保持一致的 SLA，最大限度地减少中断。

## 下一步:构建可扩展的平台

因此，在 2014 年年中，Sliwka 采取了下一个合乎逻辑的步骤，即制定一个更具可扩展性的架构。他召集了一个架构团队，让他们躲在一个僻静的地方，构建一个将成为公司“新堆栈”的蓝图，并在接下来的一年中实施。

Ruby-on-Rails 将一去不复返，取而代之的是一系列强调非阻塞 I/O 的技术，包括高度可扩展的基于 Scala 的框架。

对于这个框架，该团队考虑了 Node.js 和 Go 框架，尽管该公司担心他们无法找到足够的开发人员来覆盖这项技术，至少无法达到 Grindr 所需的规模。

“我不觉得我们的开发者生态系统有必要的经验，我们可以从中招聘，”斯利卡说。“我可以告诉你，即使是 Java，雇佣大规模工作过的 Java 人也容易得多，因为 Java 作为一个企业已经存在了很长时间。即使是 Java 人员，也很难找到熟悉解决这种规模问题的工程师。”

对于配置管理，Grindr 使用了 [Apache ZooKeeper。](https://zookeeper.apache.org/) Amazon Web Services 提供了基础设施，所以应用程序是通过 [Amazon Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/) 打包和部署的。

该公司使用开源的 RabbitMQ 进行后端消息传递，但该公司没有试图在内部维护它，而是购买了 [CloudAMQP](https://www.cloudamqp.com/) 的服务。对于缓存层， [Redis Labs](https://redis.com/) 提供了一个高度可扩展的 Redis 集群。[酱实验室](https://saucelabs.com/) 和 [Appium](http://appium.io/) 用于自动化大部分所有的功能测试。

一家名为 [Treasure Data](https://www.treasuredata.com/) 的公司处理数据捕获、摄取和加密。MongoDB 的规模可能很大，它被剥离了许多职责，转而支持[弹性搜索](https://www.elastic.co/)。为了帮助将延迟降至最低，Grindr 使用 [CloudFlare](https://www.cloudflare.com) 内容交付网络(CDN)来传输文本和照片等静态材料。

斯利卡说，所有这些外包背后的想法是“最大限度地减少对我们内部 DevOps 团队的依赖”。

“我非常支持的一件事，尤其是对初创公司或中型公司而言，是随着你的成长，你希望确保你的工程部门专注于对竞争优势贡献最大的事情。你不希望浪费这些人的周期来管理已经解决的事情，”斯利卡说。

到 2015 年 6 月，新的堆栈已经启动并运行。现在，下一步是重新定义 API，将功能扩展到新的面向用户的特性。许多服务已经或正在被重新架构为微服务，因此它们可以在多种用例中使用。

有了基础设施，Sliwka 现在能够集中精力为附加服务获取正确的数据。Sliwka 说，Grindr 现在正在雇用一个数据科学团队，“扩展我们的数据处理能力，以便能够开始将一些深度学习应用到我们去年收集的数据中”。

“这非常令人兴奋，因为我们采取的方法是真正专注于建立一个平台，专注于提供微服务和可重复使用的组件，”斯利卡说。“因此，当我们构建所有这些不同的部分时，约会和会面引擎只是公司平台的一个应用程序。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>