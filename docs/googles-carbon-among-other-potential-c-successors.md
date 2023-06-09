# 谷歌在其他潜在 C++继承者中的碳

> 原文：<https://thenewstack.io/googles-carbon-among-other-potential-c-successors/>

当谷歌在 7 月推出 Carbon T1 作为 C++的实验替代品时，它在社区中引起了巨大的轰动。

随着越来越多的开发者尝试这种语言，人们喜欢 Carbon 的生产力、性能和内存安全性。

该语言旨在修复 C++的几个明显的缺点。这种语言的两个关键目标是[可读性和“双向互操作性](https://en.wikipedia.org/wiki/Carbon_(programming_language))”，而不是使用像 Rust 这样的新语言——虽然基于 C++，但与 C++程序不双向兼容。

## 解决问题

[om dia 的分析师 Brad shimmen](https://www.linkedin.com/in/bradshimmin/)说，编程语言的出现通常是为了解决一个特定的问题。

以 [Go 语言](https://thenewstack.io/go-language-riding-high-with-devs-but-has-a-few-challenges/)为例，它是为了让工程师为现代多核系统编写更好的代码。Shimmin 解释说:“它不是为了取代一种给定的语言而构建的，但因为它是一种通用语言，所以它可以取代 C++，就像 Java、C、C++或 Python 可以用来取代几乎任何其他语言一样。”。

“简而言之，这些替换的最终成功或失败取决于新语言是否通过 a)解决现有语言中固有的一个或多个主要问题，以及 b)使现有开发人员更容易转移到新语言来吸引开发社区的注意力，”他说。

## 与 C++的区别

尽管 Carbon 试图接近 C++，但还是存在差异。

“就目前而言，最大的不同是他们试图摆脱过去 30-40 年积累的所有技术债务。甚至更长，如果你也包括继承自 C 的话，”C++专家和 SonarSource 的开发者支持者 Phil Nash 说。“所以语法看起来相当不同，它看起来更现代。比如默认不一样，东西默认不变，默认更安全。”

纳什说，在他看来，Carbon 的核心激励特征是它如何与 C++协同工作。事实上，Nash 在同一个项目中使用了两种语言。

## 互用性

“所以，在 C++本身成为 C 语言的后继语言之前，C++已经走上了这条路，”Nash 说。“因此，它不是一种全新的语言，而是被设计成无缝互操作的——我们已经看到，最初，它是一种严格的语言超集。”

同时，“与其说它与源代码层兼容，不如说它与 AST 层兼容——抽象语法树，”Nash 说。因此，编译过程的第一步是获取语法，并从中构建一个抽象语法树，然后进行编译。因此，在这一点上，他们可以建立两个兼容的抽象语法树。从那时起，相同的编译器开始工作，因此相对于从 C 到 C++的过渡，我们可以获得新的语法，同时获得相同的优势。”

虽然还不清楚 Carbon 是否会成功取代 C++，但它有助于减轻 C++用户的一些沮丧，例如与活动代码库较小的新语言相比，缺乏内存安全或缺乏创新。

“正如我们在 Java 等较老的语言中看到的，随着时间的推移，创新当然是可能的，所以我不相信这种说法，”Shimmin 说。“同样，Carbon 也没有像 Java、Python 和 Rust 等语言那样提供真正的内存安全。因此，现在看起来更有可能的是，Rust，一种内存安全、高性能、多用途的语言，现在在与 C++开发人员的竞争中可能有更好的机会。无论哪种方式，Carbon 都不太可能取代 C++，因为有太多的 C++代码在外面，有一个巨大的支持社区和一个广泛的支持框架集合，这些共同使 C++成为开发人员的持续胜利的选择。”

## 其他 C++后继者？

与此同时，过去三年一直在 ISO C++标准委员会任职的 Nash 也提到了其他潜在的 C++继任者或补充语言，包括 [Nim](https://nim-lang.org/) ，Cpp2/ [Cppfront](https://github.com/hsutter/cppfront) 语言和编译器，以及 [Val](https://www.val-lang.dev/) 。

“尼姆是另一个现在很受欢迎的人，”纳什说。“因为这样你就把自己从 C++生态系统中切断了——人们希望能够继续使用已经有几十年历史的代码库或 C++库。”

Nim 是一种静态类型的编译系统编程语言，它结合了 Python、Ada 和 Modula 等成熟语言的成功概念。

Cppfront 是由微软的软件架构师 Herb Sutter 创建和领导的，他是 ISO C++标准委员会的主席。

Sutter 在对 Cppfront 的描述中说:“我的目标是探索是否有一种方法可以让 C++本身变得简单 10 倍，更安全，更具工具性。”“如果我们有一个替代的 C++语法，它会给我们一个‘今天不存在的新代码泡沫’，我们可以在其中进行任意的改进(例如，更改默认值，删除不安全的部分，使语言与上下文无关和顺序无关，并且通常应用 30 年的学习成果)，而不受向后源代码兼容性的限制。"

与此同时，Val 语言网站上的描述称，Val 是一种研究编程语言，旨在探索高级系统编程的[可变值语义](http://www.jot.fm/issues/issue_2022_02/article2.pdf)和[通用编程](https://www.fm2gp.com/)的概念。

Val 大量借鉴了 [Swift](https://swift.org/) 的技术，也可以与 C++互操作。根据 Val 语言的网站，该语言旨在通过支持完全的互操作性来利用 C++巨大的软件资本。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>