# 你能从东京 AWS 停电中学到什么

> 原文：<https://thenewstack.io/what-you-can-learn-from-the-aws-tokyo-outage/>

杰森·易(Jason Yee)

杰森是 Gremlin 的宣传总监，他帮助公司从失败中学习，建立更有弹性的系统。他还帮助领导 Gremlin 的内部混沌工程实践，使其更加可靠。

在电影中，东京似乎一直面临着灾难——地震和海啸等自然灾害，以及巨型怪兽和超大机器人等非自然灾害。9 月 1 日早上，机械化的庞然大物是亚马逊网络服务。

日本标准时间上午 7:30 左右，AWS 位于东京的 AP-Northeast-1 区域开始出现网络问题。停电影响了所有行业的业务，从金融服务到零售商店、旅游系统和电信。尽管有无法获得金钱、购买商品、旅行或相互打电话的麻烦，但日本人民表现出了韧性，证明了至少电影中的一些事情是真实的。然而，停电造成的经济损失预计将是巨大的。

在六个小时的停机后，AWS 解释了该问题，指出:“该事件是由于多个核心网络设备使用直接连接将网络流量连接到 AP-Northeast-1 区域内的所有可用性区域时出现问题。”AWS Direct Connect 是一项服务，可在 AWS 的基础设施和客户自己的内部系统之间创建专用网络连接。但围绕这些“核心网络设备”的细节以及它们面临的问题仍不清楚。

## 对每个人的影响

AWS 的中断只是由底层网络问题引起的越来越多事件中的另一个，包括 [Akamai 在 7 月的中断](https://www.nytimes.com/2021/07/22/business/internet-outage.html)和 [Fastly 在 6 月的事件](https://thenewstack.io/what-the-heck-happened-to-the-internet-fastlys-hard-fall-and-quick-recovery/)。当我们考虑这些事件以及它们对企业的影响有多大时，就出现了一个悖论:我们的系统同时变得越来越强大，越来越不可靠。

当我们考虑我们现在的计算资源与几年前相比时，很明显它们更强大，通常也更可靠。软件和硬件都有了很大的改进。但矛盾的是:我们的应用程序更加复杂，现在依赖于更多的外部服务和系统，这增加了我们对失败的整体敏感性。虽然我们控制的单个部分可能是健壮的，但是超出我们控制的几十或几百个依赖项已经引入了更多的风险。

那么，如何降低这种风险呢？

常见的解决方案是复制:添加更多可用区域、复制新区域或使用多个云提供商。适当规模的复制是有用的，在这一事件中，复制到 AP-Northeast-1 以外的地区可能足以缓解许多公司遇到的问题。但是复制也带来了额外的复杂性。

更实用的方法是使用混沌工程来主动模拟网络故障，更好地了解后果，并确定减轻这些故障的风险和影响所需的响应或复制工作。

## 理解复杂性的混乱

术语[混沌工程](https://thenewstack.io/chaos-engineering-business-value/)已经包含了使用故障注入来识别和测试技术系统中的风险的长期实践。事实上，混沌工程的一些最早采用者(甚至在它被赋予这个名字之前)是亚马逊的工程师。

在目前的实践中，混沌工程包括与科学过程相匹配的五个步骤:

1.  观察系统以识别潜在风险并收集基线数据。
2.  创建一个系统如何响应特定故障的假设。
3.  介绍故障并收集数据。
4.  分析数据。
5.  分享结果，这样实验就可以被复制和重复。

由 [Gremlin](https://www.gremlin.com/) 发布的 2021 年[混乱状态工程报告](https://www.gremlin.com/state-of-chaos-engineering/2021)——由 Dynatrace、Epsagon、Grafana Labs、[launch darky](https://launchdarkly.com/?utm_content=inline-mention)和[page duty](https://www.pagerduty.com/?utm_content=inline-mention)供稿——指出依赖性问题是事故最常见的原因之一。研究人员还发现，在模拟网络中断来测试这些问题方面有很强的吸引力。

遵循混沌工程流程来解决最近的 AWS 中断将从观察您当前的系统开始。您使用 AWS Direct Connect 或其他 AWS 服务的本地服务在哪里？如果这些服务受到 AWS 中断的负面影响，它们会对您的业务或客户带来什么风险？

创建一个假设可能很简单:当停机发生时，您预计会发生什么？但是，当您记录您的期望时，最好更广泛地考虑您的系统，并在您的假设中包括监控、警报、事件响应措施和业务连续性/灾难恢复计划(BC/DRP)。

注入失败的方法有很多:断开以太网电缆，调整服务器或网络设备上的联网配置，或者使用 Gremlin 这样的专用混沌工程工具。重要的考虑事项是选择一种允许您在必要时快速恢复服务的方法。您不希望在准备停机时造成停机。

根据我在混沌工程方面的经验，分析数据很容易。故障引起的问题很明显，通常分为两类:

*   **我们可以解决的事情**，例如配置自动故障转移或重启，添加队列和缓存系统以进一步分离系统，或者改进重试、超时和断路器。
*   **我们不能解决的事情**，但是可以创造周边的流程。这包括改进监控和警报以更快地发现问题，更新行动手册和响应计划，以及改进响应者的通信。

我们复杂系统的挑战之一是它们也是动态的。新代码、新部署和新服务不断改变着环境。因此，混沌工程过程的最后一部分是共享和迭代——这不仅是为了我们能够不断改进，也是因为我们知道我们的系统明天将会不同。

## 准备

AWS 在东京的中断只是重大事故的一个例子，但因为现代应用程序如此依赖第三方服务，所以我们为这些和类似的中断做好准备是很重要的。随着我们的系统变得更加相互关联，我们不太可能降低复杂性，但是通过实践混沌工程，我们可以采取主动措施来更好地理解和减轻风险。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>