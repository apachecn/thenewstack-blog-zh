# 在马斯克 Twitter 时代运营乳齿象服务器是什么感觉

> 原文：<https://thenewstack.io/what-its-like-to-run-a-mastodon-server-in-the-musk-twitter-era/>

Jaz-Michael King 是一名威尔士人，自上世纪 90 年代移居美国创办一家网络公司以来，他一直生活在美国。他仍然在美国技术部门工作，但在业余时间，他经营着一个名为[嘟嘟威尔士](https://toot.wales/about) (Twt Cymru)的乳齿象实例，他称之为“威尔士和威尔士人在国内外的乳齿象社交网络”

我联系了金，讨论他经营 Toot Wales 的经历、扩大规模的挑战，以及他希望从乳齿象软件中得到什么。

像许多其他乳齿象实例一样，在埃隆·马斯克接管 Twitter 后，Toot Wales 的使用量迅速增加。它现在有近 6000 名活跃用户。但根据金的说法，后马斯克时代的 Twitter 并没有显著的注册用户增加，而是 T4 活动的指数增长。

“在他手拿水槽走进(Twitter)办公室之前，我们一天大约有 15 万条消息……我现在(每天)处理 300 万到 400 万条消息，”金说，他指的是埃隆·马斯克 10 月下旬带着厨房水槽来到 Twitter 总部。“我们的注册会员大约是现在的三倍，”他补充道，“但是活动量已经大大增加了。”

他将这种活动的爆发部分归因于那些以前注册了乳齿象的人，但他们没有使用它的习惯。现在，这些人已经恢复了他们的账户，并定期检查它们(我也把自己归为这一类，除了我在 mastodon.social instance 上)。

## 技术调整

为了运营 Toot Wales，King 将大部分技术方面的事情外包出去——尽管他有能力自己做。他使用一家名为[mastomost](https://masto.host/)的知名主机公司。“我从一开始就和他们在一起，”他说。“他们与我们一起成长，我们也与他们一起成长。”

金说，他自己的技术参与是“最小的”，但他确实对 Toot Wales 的调整有意见。

“我知道的足够多，可以询问我想要什么调整，你知道，我想要按哪个按钮。但我尽量不去碰它。我的另一个原则是我们只经营主要分支机构。没有实验性的东西，没有每夜更新的东西。我想要稳定的、功能性的、经过实地测试的代码。我在边缘做了一些小改动——我以前在前端做得更多，但随着最近升级到乳齿象 4.0，我甚至把大部分都去掉了。所以它非常小。我喜欢知道我在运行什么，我喜欢知道什么在起作用，但我尽量不去碰它。”

他还对设计做了一些修改，主要是为了让非技术用户不会对 Mastodon 的用户界面感到厌烦——即使是狂热的 fediverse 信徒也会承认，与 Twitter 的 UX 相比，它相形见绌。

“我实现的一个变化是稍微平滑了以前迭代(乳齿象)的 UX，”他说。“我坚信不要谈论多列视图，我们是单列服务器。”

他在这里指的是乳齿象的布局，看起来像 TweetDeck，有多个列。虽然这对于关注列表或标签搜索很有用，但即使是我也选择不使用这种视图——它的实现不如 TweetDeck(归 Twitter 所有)好。也许因为这个原因，在我的服务器上，切换到多栏的选项隐藏在用户偏好中。

## 社区期望和挑战

尽管金尽量不插手技术方面的事情，但自从# Twitter 迁移以来，他一直忙于处理社区和内容事务。

“内容和社区管理，包括适度，是一个沉重的负担，”他说。“这是巧妙地向人们描述我们为什么在这里[以及]我们为什么不是 Twitter 的组合——很多人认为乳齿象是两周前为了修复 Twitter 而建立的。因此，向人们描述他们将进入 4、5、6 岁的阶段，然后管理现有社区的期望和新社区的期望，并找到中间地带。”

当我问他希望看到乳齿象软件有什么改进时，他直接去了社区管理。首先，他希望“在产品中加入比现在多一点的联合和去联合服务。”他指的是在黑名单等问题上与其他服务器运营商保持联系的方法。他希望有一种方法能够在服务器之间“谨慎地、合乎道德地、小心地共享”这类信息。

金还希望“对我们的节制行为进行更强有力的审计”因此，例如，如果他暂停一个帐户，他可以准确地记录原因。

“坦率地说，根据你的管辖范围，在某些时候，你可能会被要求交出这些信息，”他说。"所以我希望看到更强的内容审核和账户管理审核."

## 搜索在哪里？

作为一个开源软件项目，乳齿象采取的一个有趣的设计决策是阻止用户搜索关键词。默认情况下，你可以搜索标签，但(不像 Twitter)你不能输入关键词或其他搜索查询——比如“埃隆·马斯克”——并期待任何结果。这一点的实现因服务器而异。例如，在我的服务器上，如果我输入“埃隆·马斯克”，我会从我自己的帖子和我互动过的帖子中得到结果(例如“喜欢”)。但是从更广泛的领域来看，没有任何结果浮出水面。

关于乳齿象 GitHub 上的这些[搜索限制](https://github.com/mastodon/mastodon/issues/21627)有一个持续的争论，但是我问金他对乳齿象缺乏搜索功能有什么看法，他是如何为 Toot Wales 管理它的？

“这是我喜欢乳齿象的一个原因，就是软件中内置了社会政治指导或护栏，”他回答道。“是软件层面，不是版主层面。所以，网上辱骂的最大载体之一是搜索你想抱怨或攻击的东西，并以此为出发点攻击那个人，或引用-推文离开那个人，指着他们笑，或其他任何可能的事情。因此，这是一种减少人们发现某个话题的方法——也许是边缘人群，也许是热点话题。没有标签，它就不再那么容易被发现了。这是非常有目的的。”

他指出，从 Twitter 迁移过来的人希望他们能够搜索关键词，因为这是他们在 Twitter 上已经习惯了的。但是他仍然抗拒。事实上，与我所在的服务器不同，Toot Wales 上的用户甚至不能搜索他们自己的帖子。金考虑过开启这个选项，但是他担心对他的网络主机的影响。

“我们可以打开一个搜索增强功能，让你可以搜索自己的内容。老实说，我认为不值得浪费 CPU 周期。”

## 你社区的乳齿象

在选择加入哪个 Mastodon 服务器时，要记住搜索限制。就我个人而言，我想要尽可能多的搜索功能，因为我是网络“话题追踪”的忠实信徒。但是每个人都有自己的想法。

撇开用户偏好不谈，King 通过 Toot Wales 为威尔士在线社区提供了一个很好的服务。他没有从中赚到任何钱；事实上，这个网站是由金创立的一个美国慈善机构所有的。

如果你正在寻找一个如何为你自己的社区建立一个乳齿象服务器的好例子，你最好学习 Toot Wales。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>