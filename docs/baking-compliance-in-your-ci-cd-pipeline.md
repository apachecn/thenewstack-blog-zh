# 在您的 CI/CD 渠道中实现合规性

> 原文：<https://thenewstack.io/baking-compliance-in-your-ci-cd-pipeline/>

[](https://www.paloaltonetworks.com/prisma/cloud)

[Scott Fitzpatrick](https://www.paloaltonetworks.com/prisma/cloud)

[Scott Fitzpatrick 是 Twistlock 的撰稿人，拥有超过六年的软件开发经验。他使用过许多语言，包括 Java、ColdFusion、HTML/CSS、JavaScript 和 SQL。](https://www.paloaltonetworks.com/prisma/cloud)

[](https://www.paloaltonetworks.com/prisma/cloud)[](https://www.paloaltonetworks.com/prisma/cloud)

当 DevOps 工程师谈论[持续集成/持续交付](https://thenewstack.io/category/ci-cd/) ( [CI/CD](https://www.twistlock.com/platform/continuous-integration-tools/) )时，合规性通常不是谈话的主要部分——但是对于任何想要领先于合规性挑战的组织来说都应该是这样。就像 CI/CD 管道中的其他东西一样，法规遵从性应该是持续的，并且应该融入交付过程的所有阶段。这不是在筒仓里能发生的事。

DevOps 组织如何实现这一目标并利用 CI/CD 的实践来帮助提高他们确保其应用程序的信息安全性和软件合规性的能力？下面我们将讨论开发管道的每个部分如何帮助实现应用程序内的符合性，同时仍然及时地交付软件。

## 什么是合规？

在软件开发领域，遵从性是指应用程序必须遵守的安全标准，符合为应用程序运行所在的特定行业制定的法规。

这方面的一个例子包括[支付卡行业数据安全标准(PCI DSS)](https://en.wikipedia.org/wiki/Payment_Card_Industry_Data_Security_Standard) 。任何接受信用卡支付的公司都必须遵守 PCI 标准。建立这些标准的原因显而易见，其中最重要的是确保客户数据的适当信息安全级别。尽管在更快的开发周期中交付软件的 DevOps 理念可能看起来对应用程序安全性有害，但是构成 DevOps 组织的主要原则实际上可以提供可行的环境，使应用程序安全性成为开发过程的固有内容。

## 将合规性融入您的 CI/CD 渠道

那么，像 CI/CD 这样的 DevOps 实践如何使法规遵从性要求更容易实现呢？答案是将法规遵从性直接纳入您的开发管道。这需要负责开发管道所有部分的人的一致努力，从开发人员到测试人员到管理员。

通过从项目一开始就承担遵从性的责任，开发人员可以帮助确保将应用程序遵从性构建到开发过程中。如前所述，持续集成提供了一种通过使用与 CI 工具的自动化测试集成来持续测试应用程序的方法。对于应用程序安全性和合规性测试，也可以做同样的事情。通过[自动化安全性和合规性测试并将它们与您的 CI 工具](https://www.twistlock.com/platform/continuous-integration-tools/)集成，您将实现对您的应用程序安全性至关重要的几个目标:

*   合规缺陷将在流程中比以往任何时候都更早地被发现。正如我们所知，漏洞发现得越早，修复的成本就越低；
*   开发人员将合规性问题引入代码库的可能性显著降低。当符合性测试作为每次提交的结果运行时，它们应该确保提交的代码符合必要的标准。测试失败将意味着构建失败，而构建失败将立即通知开发人员必须在集成他/她的代码更改之前采取行动。

## 在整个管道中微调合规性

DevOps 测试人员工作职责的主要部分是寻找机会使应用程序测试更加高效和有效。我们通常从确保应用程序质量的角度来考虑这个问题。但是，如果我们将法规遵从性视为应用程序质量的一部分呢？培训测试人员不断地识别机会来改进符合性测试，并使这种测试尽可能地可重复，这将导致符合性成为组织的第二天性。这种好处将贯穿整个开发过程，确保代码库中出现更少的合规性错误，而进入代码的错误很容易识别，并且——如果运气好的话——很容易修复，因为它们有可能在过程的早期被发现。

众所周知，当一个应用程序被部署到生产环境中时，开发管道并没有结束。有必要对生产环境进行仔细监控，以确保尽快发现并缓解任何问题。从这个意义上说，合规性监控有助于使您的应用程序符合适当的安全法规和要求。实施有助于识别这些问题(如果它们存在于生产中)的审计和日志记录可以为您的 DevOps 团队带来极大的保证和安心，即客户信息和您的环境作为一个整体按照行业标准得到保护。

## 结论

确保应用合规性需要 DevOps 团队所有成员的参与。当开发人员、测试人员和管理员共同努力将合规性融入到开发流程中时，就会大大降低发布不合规软件的几率。在全面参与的情况下，在整个过程中，法规遵从性被视为应用程序质量的一部分，团队成员在最后放弃了不太有效的合并法规遵从性的方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>