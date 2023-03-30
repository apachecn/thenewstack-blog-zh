# 明尼苏达大学的研究人员试图毒害 Linux 内核

> 原文：<https://thenewstack.io/university-of-minnesota-researchers-tried-to-poison-the-linux-kernel-for-a-research-project/>

明尼苏达大学的研究人员向 Linux 内核提交了故意的错误代码——几乎侥幸逃脱。

该研究论文的名称是“[关于通过伪君子行为](https://github.com/QiushiWu/QiushiWu.github.io/blob/main/papers/OpenSourceInsecurity.pdf)在开源软件中秘密引入漏洞的可行性”，于 2 月 10 日发表。这篇论文的目标是“从批判的角度调查[开源软件]的不安全性。”这种方法包括提交“伪君子提交”(论文的措辞)，这些看似有益的提交实际上引入了其他关键问题。

开源软件，如 Linux 内核“极其复杂，因此补丁审查过程经常会遗漏涉及复杂语义和上下文的漏洞。”

因此，为了证明他们的假设，该论文的作者，[吴秋实](https://qiushiwu.github.io/)和[陆](https://www-users.cs.umn.edu/~kjlu/)打算提交易受攻击的代码，进而将关键问题引入内核，以测量这些补丁被软件接受的科学概率。

让那件事过去一会儿。研究人员以学术界的名义，决定将有缺陷的代码(这反过来会引入其他严重的问题)提交到 Linux 内核中，以证明他们可以做到这一点。

这件事的影响是深远的。

考虑一下这个。全球财富 500 强公司都在使用 Linux 内核，它推动了企业业务的发展，并使公司不仅可以将开源技术引入到他们的生产管道中，还可以扩展他们超乎想象的能力。开源推动商业创新。

至少有一个有缺陷的补丁[进入了内核](https://lore.kernel.org/lkml/YIBBt6ypFtT+i994@pendragon.ideasonboard.com/T/#ma4bc909958aea19d8cc9e10a8182e1b3c06e3056)(在这种情况下，它明显缺少互斥解锁)。

幸运的是，内核维护者 [Greg Kroah-Hartman](http://www.kroah.com/log/) 发现了这种行为，并在 [Linux 内核开发者的邮件列表](https://lore.kernel.org/lists.html)上斥责了研究人员:

你和你的团队已经公开承认发送了已知错误的补丁，以观察内核社区对它们的反应，并基于这项工作发表了一篇论文。现在你又提交了一系列明显不正确的补丁，我该怎么看待这种事情呢？

我们的社区不喜欢通过提交已知补丁来进行实验和“测试”,这些补丁要么是故意无所作为，要么是故意引入错误。如果你想做这样的工作，我建议你找一个不同的社区来做你的实验，这里不欢迎你。

因为这些行为，整个大学被禁止向 Linux 内核提交补丁。

虽然自由和开放的研究是开源的核心，但这个项目走了一条非常好的路线，可能会产生严重的(和全球性的)反响。如果他们易受攻击的补丁被 Linux 内核接受，那么这篇论文的作者会站出来告诉内核维护者他们做了什么吗？或者他们会让它继续下去，看看它能走多远？

但是这项研究也指出了另一个令人不安的因素。如果恶意补丁很容易偷偷溜进复杂的软件，那么已经做了多少呢？

研究人员自己在他们的论文中得出结论，开源项目应该制定禁止“伪君子补丁”的行为准则，并且这些项目应该对引入的补丁使用强大的测试和漏洞发现工具。

最后，重要的是要记住 Linux 内核对全球商业的深远影响。为此，应该非常认真地对待向该项目提交代码的责任。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>