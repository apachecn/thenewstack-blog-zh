# 代码 n00b:鸭子，鸭子，完成

> 原文：<https://thenewstack.io/code-n00b-duck-duck-done/>

在计算机编程中，有些时刻我只能称之为愉快的经历。当代码从你的大脑自由流出，通过你的手指进入终端时，时间就消失了。一切都编译得很干净，没有错误，您刚刚编写的这段出色的代码完全符合您的期望，甚至更好。在这种时候，一个人可以合理地举起双臂，做出胜利的 V 字形，也许还可以做几个庆祝性的转椅。在这些最好的时候，成为一名程序员不仅仅是有趣或愉快:它是一种精神狂喜的合法形式。

然后是最坏的时候。你已经被困了几个小时，甚至几天，试图追踪一个…单一的…错误。你盯着看，一遍又一遍(一遍又一遍)地分析同一段代码，还是想不出失败的原因。什么都不管用，生活很悲惨。你开始幻想你的下一份工作，那将是快餐服务。将短语“未捕获的类型错误:无法读取属性”替换为“要不要来点薯条？”突然觉得这是唯一可能的职业发展。StackOverflow 是没有帮助的。用头撞桌子是没有用的。你的同事也帮不上忙(不管怎么说，当桌子/头撞击开始时，他们都跑了)。有任何帮助吗，任何地方？？？？

进入 duckie。

从“不行”回到编码流的状态——或者，至少，事情或多或少的工作——看起来是不可能的，但是这是每个编码人员都要经历的经历。而且，作为程序员，我们非常擅长解决问题。我们想出了一个聪明的策略来追踪目前导致我们凝视深渊的错误，这个策略包括一个可爱的小橡皮鸭。是的，你洗澡用的那种。

不幸的是，鸭子没有神奇的力量来解决你的问题。当你向他们解释你的代码和问题时，他们所做的只是坐在那里，活泼但不活跃。诀窍很简单:向其他人(或事物)解释问题迫使你逻辑地思考并分解它。这使您更容易理解自己的代码，更重要的是，更容易找到修复方法。抓住你的橡皮鸭，向他们解释你的代码应该做什么，实际上没有做什么，这通常是一种有效的调试技术。绝对比撞头更严重。

这种技术第一次被提到是在经典的软件工程教科书[《实用程序员:从熟练工到大师》中，作者是安德鲁·亨特和戴维·托马斯。自那以后，它就像一个潮湿的迷因一样传播到互联网的各个角落，并被应用于各种解决问题的职业，如](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)[自动消防喷头设计](https://hwrnmnbsol.livejournal.com/148664.html)，而不仅仅是计算机编程。

但无论应用在哪里，基本机制都是一样的:解决问题的关键部分是完全致力于问一个离你最近的软塑料*雁形目鸭科*的彻底、详细的问题。虽然任何人或无生命的物体，真实的或想象的，也应该做到这一点。只是口头上向某人介绍你的难题，一步一步地描述它，在上下文中和相关细节中，这种行为通常会引导你找到解决方案。

为什么不直接给同事看，问问他们的建议？嗯，因为只是让别人来解决你的问题是一种懒惰。如果你不愿意全力解释这个问题，以及迄今为止你为解决这个问题所做的努力，为什么其他人要这么做呢？另外，你打断了他们自己的工作，试图让他们做你的工作。真的，只要和鸭子说话。相信我。

老实说，你甚至不需要一只鸭子，不管是真的还是想象中的，尽管橡胶鸭子确实是一个有趣的桌面装饰品。没有鸭子，你仍然可以利用问鸭子解决问题的技巧自己解决问题。你有多少次被一个编码问题严重困扰，无法通过谷歌搜索错误代码找到有用的解决方案，绝望中开始写一个彻底、详细的堆栈溢出问题…却在你描述完问题之前就找到了问题的答案？对我来说，这种情况发生的次数已经数不清了，老实说，这可能是我解决大多数棘手问题的方式。

当我对 JavaScript 有足够的了解来理解我想做什么，但还不足以让它发生时，这个过程就出现了。我会花很长时间浏览谷歌和 StackOverflow，一遍又一遍地重新措辞和研究我的问题，希望最终以正确的方式提出这个问题，为我的难题找到完美的解决方案。除了浪费大量时间之外，如果我真的找到了一个大概的解决方案，我就不得不发起一场史诗般的反复试验的单人黑客马拉松，试图修改别人的代码来适应我自己的情况。

不久前，当我被 super mega 卡住，被//(未知)折磨到近乎疯狂时，一个朋友给我发了一个橡胶鸭编码迷因作为玩笑:脚本错误。(专业提示:当一个未被捕获的 JavaScript 错误违反跨域策略跨越域边界时，就会产生这种情况。)用简单的语言来说，任何出现在 window.onerror 处理程序中的错误都将被简单地报告为“脚本错误”，而不是在 try-catch 中被捕获，不会提供任何其他有用的信息。这是一种浏览器安全措施，旨在防止跨域传递数据，否则会被阻止通信。连续几天，在谷歌上搜索这个完全空白的错误消息让我一无所获。当鸭子迷因登陆我的私人休闲频道时，我的理智正慢慢粉碎。

这是一个偶然的时机。首先我笑了。好像鸭子能帮上忙似的。但是我通常的“谷歌错误信息”调试策略毫无进展，我准备尝试任何事情。所以，感觉有点可笑，我开始说话。大声说出来。一只看不见的，想象中的黄色玩具鸭。我觉得自己相当愚蠢，于是开始描述我所经历的问题的背景——我还没有想到错误信息本身——我想到了一个可能的解决方案。将 Access-Control-Allow-Origin 头设置为*以允许从任何域访问资源，然后在 HTML 源代码中的脚本标记上设置 crossorigin="anonymous"。成功了。

回头看，我意识到我一直在错误地解决我的问题，试图找到别人的解释或代码片段来让我自己的代码工作。这是一个典型的程序员新手的错误。我实际需要做的恰恰相反:让我的代码为我工作。与鸭子交谈最终让我按下了那个非常必要的开关。

问题解决了！在我绕着桌子跳完胜利之舞后，我打开了一个新的浏览器标签，为自己订购了一只合适的橡胶鸭子。我想我会给他起名叫吱吱叫的人。

约书亚·科尔曼在 Unsplash 上拍摄的特写照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>