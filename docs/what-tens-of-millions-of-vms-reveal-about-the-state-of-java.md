# 数以千万计的虚拟机揭示了 Java 的什么状况

> 原文：<https://thenewstack.io/what-tens-of-millions-of-vms-reveal-about-the-state-of-java/>

[](https://www.linkedin.com/in/benevans2/?originalSubdomain=es)

 [Ben Evans

Ben 是一位真正的 Java 大师，在位于巴塞罗纳的 New Relic 欧洲开发中心工作。他还是一名 Java 冠军，三次 JavaOne 摇滚明星演讲人，并且是 Java 书籍的多产作者，包括《扎实的 Java 开发人员》和《优化 Java》的主要作者，以及新版《Java in The 坚果壳》。他作为 Java 社区过程执行委员会(又名 JCP EC)的成员花了六年时间帮助定义 Java 生态系统的标准](https://www.linkedin.com/in/benevans2/?originalSubdomain=es) [](https://www.linkedin.com/in/benevans2/?originalSubdomain=es)

现代软件业非常庞大，可供选择的编程语言并不短缺。然而，即使在单一的技术堆栈中，比如 Java 生态系统，也很难对其市场得出有用的结论。Java 取得了令人难以置信的成功，它出现在几乎每一个主要的行业和经济部门——这在一定程度上是为什么很难对 Java 生态系统的状态有一个明确的观点。

但这并不意味着我们不能尝试评估世界的状况。

每天，数千万个 Java 虚拟机(JVM)与 New Relic 共享它们的数据。为了创建这份报告，我们对这些数据进行了匿名化和粗粒度化处理，以给出我们所看到的 Java 生态系统的一些总体概述。我们还避免了任何可能帮助攻击者和其他恶意用户使用 JVM 数据的详细信息。

我们这些观察的目的是提供一些关于 Java 生态系统现状的新的背景和见解。也就是说，我们看了以下几类:

*   生产中使用哪些 Java 版本。
*   最受欢迎的供应商。
*   最常用的垃圾收集算法
*   最常见的堆大小配置。

## 目前，Java 8 仍然是标准

让我们从 Java 开发人员一直好奇的一个问题开始:哪些版本在生产环境中使用得最多？请考虑下表:

注意:我们将 Java 8 的结果分成三部分:

*   当前:最近更新，不容易受到任何重大的最近简历。
*   滞后:具有与 Java 版本年龄相关的潜在重大风险。
*   易受攻击:对于运行这些版本的团队来说，这可能是一个严重的问题。

正如你所看到的，Java 11——一个长期支持版本——正在慢慢普及，但与 Java 8(也是 LTS)相比，市场似乎仍然犹豫不决。值得注意的是缺乏对非 LTS 版本的采用——Java 7 的使用量(2.54%)仍然是所有 Java 8 之后的非 LTS 版本总和(1.14%)的两倍多。

## 非 Oracle 供应商的崛起

我们在过去一年中观察到的另一个主要动态是，社区中对非 Oracle Java 供应商的接受度越来越高。

甲骨文现在只占 Java 市场的 75%。社区主导的 AdoptOpenJDK 是第二大受欢迎的供应商。我们的历史趋势数据(我们没有公布，因为它基于比主数据集小得多的样本量)表明，AdoptOpenJDK 的受欢迎程度逐月显著提高。

特别值得注意的是，在向 New Relic 报告的 AdoptOpenJDK 虚拟机群体中，几乎三分之一(33.19%)是 Java 11。这代表了在 AdoptOpenJDK 用户中使用 Java 11 的比率比在普通人群中高得多。

注意:为了完全公开，New Relic 是 AdoptOpenJDK 项目的赞助商，并为该项目贡献了工程时间。

## “垃圾收集”算法进展如何

由于在内存管理中扮演的角色， [Java 垃圾收集](https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html)在社区中是一个兴趣无穷的话题。根据我们的数据集，各种垃圾收集算法的市场份额如下:

概括地说，这些选择反映了不同 Java 版本上使用的默认收集器。然而，当我们按 JVM 版本分面时，出现了一些有趣的结果:

*   CMS 在 Java 8 上比 G1 更受欢迎(14.56%比 12.59%)。
*   在 Java 11 上，CMS 比 Parallel 更受欢迎(3.96%比 0.20%)。
*   CMS 在 Java 11 上的受欢迎程度是 ZGC 的 35 倍。

## 签入堆配置

如果不看一下[堆大小](https://docs.oracle.com/cd/E13150_01/jrockit_jvm/jrockit/geninfo/diagnos/garbage_collect.html)配置，Java 中关于垃圾收集和内存管理的讨论是不相关的。堆大小配置由一对值定义，即堆的最小值和最大值(通常称为 Xms 和 Xmx)。下表根据我们的数据列出了前 30 个最常见的堆大小，为了便于理解，我们将它们标准化为 MB。

令人惊讶的是，这表明 JVM 堆的大小仍然相对较小——这似乎与产生迎合越来越大的堆的算法的趋势相反。

特别是，可能会变得大于 16GB(即 set Xmx >= 16GB)的堆仅占总堆数的 3.3%。

“固定堆”标志组合的持续出现——其中 Xms 和 Xmx 具有相同的值——是另一个重大惊喜。我们的数据显示，33.48%的 JVM 仍然使用这种组合运行。

在自适应调整算法的早期版本中，使用这种组合运行可能有一些优势，但对于现代工作负载，它几乎总是适得其反。如果设置了这种组合，JVM 在如何调整堆的大小和形状方面就会受到限制，从而降低了对流量行为或请求速率的突然变化的响应能力。

如果您的运行时中存在这种组合，那么您可能希望运行一些测试，看看是否可以删除它以获得更好的垃圾收集性能。

## 一些随机但有趣的东西

总结一下，这里是我们观察到的五个有趣的数据:

1.  7.35%的 Java 8 JVMs 使用不推荐使用的标志运行(尤其是 MaxPermSize)。
2.  6.78%的 JVM 运行时启用了实验标志。
3.  8.07%的 JVM 具有在启动字符串中出现不止一次的重复标志。
4.  2.54%的 JVM 有“不匹配标志”，说的是矛盾的事情；例如，标志指定并行 GC 和 G1GC。
5.  2.59%的 JVM 将最大堆大小设置为 819MB。这几乎肯定是 8192MB(即 8GB)的一个错别字。仔细检查您的配置—剪切和粘贴配置是危险的。

## 结论

这份报告中的主要偏见是，我们只看到了向新遗迹报告的数据。这绝不是对 Java 市场的完全准确的描述，我们认识到在我们的数据中存在选择和其他不太明显的偏差。此外，我们意识到，本地化趋势可能会导致我们所展示的内容出现小范围的显著变化。例如，特定行业(如医疗保健或金融服务)的 Java 团队通常在严格的法规下运作，这些法规阻止他们及时地在版本之间移动。

然而，我们每天都会看到来自数百万个 JVM 的实时数据，这些不断变化的数据流代表了整个 Java 市场。

我们将这些数字呈现给 Java 社区，希望以一种积极的方式为正在进行的关于 Java 整体发展轨迹的精彩对话做出贡献。我们绝不打算声称“我们有所有的答案”或诋毁他人的工作。这显然是一次共同的旅程。

每一位 New Relic 客户都可以免费获得其生产环境的这一级别的详细信息。如果您是 New Relic 的客户(或者如果您愿意),并且希望看到这些见解，请与您的 New Relic 联系人联系，了解如何查询这些数据或构建自己的仪表板来跟踪这些数据。

我们将非常乐意帮助您按照您的方式观察您的系统，因为您将继续生产更完美的软件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>