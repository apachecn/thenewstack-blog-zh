# 忽略 SLA 没有好处

> 原文：<https://thenewstack.io/ignoring-slas-doesnt-pay/>

违反服务水平协议(SLA)会产生令人瞠目的后果。问问 Slack ( [、800 万美元](https://www.insider.com/slack-takes-8-million-revenue-hit-2-hours-service-downtime-2019-9)、Robinhood ( [、7000 万美元](https://www.cnbc.com/2021/06/30/robinhood-to-pay-70-million-for-misleading-customers-and-outages-the-largest-finra-penalty-ever.html))、T-Mobile ( [、2000 万美元](https://ktla.com/news/nationworld/t-mobile-to-pay-20m-after-12-hour-nationwide-outage-led-to-thousands-of-failed-911-calls/))和韩国电信([、3400 万美元](https://www.koreatimes.co.kr/www/tech/2021/11/133_318025.html))就知道了。

您可能已经与服务提供商签订了 SLA。也许你在销售过程中坚持这样做，因为你加入了供应商。但是它回避了一个问题:您如何知道您的供应商是否达到了这个目标？如果发生违规，您如何收集违规信息？

## **如何衡量 SLA**

当我们定义 SLA 时，我们真正衡量的是什么？

我们可能会说，我们希望每月测量 99.99%的可用性。该服务必须在一个月的 43，800 分钟中运行 43，795.62 分钟。这意味着我的测量系统至少和我正在测量的系统一样可用，我的测量系统和正在测量的系统之间的网络也一样可用。

通常情况下，SLA 违反情况只在异常中断时才会被跟踪，因为跟踪 SLA 是很困难的。在我们这个买家当心的世界里，你需要自己留意这些服务。

## **SLA 无处不在**

 [基特·默克

Kit 是 Nobl9 的首席运营官，负责推动企业开发团队服务可靠性的社区和增长。在 Nobl9 之前，Merker 帮助 JFrog 成长为一家价值数十亿美元的公司，在此之前，他担任 Kubernetes 和 Google Cloud 相关容器计划的产品经理，同时也是 CNCF 的董事会成员。在加入谷歌之前，他在微软工作了 10 年。](https://www.linkedin.com/in/kitmerker/) 

在过去(2010 年代)，我们在内部服务器上运行定制软件。现在，您只需注册一个托管在他人云上的软件即服务订阅即可。随着这些 SaaS 服务和 API 的激增，SLA 也随之激增。

如果你问一个采购团队，在过去的 12 个月中，他们有多少 SaaS 供应商违反了合同 SLA，你可能会遇到令人不安的沉默。让服务级别协议脱离合同并进入操作系统是当今服务级别协议管理方式中的一个巨大缺口。

这种趋势只会继续下去。无论是在 CRM、人力资源、供应链/ERP、财务跟踪、支付、薪资、旅行还是其他各种业务线应用中，软件越来越多地以云服务的形式交付。甚至是在企业内部编写的符合其业务流程和规则的软件，也经常部署在云服务上。不同的组或团队之间可能有 SLA，称为服务级别目标，或 SLO，以减少威胁。

## **基本供应商 SLA 管理**

一旦您签署了 SLA，就要设置综合监控来监视服务。以编程方式对 SLA 进行编码，这样，如果违反了 SLA，监控系统可以自动通知您。理想情况下，这些证据会很快出现在你面前，所以你可以把它交给供应商，并立即请求补救。

随着时间的推移，您可以更好地了解哪些服务正在改进，哪些服务没有达到目标，这样您就可以更好地协商并提供有关其服务可靠性的详细反馈。了解供应商违反 SLA 是否会对业务产生切实的影响也很重要。也许这些服务并不像您想象的那样关键，您可以降低供应商的服务级别目标，并通过重新协商 SLA 来收回一些成本。

## **您对客户的 SLA 的考虑事项**

如果您要向任何规模的企业客户销售产品，您必须提供 SLA。有时，条款将由客户指定；在其他情况下你可以决定。您可以构建具有弹性和冗余的系统，以确保永远不会或很少会错过这些 SLA。最有可能的是，您的 SLA 处于对您的客户来说最低的水平。您可以设置稍微高一点的内部目标，为您提供一个风险缓冲和一个可量化的不可靠性量，它可以独立于 SLA 合同本身进行测量和管理。

对于工程团队来说，即使客户的体验非常令人沮丧，也很容易将次要的可靠性和性能问题视为“在 SLA 之内”。为了避免这种情况，定义几个由客户用例和期望内部驱动的细粒度目标，不同的目标基于真实世界的用户行为。

在当今竞争激烈的软件世界中，出色的用户体验和可靠性是每个客户都期望的关键特性。要想脱颖而出，你的服务必须强硬。

## **结论:忽略 SLA 没有好处**

如果你使用这些头条新闻中的服务却没有得到报酬，你不得不怀疑自己是不是个傻瓜。技术的进步来自于不断的改进激励，而违反 SLA 会在业务环境中产生这些激励。

公司不收集 SLA 信用的最大原因是，他们没有一个系统的方法来在第一时间跟踪和注意 SLA 违规，即使是可能不会产生多大业务影响的微小违规。也许在第一线感觉到了中断，但是那些人不知道如何提醒拥有合同的采购团队。这种脱节在大型组织中很普遍，许多供应商和 SLA 都是用法律术语而不是代码来描述的。

SLA 对于企业来说是一个现实，而且它们不会很快消失。对于期望一定服务水平的消费者和公司来说，这是一件好事。许多服务意味着许多 SLA，这些 SLA 需要从操作上进行衡量和分析。让供应商负起责任可以带来更好的创新和可靠性。此外，过于严格的 SLA 可以重新协商以节省成本。违反 SLA 会有很大的损失，先进的公司会密切关注这些损失，并通过 SLA 更好地管理供应商风险。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>