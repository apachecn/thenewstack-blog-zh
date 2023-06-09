# 什么是数据可观察性，为什么它很重要？

> 原文：<https://thenewstack.io/what-is-data-observability-and-why-does-it-matter/>

[](https://www.montecarlodata.com/)

 [利奥·加维什

利奥·加维什是蒙特卡洛公司的首席技术官和联合创始人，这是一家由 Accel 和其他硅谷顶级投资者支持的数据观察公司。在蒙特卡洛之前，Lior 联合创立了网络安全初创公司 Sookasa，该公司于 2016 年被 Barracuda 收购。在 Barracuda，Lior 是工程领域的 SVP，推出了屡获殊荣的反欺诈 ML 产品。Lior 拥有斯坦福大学的 MBA 学位和特拉维夫大学的计算机科学硕士学位。](https://www.montecarlodata.com/) [](https://www.montecarlodata.com/)

2021 年，大多数企业的网站、宣传资料和职位描述都声称自己是数据驱动型公司。在这个令人向往的标签背后，你通常会发现一个令人钦佩的目标——仅此而已。除了大量未使用的数据之外。

善意的公司正在收集和存储数据，但不允许它实际驱动他们的运营。我们发现这通常是由于对数据本身完全缺乏信任，而不是毫无根据的。

随着公司从越来越多的来源收集看似无穷无尽的数据流，他们开始积累数据存储、管道和潜在最终用户的生态系统。随着复杂性每增加一层，数据宕机的机会(数据不完整、错误、丢失或不准确的时刻)就会成倍增加。

Forrester 估计，数据团队将超过 40%的时间花费在数据质量问题上，而不是致力于业务创收活动。太多的数据工程师知道那个惊慌失措的电话的痛苦——我仪表盘上的数字都是错的。一小时后我有一个报告。我们的数据怎么了？

在这一点上，不可靠的数据是预料中的不便。当然，这很痛苦，但这也是几乎每家公司经常遇到的问题。而且很难让你不信任的东西左右你公司的决策，更别说你的产品了。

## 数据工程团队能从 DevOps 中学到什么

二十年前，当一家公司的网站或应用程序关闭或变得不可用时，这被认为是意料之中的事情。如今，如果 Slack、Twitter 或 LinkedIn 遭遇宕机，就会成为全国性的头条新闻。在线应用程序已经成为几乎每个企业的关键任务，公司在避免服务中断方面进行了适当的投资。

这就是应用工程在过去几年中取得的进步。这正是数据工程需要去的地方。

我们预测，随着公司越来越依赖数据并投资于数据作为关键业务驱动因素，管道破裂、缺少字段、空值等情况将从可容忍的不便变为不可想象的罕见。当一个重要的仪表板看起来不正常时，高管不会让他们的数据团队领导快速拨号进行故障诊断，因为这不会发生。在未来十年，我们将达到数据可靠性的新水平。我们将跟随应用工程师的脚步，开发我们自己的数据操作专业，从而实现这一目标。

像 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 这样的领先公司的创新数据团队已经在[将 DevOps](https://thenewstack.io/the-basics-of-dataops-and-why-it-matters/) 的最佳实践应用到他们的数据管道和流程中。这些团队投资于工具，开发特定于数据的 SLA，并交付其公司蓬勃发展所需的高级数据健康。

随着我们看到更多公司的更多数据团队取得类似的进展，我们将进入数据工程的新领域:从一开始就防止数据停机。随着越来越多的公司优先考虑[数据可观察性](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/)，这一目标将会实现。

## 数据可观测性:数据工程的下一个前沿

简而言之，数据可观察性意味着通过监控、跟踪和故障排除事件来保持数据系统健康状况的持续脉动，从而减少并最终防止停机。

数据可观察性与应用程序可观察性有着相同的核心目标:最小化服务中断。这两种实践都涉及测试以及在停机发生时进行监控和报警。也就是说，数据和应用程序的可观察性之间存在一些关键差异。

应用程序可观察性回答了一些问题，例如，一个请求通过了哪些服务？性能瓶颈在哪里？为什么这个请求失败了？

数据可观察性应该告诉你，我最关键的数据集是什么，谁在使用它们？为什么 5000 排变成了 50 排？这条管道为什么会失败？

虽然应用程序可观察性围绕三大支柱(指标、日志和跟踪)展开，但数据工程师可以参考数据可观察性的五大支柱。我们需要明白:

*   **新鲜度:**您的数据表有多新？
*   **分布:**你的数据值是否在可接受的范围内？
*   **卷:**你的数据表完整吗？
*   **模式:**谁在什么时候对您的数据做了什么更改？
*   **沿袭:**您的数据环境的全貌，包括上游来源、下游来源，以及在哪个阶段谁与您的数据交互。

此外，与大多数软件应用程序不同，您的数据必须在不离开您的环境的情况下进行静态监控，以确保其安全。在理想情况下，数据可观察性工具不应该要求访问您的个人记录或敏感信息——而是依赖元数据和查询日志来了解您的数据血统并衡量其可靠性。

当达到数据可观察性时，数据团队将花费更少的时间来灭火。更多的员工可能会成为数据消费者，他们知道在哪里以及如何访问数据来指导他们的工作。高管们终于可以学会停止事后分析。

## 数据操作和数据可观测性的未来

实现数据的可观察性并不容易。但就像 2010 年代初的 DevOps 一样，DataOps 在这个刚刚起步的十年中将变得越来越重要。

我们预测，在接下来的五年内，所有的数据工程团队都将把可观察性融入到他们的战略和技术栈中。随着健康数据受到信任并得到良好利用，为技术和决策提供动力，越来越多的公司将获得数据驱动的绰号。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>