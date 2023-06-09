# 流星准备计划对灾难恢复的价值

> 原文：<https://thenewstack.io/the-value-of-a-meteor-ready-plan-for-disaster-resilience/>

[](https://www.blameless.com/)

 [艾米丽·阿诺特

艾米丽是“无可指责”网站的内容作家，她为学习如何实施网站可靠性工程的团队开发教育资源。她还在 SREcon 和 Conf42 会议上发表演讲，主题是“无辜作战室中的大象:责任”。](https://www.blameless.com/) [](https://www.blameless.com/)

在现场可靠性工程(SRE)中，我们认为有些故障是不可避免的。接收更新的复杂系统最终会遇到您无法预料的事件。你能做的就是做好准备，尽可能减轻这些事件的伤害。

灾难准备的一个方面是[事件响应](https://www.blameless.com/incident-response) —建立程序来解决事件并尽快恢复服务。另一个策略是通过减少单点故障的策略来减少失败的机会。今天，我们将讨论第三种类型的准备:拥有备份系统和冗余，以便在出现严重问题时快速恢复功能。

拥有备份系统可以让组织高枕无忧。不管出了什么问题，你只要切换到备份系统一会儿，然后一切都好了，对吗？灾难来临时真的会这么顺利吗？在这篇博客文章中，我们将通过以下几个方面来帮助您确保您的备份系统在您最需要的时候能够按预期运行:

*   运行恢复演习的价值
*   从整体和横向的角度思考事件
*   通过想象和准备“黑天鹅”事件来提高应变能力

## 运行恢复演习的价值

许多组织都有数据和基础架构的备份，当主系统出现故障时，他们可以切换到这些备份。这个“开关”到底是什么呢？考虑一下[一位工程师与我分享的这个故事](https://www.blameless.com/incident-response/on-call-team-faces-worst-case-sunday-scaries),它讲述了一场噩梦般的停机，起因是他们的数据库被彻底清除。该团队已经准备好了备份数据库，但是在使用之前需要对它们进行解压缩。那需要多长时间？他们不知道。

这位工程师的故事太普通了。组织感到安全，因为所有东西都有备份，但他们实际上不能依赖这些备份在灾难中立即可用。该工程师的故事中的另一个关键因素是缺乏资源:由于他们没有内部基础架构团队，他们不得不依靠一个没有经验的人来遵循过时的操作手册。

解决这个噩梦的方法是定期进行恢复训练。模拟一个场景，其中所有内容都需要从生产系统切换到备份系统。从那里，思考:

*   需要多长时间？
*   现在你有什么障碍可以消除吗？
*   还要看看你所依赖的资源。是否正在征求个人的意见？
*   您是否使用基础设施来访问操作手册？
*   如果这些人失踪了或者基础设施也瘫痪了怎么办？

你也要为这些可能性做好准备。完成这些练习后，大家一起回顾一下可以改进的地方。然后——这是最重要的部分——安排下一次训练。随着代码库的变化和数据库的增长，要确保备份恢复顺利进行。

不要对未经测试的备份沾沾自喜。在最近的一次讨论中，无可指责的 SRE [杰克·英格伦](https://www.linkedin.com/in/zeblith/)这样总结道:说到备份策略，如果你不测试你的恢复过程，那么你就不能确定你的备份是有用的。如果你不确定你的备份是否有用，那么它们可能没有用。

## 从整体和横向的角度思考事件

当事情出错时，人们很容易想到单数——某件*事情*出错了。服务器停机，代码输入错误导致错误，高流量导致延迟，等等。不过，实际上，大多数事件都会引发其他失败的多米诺骨牌效应。为失败做准备时，考虑到所有可能出错的事情是很重要的。

以下是一些需要考虑的事情:

*   你的典型交流工具也会停止吗？
*   如果您的工具停止运行，像 runbooks 这样的资源还可用吗？
*   您用来恢复备份的服务也会停止吗？
*   在发生重大故障时，您期望能够做出响应的人会处理更重要的事情吗？它们到底能不能用？
*   工程团队会有压力、筋疲力尽、无法发挥正常水平吗？

每个组织都有自己在事故中可能出现的问题。过去的事件是你找到它们的最好老师。创建[事件回顾](https://www.blameless.com/product/incident-retrospectives)来调查事件的原因和影响。像[贡献因素分析](https://www.blameless.com/incident-response/how-to-analyze-contributing-factors-blamelessly)这样的技术可以帮助你发现这些一致的问题。

一旦你发现了这些问题，确保你的备份计划能够弥补这些问题。不要遗漏任何东西:考虑每一个因素，从技术到个人。如果你有一个内部工具来运行新的服务器，不要认为你会有。如果工程师在出现问题时会感到恐慌，那么要确保解决方案有明显的标记，并且容易获取。

真正跳出框框思考，深入挖掘你提出的解决方案，发现其中可能出现的问题。杰克分享的一个例子是依靠通过卡车运送的备用发电机来解决停电问题。如果卡车堵车或者抛锚了怎么办？不要满足于只有一个解决方案；如果你的解决方案坏了，有一个解决方案，并有一个备份。

## 想象和准备“黑天鹅”事件

一个[“黑天鹅”事件](https://en.wikipedia.org/wiki/Black_swan_theory)是一个几乎不可能预测甚至想象，但会造成灾难性损失的事件。回想起来，黑天鹅事件显然是有可能发生的；然而，在它发生之前，这是不可想象的。

科技领域黑天鹅事件的一个例子是最近的[脸书停电](https://en.wikipedia.org/wiki/2021_Facebook_outage)。脸书没有为他们的 DNS 服务器完全崩溃做好准备，他们也无法想象随之而来的许多问题，比如[无法实际进入他们的办公室](https://futurism.com/the-byte/facebook-employees-have-reportedly-been-locked-out)。如果一个普通的事件会产生多米诺骨牌效应，那么一个黑天鹅事件就像推倒一座纸牌搭建的房子。

那么，如何为不可想象的事件做准备呢？一个策略是变得有创造性。杰克分享了他在谷歌工作时的一个例子:模拟整个山景城谷歌总部被流星击中。在回答练习中，每当你试图联系那里的人，访问那里的服务器，甚至依赖那里管理的带宽时，都要停下来。不能；它被一颗流星击中了。

现在，你的总部真的会被流星从地图上抹去吗？几乎可以肯定不是。如果是的话，分行部门真的会争先恐后地恢复服务吗？不，他们可能有更大的担忧。然而，通过攻击这种最糟糕的情况，你为其他你无法想象的事件做好了准备。

杰克强调了测试的重要性，“不仅仅是为了你想测试的东西。”灾难准备的目的不是得到你想要的结果，而是发现漏洞并推动系统的改变。杰克将这个想法描述为区分健壮性，测试你知道可能出错的一切；和弹性，测试你希望你不必知道的东西。一般来说，杰克发现组织非常擅长前者，而非常不擅长后者。

通过测试未知来建立弹性是一种需要迭代和反思的实践。没有一个正确的方法去做，也没有一个正确的频率去探索这些场景。重要的是彻底记录你的过程和结果。然后，分析哪些类型的实验产生了洞察力，并围绕它们构建未来的测试。坚持练习，确保在上一个实验完成后，安排下一个实验。

对于这些世界末日的场景，可能存在什么解决方案呢？Jake 讨论了一个观点，这个观点起初看起来似乎违反直觉。一般来说，一个组织走向成熟和发展的道路首先需要依赖第三方工具，然后在内部构建越来越多的工具和基础设施。主要企业组织可能会构建自己的通信、警报和跟踪工具。

然而，黑天鹅事件表明，可能还有更进一步的成熟阶段:整合第三方工具作为备份。如果你不能用你的工具来解决问题，你应该准备一些其他的工具。当然，像任何备份系统一样，您需要进行演练，以确保功能实际上会被交换机恢复。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>