# Rigetti 通过无服务器 API 向开发人员介绍量子计算

> 原文：<https://thenewstack.io/nascent-quantum-computing-development-rigettis-new-forest-api/>

量子计算系统提供商[ri getti Computing](http://www.rigetti.com/)——该公司致力于量子硬件电路以及从固件到应用层的软件层——已经发布了一个开源的量子计算环境森林 1.0 ，供开发人员开始构建，即使他们个人没有获得量子计算硬件。

Rigetti 的首席战略官 Madhav Thattai 说，目标是“让客户和社区了解量子计算并开发真正的应用。”通过 Forest 1.0，Rigetti 当前客户中的开发人员可以开始创建量子计算应用程序，而社区中的其他人可以使用 Rigetti 的量子虚拟机。

量子计算是建立在量子物理学基础上的一个新概念，利用了量子力学现象，例如光如何既是粒子又是波。在极高的速度下，量子计算可以使用大型线性代数来计算算法，这在今天是不可能的，因为必须同时评估和计算大量可供选择的数学。

“量子系统有非常微妙的关联。相对于它们的大小，它们比经典系统有更多的指数相关性。因此，即使是一个小的量子系统也无法在今天最大的超级计算机上运行。“这正是量子计算机所使用的:它们使用难以模拟的关联来进行更高级的计算。如果这些是大型线性代数机器，那么量子计算是一种资源，可以让你接触到你曾经想象过的大型线性代数问题。没有其他技术有这种潜力。”

Thattai 表示，量子计算使用[量子位](https://en.wikipedia.org/wiki/Qubit)作为内存的核心单元，每次增加一个量子位，内存容量就会增加一倍，使内存以指数方式扩展。目前，Rigetti Computing 正在使用八个量子位构建系统，但随着新硬件实验室 [Fab-1](https://medium.com/rigetti/introducing-forest-f2c806537c6d) 的推出，它有望显著加快开发速度。

曾解释说，目前还没有大型量子计算机可以比经典机器更快地解决问题，但这种情况正在迅速变化，特别是在量子化学和机器学习等领域，曾说这是两个“近在咫尺的问题”。

"我们如何才能访问这两个域？"曾指出:“我们需要制造第一台小型计算机，然后我们需要对这些机器进行编程和开发。在过去的 20 年里有很多学术研究，但只是在最近几年才出现了工业机会。但是在我们拥有大规模量子计算机之前，我们需要不同的工具来使用它。我们需要从物理设备转向应用编程接口。”

Zeng 说，这是一个巨大的挑战，Rigetti 正在分两个阶段解决这个问题:它已经发布了开源工具，因此人们可以尽早做出贡献，它正在将量子计算集成到经典计算中。

## 作为 R&D 平台的森林 1.0

曾说，用户应该把最近发布的 Forest 看作是“新生量子计算的 R&D 平台”森林有几个组成部分:

*   **工具指令集:** Forest 附带了一种语言不可知的“量子指令语言”，叫做 Quil。它使用混合共享内存模型，因此应用程序可以在量子计算的同时利用经典计算指令。在某些方面，这种混合模式类似于企业中经常使用的[无服务器](/category/serverless/)。在混合无服务器系统中，特定任务被发送到无服务器环境并在计算后返回到传统或云架构，而不是完全取代现有的云或本地架构。例如，新图像可以存储在云存储中，这触发该图像的副本被发送到无服务器工作空间以运行图像处理算法，该算法进而识别图像中的对象或面部，然后在算法被处理之后将具有新描述符的图像返回到云存储。Zeng 认为，这种应用程序环境将在未来两到五年内出现，这需要开发人员社区在这段时间内大幅提高技能。
*   **客户端库:**由于 Quil 是语言不可知的，开发者可以直接用它编写，就像用汇编语言编写一样。但 Zeng 认为，大多数人会更喜欢使用一些附带的客户端库，比如提供的 Python 库:

*   **API:** 虽然在 Rigetti Computing 的当前客户群中工作的开发人员已经有了一些可以开始编程的量子位处理器硬件，但大多数来到 Forest 平台的开发人员预计会构建通过 API 连接到 Rigetti 的量子虚拟机(QVM)的应用程序。虽然还不适合生产用例，但 Zeng 说 API 是“理解量子计算将如何影响编程的最佳方式”。QVM 是一台超高性能机器，它可以在经典计算上模拟 36 个量子位。它让你了解算法在量子计算中是如何工作的。它不仅仅是高性能，还包括逼真的噪声模型，以及使其成为反映硬件真实面貌的良好环境的所有细节。”

## 化学用例中的量子计算

量子计算可以显著改变当前科学的最令人兴奋的领域之一是计算化学。已经有很多库可以帮助开发者在计算化学中使用 Forest。

“这些都是基本的量子问题，”曾说。“我们可以做的第一件事就是改进催化剂的设计。催化剂是设计在量子系统中的小分子。如果你把它们提高 1%、2%或 5 %,就会产生巨大的影响。我们经常谈论的一个领域是固氮。为了制造肥料，我们使用一种 1910 年的催化剂，全世界 1-2%的能源被用于这一过程。如果你能让这一个分子变得更好一点，你就能显著影响世界的能源预算。你也有催化剂可以从大气中提取碳，如果我们能找到便宜的有机催化剂，我们就能制造更好的有机电池。”

## 让量子计算变得可行

虽然量子化学是一个被视为唾手可得的领域，但优化算法也是如此。森林平台中的许多可用库已经在考虑将量子计算用于大型优化和机器学习用例。

这是 Rigetti 目前的客户群已经在尝试量子应用设计的领域之一。

从实现的角度来看，下一步要做的关键工作是让量子计算在混合环境中工作，就像无服务器的例子一样。在不想过多分享他们的路线图的情况下，曾确认“增加杂交是我们正在开始做的事情。在客户端，你必须把工作分成量子部分和非量子部分。”曾希望未来的森林和硬件发展能够引导他们进入一个混合决策过程，用户可以上传他们的问题，平台将决定如何划分量子位处理中应该做的计算和经典计算中应该做的计算。

今年年初在西雅图分享了更多关于量子教学语言的信息:

[https://www.youtube.com/embed/IpoASc18P5Q?feature=oembed](https://www.youtube.com/embed/IpoASc18P5Q?feature=oembed)

视频

专题图片:由 [Johannes Plenio](https://unsplash.com/photos/a72o8w9HC2w?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄。](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>