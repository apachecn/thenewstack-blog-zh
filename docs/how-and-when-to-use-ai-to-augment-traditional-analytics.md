# 如何以及何时使用人工智能来增强传统分析

> 原文：<https://thenewstack.io/how-and-when-to-use-ai-to-augment-traditional-analytics/>

[](https://www.linkedin.com/in/chris-pouliot-aab996/)

[Chris Poul IOT](https://www.linkedin.com/in/chris-pouliot-aab996/)

[Chris 是雪花公司的数据科学和分析主管。](https://www.linkedin.com/in/chris-pouliot-aab996/)

[](https://www.linkedin.com/in/chris-pouliot-aab996/)[](https://www.linkedin.com/in/chris-pouliot-aab996/)

每个企业都希望更多地由数据驱动，人工智能技术是增强传统统计分析的重要方式。但是不要让围绕人工智能的大肆宣传说服你把它强加到不需要它的问题上。这只会导致糟糕的结果和资源浪费，并破坏未来的举措。本文将帮助您决定何时以及如何应用人工智能技术来最大化其商业价值。

退一步考虑为什么 AI 这么有价值，是有帮助的。从纯粹的规模和大小角度来看，传统方法限制了您可以使用的数据集。当你把机器学习放在问题后面时，你实际上是在应用工程学来处理计算的抽象，这种方式允许你浏览比传统方法允许的大得多的数据集。

从这个意义上说，“传统”并不是老式或传统的委婉说法。我们在机器学习和深度学习方面所做的很多事情仍然基于传统方法，它只是允许我们在更大的规模上应用这些方法。这意味着，当你将传统分析扩展到机器学习方法时，你应该应用一些与传统分析相同的批判性思维。

考虑到这一点，在考虑何时以及如何应用机器学习和深度学习来增强传统的统计分析时，有哪些考虑因素？

## 数据集的大小

正如我们上面提到的，最重要的是数据的大小。当超过一定数量的行和列时，传统的统计方法无法让我们识别所有的相关性，并理解什么是有趣的或重要的。人工智能方法增强了传统方法，以及我们作为人类的能力，允许我们分析更多数据，并识别否则将保持隐藏的见解或关系。举一个例子，机器学习可能允许我们基于数百个变量而不是几个变量之间的关系来建立客户细分。

作为一个附带的好处，机器学习算法有时可以提高对可用数据集不能为准确预测提供足够信息的认识。从这个意义上说，它们提供了一种方法来确定数据策略中的差距，并决定是否应该从第三方数据或合作伙伴那里获取新的变量，以提高模型的可预测性。

但是，处理更大的数据集也为更多的算法打开了大门，这些算法现在只需点击一下鼠标。这可能是一个问题，因为我们仍然必须批判性地思考，并对我们选择的算法和框架有所选择。

## 可解释性与性能

另一个需要考虑的是你正在解决的问题的可解释程度。如果你正在使用深度学习来控制自动驾驶汽车，你不需要了解每个变量对输出的影响(有时甚至不可能，如果交互的模型未知或计算难以处理)。你只需要高度确信它是安全的。但是如果你预测一台机器是否会出故障，你需要了解每个变量的影响——温度、湿度、机器的转速等等。—否则输出是没有用的，因为它不允许您采取纠正措施。

可解释性在其他情况下也很重要。如果一个模型产生的结果与直觉不符，那么你花时间建立的模型可能不会被使用。例如，如果一个模型预测某个变化将增加 40%的销售额，但是你不能解释为什么，人们可能会拒绝它，因为他们不相信这个结果。

更进一步的考虑是人工智能的道德使用。关于偏见是如何渗透到计算机决策中的，已经有了很多讨论。例如，如果用于监督学习的训练数据有偏差，那么输出很可能反映这种偏差。可解释的人工智能试图通过确保人类理解系统如何达到特定输出来解决这一问题。同样，用例很重要。如果该模型建议对被定罪的罪犯判处监禁，那么确保无偏见的输出远比建议接下来播放哪部电影更重要。

## 选择正确的算法

不同的算法有不同的优缺点。举个简单的例子:在预测中，你可能会在 ARIMA、ARMA、Prophet、LSTM 或其他什么之间进行选择。其中哪一项最受更广泛的社区支持？它们之间的功能差异是什么？有哪些局限性？它们会带来什么样的固有偏见？这些都是细微的考虑因素，没有同等的权重，将取决于手头的业务或分析问题。这只是时间序列预测。与领域专家合作并仔细考虑用例对于选择最合适的算法至关重要。

将领域知识映射到问题空间也是选择正确算法的一个重要因素。例如，您可能会发现有多种算法来处理分类。但是分类是一个多样化的领域，什么是正确的算法可能会因行业或用例的细微差别而有所不同。因此，领域知识对于帮助识别最适合分析问题的算法是很重要的。相反，不应用领域知识来选择适当的算法会导致无意义的结果，即使机器学习工作流的机制已经执行得很好。

## 执行速度

对于大多数组织来说，真正的价值在于数据，而不是调整算法，因此从业者可以通过 AutoML 工具加速他们对机器学习的使用。这些工具允许您针对相同的数据测试 20 或 30 个算法，并比较这些模型的性能。这允许了我们以前没有的迭代和可见性水平。这是一种以更广泛的方式测试经典算法的强大方法。

但是这里也有一个权衡。如果五个模型产生相似的高性能分数，你如何决定哪一个更可取？一种选择是使用数据子集进行 A/B 测试，以收集关于哪个模型真正具有最佳性能的经验证据。无论是在首次创建模型时，还是在更新模型和/或数据时，这都是一种良好的通用 MLOps 实践。

如果两个或更多的模型表现得一样好，一个解决方案是使用可解释性作为决胜局。这是因为，从长远来看，理解模型上下文中的特征影响和重要性最终将在维护模型、更新模型、选择更多训练数据和解决模型漂移问题方面更加有用。

## 结论

将人工智能技术应用于数据极大地扩展了数据的可能性以及如何利用数据释放商业价值的领域。但是，如何以及何时使用人工智能模型有许多细微差别和考虑因素。这在过程的早期就开始了。在许多方面，调整模型参数已经成为一种商品，性能是由数据选择和准备驱动的。云给了数据从业者利用人工智能的巨大力量，但它需要深思熟虑地应用，以获得它可以产生的令人难以置信的好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>