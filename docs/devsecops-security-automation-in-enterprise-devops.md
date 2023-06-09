# DevSecOps:企业开发中的安全自动化

> 原文：<https://thenewstack.io/devsecops-security-automation-in-enterprise-devops/>

又是一天，又是一个行李箱。DevSecOps——AdWords 上的一个昂贵的目标——试图将安全性融入 DevOps 过程。这有点傻，因为公司当然应该将安全性考虑到他们的开发中，特别是当 DevOps 的大部分内容是关于企业更快地发布应用程序的时候。

亚马逊网络服务的高级解决方案架构师 Margo Cronin 在 T2 欧洲 DevOps 企业峰会上开始了她的演讲，她说她个人不喜欢 DevSecOps 这个术语。

“DevSecOps”这个词总是让我觉得像最后一个上车的孩子，没有座位了。我们把安全视为事后的想法。无论是在金融服务领域还是现在的亚马逊网络服务领域，我从未在与任何客户打交道时考虑过安全问题。我觉得这个名字没有反映出它的重要性，”克罗宁说。

事实上，根据 GDPR 的新欧洲法规，她说设计隐私和默认隐私是固有的。

“它几乎要求你应该做开发工作，”她说。

那么，到底 DevSecOps 对 Cronin 来说是什么？尽早并经常将安全自动化作为优先事项。她来自亚马逊，来自一个有安全自动化经验的地方。毕竟，AWS 在 2017 年发布了几乎 1500 项关键功能和新服务。Amazon.com 每 11.6 秒执行一次生产部署，平均同时执行 10，000 台主机。AWS 和 Amazon.com 如何在开发运维的同时保留核心安全实践？

“如果有安全问题，它会成为晚间新闻，”克罗宁说。

最后，你可以称之为 DevSecOps 或 Rugged IT，就像敏捷和看板爱好者所说的那样，但 AWS 对它的称呼非常准确:云规模的安全自动化。

## 安全自动化避免了人为错误

克罗宁说，亚马逊“如此热情地”拥抱 DevSecOps，因为他们需要 DevOps 快速行动，考虑到他们相当大的合作伙伴，这意味着首先自动化安全，以避免这三种人性陷阱:

1.  人都会犯错。克罗宁要求观众想象他们是在深夜工作的工程师，在生产中有一个严重的问题。“您有一个 IT C 级利益相关者告诉您让服务重新上线。你正处于一级紧急呼叫的第五个小时。你在一个有 40 人的空闲频道上，其中 38 人没有真正做出贡献。你在喝第七杯咖啡。你可以改变生产来解决这个问题。”她说，在这些常见的情况下，你比在正常情况下更容易出错，也许你忘记了记录更改，下一个版本会覆盖修复。“人类会犯错，当你处于压力之下时，你更有可能犯错。”
2.  人们不遵守规则。然后，她分享了一个善意的常见用例，人们为了提供帮助和合作而变通规则，就像当你计划了一个大的发布(和发布派对)，每个人都准备好庆祝了，就快到了，所以你说:“我们只是要把它拿出来。我们将在明天发布并修复它。人们会要求你在好的地方变通规则，但这会在你的产品格局中造成缺口。”
3.  人们的行为带有恶意。“虽然像 DDoS 这样的攻击是自动化的，但幕后总有人在煽动这种攻击。”

当一个错误被写入代码或自动化流程时，这些错误会频繁地重复出现，从而产生易于诊断的模式。

机器不会犯错误，不会违反规则，也不会恶意行事，这就是为什么 Cronin 认为自动化安全任务必须是成功开发的最大优先事项。

## 实现大规模安全自动化的四个步骤

接下来，Cronin 概述了实现大规模安全自动化的四个步骤，并指出“这并不详尽，但我见过一些公司采取了四个步骤来增加 DevSecOps 流程的价值。”

### #1:建立你的信任度

对于这一点，她有她所谓的你对你的云或内部提供商的信任的界限或范围。Cronin 指出，具有明确安全流程和治理的大型分布式组织通常信任度较低或为零。这些低信任度公司想要自己的托管密钥和自己的硬件安全模块。他们处于这个范围的一端。

在这个范围的另一端是初创公司和电子商务平台，它们使用云服务提供商的所有服务。

“不管你在光谱的哪个位置，你仍然可以获得云的价值，但是你拥有的信任点与你需要实施的自动化程度是一致的，”她说。

克罗宁举了一个自动化程度更高的转移信任的例子。这个信任零可能是一个部署本地 Kubernetes、管理主节点(扩展和分布式共识)、工作节点和所有安全性的公司。

另一方面，在右侧，她提供了一个例子，其中具有较高信任度的客户使用一个名为 AWS Elastic Kubernetes Service 的 AWS 服务。

“简化了建立自己的 Kubernetes 控制平面的复杂性。您不用在您的帐户中运行 Kubernetes 控制平面，而是连接到 AWS 云中的一个托管 Kubernetes 端点。这个端点抽象了 Kubernetes 控制平面的复杂性——您的工作节点可以签入一个集群，并且您可以通过您已经知道并喜欢的工具与您的 Kubernetes 集群进行交互。默认情况下，[在 AWS 的这个场景中] Kubernetes 基于角色的访问控制[RBAC]是打开的，卷被自动加密，AWS 进行证书管理。”

在这里，克罗宁提到了一个围绕 Kubernetes 的常见问题，它默认关闭了 RBAC。这就是去年春天发生在特斯拉身上的事情，当时有人能够黑进它的控制平面，因为没有人启用 RBAC。她说，通过更加信任 AWS 的弹性 Kubernetes，Kubernetes 的 RBAC 会自动打开，与 AWS 进行本机集成，并管理主节点。

她说“无论你处于信任等级的哪个位置，都要计划集成安全自动化，但是要记住，创建这种自动化也需要开发团队的时间。”

这包括根据您在所示信任栏上的位置来映射工具。信任级别越低，DevOps 团队需要实现的安全自动化级别就越高。信任级别越高，云提供商就越能为您自动管理和自动化。这将影响你发布最小可行产品的速度。此外，信任越少，你就越需要提前计划你的安全，比如必须确保你的 RBAC 是开着的。

### #2:安全源于设计

Cronin 认为，在 DevSecOps 中，每个团队成员都感受到了安全所有者的责任——它不再是另一栋大楼中的团队，而只是项目的利益相关者。就像 DevOps 拆除开发人员和运营人员之间的孤岛一样，同样的事情也必须发生在安全性方面。

使用 DevSecOps，sprints 可以基于安全需求。将史诗分解为功能安全故事。这一安全流程过去需要几个月的本地托管时间，具有复杂的瀑布史诗。现在，她说，对于任何云服务提供商，你都可以分段安装 Web 应用防火墙，通常是:

*   身份和访问管理
*   记录和监控
*   事件响应
*   基础设施安全
*   配置和漏洞分析
*   保护持续集成和持续部署(CI/CD)渠道
*   数据保护

然后，您可以使用相同的动态 CI/CD 管道来部署您的安全特性，就像您对其余开发操作系统所做的那样。

设计安全性还意味着拥有与安全性相关的验收标准。继续以 GDPR 的需求为例，当用户登录系统时，用户拥有自己的数据有很多优先级，您已经演示了如何删除这些数据，并演示了如何实际转移这些数据。安全自动化必须测试这是否可能，并且在理想情况下，全部记录下来。

### 安全自动化第三步:保护管道

Cronin 说，上面的例子和许多安全自动化建议也可以应用于内部，包括如何处理 CI/CD 管道的安全性(包括访问角色和构建服务器和节点的强化)和安全性(包括工件验证和静态代码分析)。

她建议纳入一组 DevSecOps 开源资源 [Git Secrets](https://github.com/devsecops) 的帮助，并利用这些工具和云来完成以下重要的 CI/CD 步骤:

*   存储库中的身份验证和验证
*   记录整个环境
*   向开发人员发送构建报告，如果构建失败，停止一切
*   向安全部门发送构建报告，如果审核或验证失败，则停止所有操作

Cronin 还将基础设施称为代码，从开发>集成测试>用户验收测试>推向生产的经典水平阶段转向网络、安全、应用、日志和监控的垂直阶段。

“然后，如果你认为一个阶段的一部分受到了损害，你可以很快将其拆除，然后恢复。你可以拆除 UAT(用户验收测试)安全屏障，让 UAT 的其他部分完好无损，”她说。

这一安全自动化流程与上述垂直阶段相结合，变得高度不可改变，并降低了您的爆炸半径。

### #4:自动回复

为了使安全自动化工作，您需要根据您的日志文件知道您在做什么。围绕您的日志，可以归结为四个问题:

*   你什么时候收集日志？
*   你为什么收集日志？
*   你在哪里收集木头？
*   根据你的日志你在做什么？

以某人关闭 AWS 服务为例。它可以向您的安全团队发送一个自动事件，让他们查看环境。它允许您决定它是否被权限过高的人关闭，或者它实际上是一个需要调查的事件，也许服务器需要隔离。Cronin 指出了日志已经变得多么强大，以及云中的日志是如何防止更多事件发生的。

最后，当考虑自动化安全时，最好遵循 Cronin 关于 Sec 在 DevSecOps 中的重要性的最后一句话:

“如果安全是您最重要的工作，您应该首先考虑自动化这些任务和故事，然后再做其他事情。”

图片:[欧洲 DevOps 企业峰会推特](https://twitter.com/DOES_EUR/status/1011568996725018624)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>