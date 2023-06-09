# 一飞冲天的弊端

> 原文：<https://thenewstack.io/the-drawbacks-of-a-soar/>

这是两部分系列的第二部分。第一部分是

[here](https://thenewstack.io/automating-security-7-major-benefits-of-a-soar/)

.

[](http://christozzi.com/)

[Chris to zzi](http://christozzi.com/)

[Chris 是一名 Linux 系统管理员和自由撰稿人，拥有 10 多年的技术行业经验，尤其是开源、DevOps、云原生和安全性。他还在纽约州北部的一所重点大学教授科技历史和文化课程。](http://christozzi.com/)

[](http://christozzi.com/)[](http://christozzi.com/)

我们以前说过，现在我们再说一遍:安全协调、自动化和响应(SOAR)平台是帮助团队更智能、更快速、更高效地应对安全风险的伟大工具。

但是，单独使用时，SOA 远不能完美地满足现代组织的全部安全需求。在其他限制中，SOA 过于复杂，难以与其他工具集成，并且与现代安全文化脱节，无法实现当今企业所需的敏捷、全面的安全策略。

为了证明这一点，这里有 7 种方式可以证明飙升的不足。

## **复杂性**

一句话，SOA 最大的问题之一是它们很复杂。

你不能因此责备他们。安全威胁的大小、形状和形式多种多样，因此需要复杂的系统来检测和管理它们。(使用 SOAR 肯定会比使用 Windows Calculator 困难得多。)

然而，翱翔如此复杂的事实是一个缺点，因为它限制了谁可以利用翱翔。在很大程度上，只有安全工程师和分析师拥有直接使用 SOA 的必要技能。组织的其余部分只是间接受益，并且它利用 SOAR 的能力受到与 SOAR 一起工作的安全专家数量的限制。

## **挑战集成**

SOA 经常被吹捧为具有与各种第三方工具和平台集成的能力。

那当然是一个好处。然而，大多数 SOAR 集成的问题是它们需要技术专家来实现。你不能只点击你的 SOAR 中的一个按钮，然后说，“与我的票务系统集成”或“连接到我的日志聚合器”相反，您必须让您的开发人员或 IT 工程师编写自定义代码来实现集成。

这里，这种限制意味着企业充分利用 SOA 的能力取决于能够构建必要集成的技术专家的可用性。这还意味着非技术利益相关者必须通过中介来创建他们自己的系统所需的安全集成，这一需求通常会导致混乱和目标错位，因为技术人员和非技术人员并不总是说相同的语言或共享相同的优先级。

## **无法定义安全策略**

SOA 在自动检测、评估和帮助减轻安全威胁方面非常出色。

但威胁检测、评估和缓解只是更广泛的网络安全战略的一部分。定义一个整体安全策略还需要一些努力，比如确定你的企业面临的最大网络安全风险在哪里，优化你的安全态势(SOARs 并没有真正做到这一点)，以及确保安全是整个组织的优先事项，而不仅仅是安全工程师的优先事项。没有这些见解，您就不知道如何确定威胁的优先级，如何评估违规的影响，等等。

过度依赖 SOA 本身会使企业面临过于关注安全的操作组件(如事件检测和响应)的风险，而对构成有效安全操作基础的更广泛的策略关注不够。

## **缺乏对以安全为中心的文化的支持**

SOA 主要迎合安全专家的事实也意味着他们在整个组织中执行[以安全为中心的文化](https://torq.io/blog/build-an-automation-first-security-culture/)方面做得很差。

如果只有安全工程师和分析师需要参与管理威胁，这就不是问题了。但事实是，现代安全风险的巨大范围、复杂性和动态性要求[每个人都成为安全从业者](https://torq.io/blog/cybersecurity-culture-in-organizations/)——从人力资源部门到法律团队，再到不起眼的入门级办公室无人机。

当你需要一个网络安全硕士学位来部署安全自动化的时候，你是做不到这一点的，这是你一个人依靠一个 SOAR 就会出现的情况。

## **过度依赖软件**

SOAR 的核心任务是自动化复杂的任务，这样人类就不必忍受手动执行这些任务的单调和劳累。

然而，问题是，并不是每个任务都可以自动化。诚然，绝大多数风险可以被自动识别和评估，有时甚至可以自动补救。但偶尔，您会遇到真正复杂的威胁，如利用尚未被识别并记录在威胁情报数据库中的漏洞的全新风险，这些威胁只能通过广泛的人工干预来缓解。

如果你仅仅依赖于 SOA，你就失去了在环境需要时发挥人类专长所必需的灵活性。

## **将员工资源转向技术资源**

出于类似的原因，SOA 带来的风险是，企业可能会对自己的安全软件过于自信，从而导致对人力资源的投资不足。毕竟，如果你有一个捕捉 99%的威胁的大飙升，为什么还要继续为多个安全分析师付费呢？

当然，答案是 99%的威胁不是 100%的威胁，你需要人类来处理你的翱翔所不能处理的风险。但是当你的 SOAR 大部分时间可以代替你的大部分分析师的时候，很容易忽略这个事实。

## **不切实际的期望**

现代的 SOA 非常擅长检测和减轻威胁。但是他们不能每次都识别或解决所有的风险。

然而，我们很容易陷入假设它们存在的陷阱。如果你过于依赖 SOAR，你可能会听到你的工程师说“SOAR 说没有威胁，所以我们知道没有威胁。”

认识到飙升只是一种工具和一道防线，从而避免这种心态是至关重要的。他们不可能抓住天底下的每一个风险。

## **结论**

再说一次，我们喜欢 SOAR，我们认为每个人都应该有一个 SOAR 来帮助应对当今每个组织所面临的安全威胁。

但我们也认为，过度自信或未能实施安全工具来帮助整个组织(而不仅仅是安全和 it 专家)从自动化安全检测、评估和响应中受益是一个巨大的错误。腾飞做了很多，但并不是做了所有。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>