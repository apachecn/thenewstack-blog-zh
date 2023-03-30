# 开放图书项目:你可以自己制作电子书阅读器

> 原文：<https://thenewstack.io/the-open-book-project-an-ebook-reader-you-can-build-yourself/>

一位业余硬件爱好者想证明人们可以建造自己的电子书阅读器。

“作为一个社会，我们需要一个开源的阅读设备，”该项目的 GitHub 页面解释道。“书籍是我们文化中最重要的文件之一，然而我们最流行和最广泛的阅读设备 Kobo、Nook、Kindle 甚至 iPad——都是封闭的设备，在一系列巨大的封闭平台中作为小的移动部件运行，这些平台的所有者的利益并不总是与读者的利益一致。”

“开卷机旨在成为一个简单的设备，任何人都可以用烙铁为自己制作。”

这是一个鼓舞人心的例子，通过借鉴开源社区的工作，一个人的项目实现了它的宏伟梦想。“一个人做不出开源电子书阅读器，”该项目背后的人[乔伊·卡斯蒂略](https://twitter.com/josecastillo)在最近一集的 Adafruit 的“展示和讲述”[中承认。“我依赖于如此多的开源库，并从如此多的开源图表中学习。”](https://www.youtube.com/watch?v=iJqkwLt4Bik&feature=youtu.be&t=427)

上周，卡斯蒂略在 Twitter 上上传了一个简短的视频，展示了他的电子书阅读软件的早期原型，以及一个漂亮的自制木箱

卡斯蒂略正在设想一款 4.2 英寸屏幕的七按钮设备。“一个 400 x 300 的黑白电子纸屏幕能够实现阅读的核心体验，”该项目的网页在 Hackaday.io 上解释道。为了降低成本，Castillo 优先考虑便宜的组件，但该设备的规格包括一个 SAMD51J19A 微控制器和一个 ARM Cortex M4 处理器(512 闪存和 192 kb RAM)，加上 51 个 GPIO(通用输入/输出)引脚。

甚至还有一个微型 SD 插槽用于外部文件存储。该项目页面指出，维基百科的离线版本只有 64GB。

在 12 月下旬的更新中，Castillo 发布了他还训练了一个 TensorFlow Lite 模型来识别麦克风输入的语音命令。

更大的希望是建立一个易于扩展的电子阅读器，并且支持每一种书面语言。但是“最重要的是，它应该是开放的，”GitHub 页面补充道，“这样任何人都可以以这个设计为起点，用它来创作更好的书。”

电子阅读器的 GitHub 页面也表达了一种希望，多功能板可以找到其他用途。通过它的立体声音频输出，“你可以把它变成一个音乐播放器或语音备忘录录音机；使用 STEMMA 端口添加传感器，并将其转变为空气质量监测器；插上一个空运机翼，让它显示体育比分或运输警报。我真的很好奇人们会想出什么样的用途。”

## 自己动手

卡斯蒂略强调说，他把阅读器想象成一个 DIY 项目——他一直想让其他人也能建造他们自己的电子书阅读器。由于人们不断询问他的设备何时能准备好，卡斯蒂略周四在他的项目日志页面上发布了[。他写道，链接到 GitHub 上该项目的页面，“我的一部分感觉就像嘿，](https://hackaday.io/project/168761-the-open-book-feather/log/173457-on-how-to-get-there-from-here)[在这里](https://github.com/joeycastillo/The-Open-Book)，如果你想要的话！”

“PCB 背面的每个主要组件都有其用途的简短描述，在某些情况下甚至还有引脚分配的明细。这个想法是，它不仅使设备更容易组装和调试，而且还可以向好奇的用户解释板上的所有东西是干什么的，以及为什么有必要这样做。”

或者，正如该项目的页面所解释的那样，委员会的丝网印刷“旨在揭开开放图书自身设计的神秘面纱，为好奇的读者分解这本书是如何工作的，以及他们如何为自己建造一个。”

他现在计划与读者分享他实践的一系列小项目。“我们的目标是让每个人在另一端教授构建打开的书所需的技能的某个方面……如果我对自己诚实的话，*曾经有一段时间我无法完成打开的书*，如果我要说‘你可以完成它’，也许我需要带你一起踏上旅程。”

我们有多接近了？根据其 GitHub 页面，阅读器现在已经完成了 99%,只有一个挥之不去的硬件问题:当耳机插入 USB 端口时，会有一个小的嗡嗡声，因为“USB 电缆的屏蔽层就像天线一样，从环境中拾取射频噪声。我计划在 USB 屏蔽和接地层之间安装一个 RC 滤波器来解决这个问题。”

“我们将制造出第一批 100 台，我希望之后会有更多，但最终这不是为了制造一个你可以买到的东西，而是为了制造一个你可以制造的东西。即使你认为你今天做不到。”

* * *

## WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>