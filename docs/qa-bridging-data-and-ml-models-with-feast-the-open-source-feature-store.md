# Q&A:用 Feast(开源特性库)连接数据和 ML 模型

> 原文：<https://thenewstack.io/qa-bridging-data-and-ml-models-with-feast-the-open-source-feature-store/>

原始数据推动了当今机器学习平台的训练和预测能力。但所有这些原始数据都需要首先由数据科学家进行转换，然后才能得到有效利用。这种从数据中提取有用的[特征](https://thenewstack.io/machine-learning-in-production-lessons-learned-from-deploying-our-first-ml-model/)的做法，作为[特征工程](https://thenewstack.io/how-automl-puts-the-power-of-ai-in-the-hands-of-business-analysts/)过程的一部分，有助于避免当机器学习(ML)应用规模扩大和复杂性增加时出现严重问题。进入[功能商店](https://thenewstack.io/machine-learning-in-production-lessons-learned-from-deploying-our-first-ml-model/)的概念:一个自动管理和提供功能的工具。

早在 2019 年，谷歌与印度尼西亚初创公司 [Gojek](https://www.gojek.com/) 、 [Feast](https://feast.dev/) 、(**Fea**ture**St**ore)就是这样一个针对 ML 的开源功能商店。作为一个运营数据系统，Feast 是数据工程和机器学习之间的桥梁，它有助于自动化生产机器学习系统中出现的一些关键挑战。我们采访了 Feast 的创造者 Willem Pienaar，以便更好地了解特色商店是如何工作的，以及它们对 MLOps 的发展有什么样的影响。最初受到优步米开朗基罗专卖店的启发，Feast 已经有了很大的发展。为了使特色商店更广泛地进入大 ML 社区，Pienaar 现在将加入创造米开朗基罗的同一家公司 [Tecton](https://www.tecton.ai/) 。

**什么是盛宴，这个系统产生的背后动机是什么？**

基本上，我们有一群团队(10+人)在 Gojek 构建和部署 ML 系统。这些是定价、配对、欺诈检测和推荐系统的关键业务系统。所有这些团队都需要在生产中为他们的模型提供功能，但是他们自己手动部署和管理必要的数据基础设施。同时，所有这些项目和系统都是孤立的，所以大量的工作是重复的，功能重用是不存在的。Feast 就是为了解决这些问题而创建的。

**什么是特征、特征库，以及特征库如何适应将机器学习集成到今天的应用程序中的整个过程？**

特征是实体的单个可测量的属性。例如，一个特征可以是一个客户(实体)每天的平均交易量。特征数据是训练模型和生产模型的输入。

特征存储是可操作的数据系统。它们提供了一个中央界面，团队可以通过这个界面创建和发布新的特性，其他团队(或系统)也可以通过这个界面消费新的特性。典型的流程是，数据科学家将数据推入要素存储进行存储，或者将转换注册到要素存储，生成的数据将存储在要素存储中。一旦要素存储中的数据可用，另一个团队就可以使用这些要素来训练模型，还可以从要素存储中检索要素以进行在线服务。

所以本质上，特征库是模型和数据之间的层。

**特色商店能解决什么样的挑战或问题？**

总而言之，功能商店:

*   **加速功能生命周期。**在预特性存储场景中，数据科学家通常会在单独的筒仓中实施特性，然后将他们的代码移交给数据工程团队，以重新实施生产就绪管道。这个重新实现管道的过程会给项目增加几个月的时间，并且需要团队之间复杂的协调。通过要素存储，数据科学家可以构建生产就绪的要素，并将其自助应用于生产。
*   **提高特征精度，进而提高预测精度。**特征简化了构建特征的过程，并使 ML 团队能够使用所有可用数据进行预测。他们可以更轻松地整合批处理、流式和实时数据，以提取更多预测值。此外，要素存储可确保整个组织中的要素数据只有一个真实来源。训练数据与服役数据一致。通过消除潜在的数据偏差，模型可以更加准确。
*   **功能的共享和重用。**特性在组织中的所有数据科学家之间共享，便于跨模型共享和重用特性。
*   **类似 DevOps 的工程流程。**数据科学家天生不是软件工程师。他们通常不构建生产就绪的代码，而是依赖像数据工程师这样的独立团队来重新实现生产就绪的代码。要素存储允许数据科学家构建生产就绪的要素，并将其投入生产。这反过来允许实现类似 DevOps 的最佳实践，数据科学家拥有他们从开发到生产的所有“代码”，就像软件工程师拥有他们的代码一样。

**特色商店最初是在哪里、为什么以及如何形成的？**

特色商店最初是由泰克顿在优步的创始人创造和设计的，他们创造了米开朗基罗的机器学习平台。

大多数科技公司都有数据基础设施，试图在某种程度上解决 ML 用例，但功能商店是独一无二的，因为它们试图将这些工具专门用于 ML 用例。例如，特征存储统一了在训练和在线服务中检索特征的方式。

在某种程度上，特征商店的出现是团队试图部署越来越多的机器学习系统的结果。以前，许多开源和企业软件解决方案试图解决模型服务，但是 ML 团队意识到数据通常是更难(也更值得)解决的问题。不仅仅是特性工程，还有使数据在生产系统中大规模可用的操作方面。

大型技术公司首先遇到这些问题，这导致他们创建功能库来解决他们的用例。你可以在这里[看看其他一些做同样事情的公司。](https://featurestore.org/)

**为什么最近出现的特征库对机器学习来说意义重大？**

说明空间正在走向成熟。到目前为止，焦点主要集中在通用数据工具和基础设施上，以及局限于开发而非操作的特定于 ML 的工具上。但是考虑到想要在 ML 上运行业务关键系统的组织的数量，我们看到了对可操作 ML 的新一波兴趣。特性存储是这些 [MLOps](https://thenewstack.io/machine-learning-for-operations/) 工具之一。这很重要，因为这些问题对许多团队来说还没有解决，但我们相信这项技术将在几年内成为主流。

**数据科学家和数据工程师以前使用过哪些其他数据管理方法，它们与 Feast 等工具相比如何？**

您不必为了设计要素或向模型提供数据而部署要素存储。例如，您可以使用 [Spark](https://thenewstack.io/spark-continuous-processing-turn-integration-discussion-ear/) 进行数据处理，从您的数据仓库中训练模型，将数据推入 [Redis](https://thenewstack.io/redis-in-the-age-of-ai/) ，并让您的模型服务层直接与 Redis 交互。

问题是团队有:

*   没有集中的基础设施，这意味着每个系统都需要像在线商店和 ETL 管道这样的数据基础设施的新部署
*   没有结构化的方法来定义和发布其他团队可以使用的特性
*   无法浏览和使用其他团队的功能
*   无法以一致的方式检索用于训练和服务的特征(暂时或输出数据的形状)
*   模型和数据基础设施之间的硬耦合
*   没有监控数据处理或提供给模型的数据的方法

因此，完全不同的 ML 基础设施的自然发展是向特性存储设计发展。

**有哪些使用 Feast 的公司或组织的例子，Feast 如何改进他们的工作流程或整体运营？**

一个例子是 Postmates，一家美国公司，提供餐馆准备的食物和其他商品的本地递送。它使用盛宴进行欺诈检测。他们受益于能够将特征发布到某个主题，并自动让离线/在线商店保存他们的数据用于模型训练和服务。

在线旅行社和元搜索引擎 Agoda 是另一个例子:它使用 Feast 作为整个数据中心的在线服务层。他们特别重视通过 Kafka 优先发布特性的能力，因为 ML 团队有一个集中的 Kafka 团队，为他们提供一个“受管理的”Kafka 设置。ML 团队也重视产品中特性的标准化定义，并能够为在线用例的大规模模型提供特性数据。

**盛宴未来有哪些改进？**

计划是让 Feast 成为最好的、全功能的开源特性商店。在近期路线图中:

*   **Python-first** :完全从笔记本上运行最小版本的 Feast 的一流支持，所有基础设施依赖成为可选增强。
*   **生产就绪**:为生产而构建的经过实战检验的组件集合。
*   **可组合性**:模块化组件，具有清晰的扩展、集成和升级点，允许高度的可组合性。
*   **与云无关的**:去除与特定于云的服务的所有硬耦合，并包含可移植技术，如用于数据处理的 Apache Spark 和用于离线存储的 Parquet。

随着泰克顿对 Feast 的贡献，我们将在以下领域增加贡献:

*   特征转换。目前，Feast 从外部管理的管道中获取数据。我们希望在 Feast 本身中添加编排数据管道的能力。
*   监控运营服务水平和数据质量。
*   类似 DevOps 的特性管理功能。
*   Feast 和 Tecton 之间的简单迁移，服务 API 的兼容性对使用特性的模型和应用程序是透明的。

从盛宴和泰克顿的这次联手中，我们可以期待什么？

泰克顿以一种有意义的方式支持盛宴。泰克顿正成为核心贡献者，我将全职加入泰克顿。这很重要，因为泰克顿是特色商店的领先商业供应商。该公司由优步的米开朗基罗的原始创作者创立，这是特色商店的第一个实例。到目前为止，特色商店只对优步、Airbnb、网飞和 Gojek 等领先的科技公司开放。然而，任何将 ML 投入生产的公司都需要这项技术。泰克顿的支持意味着公司现在可以选择使用 Feast 或泰克顿商业云服务，两者都提供高级功能商店功能。用户将有更多的选择，这将提高操作 ML 的状态。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>