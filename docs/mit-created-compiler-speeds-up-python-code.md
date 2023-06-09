# 麻省理工学院创造的编译器加速 Python 代码

> 原文：<https://thenewstack.io/mit-created-compiler-speeds-up-python-code/>

[Python 是一种流行的](https://thenewstack.io/why-does-python-keep-getting-more-popular-github-knows-whats-up/)、[初学者友好型语言](https://thenewstack.io/veteran-c-developer-says-python-is-best-starter-language/)。它也是一种解释语言，这使得它易于使用，但比编译语言(如 C 或 C++)慢。正如麻省理工学院[CSAIL](https://www.csail.mit.edu/)博士毕业生 Ariya Shajii 和他的同事 Ibrahim Numanagi 在从事涉及大量数据序列的基因组研究时注意到的那样，在大范围内，这将成为一个问题。

Shajii 说，他们意识到，以前创建更快版本的 Python 的努力是基于自上而下的方法，从传统实现开始，然后试图通过即时编译来提高速度，即时编译在程序运行时编译代码。

“这样做的明显优势是，你可以获得很多向后兼容性，但你能做的事情类型真的很有限，”Shajii 告诉新堆栈。“例如，Python 有一个叫全局解释器锁的东西，它基本上阻止你做并行或多线程应用。如果你真的想要高性能，这是一个大问题。”

他说，相反，Shajii 和 Numanagi 采用了自下而上的方法，从底层开始实现一切，独立于标准的 Python 实现。这让他们采用了一种不同寻常的方法:用他们和一个麻省理工团队一起创造的工具编译 Python，这个工具叫做[密码子](https://github.com/exaloop/codon)。

“它给了你更多的灵活性来做有趣的事情和生成优化的代码，诸如此类的事情，”Shajii 说。“这就是为什么我们能够获得比其他一些编译方法更好的性能，例如，可能获得 2 到 4 倍，但对于 Codon，通常是 10 到 100 倍。”

麻省理工学院的团队在大约 10 个常用的基因组学应用程序上测试了 Codon，所有这些程序都是用 Python 编写并使用 Codon 编译的。该团队实现了原始手工优化实现的五到十倍的速度提升。

## 密码子的起源故事

最初，Shajii 和 Numanagi 计划为基因组学建立一种特定领域的语言，因为这是他们的背景。然而，他们发现人们不想让 T11 学习一门新的专业语言——他们喜欢 Python。

“这就是为什么我们尽可能把一切都做得像蟒蛇一样，”他说。“然后，随着时间的推移，我们只是越来越多地缩小差距，直到我们有了一种通用的 Python，一种 Python 的替代品。”

然后，该团队通过将所有基因组特定的库、数据结构和处理序列的方法转换为扩展，将他们的工具重构为密码子编译器。这种方法允许 Codon 支持其他特定于领域的语言，这些语言是针对特定问题的更高抽象的编程语言，所有这些都包装在一个舒适的类似 Python 的环境中。

“整个系统可以用插件扩展，所以你可以写一个插件，它有新的库，新的编译器优化；如果你愿意，你甚至可以给语言添加新的关键词，或者新的语法，”Shajii 说。“但从用户的角度来看，他们仍然在编写非常高级的 Pythonic 代码。”

该团队首先要解决的难题之一是如何向编译器提供 Python 代码。编译器的第一步是执行“类型检查”，在这个过程中，程序找出不同的数据类型——字符串、整数、浮点数等。—每个变量或函数的。有些可能是字符串，有些可能是整数。在常规 Python 中，这些信息是在程序运行时处理的，这也是 Python 速度慢的原因之一。Codon 在运行程序之前进行这种类型检查。这样做允许编译器将代码转换为本机代码，从而避免了运行时处理数据类型的开销。

然后他们关注编译器中的优化。

“例如，如果你正在使用基因组学插件，它将针对该计算领域进行一系列优化，例如，涉及基因组序列和其他生物数据的工作。结果呢？麻省理工学院表示:“一个可执行文件，可以以 C 或 c++(T1)的速度运行，甚至在应用特定领域优化后更快。”

Shajii 和他的团队发表了一篇[论文，详细阐述了密码子如何工作](https://regmedia.co.uk/2023/03/11/mit_codon_paper.pdf)。

## 编译 Python 警告

然而，编译 Python 有一些注意事项。例如，Codon 不支持在运行时动态改变数据类型。

“我们说，好吧，我们的目标是科学应用，很少做这样的事情，所以让我们把注意力转移到静态分析的事情上，”Shajii 解释道。“因此，我们不支持某些动态功能。”

这些被省略的特性中，有些在 Codon 的支持路线图上，有些则没有。例如，标准的库模块还不被支持，但是麻省理工的团队正在努力。

“这是一个非常非常大的库，但我们已经尝试实现我们通常在我们的目标应用程序中看到使用的主要库，”他说。

还有数据类型的差异。例如，Codon 中的整数是 64 位，而 Python 中的整数是“任意长的”，他说。

此外，虽然 Codon 旨在帮助项目扩大规模，但不要期望无缝输出。

“更大的代码库，可能会导致我提到的一些不兼容性。所以，你知道，我们经常给你错误信息:你需要去改变这一点，或者[我们]还不支持这一点，”他说。

他说，在更大的 Python 应用程序中还有其他使用 Codon 的方法，并指出有一个装饰器，允许开发人员允许一个特定的函数(比如一个瓶颈)进行编译，而其他所有东西都留在 Python 中。

“这是为了解决要么全有要么全无的方法的问题，”他说。“通常，如果你有一些 Python 应用程序，人们通常会做的是用 C 语言编写真正对性能至关重要的部分；例如，Cython 是另一个用于此目的的工具。所以我们很快就会发布一些东西，让你可以用 Codon 做同样的事情，这样你就永远不用离开 Python 环境，这也是这一切的潜在主题。”

## Codon 即将推出:WebAssembly 等

Codon 于 12 月发布，版本为 0.15。它可以在学术或个人应用中免费使用。

该团队希望整合几个动态特性，并扩展其 Python 库的覆盖范围。然而，有一个计划中的特性可能会吸引前端和 web 开发者:他们计划支持编译到 [WebAssembly](https://thenewstack.io/key-concepts/wasm/) 。

“我们使用 [LLVM 作为后端](https://llvm.org/)。LLVM 是许多编译器使用的一种非常常见的编译器基础设施/框架，LLVM 支持 WebAssembly，”他说。“所以我们计划增加对 Codon web assembly 的支持，这样你就可以把一个 [Python 程序编译成 WebAssembly](https://thenewstack.io/webassembly-when-you-hate-rust-but-love-python/) 。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>