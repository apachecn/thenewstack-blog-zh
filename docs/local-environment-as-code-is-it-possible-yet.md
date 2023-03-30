# 本地环境代码:可能吗？

> 原文：<https://thenewstack.io/local-environment-as-code-is-it-possible-yet/>

在过去的十年里，我们已经看到了“作为代码”的兴起、标准化和记忆化:基础设施作为代码、[作为代码监控](https://thenewstack.io/monitoring-as-code-what-it-is-and-why-you-need-it/)、[作为代码政策](https://thenewstack.io/cloud-engineers-try-policy-as-code-to-cure-misconfiguration-woes/)，也许很快就会有[数据作为代码](https://thenewstack.io/the-coming-era-of-data-as-code/)。

 [扬·范·布鲁根

Jan 负责 itopia Spaces 的开发人员关系，他与 itopia 的分布式工程团队共同设计和开发了这个项目。作为一名软件爱好者，他喜欢优化他的设置并教授他所学的东西。他为各种组织开发了 DevOps 工具，包括 Google、NASA、初创公司和开源项目，但他最自豪的是通过找到更简单的解决方案删除了代码。](https://www.linkedin.com/in/jancvanb) 

本质上，“代码填充”是通过版本控制的、声明性的配置文件对“材料”进行无状态自动化管理的实践。因此，值得一问的是，相同的 DevOps 实践是否可以有效地应用于一组不稳定的资源，这些资源对开发人员来说甚至比他们的后端(他们的本地编码环境)更近、更重要。

开发人员环境配置漂移的常见问题是，当重新访问旧项目或遵循过时的教程时，这是一个小小的不便，但是它可能会花费专业开发人员每月几天的时间来恢复/更新他们的环境，尤其是在技术多样化的团队中。

不幸的是，Terraform 无法将我们从[本地依赖地狱](https://xkcd.com/1987/)中拯救出来，Kubernetes 也无法帮助 Windows 和 macOS 笔记本电脑在一个代码库上进行协作……[对不对](https://xkcd.com/934/)？有可能用声明性配置文件、版本控制和无状态自动化实践来解决这些本地环境问题吗？

让我们考虑一个人在编写代码时所依赖的所有“本地”事物:

*   集成开发环境(ide)
*   个人设置
*   特定于项目的库
*   全系统软件包
*   操作系统
*   计算机硬件
*   互联网连接
*   电流
*   键盘旁边的一杯水

本地环境抵制配置的一个原因是，这些层中的每一层都依赖于它下面的层，因此任何无状态地自动化上层的努力都会被下面的有状态混乱所破坏。

例如，Python 项目的依赖项可能在声明性的`requirements.txt`文件中定义，但是每次执行的结果将根据设置的环境变量和安装的操作系统包而有所不同。支持容器化环境的 VS 代码是一大进步，但是它依赖于 Docker 安装的手工维护(以及兼容的操作系统和首先运行 Docker 的[订阅](https://thenewstack.io/the-time-to-decide-on-docker-desktop-has-arrived))。

那么，无状态地自动化一个完整的本地环境是不可能的吗？号码

## 配置环境

我们最近看到这些混乱的中间层的无状态可配置性有了显著的进步，开发人员的工作流也在相应地发展。让我们评估本地环境中每个软件定义层的当前可配置性:

### 个人设置

在 IDE 之下，最高层的配置是个性化。这由覆盖应用程序和工具中默认设置的配置文件组成，例如:

*   IDEs: `settings.json`，`options/*.xml`，`.vimrc`，。`editorconfig`等。
*   端子:`.bashrc`、`.zshrc`、`.tmux.conf`等。
*   其他:`.gitconfig`、`psqlrc`等。

*趣闻:这些文件名很多都以句点开头(也因此被称为“点文件”)的原因是*[*1997 年*](https://linux-audit.com/linux-history-how-dot-files-became-hidden-files/) *偶然发明了“隐藏文件”。*

ide 依赖于快捷方式、按键绑定、可访问性、布局和美观的个性化。这些文件应该总是因开发人员而异，因为每个人都有自己独特的需求和习惯。那么，我们如何能够自动管理跨设备和环境的个性化，而不对开发人员一视同仁呢？

最流行的答案是使用类似 [chezmoi](https://www.chezmoi.io/what-does-chezmoi-do/) 、 [Dotbot](https://github.com/anishathalye/dotbot) 、 [yadm](https://yadm.io/) 或其他的“点文件管理器”。点文件管理器[各有不同的特性](https://www.chezmoi.io/comparison-table/)，但是它们都自动更新个性化文件的过程，以达到期望的版本控制状态。有些甚至使用声明性配置文件！

看起来“个性化代码”是一个已经解决的问题。虽然点文件管理器还不是很主流，但强烈建议在多个设备或帐户上工作的专业开发人员使用点文件管理器，因为它将节省设置、环境切换和调试这些环境的大量时间。

### 项目库

从 Java 到 Rust，几乎每个软件项目都导入第三方库，这一层已经“作为代码”被管理。库依赖项的声明性配置文件通常包含在版本控制中的项目源代码中:

这样的例子不胜枚举，几乎每种编程语言都有一个行业标准协议。

有趣的事实:多年来，这一趋势的主要例外是 C 和 C++，因为它们与系统包的独特集成(见下一节)和(大概)遗留工作流的惯性。但是，今天无论是 [*柯南*](https://conan.io/) *还是*[*VC pkg*](https://vcpkg.io/)*似乎都流行起来，而且越来越盛。*

ide 通常依赖这些库来格式化、分析和执行源代码，所以这些配置文件分布在源代码中对开发人员来说是一个福音。事实上，“代码形式的库依赖”已经被彻底解决了很长时间，以至于:

*   几乎每个项目在第一天就开始无状态地管理它的库依赖。
*   几乎每种编程语言都应该有一个库管理协议。
*   这是一个不用的短语，因为它似乎只是常识。
*   大多数开发人员都认为这是理所当然的，直到有人在谈论其他代码时注意到它的无所不在。

### 系统包

与特定于项目的库不同，系统范围(和每个用户)的包可用于开发人员的多个/所有项目，并针对每个操作系统进行定制。其中包括:

*   像`gcc`和`python`这样的编译器和解释器。
*   客户端和服务器，像`curl`和`apache`。
*   终端外壳和图形用户界面，像`xterm`和`gnome`。

除了本身是包之外，ide 还依赖其他包来呈现视图、连接服务和分析/执行代码。每个项目都依赖于一组独特的包，所以每个开发人员都在他们的操作系统上安装了一组独特的包。但是，通常一次只能安装一个版本的软件包，有时不同的软件包会不兼容或相互竞争。这导致了令人沮丧的环境之间的依赖不匹配和环境内部的冲突。那么，有没有一种方法可以跨设备和环境自动管理一个项目的包依赖关系，而不破坏另一个项目的包依赖关系？

在过去的几十年里，有状态的解决方案一直很流行:使用像 [APT](https://en.wikipedia.org/wiki/APT_(software)) 、 [pacman](https://wiki.archlinux.org/title/pacman) 、 [Homebrew](https://brew.sh/) 或 [Chocolatey](https://chocolatey.org/) 这样的包管理器一次安装一个特定的包版本。这些工具支持强大的设置脚本，当与容器化的无菌性和短暂性相结合时，这些脚本更加可靠和可维护(下一节将详细介绍)。

不幸的是，如果没有容器化，有状态配置在本质上比无状态配置的可扩展性差，无状态配置可以在将来的任何时候知道它是否已经变得无效/冲突，然后有效地自我修复；只要问问那些因为这个原因而选择 Terraform 的基础设施即代码方法的人就知道了！

这就是为什么看到 [Nix](https://github.com/NixOS/nix) 慢慢[变得](https://shopify.engineering/shipit-presents-how-shopify-uses-nix) [更](https://blog.replit.com/nix) [流行](https://medium.com/att-israel/how-nix-shell-saved-our-teams-sanity-a22fe6668d0e)是如此令人兴奋，因为 Nix 是同一问题的无状态解决方案。通过为每个单独的包安装一个或多个不可变的版本，并显式地将包的直接和间接依赖关系转换成 DAG，Nix 可以针对大多数形式的位损坏提供面向未来的环境，并极大地简化使用不同操作系统的开发人员之间的协作。

任何经历过操作系统级依赖地狱的开发者都应该安装 Nix，看看`nix-shell`是否会让他们整个星期都精神焕发。

### 操作系统

每个开发人员软件堆栈的底层是他们的操作系统(OS)，它包括各种子系统:

*   应用平台
*   文件管理
*   司机
*   资源(处理器、内存等。)管理

不可能无状态地配置安装在大多数开发人员计算机上的操作系统，因此管理这一层最流行的方法是使用容器化的客户操作系统来托管开发人员环境。出于我们的目的，“客户操作系统”意味着每个环境都是相互隔离的，“容器化”意味着每个环境的规范都可以进行版本控制。

有趣的事实:事实上，一些无状态的操作系统确实存在，但是它们还不流行。 [*NixOS*](https://nixos.org/guides/how-nix-works.html#nixos) *是一个完全由 Nix 包管理器管理的无状态 OS，* [*Guix 系统*](https://guix.gnu.org/en/about/) *是 NixOS 的 libre 翻版。富有冒险精神的开发人员可能会爱上 NixOS，但它可能还不支持所有现成的开发工具，这主要是因为它的设计与众不同。*

自从 Docker 发明了大多数关于容器的概念和术语以来，它一直是指定、构建和运行容器的最佳平台。尽管它实现了指定构建步骤的有状态系统，但构建的容器映像是不可变的工件，可以在声明性配置文件中引用。

### 推荐方法

虽然每一层都有无状态自动化是理想的，但是您可以通过单独引入新的自动化工具来逐步升级您的环境。Nix 是项目的强大补充，chezmoi 是开发人员的友好助手。

另一方面，如果您想直接进入全自动化环境，建立和维护全自动化本地环境的最佳方式是:

*   当构建一个环境时
    *   用 Docker 有状态地配置一个客户操作系统。
    *   使用操作系统的软件包管理器有状态地配置一些系统软件包。
*   运行环境时
    *   用构建的容器映像无状态地配置容器。
    *   用 Nix 无状态地配置大多数系统包。
    *   使用您选择的语言工具无状态地配置项目库。
    *   使用 chezmoi 无状态地配置个人设置。

根据您的用例，您可能希望将一些或所有这些无状态配置步骤移动到构建过程中，以在容器图像层中缓存它们的结果。

## 运行 IDE

有了以上所有的工具，我们有多种方法来可靠地、可重复地配置本地环境。这个环境可以是一个最小和高性能的日常驱动程序，也可以与个人文件、消息应用程序、其他环境和 Docker 本身隔离。然而，如何与运行在容器中的 IDE 交互并不明显，这是下一步必须做的事情，除非您选择了不需要容器的 NixOS。

本地安装的 IDE 可以在本地使用，因为 IDE 充当自己的客户端，但是大多数容器化的 IDE 需要使用与 IDE 服务器分离的 IDE 客户端，以便在操作系统之间进行通信。以下是一些著名的 IDE 客户端，包括基于 web 的(在线 IDE)和本地的(混合 IDE):

### VS 代码

VS Code 是一个流行的 ide，它是第一个同时提供混合和在线解决方案的 IDE。

[远程开发](https://code.visualstudio.com/docs/remote/remote-overview)是一组第一方 VS 代码扩展，允许现有的 VS 代码安装作为混合 IDE 使用，连接到某处运行的 VS 代码服务器。这是一个容易建立的解决方案，但是它要求用户要么在他们的容器中配置一个 VS 代码服务器，要么使用[容器的扩展](https://code.visualstudio.com/docs/remote/containers)来托管整个开发者环境。这是一个为想要使用他们的本地 VS 代码 IDE 作为他们的 IDE 客户端的单独开发者准备的工具。

或者，[代码服务器](https://github.com/coder/code-server)是一个第三方 VS 代码 web 服务器，它将 web 应用中的 VS 代码客户端呈现为一个在线 IDE，连接到 VS 代码服务器。这是一个灵活的在线解决方案，需要先进的网站托管技能，但它不支持来自微软市场的扩展。这是一个面向希望非本地使用 VS 代码的 solo 开发者的工具。

### JetBrains IDEs

[Projector](https://lp.jetbrains.com/projector/) 是 JetBrains suite 套件的第一方容器化解决方案:PyCharm、IntelliJ IDEA、PhpStorm 等。这允许你将任何 JetBrains IDE 作为在线 IDE 运行，但是 UX 与它们的本地应用不一致，因为 Projector 为 IDE 的基于 Swing 的 GUI 实现了 HTML5 连接器。

### 其他 ide

Selkies-gstreamer 是一个 DIY 容器化解决方案，可以在一个具有基于浏览器的界面的容器中运行任何 Linux 兼容的 IDE/GUI。由于 Selkies 平台是一个非常独特的解决方案，我们将在后面的章节中详细讨论这个更广泛的平台，但是这个独立的组件对于想要运行没有自己的容器化工具或 web 前端的特定 IDE/GUI 的个人开发者来说是一个强大的工具。

### 缩放问题

这些解决方案都需要一点点 Docker 修补，但它们对于独立开发者来说非常棒。然而，部署和扩展它们以服务于中等规模的开发团队需要容器编排和网络方面的专业技能。为每个用户的应用流会话高效地配置和可扩展地维护 Kubernetes 集群是一个不小的技术挑战，分布式/远程团队可能需要位于多个大陆的多个集群，这增加了额外的维护复杂性。

## 扩展以服务您的团队

我们 itopia 的人认为，这种自动化挑战听起来对我们的远程工作站团队来说比一般的开发团队更有趣，因为大多数团队比维护工作站集群有更高的优先级。itopia 管理远程企业工作站已有近十年的历史，因此我们对大型团队如何采用、扩展和维护注重生产力的环境有一些了解。

## 为大型团队而设计

关于远程工作站，大型团队有以下偏好:

*   可移植性:[基于浏览器的 IDE 客户端比基于操作系统的 IDE 客户端更方便](https://thenewstack.io/are-cloud-based-ides-the-future-of-software-engineering/)。
*   性能:网络应用应该在云中完成所有繁重的计算和网络工作，而不是在浏览器中，以防止资源瓶颈。
*   灵活性:所有的 ide 都应该支持与本地安装相同的 UX，以最小化转换成本，最大化开发效率。
*   安全性:高安全性终端对于保护知识产权至关重要。
*   维护:对于企业来说，完全托管的服务通常比自托管的服务更实用，因为自托管需要细致入微的维护。
*   透明性:开源技术比闭源技术更加灵活、安全和可审计，这对 CTO 和系统管理员都很重要。

我们惊讶地发现，没有解决方案可以满足上述所有偏好，这意味着团队必须以某种方式妥协。浏览器渲染和本机 IDE 客户端(它们合起来涵盖了大多数解决方案)都需要将源代码流式传输到所有开发人员设备，几乎没有针对 IP 泄漏的保护。像 [GitHub Codespaces](https://github.com/features/codespaces) 这样固执己见的服务在支持单一 IDE 和版本控制系统方面不够灵活。一些解决方案提供自托管作为安全性和灵活性升级，但这增加了维护工作量。

## itopia 空间介绍:大规模的本地环境代码

itopia Spaces 为团队和企业勾选所有正确的方框；这里有一个免费的[试驾](https://test-drive.itopia.space/)来证明。它最有前途的特性之一是它能够流式传输任何兼容 Linux 的 IDE/GUI，而不需要任何定制的客户端。请参见[我们的 itopia 管理的图像开源目录](https://github.com/itopia-inc/spaces-images)，了解您独特定制图像的可能性和起点。

核心技术是公开的，所以也可以看看 [Selkies](https://selkies.io/) ，这是[开源](https://github.com/selkies-project)云原生流媒体平台，我们已经与谷歌合作创建了[。如果你喜欢今天看到的东西，](https://github.com/GoogleCloudPlatform/selkies)[加入我们的社区](https://discord.gg/byveDRm3Wv)，让我们知道你明天想看什么！我们喜欢看到人们在 Selkies 上构建，我们希望共同培养一个高质量的远程应用流新标准。

看到最近在改善开发人员环境方面取得的进步是令人满意的，并且想到编码过程在几年后会是什么样子也是令人兴奋的。然而，最起码，开发人员将能够可靠地配置他们的环境，以满足他们的需求，而不必在项目或键盘旁边的水杯角度发生变化时，花费一周时间手动键入命令和编辑文件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>