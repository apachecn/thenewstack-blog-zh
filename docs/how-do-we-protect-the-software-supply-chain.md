# 我们如何保护软件供应链？

> 原文：<https://thenewstack.io/how-do-we-protect-the-software-supply-chain/>

底特律——据拥有 25 年开源经验的资深人士 [Aeva Black，](https://www.linkedin.com/in/aevaonline)称，现代软件项目对灵活性和构建社区的强调，已经导致许多在 Linux 内核早期开发的安全最佳实践半途而废。

[我们如何保护软件供应链？](https://thenewstack.simplecast.com/episodes/how-do-we-protect-the-software-supply-chain)

“现在我们在玩追赶游戏，”微软 Azure 首席技术官办公室的开源黑客布莱克说。“过去五年，许多不太理想的做法已经根深蒂固。我们现在正努力帮助教育每个人。”

[https://www.youtube.com/embed/aQAFIw4CCJg](https://www.youtube.com/embed/aQAFIw4CCJg)

视频

[Chris Short，](https://www.linkedin.com/in/thechrisshort)[亚马逊网络服务(AWS)](https://aws.amazon.com/?utm_content=inline-mention) 的高级开发者代言人，挑战“左移”的概念，赋予开发者更大的安全责任。“如果安全是每个人的工作，它就不是任何人的工作，”DevOps-ish 时事通讯的创始人 Short 说。

“我们已经经历了这种演变:只要开发安全的代码，你就会没事，”他说。“没有安全代码这种东西。底层语言有时会有错误…没有安全软件这种东西。因此，您必须减轻风险，然后准备好防御即将到来的漏洞。”

Black 和 Short 在 New Stack Makers 播客的“在路上”一集中谈到了软件供应链的安全状况。

他们与 TNS 特写编辑 Heather Joslyn 的对话是在汽车城的 KubeCon + CloudNativeCon 北美录制的。

本期播客由 AWS 赞助。

## '信任，但要核实'

对于我们的播客嘉宾来说，“信任，但要核实”是更多组织需要遵循的口号。

Black 说，困扰软件供应链的许多安全问题是公司——尤其是较小的组织——直接从上游拉软件。他们信任某个人发布的构建，他们不验证，不检查哈希，不检查签名，他们只是从某个地方下载 Docker 映像或二进制文件，然后在生产中运行它。”

布莱克说，这种做法“让他们暴露于上游发生的任何变化。如果 upstream 在存储库中有一个错误或网络错误，那么他们也不能更新。”他们说，组织应该维护一个内部暂存环境，在将代码推向生产之前，他们可以验证从上游检索到的代码，或者在发现漏洞的情况下重建代码，并将其推回上游。

Short 补充说，构建环境也应该有防火墙保护:“创建那些安全措施，‘哦，你想从一个不被认可的来源或者不被信任的来源获取一个包？抱歉，不会发生的。"

播客嘉宾指出，能够重建有漏洞的代码以使其更加安全——或者甚至能够快速识别出问题所在——是没有足够多的开发人员具备的技能。

肖特说，更多的自动化是解决方案的一部分。但是，他补充说，这本身是不够的。“持续学习是我们在这里的工作，”他说。“如果你有点像，这是我的技能集，这是我的工具箱，我不愿意超越它，你是在给自己设置失败，对不对？因此，你必须能够在接到通知后马上说，“我需要改变我整个环境中的一些东西。”。“我该怎么做，”"

## GitBOM 和“信噪比”

正如 Black 和 Short 在我们的谈话中所说，没有绝对安全的代码。甚至像 [software bills of materials，或 SBOMs，](https://thenewstack.io/how-to-create-a-software-bill-of-materials/)这样被高度吹捧的工具也不能给团队提供他们需要的所有信息来确定代码的安全性。

“许多项目有 10、20 或 30 层的依赖关系，”Black 说。“因此，如果您的 SBOM 只有一两层，您就没有足够的信息来知道它是五层还是十层以下的漏洞。”

肖特提出了 SBOMs 的另一个问题:“你没有什么可以采取行动的。对于运营团队或安全团队来说，最重要的是可操作的信息。”

虽然肖特对最近改善用户教育的努力表示赞赏，但他表示，他对网络安全的状况持悲观态度:“现在没有多少东西可以让人们获得可操作的数据。这仍然是一个很大的问题，我们需要完善这些系统，让他们知道，仅仅因为我有 Bash 并不意味着我有 Bash 的所有漏洞。”

一个旨在解决这种情况的项目是 [GitBOM，](https://gitbom.dev/)一个新的开源项目。“从根本上说，我认为这是我们必须为防御团队提供真正高保真信号的最佳选择，”布莱克说，他一直致力于该项目的工作，并于今年 1 月[就此发表了一份白皮书。](https://gitbom.dev/resources/whitepaper/)

Black 说，Git BOM——名称可能会更改——采用 Git 所依赖的底层技术，使用哈希表来跟踪项目代码随时间的变化，并将其重新应用于跟踪软件供应链。该技术用于构建一个连接项目中所有依赖关系的哈希表，并构建 GItBOM 的创建者所称的工件依赖图。

“我们有一个团队正在研究一些概念证明，”布莱克说。“我希望由此实现的主要效果是，每种语言和编译器都有一个小小的变化……然后我们就可以在整个供应链中实现可追溯性。”

肖特说，与此同时，目前存在的最佳实践还有很大的推广空间。“我觉得安全供应商需要做得更好，让团队朝着正确的方向行动，”他说。

肖特说，今年秋天在芝加哥 DevOps，他举办了一个开放空间会议，在会上他询问了参与者与使用容器相关的痛点

“整个房间都承认没有使用最小特权，没有使用 Kubernetes 空间中可用的策略引擎，”他说。“因此，我们必须帮助人们理解对它的需求，以及如何实现它，这非常复杂。”

收听整个播客，了解更多关于软件供应链安全的信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>