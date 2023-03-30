# 深度学习难题的 5 个关键部分

> 原文：<https://thenewstack.io/five-essential-pieces-deep-learning-puzzle/>

深度学习正迅速成为计算机科学最受欢迎的应用之一，这也难怪。深度学习允许计算机基于海量数据集进行学习和决策。它使公司能够解决在语音识别、计算机视觉、自然语言处理等领域不可能解决的问题。

然而，许多公司都在努力解决深度学习难题，并充分利用其潜力。它的建造和维护可能很昂贵，需要专业知识，而且对私营部门来说，它仍然是一个相当新的概念。随着公司开始探索这项强大的技术，有不同的方法来确保他们获得最大的收益。

对于想要实施深度学习的公司来说，他们必须具备五个要素，以确保他们能够充分利用深度学习。

### 1:量化成功的方法

 [斯科特·克拉克，SigOpt 的联合创始人兼首席执行官

斯科特·克拉克是 SigOpt 的联合创始人兼首席执行官。多年来，他一直在工业界和学术界应用最佳学习技术，从生物信息学到生产广告系统。在 SigOpt 之前，Scott 在 Yelp 的广告定位团队工作，领导学术研究和推广项目，如 Yelp 数据集挑战和开源 MOE。Scott 拥有康奈尔大学的应用数学博士学位和计算机科学硕士学位，以及俄勒冈州立大学的数学、物理和计算物理学士学位。斯科特被选为 2016 年福布斯 30 位 30 岁以下富豪之一。](https://www.sigopt.com) 

首先，在开始任何建模工作之前——无论是深度学习、更传统的机器学习还是一般的数据科学——量化成功的衡量标准是很重要的。这个过程包括确定这些模型和工作将跟踪和判断的指标。理想情况下，有一种方法可以将模型的性能直接追溯到业务价值。随着欺诈检测模型变得越来越准确，您可能会因欺诈而损失更少的金钱。随着推荐模式变得更好，你可能会卖出更多的产品。当一个特定的模型和明确的商业价值之间有许多步骤时，这有时会更加困难，但是这是极其重要的一步。

> 理想情况下，有一种方法可以将模型的性能直接追溯到业务价值。

没有一个与商业价值相关联的度量标准，就不可能判断你是否正在取得进展，或者模型本身是否有任何价值。即使在看似简单明了的情况下，这也可能是困难的。在欺诈的情况下，确保准确性的定义符合业务需求是很重要的。抓住 99%的欺诈是好的，但是如果 1%的欺诈都是 1000 万美元或更多，那么对业务来说就非常糟糕了。这种成功的衡量总是难以置信地特定于领域，并且对于每个业务和应用程序都是不同的。

不定义这些指标或使用标准的学术方法会导致浪费时间，降低业务成果，以及构建没有真正目的的模型。如果不能衡量这些方法的性能并将其与商业价值联系起来，企业可能会浪费大量的时间和金钱来构建非常昂贵的算法玩具。

### 2:大量干净的数据

企业中应用程序和物联网(IoT)设备的数量意味着数据并不短缺。但是许多数据集不能用于深度学习，因为它们太小，没有结构，或者不可信。如果机器学习模型是用不完整、非结构化或不准确的数据训练的，它们充其量也不能达到最好的结果，甚至可能会严重损害它们所应用的底层应用。

例如，假设您正在训练一个神经网络来对狗和猫之间的图像进行分类。要做到这一点，神经网络必须在许多标有相应正确答案的图像上进行训练。通过向机器输入足够多的不同类型的狗和猫的图像，神经网络最终将能够学习模式，以准确识别差异。如果你只有一些图像，只包括一个品种，或者如果数据被错误标记，最终的模型将不会达到预期的一般目的。公司必须确保他们有足够的干净和清晰标记的数据，以提高其深度学习模型的准确性。在进行任何培训或学习之前，必须完成这一步。

### 3:深度学习框架

深度学习框架是开发者构建深度学习应用的库和编程模型。框架对于有效的深度学习是必要的——没有它们，公司就无法做像图像和语音识别或语言理解这样的事情。然而，从头开始构建这些框架既昂贵又耗时。

幸运的是，像 [Tensorflow](https://www.tensorflow.org/) 、 [MXNet](https://mxnet.apache.org/) 和 [Caffe2](https://caffe2.ai/) 这样的工具提供了现成的、基于云的深度学习框架，易于实现。这些框架带有开源示例，比如自然语言处理系统和图像识别系统。如果一家公司拥有训练模型的数据，那么插入数据就相当简单，而不必知道底层框架是如何构建的。在选择深度学习框架时，公司应该考虑诸如开发问题的可用资源、易用性和部署以及定制等因素。在构建第一个模型之前，必须完成这一步。

### 4:强大的云基础设施

深度学习需要极端的计算资源。传统的 IT 基础设施不适合深度学习，因为它无法处理驱动洞察力所需的大量数据。亚马逊网络服务和微软 Azure 等平台上支持 GPU 的云基础设施使公司比以往任何时候都更容易建立和扩展深度学习管道。基于 GPU 的基础设施可以将应用程序的大规模并行、计算密集型部分卸载到 GPU，而其余代码则保留在 CPU 上，使应用程序的运行速度[提高了 50 倍，并且在实践中更加高效](https://aws.amazon.com/blogs/ai/fast-cnn-tuning-with-aws-gpu-instances-and-sigopt/)。在将模型扩展到生产级别的数据集和企业应用程序之前，必须完成这一步。

### 5:优化模型的方法

一旦你有了数据，框架到位，硬件基础设施健壮，阻止深度学习性能实现其真正潜力的最后一步是模型优化和超参数调整。对于任何深度学习模型，研究人员都需要设置几十个超参数，才能输入数据来训练模型。这些参数包括网络的层数、每层的节点数或学习速率等。如果最初的训练表现不佳，研究人员通常会调整几个旋钮，再试一次，或者他们可能会依赖昂贵的暴力方法，如[网格搜索](http://nogridsearch.com/)。这些调整深度学习模型的方法是时间密集型的，并且不保证有好的结果。

为了让开发者、数据科学家和研究人员更容易做到这一点，像 [SigOpt](http://sigopt.com/) 、 [Amazon SageMaker](https://aws.amazon.com/blogs/aws/sagemaker/) 和 [Google Hypertune](https://cloud.google.com/ml-engine/docs/using-hyperparameter-tuning) 这样的软件即服务解决方案可以消除超参数调优中的猜测。这些优化工具位于模型之上，并观察它们的输入和输出，以帮助研究人员确定他们需要调整系统的地方。优化机器学习算法和深度学习框架可以在[准确性、性能和效率](https://devblogs.nvidia.com/parallelforall/sigopt-deep-learning-hyperparameter-optimization/)方面提供许多数量级的改进。这一步可以让你从深度学习投资中获得最大的商业价值。

### 采取以下步骤

深度学习仍在大公司中获得立足点，不知道从哪里开始可能会令人困惑。有许多工具可以确保公司能够利用深度学习提供的所有资源。这项技术将继续改变企业的运营方式，在这一过程中，企业将需要具备这些要素，以确保自己不会被竞争所淘汰。

通过遵循这些步骤，公司可以确保他们的模型瞄准正确的方向，并且他们的深度学习努力是可能的、可扩展的和最优的。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>