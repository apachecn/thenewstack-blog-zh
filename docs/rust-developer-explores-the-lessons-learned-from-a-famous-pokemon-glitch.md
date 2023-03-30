# Rust Developer 探讨了从一个著名的口袋妖怪故障中吸取的教训

> 原文：<https://thenewstack.io/rust-developer-explores-the-lessons-learned-from-a-famous-pokemon-glitch/>

随着八月接近尾声，一年一度的 [Rust 开发者大会](https://rustconf.com/)虚拟化，不仅有在线演示，还有数字分组会议和聚会。

但是[有一个特别的闭幕主题](https://www.youtube.com/watch?v=RNsEsZbXE-4)，来自[的 sian Griffin](https://github.com/sgrif)，他共同领导着管理 Rust 的 crates.io 包库的团队。(会场的发言人简介[将格里芬](https://rustconf.com/speakers/si-n-griffin)描述为“如果服务中断，他会在凌晨 3 点被叫醒。”)格里芬还创建了 Rust 查询构建/对象关系映射工具 Diesel，并为开发人员共同主持了一个名为“Yak Shave”的播客对于虚拟会议的与会者，格里芬带来了一个关于计算机编程历史上的小故障的启发性故事。

它直接来自口袋妖怪的世界。

“哦，你好。“我没看到你在那里，”格里芬穿着黄色皮卡丘服装，漫不经心地说道——接着说，“我想给你讲个故事。”

## 生锈之前的世界

格里芬首先回顾了 20 世纪 90 年代末，当时“仅仅使用 Rust”并不是一个选项这个故事是关于一个任天堂 64 口袋妖怪游戏——以及编写这个游戏的汇编程序员。格里芬告诉观众，1998 年全球发行的*口袋妖怪红*和*口袋妖怪蓝*成为有史以来最畅销的两款电子游戏。但是有史以来最著名的口袋妖怪——皮卡丘——的幻灯片后面是第二著名的幻灯片:[小故障口袋妖怪](https://bulbapedia.bulbagarden.net/wiki/Glitch_Pok%C3%A9mon)，这只能是因为游戏程序员独特的错误组合才会遇到。

格里芬后来称之为“有史以来最著名的故障之一。”

演讲的重点是我们能从这个著名的小故障中学到什么。“就像大多数主要的小故障一样，这里没有一个单独的 bug 要对此负责。发生这种情况是因为一堆不同的错误。在大多数情况下，你甚至不能称之为 bug，只是代码的属性被以意想不到的方式使用。”

虽然这个演讲包含一些猜测，格里芬也“花了很多时间”查看游戏原始代码的“反汇编”，“我认为我们可以从阅读代码和了解他们工作的约束条件中推断出很多意图。”

在整个演示中，Griffin 通过向 Rust 展示代码的翻译来演示代码是如何工作的。格里芬称第一个 bug 是 Rust 程序员今天“最容易嘲笑的”,但随后解释了为什么如果你在 20 世纪 90 年代末用汇编语言编写代码，你会有不同的编码方式。他们说:“在汇编语言中，你不只是有你想要的那么多局部变量。”

事实上，GameBoy 使用的 Z80 程序集只有四个通用的全局变量寄存器，所有这些寄存器都在使用中。

[https://www.youtube.com/embed/RNsEsZbXE-4?feature=oembed](https://www.youtube.com/embed/RNsEsZbXE-4?feature=oembed)

视频

“当你用 Rust 写一个程序时，编译器会决定你写的每个变量的存放位置。要么把它赋给一个寄存器，一种你的 CPU 使用的全局变量，要么把它放到堆栈里。现在在口袋妖怪游戏中，他们有一个堆栈，但它真的很小——只有 207 字节。所以他们基本上从来不用，除非绝对必要。格里芬说:“它主要用于音频播放。

这意味着游戏包括一些代码行，其中一些变量稍后会被重新初始化——在一次疏忽中，有两行代码都作用于同一个变量——相隔 50 行。“仅此一点，对我来说，就使它更有理由逃过代码审查，”他们指出。

第二个错误只是没有清除变量的值，留下了游戏早期的数据。但是可以通过确保它获得具有意外值的数据来利用这一点，例如，控制字符表示可以为你训练口袋妖怪的不可玩角色的名称结束。

> “我们中的每一个人都参与过一个项目，在截止日期前两天，需求从你的下面发生了变化。”辛格里芬。

但更好的是，一个游戏中的教程将触发玩家的名字存储在相同的位置。这意味着精明的玩家可以将该变量的值设置为他们想要的任何值——通过选择他们想要的值作为他们角色的名称，然后执行游戏中的教程。

由于最终是玩家自己的用户名决定了什么样的故障口袋妖怪会出现，任何有偶数个字母的名字都意味着关键的名字结尾字符最终会出现在口袋妖怪栏中——并引发故障口袋妖怪的出现。大写字母 S、H 或 M 以及大多数小写元音也是如此。如果你的用户名中有小写字母 w、x 或 y，一些小故障口袋妖怪就会出现。

但是这个小故障带来了其他意想不到的后果。该代码包括一个跟踪游戏中出现的口袋妖怪的数组——带有玩家是否捕捉到它们的值。但是当玩家看到一个故障口袋妖怪时，代码会尝试将其记录在远远超出数组末尾的位置，具体来说，就是在玩家物品清单的数据中。(更具体地说，在第 13 个字节的高位部分，表示该库存的第六个项目的数量。)“它增加了 128 个项目——只要你之前的项目少于 128 个，”格里芬解释道。玩家们开始愉快地利用这个小故障，神奇地制造出他们最喜欢的口袋妖怪物品。

![Sian Griffin at Rust Conf 2020 (on glitches in Pokemon Blue)](img/749125408029694084bfb0b74775facc.png)

但是界外失误也在其他方面影响了比赛。显示故障口袋妖怪外观的精灵最终比游戏中的其他精灵占据了更多的空间，并最终覆盖了游戏结束“名人堂”的数据。格里芬指出，游戏中的一切都必须优化以节省空间，所以没有边界检查代码。它是基于这样的假设编写的，即它将总是接收“可信的输入”，“这段代码行为不端的唯一原因是因为一个完全不相关的错误，该错误导致它获得垃圾数据。”

格里芬停下来解释故障的图像来自哪里。虽然在程序的某个地方，每个口袋妖怪的图像都有一个方便的查找表，但访问它的代码有自己的错误。Griffin 展示了获取数组中某个位置的代码行，从一个数字中减去一表示它在索引中的位置。但是对于从未定义的值，这意味着从…零中减去一。由于这涉及到无符号的 8 位整数，最终结果是一个比 256 小 1 的值，所以是 255。这使得程序开始疯狂搜索故障图片，远远超出了可用图片的范围。相反，它发现的是一些不可玩的驯兽师角色的数据，这些数据被解释为一个指针，将它引向另一个区域的代码 Safari Zone。

然后它试图将代码解释为图像。

## 口袋妖怪验尸报告

这个演讲以一个深思熟虑的分析结束，分析了我们可以从口袋妖怪故障中学到的真正教训。

这个演讲的题目是“从口袋妖怪蓝中学习同理心”，格里芬提醒观众，这些代码是在“巨大的空间限制下”用汇编语言精心创建的。每条指令都很重要。”但更重要的是意外后果法则。“现在我们已经看到了这个小故障的每一部分，我们可以看到它只是一堆无关代码位之间的小的、看似良性的交互。在我看来，这个小故障中没有一个是疯狂的，或者是明显可以在代码审查中被阻止的。”他们强调，这不是糟糕的编码或缺乏质量保证的结果。"这种小故障本身相对来说是良性的."

然而，当你把它们放在一起时，仍然会发生一些强大的事情。“当你把所有这些结合在一起时，你会得到有史以来最著名的故障之一。”

虽然有些人形容这款游戏“完全崩溃”，但格里芬认为，这个词应该从每个人的词汇中删除。“在这种情况下以及其他许多你试图使用该术语的情况下，更有可能软件是在你没有意识到的一些约束条件下开发的，在同样的情况下你不会做得更好。当然，现在不太可能有技术上的限制，但是我们每个人都在一个项目上工作过，在截止日期的前两天，需求从你的下面发生了变化。或者你的公司突然转向，现在你做医疗服务，你必须弄清楚如何制作一堆与此相关的代码。”

“不过，对我来说，很多小故障都可以归结为‘因为组装’对我们来说，很容易把我们今天掌握的技术视为理所当然。“今天，代码大小很少是一个约束，如果是，通常只是因为 CPU 缓存，”这是我们在优化代码时发现的一个问题。“此外，我们的现代机器有能力运行”各种安全检查。"

“但在 1996 年，‘只使用铁锈’不是一个选项。甚至使用 C 语言也不是一个选择。

“我真的很高兴我们不再生活在那个世界里了。”

![Screenshot from RustConf dot com](img/9c35d70e80b8b1a89c7f5afbe4625613.png)

* * *

## WebReduce

*   彭博采访了吉多·范·罗苏姆和 Python 的核心开发者 T2。
*   一名软件工程师将 Rust 重新想象成用一种叫做“Rune”的新编程语言动态输入的。
*   开发人员重访甲骨文有史以来最伟大的 25 款 Java 应用。
*   所有在推特上推荐的书都是由[埃隆·马斯克](https://mostrecommendedbooks.com/elon-musk-books/)、[比尔·盖茨](https://mostrecommendedbooks.com/bill-gates-books/)、[杰夫·贝索斯](https://mostrecommendedbooks.com/jeff-bezos-books/)和已故的[史蒂夫·乔布斯](https://mostrecommendedbooks.com/steve-jobs-books/)推荐的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>