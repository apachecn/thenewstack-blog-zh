# 如何在你的网站上支持一百万用户:一个成功的故事

> 原文：<https://thenewstack.io/how-to-support-a-million-users-on-your-website-a-success-story/>

10 月，在加州洛杉矶的“梦幻好莱坞”酒店，开发者 Nadia Odunayo 讲述了一个鼓舞人心的故事，讲述了她如何在短短 29 个月内建立了自己的网站，并获得了超过 100 万个注册账户——几乎是单枪匹马。

作为 Storygraph 的两位联合创始人之一，也是唯一的网络开发者，Odunayo 回顾了他们的小公司是如何保持活力的，在好运终于到来时，让自己处于有利地位。

但是在首届“Rails SaaS 会议”上，Odunayo 讨论的不仅仅是技术栈和有效扩展。她还介绍了一个案例研究，内容是创始人的态度、雄心与有效决策的结合——成功识别所有瓶颈，然后识别解决方案并采取成功行动。

在漫长而令人兴奋的旅程结束时，Odunayo 分享了她一路上学到的所有经验教训。

## 它是如何开始的

凭借其图形和图表，[story graph](https://www.thestorygraph.com/)向读者承诺“简单的跟踪和深刻的统计数据”，以及通过机器学习算法生成的个性化建议。但是该网站的[“团队”页面](https://www.thestorygraph.com/team)也解释说，它最初是作为 Odunayo 的个人项目而存在的。

从牛津大学毕业后——在伦敦创客学院参加了为期 16 周的代码营——Odunayo 已经成为一名软件工程师和一名连续创业者。2015 年，Odunayo 与他人共同创立了软件咨询公司 [Ignition Works](https://www.linkedin.com/company/ignition-works/) ,“帮助企业客户通过 Pivotal Cloud Foundry 取得成功”

然而，Odunayo 很快意识到她真正的激情是书籍，并决定建立一个网络应用程序，可以帮助读者找到完美的书籍。一次公开测试带来了有益的反馈——以及来自软件工程师 [Rob Frelow](https://www.crunchbase.com/person/rob-frelow) (他最终成为该网站的联合创始人兼首席人工智能官)的一封电子邮件。

Odunayo 通过回顾 2020 年 1 月 1 日开始了她的演讲。“在我的初创公司 Storygraph 连续一年每天工作后，大部分时间都是独自一人——我们最近达到了令人垂涎的里程碑……100 名用户注册。”这些最早的用户是 Instagram 的图书爱好者社区中的朋友和联系人——但也包括任何被口碑吸引的人。

这就是挑战开始的地方。到 6 月 11 日，Odunayo 的网站已经增长到 1000 名用户，但在一波积极的推文之后，六天内就飙升到 5467 人。“现在我们遇到了一个问题。”

该网站的“欢迎”电子邮件承诺将用户的 Goodreads 帐户数据导入他们的 StoryGraph 帐户，但这无法实现。(至少，不是很快……)该网站从来没有一次处理成千上万的进口，突然积压需要几个月的时间来处理。“那天晚上我没有睡觉，”Odunayo 回忆道。“我不能…”

然后第二天…甚至更多的推文开始称赞 StoryGraph。“我们的用户数量每*小时*就增加数百到一千人！”他们的作业调度程序显示有 18，364 个导入在队列中等待。“不仅没有人完成他们的 Goodreads 导入，也没有人收到我们任何精彩的个性化书籍推荐——这些推荐也是由后台工作产生的

 *“网站处于停滞状态，而推文却不断涌入。我不知所措。我压力很大。我处理不了这个。我不知道该怎么办。”

## 怎么样了

这是 Odunayo 上第一堂课的地方。“你能控制的*是*——最终，你如何建立自己的公司和产品——将决定你如何应对好运和厄运。”Odunayo 说，在创办她的公司时，她选择了“无聊”的答案，“不担心任何增长或扩展我还没有的痛点。”Odunayo 建议观众坚持他们知道的东西——并且尽可能少地使用它们。"使用最稳定、最成熟、最乏味的平台和工具."

在 Odunayo 的例子中，那是[轨道](https://thenewstack.io/why-were-sticking-with-ruby-on-rails-at-gitlab/)。因此，当面对大量用户时，Odunayo 自信她面对的是已经解决的问题。"我不会是第一个开发支持成千上万用户的 Rails 应用的人."他们重新设计了网站，以便更多的导入可以同时进行，并加快他们的推荐速度。有一些不熟悉的增长规模问题——比如优化数据库的输入/输出操作，升级 Heroku 的轻量级 Dyno 容器——所以在漫长的两周内，两位联合创始人几乎没有睡觉。但他们保持乐观积极的态度，“在解决了所有资源瓶颈后……我们又开始做生意了。”

“从那时起，我们每天至少增加数百名用户，所有这些都是通过口碑传播的。”

成本持续上升，Odunayo 将其归因于“标准的 SaaS 公司订阅——想想 Cloudflare、SendGrid、Mailchimp……但我们最大的成本是 Heroku。”这引出了她的第二条建议:保持低成本。“至少每月一次，我们审查我们付费购买的工具列表，尝试各种 Heroku 附加组件的最低层，并尽可能切换到[开源替代方案](https://thenewstack.io/where-can-heroku-free-tier-users-go/)…我们尽可能多地做我们能做的事情，而不是雇佣人员，我们投入时间来提高我们需要的水平。”

这方面的一个例子发生在 2021 年 5 月，当时有 18 万用户，他们意识到他们需要一个移动应用程序。“我们请不起 iOS 或 Android 开发人员，所以这项工作就落到了我身上！”但幸运的是，Odunayo 可以转向 Hotwire 和 Turbo——以及它们附带的移动适配器——这“给了我们一条在合理的时间内开发半原生应用程序的道路，所有开发都在内部进行。”作为该公司唯一的网络开发人员——也是唯一的应用程序开发人员——Odunayo 花了整整六周的时间编写代码，“将 Ruby 与 Swift 和 Kotlin 混合在一起。”

但他们的移动应用最终帮助推动了他们的增长，到 2021 年 7 月 8 日，他们的注册用户已经超过 25 万。

## 来自抖音的麻烦

成功只会带来挑战。突然，一个她们从未听说过的女人创造了一个病毒式的抖音，开头写道，“所有的辣妹都从 Goodreads 转向 StoryGraph，这就是原因。”突然有 1600 人试图同时使用他们的应用程序——它在出乎意料的高负载下不断崩溃。“我们以前从未有过这么多的并发用户…”

是时候进行一些调试了 Odunayo 很快发现问题出在一些低效的代码上(事实证明，这些代码完全是多余的),每次加载主页时这些代码仍然在运行。问题解决了——与此同时，这个病毒式的视频持续播放了 170 万次，分享量超过 30 万次。这在一天之内带来了 4 万多名用户，暂时将该应用推上了苹果美国应用商店排行榜图书部分的第一名——甚至超过了亚马逊的 Kindle 和 Audible 应用。到 2021 年 7 月 28 日，他们有 31 万用户……到 9 月 23 日，这个数字上升到了 50 万。

不幸的是，“随着我们用户群的增长，我们的成本也在成千上万地增加……”他们一直在使用 Heroku 的平台即服务产品，但现在“这些成本正在杀死我们。”这是他们最大的支出，让公司损失了钱，而且“随着我们用户群的持续增长，我们 Heroku 的成本也在同步增长。”他们探索了所有“标准、简单、无需雇佣开发人员的平台”但是他们还有一个选择。

联合创始人 Rob 有 15 年的运营经验，他们决定让他接管基础设施的管理。2022 年 1 月 22 日，他们从 Heroku 的平台即服务产品迁移到 Cloud 66 提供的基础设施管理服务。“离开 Heroku 的安全空间很可怕，”Odunayo 承认。“我们花了数周时间整理了一份实际迁移的分步文档。迁移的早晨是 6 个小时不间断的工作，照看整个过程，直到全部完成。”

然而，当他们到达关键转变的终点时，他们做到了。他们还削减了 80%的服务器成本。“除了与工作维护模式和数据库备份命令最初超时有关的一些小问题，一切都很顺利。”尽管有一个令人讨厌的惊喜。“事实证明，这次迁移让我们 760，000 名用户中的每一个人都退出了应用程序。”当然，还有忘记密码或忘记与帐户相关的电子邮件地址。但该团队最终让每个人都与他们最初的账户相匹配。

Odunayo 告诉观众，今天 Storygraph 拥有超过 120 万个注册账户，每月有 3600 万次浏览量。

但更重要的是，“我们每月的成本一直低于每月的经常性收入！”

[https://www.youtube.com/embed/efCI1ByPT5s?feature=oembed](https://www.youtube.com/embed/efCI1ByPT5s?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*