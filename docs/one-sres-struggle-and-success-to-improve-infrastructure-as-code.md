# 一个 SRE 的斗争和成功，以改善基础设施作为代码

> 原文：<https://thenewstack.io/one-sres-struggle-and-success-to-improve-infrastructure-as-code/>

10 月 9 日至 10 日，木偶赞助了这篇为[木偶 PDX](https://puppet.com/puppetize) 写的帖子。这个为期两天的多轨道会议将举办以用户为中心的开发运维及基础设施交付讲座和实践研讨会。

 [阿利·克拉克

Allee 是 Oscar Health 的一名 SRE，她积极参与动态证书基础设施的工作。在此之前，他在戴尔的数据科学团队工作，构建高度可用的集群。作为历史上黑人学院和大学(HBCU)的产物，具有文化责任感对他来说非常重要。Allee 也喜欢烹饪，把烹饪书当成教科书(希望有一天能出版一本)。](https://www.linkedin.com/in/alleexyz) 

去年，[Oscar Health](https://www.hioscar.com/about)-一家开发无缝技术并为我们的会员提供个性化支持的健康保险公司-由于员工和会员与我们产品的互动快速增长，决定拨出时间来改进我们的基础设施审查流程。Oscar 的目标是吸引我们的会员，让他们的医疗保健更容易操作、更透明、更实惠。值得注意的是，我们是一家全栈保险公司:我们建立了全栈技术平台来支持我们成员的医疗保健需求。

因为我们发展迅速，并且雇佣了大量的开发人员，我们希望确保这些团队不仅仅是支持我们基础设施的持续发展。然而，这并没有发生。当我们入职时，我们听说技术团队花费数小时手工构建系统，或者不得不等待数周让别人为他们构建系统。这不可避免地导致基础设施交付缓慢，并造成质量不一致，我们的基础设施工作变得不可重复。

最终结果是，我们在基础架构之上交付的所有应用和服务都不可避免地受到影响。

经过一些研究，我们发现意想不到和未经审查的更改是停机的主要原因之一。当务之急是我们要开始构建一个更好的基础设施实践，即代码和围绕它的文化。我们发现(至少在我的公司)基础设施作为代码更多的是文化的改变而不是技术的改变。

在这篇文章中，我们描述了我们为改进代码审查所做的关键事情，以改进我们的系统。它强调了我们面临的一些挑战，不仅是工具方面的挑战，还有团队动态方面的挑战——我们必须改变工作流程和系统，以减少我们基础设施的停机时间，并使我们所有的应用和服务表现良好，从而转化为更好的会员体验。

我们也进行了这种转变，部分是通过应用我们在 [Puppet 的](https://puppet.com/resources/ebook/gorilla-guide-infrastructure-code)指南中所学的内容，将基础设施转变为代码。我们用来帮助解决应用程序和服务交付问题的指南部分是关于代码审查基础设施的。

### 找到你想要的状态

收敛是我们的目标，因为我们期望我们的基础设施随着时间的推移达到代码中表示的期望状态。软件幂等性意味着软件可以想运行多少次就运行多少次，并且不会发生意想不到的变化。因此，我们构建了一个内部服务，它按照指定的方式运行，以在源代码控制中应用配置。传统上，我们的目标是实现无主配置设计，因此我们的配置代理会在主机上查找信息。

例如，一个特定的主机可以运行 N 个角色。数据一致性包括一个由配置任务组成的常见角色，例如确保每台主机上都安装了网络、服务和软件包。然后，主要角色被分解为次要和其他标记规则。

只有少数例外情况，需要不时地将凭据推送到特定主机。我们试图重构这些异常，不使用“SSH ”,因为我们认为 SSH-ing 本身就是一种反模式，这在可操作性方面造成了复杂性。(好在我们的工作基础设施中只有 5%依赖 SSH。)

### 将开发工作流程付诸实践

经验表明[基于主干的开发](https://trunkbaseddevelopment.com/)是持续交付和持续部署的关键促成因素。基于主干的开发鼓励开发人员致力于单个分支，以避免冲突。在 Oscar，我们称之为“世界”,它包括在我们公司构建特定软件所涉及的每个依赖项，还包括通过测试。

基于主干的开发有利于确保配置漂移不会发生。它还尽可能保持机器的一致性。从文化的角度来看，Oscar 关注于一种共享责任模型，在这种模型中，开发人员可以自由地为基础设施库做出贡献。我们希望差异包含尽可能多的上下文，包括但不限于设计文档和 JIRA/Phabricator 票证。差异和提交消息作为变更的历史记录，在重构、调查问题等时非常重要。，尤其是原创作者来来去去或者换团队的时候。

### 文档设计

执行基础架构升级应包括一份文档，其中包含建议的维护时间、发送给利益相关方的示例电子邮件、所有可能出错或出错的地方，以及升级和回滚步骤的清单(如果可能)。我们的清单概述了飞行前、飞行中和飞行后的计划。记录想法可以让别人提供专业知识，你可以学到很多东西。这也给了其他团队发言权，尤其是在做出影响其他团队的改变时。这有助于我们及早发现问题，而且成本低廉，易于实施。

### 代码评审过程的自动化

不要担心一开始 30%的自动化覆盖率。我们目前还没有实现一切自动化。尤其重要的是在提交级别向开发人员呈现构建输出，无论是格式化程序、静态分析器还是任何根据您的开发标准评估代码的工具。这可能包括变量声明、命名方案和其他样式检查。它们让每个人都更容易阅读并及早发现问题。增加反馈循环可以激励开发人员遵循标准。

另一个技巧:在提交时自动化 linters 和配置错误是迈向连续交付的良好步骤。

### 测试您的基础设施

例如，当引入具有一致算法的系统(如 [Raft](https://raft.github.io) )时，部署变得复杂。由于很难避免引入 Raft 和 ETCD 这样的服务，因此必须应用有效的金丝雀策略。例如，应用涉及为集群中的每个节点重新启动服务单元的配置并不是一个好主意。每个人都很难知道这些变化对特定应用程序的影响，即使是随叫随到的初级工程师也是如此。我们团队防止这些故障的一种方法是发送一个通知，告知在生产中检测到配置更改，需要手动交互才能使更改生效。

总是在生产中测试。在有些角色中，您可能只有生产实例，或者环境非常不同，您不得不“实时操作”一个例子是在敏感的日子测试字符集的变化，您不能把它带到非生产环境中进行测试。测试配置更改的例子没有我们希望的那么多，而配置更改不应该导致您的集群宕机。例如，[普罗米修斯](https://github.com/prometheus)提供了一个测试标志来测试配置。将此步骤添加到您的配置中，以确保配置能够构建和运行，并且在服务无法启动的情况下很难失败。

### 从已定义的模型实例化您的基础设施

将您的基础设施也视为一种服务。即使是第三方服务，运营它也是你自己建立的。尽可能用相同级别的发现、监控、警报和跟踪来对待服务，即使它是运行的一次性脚本。将它注册为一项服务，这样运营商或用户就不必使用 SSH 来判断它是否在运行。

我们花费了大量的时间去修理机器，看看配置是否在运行。我们开始添加一些指标来生成警报，以了解某个配置是否没有按照预期的次数运行。注册服务，以了解从主配置流程派生的子流程是否有 UI，以便操作员和用户可以知道配置当前是否正在运行。

### 深入了解 SLO 文化

如上所述，我们使用了一个[木偶指南](https://puppet.com/resources/ebook/gorilla-guide-infrastructure-code)作为代码来过渡基础设施。该指南还涉及我们使用过的其他流程，例如如何为您的基础设施代码设置[服务水平目标](https://landing.google.com/sre/workbook/chapters/implementing-slos/) (SLO)。

你的基础设施的用户不关心任何其他团队的服务性能。所有者想知道他们的服务是否会比现在做得更好。深入 SLO 文化让团队准备好围绕指标、可用性和可操作性进行交流。

主持基础设施实验室以获得支持。我们每周运行 SRE 实验室。我们 SRE 实验室的目标是让与运营系统交互的团队前来提问、获得反馈并了解基础架构团队的世界。教其他人如何配置、编写客户端代码，以及当您遇到错误率增加时应该做什么。当我们的 SRE 实验室专注于他们日常交互的服务时，我们的出席率增加了 200%。开发人员花时间分享他们对服务中断的反馈，以及从他们的角度看可用性如何。

### 我们下一步去哪里

我们现在正在进行更多的自动化测试，因为我们现在手动执行大部分测试。然而，在审核流程和更新过程中所做的这些小改动使我们能够做出明智的决策，并确保我们的基础架构能够以更加简单和可控的方式运行。

为了了解更多关于如何将基础设施转化为代码和其他 DevOps 流程的信息，我们邀请您参加 10 月 9 日至 10 日在俄勒冈州波特兰举行的[PDX](https://puppet.com/puppetize)。这是一个为期两天的多轨道会议，重点关注更广泛的 Puppet 用户社区，包括以用户为中心的 DevOps 和基础架构交付讲座以及实践研讨会。

来自 Pixabay 的 Zsóka Vehofsics 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>