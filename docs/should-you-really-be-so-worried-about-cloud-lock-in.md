# 你真的应该如此担心云锁定吗？

> 原文：<https://thenewstack.io/should-you-really-be-so-worried-about-cloud-lock-in/>

让我们从剧透开始:对云锁定的担忧可能被夸大了，并且可能适得其反。多重云是目前的一个主要流行语。许多平台和工具明确地向客户推销，它们将帮助他们避免锁定。

那么这种避免锁定的执念从何而来？有多理性？这到底意味着什么——一个组织是否需要能够即时、无缝地切换，从 AWS 迁移到 Azure，以实现真正的多云？或者在两个月内迁移到不同云的能力是否足够好？

## 锁定恐惧症的起源

根据 [Scale Venture Partners](https://www.scalevp.com/) 的常驻高管 Donnie Berkholz 的说法，避免锁定的愿望是完全可以理解的，这种反应不是对云提供商实际工作方式的反应，而是对数据中心供应商所经历的锁定型大企业的反应。他们会被某个供应商缠住，并不真正理解许可，然后让该供应商进行审核，发现违反了许可。接下来你知道，企业正在开一张数百万美元的支票。“每个人都看到了内部锁定对你的影响，”他说。“公共云中的锁定是一回事吗？”

他说，答案是否定的。在公共云中，用户已经被计量并按实际使用收费，因此不存在被“发现”做错了事并突然欠下数百万美元的风险。尽管如此，很容易理解为什么经历过多次数据中心供应商审计的人会竭尽全力避免同样的云中锁定。

> “为了实现这种灵活性，您投入了多少工程时间和权衡？这可能比你在任何情况下节省的钱都要多。”—科里·奎因

事实上，避免锁定的一个核心论点是利用优势对抗云提供商。在个人和组织层面上，没有人希望完全受供应商的支配，这正是大多数企业对其数据中心供应商的感受。但是云谈判是什么样子的呢？鸭嘴集团[的云经济学家](https://www.duckbillgroup.com/about/)[科里·奎因](https://www.linkedin.com/in/coquinn/)解释道:“在规模上，一切都变得可以商量。但是，谈判能在多大程度上降低成本，以及对抗性谈判立场的效用，都是有限度的。“让我们假设你是世界上最好的谈判者，你可以扳动开关去别的地方，你绝对会打败他们。你说的是天上掉馅饼，也许一年能节省 5%。”

这就是锁定恐惧症的核心问题。正如 Quinn 所说，“为了达到这种灵活性，你投入了多少工程时间和权衡？这可能比你在任何情况下节省的钱都要多。”

## 但是如果我想和沃尔玛做生意呢？

这并不是说没有一些合理的商业理由来采用多云策略，尽管也应该清楚的是，仅仅因为一个组织使用多个云并不意味着它可以在两者之间无缝移动。

一个问题是关于法规遵从性和数据隐私。 [Ellie Mae](https://www.elliemae.com/) 的云运营副总裁 [Justin Brodley](https://www.linkedin.com/in/jbrodley/) 解释说:“我认为有很多问题，如果价格发生变化，或者如果出现安全事件，使亚马逊、谷歌或微软对我们的客户不再有吸引力，我如何获取我的数据。"有一个应急计划是有意义的."

还有沃尔玛的例子。“如果你是一个 SaaS 供应商，如果你只在一个云上，你向一些企业销售的能力是有限的，”Brodley 说。有些企业不想支持亚马逊网络服务(AWS)，有些企业不想支持微软。您可能希望向这两种类型的企业销售。

奎因说:“这是一个非常有效的商业理由，最终至少建立你在第二提供商上所做的事情的子集。”然而，即使这样，也可能走极端——当你实际上与有这些需求的潜在客户交谈时，最好担心这种可能性，而不是在你有一个客户之前花费大量的工程时间来确保它是可能的。

## 揭示隐藏的成本

对于大多数组织来说，对云提供商锁定的担忧归结于成本。组织在云上花费了大量资金，他们与数据中心供应商打交道的经验使他们对基础设施提供商保持警惕。然而，问题是避免锁定并不是免费的——但这样做的真实成本通常不会计入财务计算中。

首先，是员工成本。Quinn 说:“很少有公司在 AWS 上的花费超过他们在工资上的花费。”“人的时间是公司最受约束和最昂贵的资产。您希望他们维护一个数据库或解决您公司解决的任何业务问题吗？”

> “问题是，因为没有使用原生函数而产生大量额外成本并损失大量功能，您试图对冲的风险是什么？”唐尼·伯克霍尔茨

其次，迁移到云的主要优势之一是上市时间。但是大多数公司都没有对一个月内推出一个新应用程序的价值进行评估，而不是六个月。“当你试图抓住市场上的一个机会时，这个机会的窗口是有限的，”伯克霍尔茨说。

“这是人们将云误解为成本故事的更大问题的一部分，”Quinn 说。“那倒不是。这关系到提高功能速度，关系到加快上市时间。”

## 所以构建云不可知是浪费时间？

根据 Berkholz 的说法，真正不知道云的公司数量实际上很少——因为这很难而且很昂贵。“问题是，因为没有使用原生函数而产生大量额外成本并损失大量功能，您试图对冲的风险是什么？”他说。

Brodley 同意，当你构建真正的云无关的应用时，这正是会发生的事情。不过，和往常一样，有时额外的花费是值得的。“那些做得正确的人是出于正确的原因，”他说。“这些公司花时间仔细考虑他们的客户需要什么。他们真的花了很多时间来思考价值主张，而不是仅仅说，“我们将成为云不可知论者，因为这是所有首席技术官都在做的很酷的事情，我担心成本。”"

那么，对成本的担忧呢？他们到底有多不理性？

“迄今为止，云提供商从未提高价格，”Brodely 说。“最大的担忧是它们都将被大量市场采用，然后提高价格。这种情况有可能发生，但我认为根据目前的记录，这种风险相对较低。”

亚马逊网络服务是新堆栈的赞助商。

来自 ErikaWittlieb de Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>