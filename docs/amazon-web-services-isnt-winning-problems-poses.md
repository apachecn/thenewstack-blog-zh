# 亚马逊网络服务为什么没有成功以及它带来的问题

> 原文：<https://thenewstack.io/amazon-web-services-isnt-winning-problems-poses/>

服务将对应用程序开发产生什么影响？Joe Emison 看到了一种趋势，即在 Parse 和 Firebase 等服务中体现出更高的复杂性抽象。这给亚马逊网络服务及其虚拟化基础设施带来了什么？简单地说，对于 Emison 来说，它提出了一些触及核心的问题，即世界上最流行的 IaaS 实际上是如何构建的。

如今，亚马逊网络服务(AWS)是公共基础设施即服务(IaaS)市场无可争议的领导者。随着越来越多的组织意识到公共 IaaS 的巨大业务灵活性优势，很难想象在不久的将来没有亚马逊作为越来越多公司的关键基础设施提供商。当人们看到亚马逊对其公共 IaaS 的持续改进进行的智能投资时，这一点尤其如此，从越来越多的实例类型到越来越有效和更简单的 AWS 使用方式，如 Lambda。

但是对于 AWS 来说，迭代改进它创建的公共 IaaS 市场是不够的。因为虽然公共 IaaS 为公司提供了巨大的业务敏捷性，但除了当今的最佳实践公共 IaaS 部署之外，还可以获得更大的敏捷性收益。

> 具体来说，下一个创新似乎是从像牛一样的[服务器转移到根本没有服务器的](https://thenewstack.io/why-the-middle-tier-including-docker-wont-matter-to-most-of-us/)。

AWS 似乎明白未来会发生什么(参见前面提到的 Lambda)。但亚马逊有效竞争的能力受到其构建方式的制约。除非亚马逊改变 AWS 的一些基本方面，否则它将继续受到阻碍。事实上，对无服务器领域的公平分析表明，亚马逊不是领导者，而是一个遥远的追随者。

一个例子最能说明亚马逊是如何落后的。看完这个例子后，我将概述为什么我认为亚马逊需要做一些根本性的结构性改变，以便在这个新的无服务器战场上有效竞争。

所以让我们从头开始构建一个应用程序的例子。Instagram 是一个有用且相关的示例应用程序，因为它相对容易理解，并且具有许多现代应用程序(甚至在企业中)都需要包括的一些核心功能:移动应用程序、响应式 web 应用程序、一些社交共享元素和一些私有数据所有权元素。出于这个例子的目的，让我们考虑一个具有这些功能的类似 Instagram 的应用程序:使用社交媒体凭据登录，搜索并添加朋友到您的“私人共享”中，并以公开或私人的方式发布照片。

让我们将 Instagram 的[发布的 2012 年架构](http://highscalability.com/blog/2012/4/9/the-instagram-architecture-facebook-bought-for-a-cool-billio.html)(大多数人仍然认为这是今天公共 IaaS 部署的基本“最佳实践”)与今天的 AWS 无服务器架构和今天的[解析](http://www.parse.com/) [无服务器架构](https://www.parse.com/tutorials/anypic)进行比较。我也不会谈论移动应用或响应式 web 应用架构，因为它们本质上应该是一样的。出于我们的目的，我们我们只是在谈论后端(和中间层)。

下表最好地说明了为什么无服务器的未来如此令人向往。Instagram 2012 架构充满了如此多的不同技术和如此多的服务器。这意味着 Instagram 2012 需要非常好的知识和对这些技术的理解。更新 Instagram 2012 还需要考虑这些不同的系统会受到怎样的影响。

这当然比必须了解所有这些技术并运营数据中心要好得多。但是，为什么 Instagram 一定要知道 mdadm 或 Fabric 呢？这些是通用工具，可以外包给其他公司，而 Instagram 只专注于 Instagram 的特定需求。

这正是无服务器未来所做的。这并不是说像 mdadm 或 Fabric 这样的技术会消失，而是它们可以由其他公司来运行。亚马逊认识到了这一点，这也是 AWS 如此推崇 Lambda 的原因——它是一种不需要运行服务器就能运行代码的方式。

> 问题是 AWS 的无服务器未来(至少现在是这样)比它的竞争对手之一——脸书旗下的 Parse 要糟糕得多。

没错，脸书——一家不完全被定位为云发电站的公司，但它目前拥有一家比 AWS 做得更好的公司(至少在这个例子中)。

从左到右，你还可以看到列出的不同服务的数量，虽然今天的无服务器 AWS 在简单性方面肯定胜过 Instagram 2012，但 Parse 是一个比 AWS 更好的集成无服务器解决方案。我将解释为什么，但首先让我给出更多关于为什么 AWS 落后于 Parse 的细节。

分享是 Parse 如何在无服务器 Instagram 架构中击败 AWS 的最好例子。AWS 的无服务器身份服务名为 [Cognito](http://aws.amazon.com/cognito/) ，但它是单用户数据同步。这在你写了一个视频游戏并想保存用户当前的等级时非常有用，如果你想做任何不是 100%公开的分享，这是完全没有用的。

我担心通过 Cognito 共享数据对 AWS 来说是一个很大的问题，因为它的安全模型的工作方式。具体来说，AWS 正在重用其身份和访问管理(IAM)服务，该服务主要用于组织对 AWS 的内部访问，作为通过移动应用程序和网络进入 Cognito 的所有各种外部用户的访问控制方式。因此，实际上能够编写 IAM 权限和策略是一件非常重要的事情，尽管 AWS 在 IAM 中内置了一些惊人的灵活性， [AWS 并不是为了存储大量不同的 IAM 策略而构建的](http://docs.aws.amazon.com/IAM/latest/UserGuide/limits.html)。

谷歌现在拥有的另一个无服务器服务 Parse 和 Firebase 通过保存特定对象的权限来进行数据共享，这意味着[拥有大量不同的安全规则](http://blog.parse.com/learn/engineering/parse-security-iii-are-you-on-the-list/)。这在很大程度上是由于“不受信任的”客户端直接连接到您的数据存储，而不是通过“受信任的”中间层应用服务器。如果没有特定于对象的权限和大量的安全规则，似乎就无法处理无服务器的社交共享。这意味着亚马逊将不得不做出重大改变，以支持现代共享功能。

即使 AWS 能够解决如何进行无服务器共享，它也有一些基本的结构问题需要解决。它有 IAM 问题和许多其他问题，这使得无服务器 AWS 环境比使用 Parse 要糟糕得多。具体来说，AWS 是作为 API 驱动的服务构建的，它执行离散的通用任务。这意味着:

*   它要求 IAM 处理可信的内部用户以及完全不可信的外部用户。
*   通过这个 API 驱动的过程，AWS 要求它的每个其他服务也与不受信任的外部用户一起工作。
*   这迫使 AWS 服务以最初从未预料到的复杂方式工作。最终，AWS 不再是一系列微服务，它开始变得更像一个单片应用程序，似乎需要越来越多的时间来添加重要的功能。你可以在最近对 AWS 的 API Gateway 的评论中看到一些这样的内容。

对于软件开发人员来说，今天的无服务器 AWS 环境与 Parse 或 Firebase 没有可比性。相比之下，AWS 相形见绌。

Parse 和 Firebase 的开发人员体验(DX)比 AWS 提供的要简单得多。目前还不清楚 AWS 是否在以任何严肃的方式追求前端开发人员(就商业客户体验而言，通常是最重要的开发人员)。从前端的角度来看，所有的 AWS Lambda 和 Cognito 教程都是非常基础和初级的；充其量，它们处理认证和一些次要的数据传输。与 Parse 的丰富教程相比，你会明白为什么前端开发者不选择 AWS 作为他们的无服务器后端。

## 哲学问题

我还看到了一个哲学问题。亚马逊似乎认为公司需要的基本构建模块是 API 驱动的虚拟化硬件。2008 年，亚马逊追求数据中心和控制机器和虚拟机部署的 IT 人员，并允许开发人员使用 API 完成所有这些工作。亚马逊一直坚持这一愿景，并继续添加越来越多的 API 驱动的服务，增加了使用亚马逊 Web 服务的复杂性，并迫使组织雇佣云架构师和 DevOps 工程师来管理这些服务。即使是理论上更加抽象的服务，比如 Lambda，在实践中也需要一些重要的系统管理和/或 DevOps 经验才能正常运行。

相比之下，无服务器的未来只寻求管理那些需要特定业务逻辑的服务。运行虚拟机、存储、备份、负载平衡、缓存以及 AWS 擅长的许多事情都不是特定于业务的，对于绝大多数应用程序来说，可以毫无问题地外包出去。无服务器未来的基础构建块是一组执行特定于业务的代码的抽象计算资源。

那么，为什么亚马逊现在很难与 Parse 或 Firebase 正面竞争呢？也许这是因为亚马逊看到 Parse 和 Firebase 在处理市场的一小部分，但我认为[无服务器后端的胖客户端应用显然是企业的发展方向](https://thenewstack.io/why-the-middle-tier-including-docker-wont-matter-to-most-of-us/)，亚马逊也看到了这一点。这就是为什么他们要推出 Cognito 和 Lambda 以及 API Gateway。只是亚马逊被他们现有的服务、现有的客户和压倒一切的产品理念束缚住了手脚。

亚马逊在无服务器未来保持领先地位的唯一方法是将无服务器服务从以虚拟数据中心为中心的服务中分离出来，摆脱以服务器为中心的包袱继续前进。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>