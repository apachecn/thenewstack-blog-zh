# Linux 核心开发者小心翼翼地将 GPL 违反者告上法庭

> 原文：<https://thenewstack.io/dangers-linux-litigation-businesses/>

违反开源 GPL 许可条款的公司应该被送上法庭吗？对于世界上最流行的通用公共许可证(GPL)项目 Linux 的维护者来说，答案出奇的复杂。

GPL 是允许开源协作发生的基石，但是它要求那些公开使用 GPL 代码的人发布他们的改变。可以说，越来越多的公司没有做到这一点。当[软件自由保护协会](https://sfconservancy.org/)、[的执行董事](https://lists.linuxfoundation.org/pipermail/ksummit-discuss/2016-August/003542.html) [Karen Sandler](https://twitter.com/o0karen0o) 发布了一条关于在下个月即将到来的[内核峰会](http://events.linuxfoundation.org/events/linux-kernel-summit)期间围绕 GPL 实施的可能会议的消息时，最近在 Linux 内核邮件列表(LKML)上引发了一场热烈的讨论。

在 LinuxCon North America，与 VMware 副总裁兼首席开源官 [Dirk Hohndel](https://plus.google.com/+DirkHohndel) 的谈话中，Sandler 似乎受到了 Linux 创造者 Linus Torvalds 对 GNU GPL 的赞赏的鼓舞，他认为 GPL 是避免 Linux 碎片化的一个主要因素。

这是一个很长的讨论。我花了两天的时间梳理每一封邮件，了解所有的观点。我仅从电子邮件中获取的笔记就超过了 20，000 字。在这个故事中，我将试图触及什么是利害关系，谁是利益相关者，以及他们为什么做他们正在做的事情。

## GPL 拯救了 Linux 免于崩溃

托沃兹可能不喜欢自由软件基金会(FSF)和理查德·M·斯托曼(T21)，但是他喜欢他们开源软件许可背后的基本理念。“如果你拿走了我的代码，并对它进行了修改，我希望我的修改能回来，”托瓦尔兹在早些时候的一次采访中说。GPL v2 确保了他自己，或者开发人员——无论是个人还是公司——对 Linux 做出贡献的人，不会被锁在他们自己的修改之外。

“我真的认为许可证(GNU GPL 第 2 版)是 Linux 成功的决定性因素之一，因为它迫使你必须归还，这意味着从技术角度来看，碎片化从来都不是可行的，”Torvalds 在 LinuxCon 上与 Hohndel 交谈时说。

Torvalds 最初在非 GPLed 许可下发布 Linux，这显然限制了 Linux 的商业化。1992 年，Torvalds 将许可证更改为 GNU GPL v2，取消了商业限制。

## Linux 在开源成功中的作用

虽然托瓦尔兹将 Linux 的成功归功于 GNU GPL，但他经常对推广开源软件的功劳犹豫不决。托沃兹告诉我，Linux 的与众不同之处在于，它不仅传播了编码工作，还传播了愿景工作。Linux 对它想去哪里没有一个愿景，个人和公司带着他们自己的愿景来到 Linux；他们想把 Linux 带到哪里。

这是 Linux 独有的，尽管 BSD 的存在，但很大程度上，Linux 被广泛采用。Linux 因让商业实体适应开源而受到好评。Linux 成为了实现商业目标的催化剂，而没有损害代码质量和个人贡献者。没有精英 Linux 俱乐部；从单人发行版到 IBM，任何人都可以使用 Linux，并对代码有同样的影响。难怪现代经济实际上运行在 Linux 上。

今天，Linux 实际上为现代经济提供了动力，并被广泛使用:嵌入式设备、数据中心、智能汽车、智能手机、平板电脑、智能电视、证券交易所……几乎无处不在。Linux 正在为企业创造数万亿美元的收入。有成千上万的公司在使用 Linux，许多公司甚至在为 Linux 做贡献。

这种流行和大规模采用的另一面是，据说有许多公司使用 Linux，但不遵守 GPL。这可能是故意的，也可能是无心之过。细节决定成败。公司正在销售运行 Linux 的产品，但是他们不发布源代码，这违反了 GPL 的条款。

有问题吗？看你问谁了。

## 违反 GPL 有多严重？

如果没有人尊重它，许可证有什么用？不同的人从不同的角度看待 GPL 违规。像 FSF、SFLC、证监会这样的组织认为这是一个严重的问题，因为他们出于非常真实的原因关注软件自由。违反 GPL 削弱了软件自由，所以这些组织非常努力地确保 GPL 的实施。

还有像马修·加勒特这样的开发者，他们真正关心人们的安全和权利。他们希望实施 GPL，这样用户就可以保证他们设备的安全，并访问在他们设备上运行的源代码。

有些开发人员希望 GPL 符合性，因为他们希望看到，并可能使用其他方(包括公司)对他们代码所做的修改。这些团体和个人努力执行 GPL，因为他们似乎优先考虑软件自由，用户对他们使用的软件的权利。

## Linux 社区有什么感受？

Linux 内核社区的情况很独特。Linux 内核是迄今为止最大的 GPL 项目。虽然内核社区承认违反了 GPL，但它也认为情况实际上正在好转。

公司总是“违反”Linux GPL 许可，但这并没有减少许可的真实性或有效性，核心 Linux 内核维护者 Greg Kroah-Hartman 在回复 Sandler 的帖子时写道。他补充说，“就个人而言，在这方面，我们今天似乎比 15 年、10 年甚至 5 年前要好得多。”

## 对于 GPL 的实施可以做什么？

让公司遵守 GPL 有不同的方法。最常见的实践是开发人员级别的参与。大多数开发人员会与相关公司沟通，并在大多数情况下让他们遵守。

[James Bottomley](https://twitter.com/jejb_) ，IBM 的杰出工程师，Linux 内核社区的领军人物之一，他说他职业生涯的大部分时间都在各个公司的高层工作，为他们建立开源战略和商业模式。

克罗亚-哈特曼在与企业对话并让它们参与进来方面也发挥了极其重要的作用。甚至像 SFC 这样的机构也是从对话和沟通开始，让公司合规。

然而，SFC 似乎担心由于 Linux 的流行，GPL 违规的增加。[SFC 的 Bradley M. Kuhn](http://www.ebb.org/bkuhn/) 在邮件列表上写道:

我现在注意到，在过去的 10 年里，出现了其他任何受版权保护的代码从未出现过的情况。具体来说，对于 Linux，我们发现主要和次要的行业参与者都决心故意违反 GPL，并且拒绝遵守，并且当面告诉我们:“你认为我们必须遵守 GPL？好吧，那就带我们去法院。否则我们不会遵守。”(Greg，在你的历史案例中，没有一家公司这样做过。)而且，采取这种立场的决定完全掌握在违反者手中，而不是执行者手中。

他表达了对这种情况的失望，并写道，“作为回应，我们有两个选择:我们都可以决定放弃 GPL，或者我们可以在法院强制执行它。”

这导致了一场激烈的辩论。

“我认为这是扯淡，”通常非常冷静的克罗阿-哈特曼回击道。坦白地说，我已经听腻了，因为它完全不正确，并且轻视了成千上万的人 25 年来为维护 GPL 授予我们的权利所做的努力。"

托沃兹也附和道，“我个人认为这种为律师辩护的争论已经成为一种令人讨厌的溃烂的疾病，而证监会和布拉德利·库恩就是传播这种疾病的伤寒玛丽。”

是什么激怒了他们？库恩关于将此类违规者送上法庭的声明。这让许多其他领先的内核开发人员感到不安，因为库恩在 2016 年澳大利亚 LinuxConf 大会上发表了一篇演讲，他说“Linux 是 copyleft 的战场。”

显然，没有人希望自己的后院变成战场，尤其是当他们不想要那场战争的时候。对诉诸法律的想法遭到了猛烈的反对。Bottomley 说他没有起诉过任何人，并且“在行业中的声誉确实有助于我在说服一些实体对 GPL 更加友好时迈出第一步。”

但问题是，公司会遵守规定而不被起诉吗？事实是很少有法律案例迫使公司遵守 GPL。与此同时，有更多的公司开始时是最坏的违法者，后来成为内核的主要贡献者，却从未被起诉过。

Kroah-Hartman 举了英特尔的例子，过去[曾滥用 GPL](https://software.intel.com/en-us/forums/intel-software-development-products-download-registration-licensing/topic/266663) 。今天，英特尔不仅是领先的贡献者，也是 Linux 最亲密的朋友之一。微软是另一个从敌人变成朋友的例子，没有任何诉讼。

但不是非黑即白。法律行动确实起到了教育其他违法者后果的作用。然而，也付出了巨大的代价。

顶级维护者担心这些费用。 [BusyBox，](https://busybox.net/)一个在嵌入式领域广泛使用的 Unix 工具包，就是一个很好的例子。

BusyBox 被视为 SFLC 提起的第一起 GPL 强制执行诉讼。季风多媒体被发现在其固件中使用 BusyBox 代码，但他们从未发布源代码。虽然 SFCL 赢了 T7 并获得了源代码，但 BusyBox 被许多商业玩家视为碰不得的 T9 并失去了应用。BusyBox 现在被视为破坏开源项目的法律行动的典型代表。提起诉讼的主导维护者后悔了。

Bottomley 说，“BusyBox 势头的减弱是事实，确实引起了共鸣，关于这是因为太多强制行动的理论也是如此。”

顶级维护者不希望 Linux 成为下一个 BusyBox，即使它让一些公司遵守 GPL。这就是为什么他们对库恩提出的法律选择反应如此强烈。

你会等多久，直到一个违反者不顾谈话继续违反？当你说的够多了，是时候把他们告上法庭了，这有什么意义吗？库恩的观点是，最终，你必须诉诸法律。最大的问题是什么时候。

库恩举了 VMware 的例子，据说它有违反 GPL 的软件。经过七年失败的讨论，一个 Linux 开发者决定采取法律行动，SFC 支持他。然而，他们在德国法庭上输掉了第一轮。

如果 SFC 赢了拿到代码怎么办？它会把 VMware 变成下一个谷歌或英特尔，一个伟大的 Linux 贡献者吗？难道 VMware 不会敌视 Linux，转而采用比 GPL 更宽松的其他技术吗？而如果 SFC 输了呢？

SFC 可能赢也可能输，但是和 BusyBox 一样，Linux 社区可能会以双输告终。这是主要的内核开发者所不希望的。Kroah-Hartman 对 Kuhn 说了一些强硬的话，“为了以某种方式验证 GPL，你愿意拿 Linux 冒险。我不愿意拿 Linux 去冒险做那样愚蠢的事情。我是在一小群观众面前告诉你的，现在我愿意在更多的观众面前这样做。”

## 法律行动的副作用

除了担心失去可能的协作和社区，以及对 Linux 不可修复的损害，就像 BusyBox 的情况一样，还有其他的担心。这可能会变成一场公关灾难。内核的顶级维护者肯定不希望“Linux vs XYZ 公司”的新闻流传开来。没有一个对 Linux 有既得利益的人会希望 Linux 被视为诉讼方。这将使 Linux 变得不可触及。

人们越来越担心打官司会引发不愉快。有极小的可能性是，一些为内核贡献了一些代码的流氓开发者或者一些通过雇员拥有代码版权的公司可能会变成一个 GPL troll。它可能开始起诉违反 GPL 的人，以勒索金钱。看看违反 GPL 的数量，这可能会成为一个利润丰厚的市场，就像专利钓鱼者一样。已经有这样一个案例，证监会试图减轻。

对于使用 Linux 构建产品的企业客户、开发人员甚至公司(大多数是小公司)来说，trolls 的崛起是一个问题。我们从美国的专利钓鱼者那里学到的是，我们当然不想让 GPL 钓鱼者充斥市场。

还有另一个有趣的事实，那就是如果有人严重违反 GPL，带着会直接伤害 IBM 这样的巨头的代码逃跑，这些公司不会坐视不管。在不伤害 Linux 社区的情况下，他们不会回避对这些违法者提起诉讼。

## 不要带着核武器去打代码战

这并不意味着托沃兹或其他主要开发商将法律选项排除在外；他们不是。他们想要核选项，但在一些安全的地方，而不是有人带着手提箱到处走。

“我确实认为，在最后一点上，律师确实需要介入。但这真的应该被看作是最后的努力。这是核选项，”托瓦尔兹说。

他们(领先的内核开发人员)似乎在向更大的 Linux 社区传达这样的信息:让我们按照开发人员的方式来做。开发者的方式是在代码上合作，让人们加入到项目中来，让公司从中受益。Linux 就是这样开始的，他们也想这样运行它。

托沃兹总结得很好:“让我们清楚这一点:诉讼摧毁。他们不“保护”诉讼摧毁社区。他们破坏信任。他们会毁了我们多年来友好建立起来的所有善意。"

并不是说他们反对法律诉讼。如果有人获取了 Linux 的全部代码，并将其转化为专有技术，Torvalds 将面临法律诉讼。他们希望它成为真正的核选项，一个你拥有但从未真正使用过的选项。

英特尔是新堆栈的赞助商。

由[阿玛尔·雅斯拉哈](https://unsplash.com/@pictagramar)通过 [Unsplash](https://unsplash.com/?photo=sAGXVK6bNFc) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>