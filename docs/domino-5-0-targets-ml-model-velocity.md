# Domino 5.0 以 ML 为目标'模型速度'

> 原文：<https://thenewstack.io/domino-5-0-targets-ml-model-velocity/>

“模型速度……是交付新的(机器学习)模型或改进这些模型的速度。这不仅仅是让一个模型快速投入生产，还包括你能以多快的速度和多频繁地迭代这个模型，以便它能利用当前的业务条件。”

这是多米诺数据实验室的产品营销高级总监鲍勃·劳伦特(Bob Laurent)向《新堆栈》讲述他公司的新版本[多米诺 5.0](https://www.dominodatalab.com/blog/whats-new-in-domino-5.0) 时所说的话。Domino 是一个具有 [MLOps](https://thenewstack.io/what-is-mlops/) 功能的企业数据科学平台，其新的 5.0 版本旨在通过灵活的基础设施、可伸缩的计算资源、重用先前工作的能力、增强的协作特性以及更简单的将模型投入生产的方式来帮助用户提高模型速度。

虽然新版本是在 1 月份宣布的，但它的重点对于机器学习领域来说意义重大，我们认为现在值得进行一些调查和分析。

## 四大支柱

技术复杂的组织，以及那些渴望实现这一目标的组织，已经过了机器学习的“神奇”阶段。他们的概念证明已经完成。他们的模型已经投入生产，并且正在工作。但这一过程仍然过于个性化，与其说是一门工程学科，不如说是一门手艺。因此，像 Domino 这样专注于 MLOps 的供应商正在努力帮助这些组织提高标准。Domino 5 专注于此，它的努力基于四个关键元素:

*   **分布式计算集群的自动扩展。**在 5.0 版本中，Domino 根据工作负载动态地增加或减少用于训练 ML 模型的分布式计算集群，或者根据它们对数据进行评分。对于数据科学团队来说，这消除了为处理器能力或为分布式计算预留的内存量指定参数的需要，从而使资源调配更加容易。对 IT 而言，它消除了将资源过度用于工作的问题，并有助于实现相应的成本节约。自动伸缩能力在内部和云中均可用，并且它支持 Domino 已经可用的所有集群类型: [Spark](https://spark.apache.org) 、 [Ray](https://www.ray.io/) 和 [Dask](https://dask.org/) 。
*   **更轻松的数据源连接。**在 5.0 版本中，Domino 为雪花、红移和亚马逊 S3 提供了预建的连接器，数据科学家只需提供他们的凭证就可以使用它们连接到他们的数据源。与一般的 ODBC 或 JDBC 驱动程序不同，Domino 的连接器被设计为与专门的机器学习框架(如 [PyTorch](https://pytorch.org/) )一起工作，能够生成兼容的代码，并构建和训练模型。这减少了大量的特别编码工作，否则这些工作将是必要的。对于雪花、红移或 S3 以外的数据源，用户可以创建自己的连接器并与同事共享。这增加了协作，因为除了代码和数据工件之外，用户现在还可以共享用于创建数据集的连接器。
*   **综合监控能力。**在新的 5.0 版本中，Domino 将其 Domino 模型监视器(DMM)功能引入了核心 Domino 平台。升级到 5.0 的所有 Domino 用户都可以访问模型监控，包括数据漂移检测和基本事实跟踪等功能，以帮助维护模型的质量和准确性。这就是模型速度的迭代组件发挥作用的地方，允许数据科学团队在生产中监控他们的模型，而无需使用单独的产品。如果检测到数据质量问题，Domino 只需单击一下就可以重新构建原始的开发环境，然后重新训练模型或进行冠军/挑战者测试，以找到最佳模型并将其投入生产。
*   模型漂移的自动化洞察。如果在监控期间检测到模型漂移，自动化洞察可以提供解释，通过检查模型的特征(输入变量)及其值如何随时间漂移来揭示漂移的根本原因。这些见解通过生成的可定制报告提供。

## 被“科学”蒙蔽了双眼？

尽管名为数据科学，但它更多地表现为一门手艺，而不是一个可重复的科学过程。整个人工智能和分析领域的供应商都面临着满足这一要求的压力。这为那些奋起直追的人提供了一个机会，但对不适应这种机会的供应商构成了威胁。

在其新版本中，Domino 将 MLOps 带到了云中，允许与开发和部署环境更紧密地集成，并简化了数据科学工作流。该公司显然注意到了这一呼吁，即让其客户能够以更加面向工程的方式来接触人工智能。其他供应商也已经开始这样做，并且可能会进一步加大赌注，不仅简化将模型部署到生产的过程，而且在需要时对它们进行监控和再培训。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>