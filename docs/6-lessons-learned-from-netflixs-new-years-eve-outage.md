# 从网飞新年前夜停电中吸取的 6 个教训

> 原文：<https://thenewstack.io/6-lessons-learned-from-netflixs-new-years-eve-outage/>

[](https://www.linkedin.com/in/adamlagreca/)

 [亚当·拉格雷卡

亚当是 B2B DevOps 的精品公关机构 10KMedia 的创始人。此前，他是 DigitalOcean、Datadog 和 Gremlin 的通信总监。](https://www.linkedin.com/in/adamlagreca/) [](https://www.linkedin.com/in/adamlagreca/)

最近，我有机会与 MinOps 公司首席执行官、前网飞和 Reddit 网站可靠性工程师(SRE)杰瑞米·埃德博格(Jeremy Edberg)以及 Rookout 和 Kintaba 的创始人利兰·海莫维奇(Liran Haimovitch)和约翰·埃根(Liran Haimovitch)谈论事故管理最佳实践。

在科技行业，我们感觉自己处于前沿，但实际上我们经常在追赶其他行业。例如，航空业已经认识到，当试图变得更有弹性时，试图减少事故计数会适得其反。实际上，你想要的是一种包容事件的文化。一种尽早并经常提出问题、传播经验教训的文化，这反过来大大降低了发生严重灾难的几率。

为了打开话题，Jeremy 谈到了他在 2012 年经历的一次网飞停电。除夕午夜过后一分钟，他收到了用户注册被破坏的警报。他的直觉告诉他，这个问题一定与时间有关，但他不断得到保证，不可能是这种情况，因为一切都是格林威治标准时间(GMT)，任何与时间有关的事情都会在 8 小时前发生。

经过三个小时的故障排除，他们发现了问题:用户注册流要求每年创建一次数据库表，因为它存储了太平洋时间的创建日志。在午夜之前没有人创建过这个表，所以当系统找不到它要找的表时就会崩溃。

杰里米很想说“我早就告诉过你了”，但众所周知，这在回顾会上是没用的。因此，为了提高工作效率，我从对话中总结了关于现代事件管理的六个要点:

相信你的直觉。通常是对犯错的恐惧阻止我们采取行动。没有人想假设一个不正确的理论，更不用说引发一场人人都知道的火警了。但是创造一种积极的事件文化意味着每个人都应该感到被授权去公开和说出来。

尽早并经常声明。营造积极的事件文化也意味着尽早、经常地提出问题。这也被称为“大红色按钮”——自 20 世纪 50 年代以来，工厂就有了任何人都可以随时按下的大红色按钮。这里的见解是，你真正想要的是你的事件计数上升，通过增加声明它们的机会，因为尽早解决它们将防止它们滚雪球般变成 SEV0/SEV1 灾难。

**3)让整个组织参与进来。**在科技行业，我们倾向于将恢复能力的责任交给 sre。但事实是，问题来自四面八方，因此任何员工都应该能够按下那个红色的大按钮。是的，通常问题是在 Datadog 仪表板或寻呼机工作警报中发现的。但是也可以在支持票或客户投诉中标记它们。给每个人一把钥匙来宣布一个事件意味着问题将会更快地出现和解决。此外，在问题解决后，SREs 的工作不应该是随着事件的展开处理从客户代表、法律和公共关系循环的所有事情。采用现代工具应该有助于协调该过程。

**开发者应该对可靠性负责。**根据 Gremlin 的"[混乱状态工程报告，糟糕的代码部署是 SEV0 或 SEV1 事件的主要原因。](https://www.gremlin.com/state-of-chaos-engineering/2021/?soce2021=true)*开发人员编写代码，然后把它扔到墙外去运营的日子已经一去不复返了。他们需要在游戏中有皮肤，并对代码是可靠的挂钩。这意味着采用像可观察性和实时调试这样的现代工具来进行更有效的故障排除和根本原因分析。*

 ***5)尽可能实现自动化:**正如网飞的故事所展示的，如果在午夜之前创建一个新表是一项必要的可重复任务，为什么不实现自动化呢？杰里米在谈话中解释说，因为这是一个简单的任务，所以每个人都认为别人会做这件事。在理想情况下，可预测和可重复的任务应该自动化，将手动事件管理工作留给真正独特的、黑天鹅式的、不可预测的事件。

多读一些验尸报告。每次事故发生后，应努力用至少一句话记录发生的事情，并采取一项行动防止事故再次发生。这些对话发生在水冷却器周围或保存在一个工程师的头脑中，但特别是在一个偏远的世界，这些知识被记录和分发是很重要的。关于现代事件管理的一个大误区是，事后分析需要是具有多个数据字段的复杂的长文档。但事实是，这通常会成为阅读验尸报告的阻碍——或者一开始就写它。从事件发生时在场的人那里记下一些事情，即使只是几句话，对提高应变能力至关重要。众所周知，美国宇航局实际上阅读其他公司的事后分析*，*，因为该机构渴望获得更多内部没有的知识。(如果你想自己养成这个习惯，请查看[。](http://www.postmortem.io)

正如你所看到的，弹性不仅仅是整个公司的努力，也是整个行业的努力。阅读网飞新年前夜的停电可能会让你们中的一些人确信在午夜之前会自动创建一个新的数据库表！这些是我们可以相互分享的知识，只要变得更加开放和透明。

*听听网飞除夕夜停运的完整故事[这里:](https://youtu.be/n3OtykuQxyM)*

[https://www.youtube.com/embed/n3OtykuQxyM?feature=oembed](https://www.youtube.com/embed/n3OtykuQxyM?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*