# 为什么富国银行希望每天“重新铺设”其平台

> 原文：<https://thenewstack.io/why-wells-fargo-repaves-its-entire-platform-every-day/>

[](https://tanzu.vmware.com/)

 [德里克·哈里斯

德里克是 Pivotal 公司产品营销高级经理。前世包括出版 Architecht 时事通讯和播客；涵盖 Gigaom 的云计算、大数据、人工智能等；以及软件创业公司的各种营销角色。](https://tanzu.vmware.com/) [](https://tanzu.vmware.com/)

尽管石洗牛仔布和复古飞人乔丹气垫鞋凯旋归来，但我们真的不是生活在 20 世纪 90 年代。这一点在技术领域最为明显，在这个领域，我们已经从一个蓬勃发展的互联网发展到一个几乎做任何事情都需要互联网连接的世界。然而，伴随着无处不在而来的是机会——对企业，对消费者，不幸的是，对罪犯。

这就是为什么第一次互联网繁荣时期的另一个重大转变是公司如何对待他们的基础设施。对于有远见的公司来说，容器、函数和应用程序实例等事物的不可改变性也为提高安全性提供了机会。从一个已知良好的状态中终止并重新启动应用程序组件比不断地打补丁、配置和尽一切可能保持服务器运行更安全(也更高效)。

这就是为什么富国银行开始通过 Pivotal Cloud Foundry 实现基础设施和开发实践的现代化，同时也在加强网络安全方面的游戏。作为世界上最大的银行之一，它不能冒险保护敏感数据免受入侵。许多安全计划侧重于应用漏洞和检测入侵，但 PCF [通过零停机修补和将虚拟机“重新修复”到已知干净状态，帮助确保平台级](https://builttoadapt.io/the-three-r-s-of-enterprise-security-rotate-repave-and-repair-f64f6d6ba29d) 的安全。

在 SpringOne Platform 2018 的演示中，富国银行的云铸造产品负责人兼技术经理 Lance Rochelle 解释了该公司如何通过每周多次重新铺设其整个平台来应对高级持续威胁以及 CVEs 的冲击，目标是到 2019 年底每天都这样做*。*

 *你可以观看 [视频](https://www.youtube.com/watch?v=j15pR_aOxD8) 了解所有细节，或者继续滚动观看视频下方他的讲话中的一些亮点——为了简洁起见，这些都经过了编辑。

[https://www.youtube.com/embed/j15pR_aOxD8?feature=oembed](https://www.youtube.com/embed/j15pR_aOxD8?feature=oembed)

视频

以下是罗谢尔关于富国银行安全改造的讲话摘录:

## 来自“为什么打补丁？”让我们每月做一次。'

二十年前，我们将正常运行时间作为衡量成功的标准。每个人和他们的兄弟都有这些传统服务器。他们害怕重启它们。他们有几千天的正常运行时间。你不能真的修补它们，因为你担心磁盘不会旋转或者内存会失效。

在 2002 年，有人说，“你知道，我们真的应该修补，即使只是做一个健全的检查。”也许是，也许不是。在我工作过的许多企业环境中，这就是它的工作方式。大约在 2004 年，我们会说，“这种修补并不太糟糕。一年一次，两次，也许一年三次。”…[E]最终我们减少到每季度一次，然后在 2011 年、2012 年左右，一些出色的安全人员就像这样，“让我们开始一个定期的修补周期。一个月做一次吧。”

## 简历从未停止过

每个月都有成千上万份简历被报道。我们不想做的是将这些 cv 放在平台上，放在应用程序代码中。我们希望确保它们得到修补和更新…你们中有多少人处理合规性和许可，然后他们来找你，因为某个地方的某个库不再维护，或者某个地方的某个库有一个与 CVE 相关的漏洞？

我估计今年会有 19500 多份简历被报道。那太多了。去年只有 14714 辆。…应对这些威胁的唯一方法是不断自动更新一切。

## 日常重铺需要自动化

是什么阻止了您每天重建一次环境？我可以告诉你，如果你手动修补你的环境，你永远不会得到一天一次。你将每个月纠结一次，每周纠结一次…

…但我想为您分解一下，以便您了解当您部署一个应用程序时，该应用程序有许多实例，这些实例遵循…一种云原生实践，它们能够被修补…而不会对客户造成影响。我们已经看到了这一点，因为我们现在每周做一次，到明年年底，我们将每天做一次。在我们所有的[PCF]基金会中，我们已经看到了大概 7[百]或 800 次。

## 用结果和耐心说服您的客户

当[内部客户]向我索要[维护]时间表时，我不会给他们。然后，我解释说，我们有一个预先批准的变更记录，允许我们在关键的在线窗口后的任何晚上进行变更。然后他们会问，“那你怎么通知我们？”我说，“我没有。”

我会告诉你:一开始……你会花几个小时——几百个小时——开会。但是，在这种情况发生五六次后，其他应用团队会说，“老兄，我们还没有遇到问题。你重铺了几次？”我说，“我不知道，大概 40 岁吧。”

然后，其他应用程序团队开始成为倡导者，因为他们喜欢，“当你们修补程序时，我们不必从晚上 7 点到凌晨 2 点站在桥线上……”但是，前几个客户，你必须花大量的时间向他们解释。这就是为什么[这个]演示通常是两个半小时…我必须从“什么是云铸造厂？”

## 与 Pivotal 合作实现最高安全性

PCF 管理重铺的方式]允许我们将一段代码部署到环境中，并且知道它的每次实例化都基于一周前、一天前、一个月前最初部署的同一组代码。

Pivotal 对我们来说是一个很好的合作伙伴，但是作为富国银行，我们不相信任何人[所以我们在内部采取了一些额外的措施来满足我们的要求。]

然后我们使用扫描代理，类似于 Pivotal 使用的，然后我们比较笔记。每次有更新时，我们的安全漏洞评估小组和他们的安全漏洞评估小组都会交换意见，以确保我们没有遗漏他们发现的内容，他们也没有遗漏我们发现的内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*