# 为什么大型机零信任是金融机构的当务之急

> 原文：<https://thenewstack.io/why-zero-trust-for-mainframes-is-a-financial-institution-imperative/>

[](https://www.linkedin.com/in/christophertperry2/)

 [克里斯·佩里

克里斯·佩里是网络安全战略家，对于 BMC](https://www.linkedin.com/in/christophertperry2/) [](https://www.linkedin.com/in/christophertperry2/)

大型计算机继续构成金融服务 IT 运营的支柱。[根据 Constellation Research 的调查，](https://www.constellationr.com/blog-news/mondays-musings-inside-why-mainframe-alive-and-thriving)排名前 50 位的银行中有 45 家的核心银行功能依赖于它们。[大型机系统每天处理大约 3 万亿美元的交易，这个数字可能低估了大型机在金融服务中的影响，因为它只计算了使用 COBOL 的交易。](https://www.reuters.com/article/us-usa-banks-cobol/banks-scramble-to-fix-old-systems-as-it-cowboys-ride-into-sunset-idUSKBN17C0D8)

这种需求将继续增长。根据德勤最近的一项调查，依赖大型机的公司中 91%的管理人员将大型机的扩展视为未来 12 个月的首要任务。

然而，大型机的安全性容易受到误解的影响，从而使金融机构暴露无遗。高管们过于依赖“通过模糊实现安全”的想法，这是一种说威胁行为者避免攻击大型机的方式，因为他们更熟悉 Windows 或 Linux 操作系统。

默默无闻的安全是不够的。现实是，今天所有的大型机都运行 Unix 系统服务，具有黑客熟悉的基于 Linux 的相同功能和工具。最重要的是，大型机通常缺乏现代的检测和响应工具，而这些工具在网络的其他部分已经变得无处不在。这意味着能够访问大型机系统的攻击者将能够保持持久性，并轻松扩展他们的初始足迹，以获得对平台的完全控制。

## 大型机信任的风险

为了保护他们的大型机并保持弹性，金融服务公司需要迁移到一个现代的零信任架构，该架构由“永不信任，永远验证”的口号定义。随着网络安全维护者意识到他们需要更深入的防御，零信任越来越受欢迎。有太多的例子表明，黑客通过窃取凭据获得对组织的初始访问权限，并意识到他们可以使用这些凭据获得对整个环境的访问权限。这极大地减少了黑客窃取或破坏敏感数据的工作量，同时限制了防御者有效检测和响应入侵的能力。

使用零信任，您将不断评估用户的身份、用户与之交互的资源的敏感性以及用户访问这些资源的权限。它旨在防止网络内的特权提升和横向移动，而高级威胁参与者经常成功地使用这种方法。这一理念虽然存在了近十年，但在过去的一年里，随着美国国家安全局推出指导方针和 T2 白宫发布自己的零信任战略，这一理念获得了巨大的发展势头。

## 加剧风险

过度依赖传统的基于边界的安全模型，这种模型赋予用户巨大的信任，通过模糊性加剧了安全性的弱点。不幸的是，仍然经常听到有经验的大型机专业人员声称大型机没有风险，因为它不是面向 internet 的。然而，他们也从典型的笔记本电脑连接到大型机，这是一种有针对性的网络钓鱼攻击，而不是通过单因素凭据访问进入大型机。

在配置不佳的大型机中，用户可以访问文件、导出数据并横向移动以获得更多权限。虽然大型机拥有来自最大的外部安全管理公司之一的身份访问管理控制，但现实情况是，这些平台几乎从未经过基于对抗的渗透测试器的评估，这意味着大多数金融机构的系统每天都存在大量未知漏洞。缺乏足够的控制使这种类型的系统极易受到内部威胁或外部参与者获取受损凭据的威胁。

例如，一家公司的主机不具备现代网络安全能力，成为勒索软件攻击的受害者。黑客在一台可以进入主机的笔记本电脑上使用了一个无文件键盘记录器。随着时间的推移，他们获得了敏感密码，并能够在加密大型计算机后勒索数百万美元的赎金。这些黑客不太可能拿了赎金就退休了。

最终，因勒索软件或另一次网络攻击而失去大型机对几乎所有金融机构来说都将是灾难性的。如果你是一家因为主机坏了而无法处理信用卡交易或允许用户查看账户的银行，那么你将根本无法开展业务。这要求大型机获得与企业中其他服务器相同的安全功能和关注，这些都由零信任架构提供最佳服务。

## 步行和跑步到零信任

对于 IT 管理员来说，大型机零信任策略的核心组件包括强大的身份管理和增强的设备安全规则。这些组件需要管理敏感数据与访问这些数据的人员、工作负载、网络和设备之间的交互。在这个领域没有十全十美的东西，但是当你开始你的零信任之旅时，你可以在前进到更复杂的能力之前执行小而高效的解决方案。

下面是可以立即采取的四项措施，这些措施可以显著提高大型机环境的恢复能力，并帮助您实现零信任体系结构:

1.  **加密:**大型机与云等其他环境之间的工作负载应该加密。这听起来可能是显而易见的，但许多公司仍在运行没有加密的 3270 连接，这使得用户名和密码以明文形式留在网络上。

2.  **监控:** IT 管理员需要强大的网络可见性来执行和监控这些策略。问问自己，您的大型机数据是否集成到了实时安全工具中，如企业安全信息事件监视器(SIEM)。如果不是，这个盲点会给你带来很大的风险。

3.  **多因素身份验证(MFA):** 您不能让一个大型机管理员成为外部威胁和对您的大型机的特权控制之间的唯一网关。如果这个管理员被钓鱼会怎么样？MFA 虽然不是万灵药，但已被证明能够显著降低外部威胁破坏凭证和进行伪装攻击的能力。

4.  **特权访问管理:**您不想让安全控制限制您的运营团队开展工作所需的灵活性。自动管理与合法和批准的服务工作相关的特权访问，以便在遵循最低特权原则的同时平稳维护大型机。

虽然这些策略将极大地提高安全性，但列表并不完整，其中一些功能比其他功能更容易实现。最终目标是您的技术强制执行这样一个策略，即您的数据真正只被那些被适当授权使用它的人访问。

最重要的是，你决定零信任是一个关键的业务目标，并形成一个正式的倡议，因为零信任架构不会偶然发展。如果您在 CISO 下的企业安全团队已经有了一个零信任计划，那么确保大型机是有意范围的一部分还不算太晚。如果没有，这是开始旅程的最佳时机，同时确认从大型机到云的所有服务器都受到同等保护。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>