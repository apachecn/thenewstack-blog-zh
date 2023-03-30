# 为什么人工处理的源代码属于 Git

> 原文：<https://thenewstack.io/why-human-processed-source-code-belongs-in-git/>

本系列中关于人工处理代码的更多内容:

GitLab 赞助了这篇文章，预计 [GitLab 将于 10 月 9 日在伦敦](https://about.gitlab.com/events/commit/)提交。

 [达尔文·萨诺伊

Darwin 是 Infor 的高级云架构师和 DevOps 工具团队负责人。他对自动化的职业关注引发了他对云、DevOps 和 CI/CD 的热情。他和他的两个孩子和妻子住在费城附近。当他不在路上试图弄坏他的山地车时，他就在车库里调音。](https://www.linkedin.com/in/DarwinSanoy/) 

很容易认为代码只是计算机的事情，但事实上，几个世纪以来，人类一直在编纂各种知识。有一种类型的人类知识更像计算机代码，那就是流程执行知识。

我们都熟悉计算机执行代码的概念——它采用结构化的指令并执行它们，以产生预期的最终结果。计算机非常擅长这种细致的工作，可以多次完美地执行指令。

那么，在人类领域中，对等物是什么呢？为达到预期的结果，必须完成的一组详细的有序步骤怎么样？这似乎是对程序清单的恰当描述。

[《清单宣言》](https://en.wikipedia.org/wiki/The_Checklist_Manifesto)这本书描绘了清单的使用如何通过在细致和重复的人工执行任务中实现一致性来对质量结果产生巨大影响。清单实际上在许多高风险的情况下挽救了生命，比如开飞机和做手术。

GitOps 承诺确保成功构建和运行软件所需的一切都存储在 Git 中。事实上，Git 最终充当了真理的唯一来源。然而，大多数时候我们秘密地将“一切”限制为“计算机执行的一切”，而忽略了人类为确保软件完整性而做的事情。

虽然对“Git 中的一切”原则的真正承诺会鼓励在 Git 中存储人类执行的清单，但在人类代码和最终自动化这些过程的计算机代码之间存在一些更深层次的联系。

这里真正的焦点是软件成功的可操作清单(尽管我们会在总体上讨论很多关于清单的内容)。将它们视为构建、部署或测试步骤。

### 所有面向过程的工作的起源

面向过程的计算机工作源于人类所做的工作。我们希望摆脱对极其详细、顺序敏感的步骤的精确、可靠执行的单调乏味。如果这项工作是在一个重复的周期中完成的，我们就更有动力去摆脱它，并通过把工作交给那些不会因为无聊而经历精神漂移的机器来保证质量。

### 最佳进程发现机制

在我的职业生涯中，曾有过频繁乘坐飞机过夜的时期。由于我很忙，忘记带东西的可能性非常真实，并造成了很大的压力。通宵空中旅行包括几个“不归点”里程碑，因为在某一点上你不再有时间折回你的家去拿东西，后来，你也不再能折回你的车去拿东西。

一个主清单解决这个问题的能力是惊人的。在保持这个清单的这些年里，我还注意到了一些其他的事情:创建和执行清单的过程会让一些事情浮现在脑海中，这些事情需要被包含在清单中(或者从清单中删除)。

有时候，这些是我以前从未想过要放在清单上的全新类型的事情。这份清单现在是按 T 减转换排序的——就像追踪宇宙飞船发射清单一样。像“出门前”和“最后一分钟从车里拿东西”之类的话它也有条件句，如如果国际旅行，如果空屋。

### 大脑倾倒和心理联想

似乎当我们从我们对一个过程的隐性知识中创建一个具体的清单时，它会激活我们的思维去寻找相关的项目。这是人类认知的自然部分，但是对于发现边缘情况和条件步骤特别有帮助。主清单的长期维护也继续增加该领域的价值，因为有地方可以提出新的想法，即应该做些什么来使清单更有效地确保其正确执行。

### 隐性过程知识显性化

当我们构建软件来代替人工过程驱动的工作时，人工清单是一个无价的信息来源。即使清单必须专门为软件构建而制作，它也提供了对那些执行过程的人的隐性知识的完整提取，因为它可以由没有隐性知识的人来验证——这正是计算机代码必须做的，因为它也没有隐性知识。隐性过程知识是专家很难向你解释的知识，因为它对他们来说已经变得如此反射性，以至于他们没有注意到它对于那些不熟悉的人来说是过程执行的重要部分。

### 开发积压优化

清单的构建和提炼实际上代表了过程自动化需求的某种程度上的自动提炼。不要试图凭经验发现*应该做什么*而编码*如何做*——发现和编码可以分开。当有不同的人在做每项活动时，这很有帮助，但当同一个人在做活动时，这也很有帮助，因为将“编码”和“重点清单执行”的流状态分开会产生顶级的意识，从而提高两项活动的结果质量。

### 识别低的和负面的自动化投资回报率

虽然“自动化所有的事情”这个迷因很有趣，但它也是对一个走得太远的哲学立场的评论。自动化关乎效率，而效率又关乎投资回报。几个勇敢的作家和博客已经发表了关于自动化没有投资回报的情况的指导方针。在这些领域中，人的判断和/或执行之间的强可变性是过程的固有特征。清单有助于辨别自动化 ROI 可能较低的地方，因为尝试创建一个包含大量判断调用的清单有助于阐明做出相同判断所需的代码是否可行以及是否具有成本效益。另一个指标是，清单每次执行都需要新的定制步骤。这些特征表明，维护自动化代码所花费的时间将比人类执行任务所花费的时间要多——可能是数量级的。尝试自动化的过程也可以剔除那些自动化投资回报率低的子过程，同时还可以自动化任何自动化的候选对象。在整个自动化发现流程中，可以识别低或负的投资回报率，但必须相信低/负投资回报率的存在，并进行过滤，以避免“无论投资回报率如何，都要自动化 it”的陷阱。

### 人类代码更新、审查和采用

正如计算机代码受益于协作维护更新一样，人类代码——以主清单的形式——也可以受益于这种协作方法——无论它是否可以归结为自动化。协作编码是 Git 的一个主要特性，获得好处就像确保清单以文本格式存储在 Git 中一样简单，这样 Git 就可以对变更执行人类可读的差异。本质上，这自然会导致选择 Markdown 作为文档格式。

### 人类代码可审计性

由于人类在高保真地执行细致的、重复的活动方面存在挑战，我们倾向于让他们提供证据，证明他们按照规定执行了行动，或者描述采取了什么替代行动。通过将完成的清单存储在 Git 中，我们可以促进可审计性。正如后面所讨论的，我们可以确定使用哪种类型的“完成”标记来提高可审核性——例如是否在每个步骤的完成标记中包含日期时间戳。

### 自动化和清单一起更好

一些 DevOps 工程师可能会因为花费精力编写清单而不是直接创建计算机代码来完成这些活动而感到沮丧。上面的列表显示了非常有效的理由，说明了为什么在自动化的初始和持续维护过程中承认并有目的地合并检查表是有意义的。由于作为人工过程被很好地记录，一些东西可能不能被自动化，这种风险不应该导致我们忽视这样一个事实，即未被编码的人工过程对于软件解决方案的整个 DevOps 生命周期的完整性是一个大规模的风险。

### 实时清单状态共享

在一个变更事件中，理解过程中的每一件事是非常方便的——特别是当多个检查表必须同时执行的时候。虽然一些 SaaS 清单解决方案提供实时共享作为主要价值，但如果被监视的清单经常被推送到 git 服务器，并且查看它的个人刷新他们的视图，Git 存储的列表可能会更接近。您甚至可以在执行清单的工作站上设置一个循环的“git commit and push”脚本。

### 代码就是代码，应该存储在 Git 中

通常认为“代码”是计算机代码——但是人类代码符合清单形式的模型，具有非常详细的、特定于顺序的和相互依赖的执行指令。当我们以一种导致有效执行的方式记录人类代码时，我们自然会想到清单的概念。正如我们所讨论的，人类代码与计算机代码有许多相似之处——包括它如何受益于 Git 提供的可见性和协作能力。

当人类代码对软件栈的开发、构建、测试和操作至关重要时——它符合 GitOps 的定义——成功管理软件栈的唯一真理来源。

编写和维护良好的人类代码是创建计算机代码的最佳起点。

在[的后续文章](https://thenewstack.io/part-2-how-checklists-on-github-and-gitlab-can-help-team-collaboration/)中，我们将看看两个免费的、开源的、多平台的工具，它们使得基于 markdown 的清单的创建和执行更加容易。它还将包括配置代码，让您从简单的“完成标记”开始，以保持清单执行的压力尽可能低，并在团队成员之间保持一致。

*有关基础设施最佳实践的更多案例研究讨论，请参加 10 月 9 日在伦敦举办的 [GitLab Commit。GitLab 的首次用户活动将通过战略和技术讨论、经验教训、开发生命周期的幕后观察等展示 DevOps 的强大功能。](https://about.gitlab.com/events/commit/)*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>