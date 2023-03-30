# 问与答:为什么开发人员处于“数据革命”的前沿

> 原文：<https://thenewstack.io/why-developers-lead-a-revolution-in-data/>

数据库领域充满了寻求让开发人员及其团队更容易在云原生环境中运行工作负载的供应商。

例如，随着最近发布的 [Aerospike Database 6](https://thenewstack.io/latest-aerospike-update-supports-large-scale-data-models/) ，数据平台公司 [Aerospike](https://aerospike.com?utm_content=inline-mention) 为其数据库增加了开发人员友好的特性，包括对 JSON 文档模型的原生支持和 JSONPath 查询支持。

在 5 月 4 日[虚拟 Aerospike Summit 2022](https://www.ampslide.com/e/aerospike-summit-2022-mission-now) 之后，新的 Stack 采访了 Aerospike 的首席执行官 [Subbu Iyer](https://www.linkedin.com/in/iyersubbu/) ，讨论了开发人员在他们的组织如何处理[数据](https://thenewstack.io/category/data/)中扮演的角色，以及他们在选择数据库时应该寻找什么。(为了简洁明了，这篇采访经过了编辑。)

**新的堆栈:许多组织很难充分利用他们收集的所有数据来改善他们的业务。据推测，其中一些问题将需要由数据分析师和数据科学家来部分解决。但是，开发人员在帮助解决这个问题方面有什么作用吗——如果有，是什么作用？**

**Subbu Iyer:** 尽管我们谈论了数据世界中的一切，但我相信我们可能正处于大多数组织的数据之旅的第一局。

在这一过程中起步较早的组织在解决这一问题的方式上相对于确定对他们来说真正重要的数据源来解决特定的业务成果或建立新的业务中断方面更加成熟。

我认为开发人员站在这场数据革命的最前沿，与其说是从数据的角度，不如说是从利用数据为企业带来颠覆性成果的角度。

![Portrait of Subbu Iyer, CEO of Aerospike](img/eafeb7779412eb9988781b2ea9f40454.png)

Subbu Iyer，Aerospike 的首席执行官。

作为一名开发人员，您尝试构建应用程序，或者尝试构建利用不同数据源的服务，并构建以前不可能的东西—无论是金融服务中的欺诈分析应用程序、电信或在线电子商务平台中的客户 360，还是在电子商务供应商中构建推荐引擎。

这实际上可以归结为老牌公司通过利用数据来构建以前不可能实现的服务和应用程序，而所有这些都是由开发人员完成的。

[数据科学家和数据工程师](https://thenewstack.io/why-data-jobs-are-hot-and-how-to-get-one/)确实发挥了巨大的作用，但是在光谱的末端是实际上推动商业价值的应用程序。

**企业[开发团队](https://thenewstack.io/category/devops/)在选择数据库之前应该问哪些问题？**

我们在实时数据和实时应用程序的世界中看到，一些关键组件非常重要。

第一，数据库是否提供可预测的性能？从规模角度来看，我选择的数据库平台是否有助于支持我的发展和抱负？

第二，数据库平台是否将具有高可用性？如果我要在这个数据库上建立一个任务关键型服务业务，我不能让它宕机。开发人员不必关心分布式数据库中的某个节点是否停机，或者是否必须添加某个节点来增加规模和容量。数据库的基础设施应该解决这个问题。

这些应用和服务的第三个方面是延迟。重要的不仅仅是您能够推动巨大的吞吐量，还有您能够提供低延迟，这两者都会影响客户体验和应用程序性能。

要考虑的另一个方面是，所有这些能否以可承受的成本实现？这是很多人实际上跌倒的地方。他们的旅程开始得很好，但后来他们发现自己在这场战斗中，收入增长很好，但他们的成本曲线在曲棍球杆上，这对他们来说是一个巨大的挑战。

**当他们的组织选择一个数据库，并且根据他们的组织的需求对其进行定制时，应用程序开发人员应该扮演什么角色？**

我认为开发人员必须有很强的话语权和一席之地。

要成为一名优秀的开发人员，你不仅要交付你今天正在做的东西，还要不断地尝试了解即将到来的事情——即将出现的新技术是什么。

我认为开发人员正在制定组织中一些最重要的决策。总的来说，无论是 DevOps 工具链还是真正利用数据和构建新服务，开发人员都是向公司和组织展示可能的艺术并推动组织内下一波颠覆的人。所以他们应该尽早入股。

开发人员和应用程序团队需要参与进来，因为他们是必须交付的人。

**对于需要使用数据库的开发人员来说，多云或混合架构是如何使事情复杂化的？你认为应对这些挑战最有希望的方法是什么？**

在当今世界，有时一个[云](https://thenewstack.io/category/cloud-services/)适合特定的服务，而另一个云可能适合另一个服务，你可能真的有一个基于[微服务的架构](https://thenewstack.io/category/microservices/)，它利用多个云平台。即使你不打算这么做，我认为大多数组织都希望利用多云平台。

开发人员必须做出的决定，尤其是在选择数据库时，是不是要在一个只在特定云上可用的数据库上构建我的服务，以及如何将我的服务真正迁移到另一个云上？

您希望寻找多云数据库，这样可以让开发人员的生活变得非常轻松，因为他们将时间花在他们试图构建的服务或应用程序上。数据库层本质上是相同的，您只需构建一次，然后将它部署在另一个云平台上，因为数据库已经在那个特定的平台上可用。

它与您决定在其上构建服务的任何基础设施选择相关。您需要确保它在多云架构上可用。

**您发现企业开发人员在使用数据库时最大的痛点是什么？**

我们在那里看到的是，当数据库不能满足他们的需求时，开发人员在苦苦挣扎。他们开始了旅程，然后在某个时间点碰了壁，他们面临一个选择，即，我是应该尝试真正实现这一点，并与我的运营团队一起花很多时间在这个特定的数据库平台上继续我的旅程，还是应该转换？

大多数情况下，他们会进行转换，但是对于组织来说，这是一个非常昂贵和痛苦的转换，不仅仅是开发团队。

您实际上可以让一个数据库支持多个模型。一个具体的例子是 Aerospike Database 6，我们现在实际上本地支持 JSON 文档。

我们有意构建对原生 JSON 和 JSONPath 查询的支持，因为我们看到客户在说，“如果你这样做，我们实际上可以在特定应用程序的多个工作负载中使用你的数据库，这使我们作为开发人员的生活变得非常容易。”

这确实是我们的愿景，建立 Aerospike 数据库和数据平台以支持多种模型，因为客户正在推动我们实现这一目标

<svg viewBox="0 0 68 31" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink"><title>Group</title> <desc>Created with Sketch.</desc></svg>