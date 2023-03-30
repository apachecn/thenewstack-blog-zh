# 开发人员:模糊化、符号化的回归测试为应用提供了弹性

> 原文：<https://thenewstack.io/developers-fuzzing-symbolic-execution-with-regressive-testing-offers-app-resilience/>

[](https://www.linkedin.com/in/mel-llaguno-23aa9659/?originalSubdomain=ca)

 [梅尔·拉古诺

梅尔·拉古诺是 ForAllSecure 公司的商业解决方案主管，他负责开拓新市场，并在行业内采用该公司屡获殊荣的技术。此前，他在 Synopsys 工作，负责运营他们的 Coverity SCAN 项目，该项目为世界上一些最重要(也是最大)的 OSS 项目提供商业级 SAST。](https://www.linkedin.com/in/mel-llaguno-23aa9659/?originalSubdomain=ca) [](https://www.linkedin.com/in/mel-llaguno-23aa9659/?originalSubdomain=ca)

今年的[黑帽](https://www.blackhat.com/)再一次体现了软件正成为我们日常生活中必不可少的组成部分这一认识。甚至有更多的解决方案正在被吹捧，以应对软件不断增长的恶意威胁。不幸的是，许多解决方案集中在处理我们当前困境的症状上，而没有解决根本的事实——尽管我们尽了最大努力，软件仍然是不安全的。

需要的是改变观点。软件*就是*基础设施。

在安全临界系统中尤其如此。想想汽车工业、航空和医疗设备的最新进展。如果没有引入软件作为创新的一部分，这一切都是不可能的。然而，这有一个不幸的副作用，即给这些系统注入了一个额外的特征——硬件和软件的融合使这些系统本质上成为信息物理系统。问题是，我们为应对现代软件开发的挑战而开发的过程总体上还没有达到生死攸关的系统所需的成熟度。

这个过程中缺少的是弹性的概念。弹性是面对不利条件时抵御灾难性失败的能力。弹性是安全关键的信息物理系统的基本要求，特别是当这些系统预计将运行几十年，而不仅仅是几年。

虽然有许多技术可以帮助解决构建弹性系统的挑战，但它们本身只能解决问题的一小部分。让我们来看看这些解决方案的各种优势和劣势:

*   **软件组成分析**允许组织找到过时的软件依赖关系。通过使用这些组件的非易受攻击的版本，可以立即提高安全性。挑战在于这种安全感是在一个时间点上。不能保证拥有最新的组件，你的应用程序就能安全抵御*未来的*威胁。
*   **静态分析** (SA)可以应用于一个程序的源代码，但是与一个抽象一起工作，这个抽象不针对实际执行的代码。此外，即使是最好的工具也需要组织的努力来使用，因为该技术存在一个基本问题，即误报(FP)，即错误识别实际上是*而不是*缺陷的问题。随着代码库规模的不断增长，SA 的应用变得更加复杂。虽然最好的 SA 工具的 FP 率可以低于 5%，但是当应用于 1MLoC 到 10+MLoC(代码行)的项目时，这导致识别出大约 50k–500k 的缺陷(使用 5%作为 FP 率)。这个数量的缺陷需要大量的时间和资源来解决。想象一下，当正在使用的 SA 工具具有更高的 FP 速率时…
*   **动态分析**(如协议模糊器、交互式应用安全工具——IAST、漏洞扫描器)在验收测试的环境中很有用，但是这些工具的应用需要了解*在软件开发生命周期(SDLC)中的*何时可以应用。这些工具通常适用于完全开发/部署的应用程序，这从根本上改变了它们在 SDLC 中的位置*最右边*。开发人员反馈周期中的这种滞后是有代价的。
*   **软件审计和渗透测试**也可用于保护软件，但成本较高(因为它需要一定程度的专业知识),并且受到人力规模的限制。该选项通常仅适用于有资源租用/购买这些服务的组织，这使得大多数公司面临不必要的风险。

那么解决办法是什么呢？

覆盖引导模糊化是一种越来越受欢迎的技术，这得益于云规模基础设施的最新进展。模糊化是生成伪随机输入并输入到程序中以查看它是否以意外方式运行的过程。令人惊讶的是，这种技术在发现可能具有稳定性/安全性含义的新缺陷方面非常有效。众所周知，黑客使用模糊化来发现新的漏洞。

谷歌(通过[OSS-模糊倡议](https://github.com/google/oss-fuzz))和微软(通过开发其[安全风险检测引擎](https://www.microsoft.com/en-us/security-risk-detection/))已经非常成功地应用了这项技术，使他们的应用程序更具弹性。

这种技术的尖端结合了模糊化和符号执行(SE)。虽然模糊化可以被认为是暴力突变输入测试，但 SE 可以查看程序的执行上下文，并发现有趣的分析路径，而模糊化本身很难取得进展。

此外，测试用例是作为分析的一部分自动生成的*。这些测试案例非常重要，因为:*

 *1.  它们可以作为软件未来版本的回归测试，而不需要额外的开发工作。您可以测试一个依赖项的最新版本，以确保程序行为的完整性，而不是等待将来版本报告缺陷/漏洞。
2.  一个发现的缺陷对正在运行的程序有直接/可测量的影响，并且不太可能导致误报。
3.  它们可以被简化为一个最小的案例集，来执行所发现的执行路径。这比运行程序的完整分析要快得多，并且可以很容易地集成到 DevOps 管道中。这使得开发人员可以立即看到通过分析发现的回归/缺陷。
4.  它们可以用来提供缺陷再现器，这样开发人员就可以快速识别代码需要修复的地方。本质上，测试给出了一个有经验的审计员/测试员可以提供的环境类型。
5.  随着分析的进行，新的测试用例被生成。

虽然没有一个分析可以声称找到所有可能的 bug，但是拥有一个与程序一起发展的测试用例集合可以让组织相信一个经过分析的程序是有弹性的。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*