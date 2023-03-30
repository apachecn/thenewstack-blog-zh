# Linus Torvalds 解释为什么开源解决了最大的问题

> 原文：<https://thenewstack.io/linus-torvalds-on-why-open-source-solves-the-biggest-problems/>

![LinuxCon_Europe_Linus_Torvalds_03 2014 by Krd (via Wikipedia)](img/b80f79b2064e1254659331f0bc83a267.png)本月，Linux 和 Git 创造者 Linus Torvalds 在[一个新的两部分](https://www.tag1consulting.com/blog/interview-linus-torvalds-linux-and-git) [电子邮件采访](https://www.tag1consulting.com/blog/interview-linus-torvalds-open-source-and-beyond-part-2)中，与 Jeremy Andrews 进行了长时间的交谈，Jeremy Andrews 是全球技术咨询公司 [Tag1](https://www.tag1consulting.com/) 的创始合伙人兼首席执行官，也是 Drupal 的第二大贡献者。作为对开源领导者的新[系列采访的一部分](https://www.tag1consulting.com/open-source-leaders)，安德鲁斯想要在今年 8 月 Linux 周年之前赶上托瓦尔兹。

托沃兹已经花了 30 年的时间——从 21 岁开始——坚定不移地主持着这个社区，这个社区维持着一种全球现象，这个开源操作系统“实际上是从我开始的，最初只是试图了解我的新 PC 硬件的细节，”他写道。

51 岁的托瓦尔兹现在住在波特兰，他描述了自己是如何度过每一天的，阅读来自维护人员和科技记者的无尽电子邮件。他描述了他的家庭工作环境，双 4k 显示器运行 Fedora，还有一个古怪的文本编辑器，名为“micro-emacs”，他在大学时就迷上了，“现在我的手指都被硬编码了。”另外，两只狗和一只猫。

尽管采访并没有明确提到最近明尼苏达大学的研究人员向 Linux 内核维护团队发送假冒补丁的争议，但托瓦尔兹还是传达了一个令人欣慰的消息，即开发人员仍在努力维护内核。他承认，是的，全球疫情“显然以其他方式影响了我们所有人的生活——只是一般的社会影响。但总的来说，作为一个几乎完全通过电子邮件与人互动的内核开发人员，我们可能是受影响最小的。”

因此，现在在一次感觉像看望老朋友的采访中，托瓦尔兹强调了是什么使 Linux 内核保持健壮和稳定——包括他关于正确的开源许可证的关键早期决定，以及找到具有这一成功的所有重要属性的开源开发者的能力。

## 金钱不会激发

最大的问题是——他对选择 GPLv2 许可证有任何遗憾吗？——托瓦尔兹回答说“绝对不是……我 100%相信许可证是 Linux(以及 Git，就此而言)成功的重要因素。我认为，当每个人都知道自己拥有平等的权利，没有人在许可方面是特殊的时，参与其中的每个人最终都会更开心。”

在选择了保护开放性的 GPLv2 许可证之后，他将几十年来的所有变化描述为“渐进式的”,这是他在一个充满关于 BSD 和 GPL 许可证之间区别的激烈争论的时代做出的选择。(“我认为部分原因是理查德·斯托尔曼真的有惹恼别人的本事。”)托瓦尔兹在新闻组的新闻组如 comp.arch 和 comp.os.minix 上看到过一些这样的讨论，并从他的朋友 Lars Wirzenius 那里听到了更多，他“比我更热衷于许可证讨论”但最重要的是，Linux 需要一个像 gcc 这样的 C 编译器——它使用了 GPL 许可证——托瓦尔兹记得“我觉得亏欠了 GCC。”此外，GPLv2 许可证“符合我‘你必须归还源代码’的期望。”

今天，他将这与两用许可证进行了对比，在两用许可证中，“我认为围绕这种情况建立一个社区真的很难，因为开源方总是知道它是‘二等’的。”托沃兹后来甚至补充说，“金钱真的不是一个很大的动力。它不能把人们团结在一起。我认为，有一个共同的项目，并真正感到自己真的可以成为这个项目的完全合作伙伴，这可以激励人们。”

两用许可的另一个缺点是什么？“这导致了许多公正的许可文书工作，以便特殊方始终保留他们的特殊权利。所以它给这个项目增加了很多摩擦(T2)

在采访的第二部分，Andrews 带着一个关于企业用户从开源项目中获利而没有贡献或支持正在努力谋生的实际维护者的问题回到了主题。但是托沃兹提出异议，回应道“我真的没有这个问题的答案，由于某种原因，内核总是回避这个问题……[我]有这么多大公司非常公开地参与上游内核开发，并且是社区的主要部分，这实际上非常令人鼓舞。”所以对于开源开发是否可持续的问题，托沃兹说他确信答案是肯定的。

但是作为题外话，托瓦尔兹指出，Linux 有意识地欢迎企业用户，避免了自由软件基金会的“近乎宗教的暗示”，他认为这种暗示赶走了商业用户。甚至还有具体的推广工作，不仅向公司教授开源软件的合法性，还教授与开源社区合作的技术方面。托瓦尔兹认为，最终，即使是不直接贡献或支持内核的企业用户，也仍然最终依赖于承包商或发行商，这为内核开发人员创造了就业机会。后来他直接强调了这一点。“我确实认为，有些项目可能因过于反商业而搬起石头砸了自己的脚，让企业很难参与进来。”

很快他更进一步，补充道“对于复杂的技术问题，你真的需要开源，因为问题空间太复杂了，一个公司无法管理。即使是一家有能力的大型科技公司。”

## 良好品味的重要性

采访还提供了一些关于托沃兹思维方式的有趣见解。(“作为一名工程师，我强烈认为‘细节很重要’。细节几乎是*唯一*要紧的事情。如果你把细节做对了，剩下的就会水到渠成，”他写道。

但与此同时，对于三十年后，托沃兹认为什么是一个好程序员的关键属性，或者至少是一个开源软件重要部分的好维护者，也有一些见解。托瓦尔兹讲述了创建 Linux 源代码管理器 Git 的故事，从一开始，他就想让别人来接管它的维护工作。他写道，“事实上，如果我一开始不用写，我会最开心的。”几个月之内，他在[的 Junio Hamano](https://www.linkedin.com/in/gitster) 身上发现了他喜欢的东西——他从 2005 年开始就一直是 Git 的核心维护者。Hamano 拥有 Torvalds 描述为“好品味”的那种罕见而难以捉摸的特质:

“编程是为了解决技术问题，但你如何解决它们，以及你如何思考它们也很重要，这是你随着时间的推移开始认识到的事情之一:某些人有‘好品味’的东西，并选择了‘正确’的解决方案。

“我不想声称编程是一门艺术，因为它实际上主要是关于‘好的工程’。我非常相信托马斯·爱迪生的“百分之一的灵感和百分之九十九的汗水”这句格言:它几乎都是关于小细节和日常工作的。但偶尔会有“灵感”的部分，那种“好品味”的东西不仅仅是解决一些问题——干净漂亮地解决它，是的，甚至是漂亮地解决它。

“朱尼奥有那种‘好品味’。”

Torvalds 称 Hamano 为“模范维护者”，提醒 Andrews“已经 15 年多了，我只在第一年参与 Git。”

但是很快，这使托沃兹进入了一个更大的视野，这可能最终解释了质量开发的这种属性是如何扩展成宏伟的东西的。

“与 Git 不同，Linux 显然是一个我仍然积极维护的项目，但与 Git 非常相似，它也是一个有许多其他人参与的项目，我认为 Linux 的一个巨大成功是有数百名维护者，他们都有难以定义的“好品味”…”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>