# 勒索软件缓解措施现在就要采取，否则后果自负

> 原文：<https://thenewstack.io/ransomware-mitigation-steps-to-take-now-or-else/>

勒索软件攻击的激增在全球范围内产生了连锁反应。此后，随着关键的医院和基础设施目标被关闭，此类犯罪袭击的规模和程度都有所增加。

对于拥有运行所需的数据资产和应用程序的组织来说，这种威胁是实实在在的，换句话说，几乎每个人都面临这种威胁。为这类袭击支付赎金的成本正在迅速攀升。

根据帕洛阿尔托网络公司及其威胁情报部门 Unit 42 的报告，平均支付的赎金已从 2019 年的 115，123 美元飙升至 2020 年的 312，493 美元，同比增长 171%。在 2015 年至 2019 年期间，最高赎金总额为 1500 万美元，而 2020 年为 3000 万美元。报告显示，去年支付的最高赎金翻了一番，达到 1000 万美元。

到目前为止，2021 年支付的最高赎金来自对美国和澳大利亚部分地区属于食品加工和肉类包装集团 JBS 的物流基础设施的攻击，导致支付了 1100 万美元的比特币以恢复运营。

可悲的是，当攻击发生时，IT 部门通常没有做好准备来适当地减轻攻击或应用损害控制流程。

[企业管理协会](https://www.enterprisemanagement.com/)的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新的堆栈:“如果我们共同完成了自动化作业，这将是一个小得多的问题。”。“但是，由于大多数组织仍然依赖人工安全人员来手动处理各种访问请求，应用最小特权原则会非常痛苦，而且不可维护。一旦你开始制造例外，就很容易招致勒索软件和其他邪恶势力的入侵。”

## 这么多洞要堵住

这并不是说 DevOps 团队领导和 CTO 是坏人，因为他们未能完全保护他们组织的运营免受勒索软件的攻击。鉴于威胁的规模和严重程度，当有如此多的漏洞需要填补时，人们很容易对加强安全感到无助。

IT 部门的日常需求很容易优先于勒索软件安全，因为 DevOps 团队可能会面临以更快的速度交付软件或修复部署后修复的巨大压力。

“勒索软件攻击对我们所有人来说都是一个巨大的威胁，因为它们无情地利用了我们在应用最佳实践来强化软件应用程序堆栈方面的疏忽，”Volk 说。“事实上，在锁定我们的应用和数据时，几乎所有人都在走捷径，原因很简单，那就是为合法的内部和外部各方提供严格控制的访问会增加工作量。”

但是，可以采取比您想象的更容易实现的缓解措施，以使您的组织在抵御勒索软件攻击方面变得相当安全。

## 现在要实施的最佳实践

今年 6 月，美国政府[发布了一份备忘录](https://s3.documentcloud.org/documents/20796934/memo-what-we-urge-you-to-do-to-protect-against-the-threat-of-ransomware.pdf)，反映了勒索软件威胁的严重性，指出勒索软件是如何威胁美国和国际商业运营的。备忘录中的关键要点包括为减轻威胁而采取的措施:

这些最佳实践包括:

*   定时和一致的备份以及定期测试。
*   及时更新和修补系统。
*   响应计划测试。
*   由第三方对安全团队的实践进行检查。
*   网络分段。

“拜登总统最近关于改善国家网络安全的行政命令可以发挥作用。安全解决方案提供商 [Untangle](http://www.untangle.com/) 的首席执行官 [Scott Devens](https://www.linkedin.com/in/scott-devens-908852) 说:“提供具体的、可操作的指导方针不仅对联邦机构很重要，对一般企业也很有帮助。“看到恶意行为者如何利用漏洞，很高兴看到详细的指导方针和可操作的时间表，所有公司都可以遵循这些指导方针来防范可能会造成数百万美元损失的攻击。”

## 微分段意味着零信任

在白宫备忘录中描述的五个最佳实践中(所有这些都很重要)，网络分段可以作为一种特别有效的方式来保护作为组织命脉的应用程序和数据。

作为 Palo Alto Networks Prisma 云产品的一部分，这种数据和应用程序的分区过程也称为微分段(或[零信任分段](https://www.paloaltonetworks.com/blog/2021/01/cloud-zero-trust-microsegmentation/)),可以保护攻击面。一旦攻击者突破了网络安全边界，它还可以阻止攻击者访问关键数据的横向尝试。

帕洛阿尔托网络公司 Prisma Cloud 的产品营销经理[贾森·威廉姆斯](https://www.linkedin.com/in/iamjasonwilliams/)说:“微分段是验证你的数据中心、组织或云内部的连接，以及是否应该允许这种连接，如果允许，在什么情况下允许。“您希望限制这种连接的原因是，在发生违规时，您可以防止横向移动。”

一些安全决策者可能会对微分段概念犹豫不决，担心它太复杂，难以实施和管理。其他人，如 DevOps 团队，可能担心通过阻止对某些数据集和应用程序的网络访问来减缓业务流程，包括软件开发。

“一旦你阻断了一个网络连接，你需要确保你有 110%的信心这样做，因为如果你阻断了错误的连接，你可以关闭整个应用程序，然后可以关闭操作，”威廉姆斯说。“因此，我们希望帮助客户树立信心，因为微分段已被证明可以防止横向攻击。”

## 当封锁边界还不够的时候

可以理解的是，作为一种下意识的反应，许多组织将寻求锁定外围安全作为起点。这种尝试不一定是不合理的，因为从理论上讲，完全防火墙式的外围保护可以阻止任何入侵者进入网络并发起勒索攻击。

但考虑到在不完全了解所有漏洞发生的时间和地点的情况下修补漏洞的猫鼠挑战，以及与人类行为相关的风险，人们一致认为，仅仅依靠网络锁定来防止勒索软件攻击几乎甚至是不可能的。

> "如果我们共同完成了自动化作业，这将是一个小得多的问题."

—Torsten Volk，企业管理协会分析师

提供人工智能威胁检测和响应平台的 [Vectra](http://www.vectra.ai/) 的首席技术官[奥利弗·塔瓦科利](https://www.vectra.ai/leadership/oliver-tavakoli)说，虽然发展必要的文化和采取健全的政策来防止勒索软件攻击肯定有所帮助，但员工只需通过点击电子邮件中的链接，在不知情的情况下成为勒索软件攻击的入口。

“试图在一个组织的外围实现完美的安全性已被证明是不可能的，”Tavakoli 说。“只是随着最近勒索软件的泛滥，这种间歇性故障的潜在最终结果变得更加可怕。”

塔瓦科利建议说，对于已经越过你的第一道防线的攻击，实现一定程度的弹性也是必要的。他建议说:“建立检测它们的能力，并以紧迫感应对它们。”

通常，勒索软件或其他类型的攻击者通过未修补的安全漏洞、受损用户的帐户或其他方式进入网络，并可以在网络中隐藏数周甚至数月，直到他们能够找到一种方法来访问他们需要的真实数据，以策划勒索软件攻击(之前称为横向攻击)。因此，必须假设没有一个网络是完全安全的——这一概念也被称为零信任。

“虽然我们提倡微分段，但我们也敦促采取零信任政策:也就是说，假设所有网络内部的任何东西都与网络外部的任何东西具有相同的信任级别，”Williams 说。

## 你的备份有多好？

如果发生攻击，拥有微分段、受保护的数据和应用程序层，以及在遭遇勒索软件攻击时无法恢复公司运营的情况下恢复运行的能力至关重要。然而，风险很高，因为备份数据——无论是记录用户数据、过去交易、库存或对组织运作至关重要的其他信息的系统——都是勒索软件攻击者的关键和有利可图的目标。

访问协调安全提供商 [Pathlock](https://pathlock.com/) 的总裁[凯文·邓恩](https://www.linkedin.com/in/kevindunnesecurity)说，攻击者因此专注于部署勒索软件来加密公司数据和系统，以给受害实体造成系统停机。邓恩说，他们还会泄露敏感的公司数据，用于在黑暗的网络上赚钱，经常以罚款和收入损失的形式给受害者带来额外的痛苦。

“备份和数据复制有助于将停机时间的影响降至最低，”他说。但是，它们无法阻止公司数据的外泄，这是存储敏感客户信息的大型实体的一大担忧

此外，分布式应用程序架构增加了检查备份完整性的难度，Volk 说。“最糟糕的事情莫过于，看似所有代码和数据都已恢复，但由于备份中未包含一些小细节，导致无法运行。”

Volk 说，防范勒索软件的最佳保险是让组织能够恢复到已知的最新数据和应用状态。

“虽然这让我们所有人都感到害怕，但在保护我们的组织免受勒索软件攻击方面，除了自动定期测试恢复，没有其他选择，”他说。“这类似于早期的高可用性数据，在这种情况下，购买两次应用程序硬件，以防有必要进行故障切换，往往太痛苦了。但是，一旦时机成熟，需要故障转移环境时，我们发现我们在这上面花的每一分钱都是值得的。”

因此，加密复制和可行的灾难恢复平台至关重要，尤其是在分布式 Kubernetes 环境中。Volk 说，这是因为“Kubernetes 在部署、运营、可扩展性和升级方面遵循完全策略驱动的方法，无情地暴露了我们应用程序的弱点。

“除非我们在策略级别满足复制和灾难恢复要求，否则我们的应用程序无论在哪里运行都会普遍暴露。”

从最近的新 Stack 播客中了解有关保护您的组织免受勒索软件攻击的更多信息:

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>