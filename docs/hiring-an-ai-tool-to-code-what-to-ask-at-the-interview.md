# 雇佣一个人工智能工具来编码？面试时要问什么

> 原文：<https://thenewstack.io/hiring-an-ai-tool-to-code-what-to-ask-at-the-interview/>

自从 ChatGPT 于 2022 年末发布以来，互联网上一直充斥着悲观和乐观的声音。不管你喜不喜欢，人工智能(AI)正在向你的开发机构走来。即使你不打算开发一个人工智能产品或计划雇用一个人工智能开发机器人来为你编写代码，它仍可能被集成到用于构建、测试和运行你的手工源代码的工具和平台中。

我们已经看到，人工智能工具将具有独特的风险，这些风险可能会抵消自动化曾经需要人类脑细胞的任务所带来的巨大生产力收益。这些风险源于人工智能的训练、构建、托管和使用方式不同于开发者信任的其他软件工具。理解风险是管理风险的第一步，为了帮助你理解与即将到来的人工智能工具相关的潜在风险，我们写了一些面试问题，这些问题应该是入职流程的一部分。

任何级别的人工智能工具都有一些共性，无论人工智能的类型或目的如何，都应该问这些问题:

*   它将在哪里举办？现代人工智能目前需要专用和昂贵的硬件来完成我们今天看到的令人震惊的任务。除非你打算收购一个新的数据中心，否则你的人工智能机器人将远程工作，并需要与使用远程访问和异地数据存储的人类工人相关的相同的安全考虑。
*   **当代码离开边界时，有什么样的保护措施来防止知识产权的丢失？**从智能电视到汽车，一切都在向制造商报告使用数据。一些人用这些数据来改进他们的软件，但是其他人把这些数据卖给广告商。准确理解你的人工智能工具将如何使用或处理它用于其主要任务的源代码或其他私有数据。
*   **你的输入会被用于未来的人工智能训练吗？对人工智能模型的持续训练将是一个越来越受关注的领域，无论是对所有者还是对那些使用其数据来训练模型的人来说。例如，所有者可能希望阻止广告商影响人工智能机器人，使其朝着有利于客户的方向发展。在网上分享作品的艺术家已经看到人工智能图像生成机器人能够大规模复制他们的风格，并且非常担心创作身份的丢失或被盗。**
*   **其结果的保真度如何？ChatGPT 最广为人知的缺点是其结果的不准确性。它会自信地断言谎言就像断言真理一样容易。这被称为人工智能幻觉。了解人工智能如何以及在哪里产生幻觉，可以帮助它在出现幻觉时进行管理。**

最重要的是，人工智能的所有者和开发者将有他们自己的安全顾虑。这些新的担忧包括对人工智能训练模型的威胁，这些威胁可能会破坏其结果并泄露有关模型如何运行的专有信息，以及可能破坏模型结果质量的威胁。此外，人工智能模型必须通过 API、web 访问、移动应用程序和其他需要安全构建的应用程序与传统世界进行交互。

除了一般的问题，开发人员在使用人工智能工具时还必须问一些额外的问题，例如人工智能安全扫描器，以管理软件开发过程中引入的风险。

*   **人工智能工具最适合这种用例吗？理解人工智能擅长什么和不擅长什么是关键。一项任务越能被分解为“根据学习到的规则做出决定”或“编写符合学习到的规则的内容”，人工智能就越能胜任。随着问题的变化超出这个范围，人工智能会变得更糟。**
*   **如果工具没有捕捉到一些东西或者产生了一些不存在的幻觉，有什么安全措施？**永远不要在流程中引入单点失败，尤其是可能产生幻觉的单点失败。依靠与深度防御相关的传统实践，或管理风险的“瑞士奶酪”方法，即使一层遗漏了一个问题，下一层也会发现它。
*   **审查工具结果需要什么监督？**这是一个旧问题变新了；传统的测井指南分为两部分。第一个是捕获重要事件的数据；第二个是审计日志。直到人工智能进一步成熟，它的缺点被理解或减轻，人类仍将需要保持在循环中。

越来越多的开发者“雇佣”ChatGPT 来编写源代码。最初的报道是 ChatGPT 能够用许多编程语言编写源代码，并且能够流利地使用所有常见的和公开讨论的语言。由于这个测试版的训练和模型的限制，它产生的代码并不总是完美的。它通常包含可以改变软件运行方式的业务逻辑缺陷、混合不同版本软件的语法错误以及其他看似源于人为的问题。

> 基本上 ChatGPT 是初级开发者。谁将是它的经理？

换句话说，ChatGPT 是初级开发者。当使用这个初级开发人员编写的代码时，必须考虑如何管理它:

*   谁将是它的管理者，确保编写的代码是功能性的、优化的、高质量的并且符合安全标准？初级开发者需要高级开发者。每一行代码都必须经过测试，有些还必须修复。然而，最初的报告是，这种校对过程比从头开始编写代码更快更容易。
*   是将训练代码注入还是重新混合到您的代码库中？一个更阴险的威胁是，有时像 GitHub Copilot 这样的人工智能机器人会产生源代码，完美地复制其训练数据中的代码块。将需要反盗版工具来确保许可证风险得到管理。
*   **机器人从哪里获得训练数据？**人工智能模型的好坏取决于它的训练数据。如果机器人在旧的或不正确的代码上训练，它将产生旧的和不正确的结果。
*   **引擎托管在哪里？**分析源代码的人工智能机器人需要将源代码带到其处理设施。额外考虑数据在离开公司边界后如何保护、使用和处置。

12 月 ChatGPT 的发布预示着软件开发的新时代。重要的是适应变化，而不是被它们击倒。当采用这些新工具时，要明白事情变化越多，它们保持不变的情况就越多:预防安全事故总比被意外发现要好。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>