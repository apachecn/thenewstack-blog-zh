# 生产前环境:关键概念和最佳实践

> 原文：<https://thenewstack.io/pre-production-environments-key-concepts-and-best-practices/>

伊斯梅尔·埃吉尔梅斯

伊斯梅尔是桑德拉公司的业务发展经理。他热衷于销售、营销和发展战略。

在编写代码和将其投入生产之间有几个步骤。这些步骤通常属于“前期制作”的范畴预生产指的是帮助开发人员安全地开发、测试和集成新代码的各种阶段环境。

您可能认为这些额外的步骤会减缓开发和进展。但是预生产环境——如果设置正确——可以极大地提高性能，减少开发人员推送代码的时间。

在本文中，我们将探索各种生产前环境，并讨论创建理想环境需要哪些组件。

## 主要的生产前环境

生产前环境通常在应用程序投入生产之前构建。两个主要环境包括:

*   开发环境:开发环境提供了一个层，软件工程师可以在这个层上构建和测试他们的代码。这些测试通常是有限的，主要集中在单元式测试上。
*   **测试环境:**测试环境通常是 QA 工程师运行一长串测试用例以确保代码按预期运行的地方。

在过去，这大部分是手动完成的，但现在这些步骤开始融合在一起。为了理解这是如何发生的，我们将介绍一些其他概念，如 CI/CD 和环境监控。

## 设置环境时要考虑的关键概念

对于任何维护软件的企业来说，设置生产前环境都是至关重要的一步。您的开发团队如何组织其预生产环境会影响他们维护代码的速度和容易程度。

小型团队可能会使用手动过程来推动对代码的更改，例如从他们的 repo 中手动提取代码，并用它替换旧的代码。但是这对于拥有大型开发团队和复杂软件的大公司来说是不可持续的——这也是建立预生产环境的关键所在。

以下是一些可以改善生产前环境的概念。

### CI/CD

持续集成和持续交付(CI/CD)代表了最佳实践和操作方法的组合，允许工程团队快速可靠地推送代码。

持续集成的技术目标是开发、建立和维护一个一致的自动化流程来构建和测试应用程序。这里的关键词是*一致*。拥有一致的集成过程可以确保被测试和打包的代码是可靠的。有了可靠的 CI 系统，团队可以转而推动更多的提交，因为他们不再等待手动过程。

持续交付从持续集成停止的地方开始。

CI/CD 充当完整的代码集成和交付管道。CI 部分帮助自动化集成，然后 CD 通过将应用程序推送到目标环境来完成该过程。例如，当代码通过测试环境时，它会被预先编写的测试用例自动测试。这比 QA 工程师手动测试代码变更并在电子表格中记录输出要容易得多。

### 监视

监控不仅仅针对您的 DevOps 生产系统。在生产前环境中设置监控可以提供多种好处。

其中最主要的是知道开发人员没有意外地改变监视器处理代码变化的方式。特别是，监视您的测试环境、测试用例以及可能的用户路径，可以提供很多关于当您的代码进入生产时可能出错的洞察。

在现代软件中，很难跟踪每个可能的用户路径和 bug。监控确保您可以更容易地跟踪未来的错误。即使测试用例通过了。

有条件地监控各种环境的能力对于您的敏捷开发团队和精心编排的 DevOps 过程来说非常关键。最重要的是，它有助于快速推进大量代码变更。

### 调试和测试设置

开发可靠的测试和调试过程有助于您的团队不断推出高质量的代码。这意味着实现自动化测试和有意识的日志记录，以及追踪 bug。

这些系统中有许多曾经是现场和/或手动管理的。然而，在当前云驱动的开发环境和自动化测试的推动下，新的工具出现了。

例如，[桑德拉助手](https://blog.thundra.io/introducing-thundra-sidekick-intellij-idea-plugin)为开发人员提供了几个调试和测试工具——比如不间断断点——来帮助简化测试过程。此外，桑德拉 Sidekick 集成了分布式跟踪，为开发环境提供了终极可见性。

所有这些优势都有助于使您的生产前流程更加顺畅，尤其是在云环境中。

## 现代设计考虑

上面引用的概念有助于改进您的生产前环境最佳实践。但是有一些新概念在简化预生产和简化代码部署方面发挥了作用。特别是，集装箱化和微服务的实践已经集中于尝试改进预生产过程。

### 集装箱化

容器使开发人员能够创建包含在单个单元中的独立模块。公司正在转向容器，因为这种转变允许他们将大型软件项目分解成多个小型敏捷团队的并发发布。

理论上，容器简化了将代码推送到不同层的过程。这是因为容器本身应该已经拥有应用程序运行所需的所有库和依赖项。当然，还有数据库和技术组件的问题，比如需要管理的代码库、服务器和基础设施。

### 微服务

另一个现代开发实践是使用微服务架构。这种设计方法允许团队构建隔离的、可管理的服务。这种实践应该使在各种环境中推动代码变得更加容易。但是，这也增加了一层复杂性，因为如果没有合适的工具，跟踪和监控会变得更加困难。

简而言之，微服务可以在您的生产前环境中很好地工作，只要您已经围绕它开发了一个系统。

## 维护您的生产前环境

生产前环境不是静态的。随着多个开发人员不断测试、编辑和更新它们，它们不再保持原始状态。这可能会导致您的各种环境不同步，并在未来造成问题。

您的团队可以使用多种工具和最佳实践来确保您维护一个强健的生产前环境。

*   **自动化:**您的前期制作流程应该有自动检查，以确保每一层都按照要求保持同步。例如，实现扫描数据库和代码库以发现文件或数据变化的自动化过程。
*   **代码库实践:**这是确保预生产和活动生产环境保持同步的最简单方法之一。您的团队不应该在生产或测试环境中编辑代码。这使得开发人员可以在开发环境中编辑代码，并且至少在理论上可以看到代码一旦上线将会如何交互。
*   **版本控制:**跟踪单个项目的多次迭代允许你重新访问以前的版本，并确保你的代码库不会改变，除非它是有意的。

总的来说，这些额外的层有助于您维护一个强健的生产前环境。

## 要点:不要忽视你的前期制作环境

成功的开发流程包括有组织的生产前环境。拥有正确的工具和最佳实践来管理您的代码集成和交付，可以确保您的团队总是能够产出可靠的代码。维护您团队的 CI/CD 流程并建立生产前监控将对您团队的绩效产生巨大影响。

*桑德拉 Sidekick 在前期和后期制作环境中结合了云调试和分布式跟踪，使开发人员能够对远程应用进行故障排除和调试。快速轻松地将您的代码投入生产。[与桑德拉搭档免费开始](http://www.thundra.io/sign-up)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>