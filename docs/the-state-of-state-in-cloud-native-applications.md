# 云本地应用中的状态状态

> 原文：<https://thenewstack.io/the-state-of-state-in-cloud-native-applications/>

在最近由 [The New Stack](https://thenewstack.io/concern-about-state-lessens-as-more-applications-use-stream-processing/) 与流数据平台提供商 [Lightbend](https://www.lightbend.com/company/news) 合作进行的一项关于公司如何在容器化应用中处理状态的调查中，68%的人表示，管理状态至少在某种程度上是将更多应用迁移到基于微服务的架构的障碍。

那么，企业如何在其云原生应用中管理从应用配置到持久存储的一切呢？让我们深入了解一下[云原生应用](https://thenewstack.io/10-key-attributes-of-cloud-native-applications/)的现状。

### 无状态的开端

要了解我们现在在管理云原生应用程序中的状态时的情况，记住一个关键事实很重要:容器被设计为无状态的，而 Kubernetes 被设计为编排无状态的、短暂的、不可变的容器。起初，这些应用程序需要的任何状态都只是存储在外部。

[StorageOS](https://storageos.com/) 的首席执行官 [Alex Chircop](https://www.linkedin.com/in/alexchircop/) 解释道:“即使容器应该是无状态的，容器化的架构仍然需要状态。这种状态不能存储在容器中，也不能由 orchestrator 管理。

然而，随着公司开始看到 Kubernetes 和容器化架构如何提高应用程序的灵活性和速度，越来越多的公司开始将越来越多的应用程序打包到容器中，并使用 Kubernetes 来管理计算和存储资源。

“现在每个人都开始将有状态的应用程序放入容器中，”NetApp 的首席技术专家 Chris Merz 解释道。“不管这是不是正确的设计，不管这是不是有意的，这就是正在发生的事情。”

### 错综复杂的风景

“应用程序可以用很多不同的方式存储状态，”Chircop 解释道。当谈到如何管理状态以满足特定的应用程序需求时，组织有过多的选择——这不是一个成熟的前景，所以在大多数情况下，成功地在容器中处理状态的公司是早期采用者，并且仍然处于使用容器处理状态的过程的相当早期。

事实上，在基于容器的架构中，没有一种“标准”的方法来处理状态，这也是一件好事。每个公司和每个应用程序都有不同的需求，在一种情况下管理状态的最佳方法可能不适合另一种情况。

“这是一个决策矩阵，”迈克尔·费兰蒂解释道，他是[波特沃斯](https://portworx.com/)的营销副总裁。首先，您决定是在 Kubernetes 上还是在 Kubernetes 之外处理数据。如果您的数据在 Kubernetes 之外管理，它将通过 API 连接到 Kubernetes，可以是云提供商数据服务，也可以是由数据库管理员管理的本地数据库。如果您选择直接使用 Kubernetes 来管理存储，您将通过一个[容器存储接口](https://github.com/container-storage-interface/spec) (CSI)与 Kubernetes 进行交互，以提供卷。

通常，您想要的存储是对象存储、键值存储和文件的某种组合。处理数据的最佳方式取决于特定的用例——例如，视频可能最好使用对象存储来存储。

由于管理云原生应用程序的状态仍处于相对早期的阶段，对于如何在任何给定的情况下处理状态，还没有广泛的共识或最佳实践清单。

“对于以开发为中心的开发人员来说，这是一个新问题，”Merz 解释道。“传统上，解决大规模状态是运营或数据库管理员的事情。这些都是核心的操作功能。处理大规模的状态似乎是巴塞罗那库比康大会的最大话题。

### 充满希望的未来

Lightbend 首席技术官 Jonas bonér[解释说，在实践中，迁移到云原生架构也是一个巨大的飞跃。根据他的经验，许多公司并没有意识到需要将应用程序架构改变为云原生的，并继续以与过去在 monoliths 上完全相同的方式处理状态之类的事情——至少在他们学会不这样做的艰难方式之前。](http://jonasboner.com/)

本文采访的每个人都同意，在基于容器的云原生应用程序中，状态是可以成功管理的——事实上，如果公司要将其整个应用程序套件迁移到基于容器的云原生架构，就必须成功处理状态。总的来说，公司似乎在朝着正确的方向前进——例如，慢慢地放弃在整体系统中工作而不是在分布式系统中工作的实践。

但是还有一些问题比较棘手。在实际数据放置由软件而不是数据库管理员处理的分布式环境中，可见性或了解特定数据位于何处是很困难的。但这很重要:如果一台服务器遭到黑客攻击，出于合规原因，公司需要知道那台特定服务器上存储了什么数据。Chircop 说，随着公司将更多敏感数据转移到云原生应用程序，默认情况下始终保持数据安全也是一个主要问题。

Bonér 说，特别是随着越来越多的应用程序变得以数据为中心，机器学习变得越来越重要，将数据存储在靠近计算资源的地方也很重要。另一方面，Merz 认为专注于局部性是短视的，但也承认核心目标——使数据和计算更容易交互并减少处理摩擦——是重要的。Merz 认为非常智能的编排平台是解决以数据为中心的应用程序中计算和数据之间的连接的更好方式。

还有文化方面的挑战。存储曾经是一个运营问题，开发人员通常无法控制存储配置流程。在云原生环境中，DevOps world 开发人员既有能力也有责任进行存储，包括做出将影响应用程序性能的选择。

Merz 说，最终，企业客户在管理状态时需要解决的挑战类型与 20 年前的挑战相同。他们需要一种方法来管理持久性，并以可扩展的方式来实现。数据需要保持安全，并且需要高度可用，满足与法规遵从性相关的业务需求。但是生态系统变了，体系结构变了，数据量变了，数据集成到应用程序和业务中的程度也变了。

“我想说的是，大多数企业还没有以云本地的方式运行他们的有状态服务，”Ferranti 解释道。“但他们会在未来 10 年。以云原生方式运行您的整个应用程序堆栈所获得的灵活性是如此之大，一旦业务需求得到满足，各种规模的企业都会开始这样做。”

KubeCon + CloudNativeCon、Lightbend、NetApp 和 Portworx 是新堆栈的赞助商。

来自 Pixabay 的 A. H .的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>