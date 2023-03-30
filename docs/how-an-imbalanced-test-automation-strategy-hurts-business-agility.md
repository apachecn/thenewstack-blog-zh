# 不平衡的测试自动化策略如何损害业务敏捷性

> 原文：<https://thenewstack.io/how-an-imbalanced-test-automation-strategy-hurts-business-agility/>

[](https://twitter.com/bluefug?lang=en)

 [杰森·英格利西

Jason 是 Intellyx 的首席分析师和 CMO，他为领先的技术解决方案提供商和软件初创公司提供数字化转型方面的建议。他的企业软件背景包括供应链、交互设计、软件开发和测试、虚拟化、云计算和区块链。](https://twitter.com/bluefug?lang=en) [](https://twitter.com/bluefug?lang=en)

任何参与软件交付的人都会告诉你，自动化——在任何可能的地方——本质上是一件好事。但是为了测试自动化而测试自动化会使我们的软件生命周期失去平衡吗？

最近，我们都敏锐地意识到，在确保我们自己的健康和我们所关心的人的健康时，需要保持平衡。为了寻求这种平衡，我们从流行病学家、营养学家和私人教练那里获取信息。

随着时间的推移，我们身体的表现与实现平衡有很大关系。控制热量摄入对饮食很重要，但为了长期的成功，你也需要适量的全食物脂肪和胆固醇。在为一项运动进行训练时，锻炼是有益的，但在没有足够休息的情况下走极端可能会削弱身体的恢复能力，并在赛场上造成伤害。你可能需要维生素 D 和钾来预防感染，但是过多的这些化合物可能是危险的。

这甚至还没有涉及到我们的精神状态，如果突然受到不适当的精神压力，这种状态既可以稳定我们，也可以对我们的健康产生最具破坏性的影响。

同样，构建、测试、部署和可观察性的自动化对我们软件的健康都是有益的——但只是适度的。例如，我们可以用自动化来代替大多数功能性的 UI 测试，但是仍然需要某种程度的手工用户验收测试(UAT)和人工验证。

如果太多的测试自动化被应用，在最不适宜的时间和错误的原因下，软件生命周期——以及随之而来的，您的业务敏捷性——将会失去平衡。

## 盲目的自动化是有风险的

测试是软件开发的阴阳两极——没有它，就不可能知道软件是否满足需求。

随着敏捷软件开发和交付的加速，很明显我们可以(也应该)尽可能多地进行连续的自动化测试。但是我们需要有策略地去做，而不是盲目地去做。否则，下面的坏习惯可能会导致测试自动化变得适得其反，并且实际上破坏我们的业务敏捷性:

*   **让天平偏离客户结果。测试自动化的目标应该总是与客户的目标一致:更好的软件功能、可靠性、安全性、性能。很容易忘记将商业激励与每一个被引入和维护的测试自动化的实例联系起来，但是如果没有这种一致性，团队仅仅是为了检查一个盒子而创造了无效的劳动和成本。**
*   **感觉一种虚假的安全感。**这种习惯的症状可能包括声称 99%或更高水平的“测试覆盖率”,这是通过执行成千上万的静态代码检查、单元测试、数据比较和回归而产生的。在软件交付生命周期的每个阶段，大量的测试过程对于质量控制网关都是有用的。但是在任何一个级别上说“我们的百万单元测试通过了”并不能自动转化为更好的用户体验；这样的统计数据不能提供超过一个复杂应用程序组合的遮羞布的价值。
*   **对变化不灵活。如果测试策略不是为变化而设计的，那么每一个新的更新、组件或者贡献都会使测试自动化不可用，测试数据无效，结果难以重现。脆弱测试——那些不能经受住变化的测试，尤其是在敏捷环境中——会产生测试人员看到的 60%到 80%的假阳性和假阴性。当资产不响应变更时，团队开始放弃修复现有测试和构建新测试的无用努力，这会影响组织向前发展的能力。**
*   **试验腹胀和烧伤。对不平衡的测试自动化的本能反应是创建越来越多的简单测试，或者现有测试的微小变化。由于冗余测试的失败很难追溯到它们的源头，所以几乎同样多的时间都花在了重新创建测试上——因为人们认为失败的发生是因为测试不好，而不是应用程序本身。测试膨胀会导致运行测试工作负载以及收集和清理测试数据的系统成本和云运营支出增加，从而导致更高的人力消耗率。如果集成合作伙伴参与并被激励进行更多的测试，他们可能会以惊人的速度消耗预算，内部测试人员将会经历更高的倦怠。**

所有这些挑战一起消耗了大量昂贵的资源，这些资源可以更好地投资于最高价值的工作，而这些工作是无法自动化的。随着时间的推移，这削弱了组织对测试的信心，对您快速发布满足客户不断变化的需求的软件的能力产生了巨大的影响。

## 成功的正确资源

幸运的是，通过在正确的时间，正确的地点，使用正确的资源来自动化正确的测试类型，打破这种恶性循环是可能的。

*   **在正确的时间进行测试:**我们可以做更多的事情，将关键的功能、回归、集成、性能和安全性测试融入 SDLC 的每个阶段，使其体验更加顺畅。问题可能不是“太多的自动化”，而是确保我们所做的测试自动化增加了商业价值——在软件开发的任何一个阶段，避免任何一种测试的不平衡和/或潜在的不健康的情况。
*   **在正确的地方测试:**多年来，为了平衡我们自己的健康，我们拉伸身体以保持灵活性和更好的运动范围。在软件方面，我们也训练灵活性，以便我们的测试在任何有风险的地方——在应用程序架构的每一层——都保持弹性和有用。这包括弹性 UI 测试、API 和微服务层验证、端到端数据测试，以及关注高风险变更影响以缩小测试范围。
*   **用正确的资源进行测试:**表现最好的公司总是强调提高所有团队成员的生产能力——通过职业成就、组织设计、教育和技能发展的文化组合——与将程序、工具和基础设施到位以使他们成功相平衡。

## 基本成分

这些基本要素应该总是存在，以促进高质量、敏捷的软件交付:

*   **快速反馈循环。**实现对测试运行的近乎即时的响应，以及来自模拟环境和真实客户使用的快速反馈，被认为是测试驱动开发的“超级食物”。高测试响应性允许团队调试问题或查明开发人员问题解决的根本原因，而无需上下文切换。
*   **需求测试自动化。如果你真的想把测试一直向左转移，为什么不开始测试测试需求本身呢？这种方法听起来可能很荒谬，但几十年来，需求测试一直是高度监管环境(如电子和国防)的重要设计证据。像 [Tricentis Tosca](https://www.tricentis.com/products/automate-continuous-testing-tosca/vision-ai/) 这样的解决方案允许测试需求根据业务价值和风险进行加权和优先排序，允许相关性和影响较小的测试完全脱离预算。**
*   **自助服务自动化环境。**软件定义的基础架构代码(IaC)和可弹性扩展的公共/私有云容量的所有优点不仅仅是针对软件构建和部署团队。完整测试环境的自动设置和拆卸，补充了黄金状态测试数据，大大减少了周期时间和管理费用。自助服务在这里非常重要，因为当测试团队可以随时调配自己的资源而无需记录 IT 支持请求时，他们会发展壮大。
*   **服务虚拟化进行模拟。**有时，你需要挑战现实，满足于虚拟环境。服务虚拟化(或 SV)允许捕获、配置和模拟系统，因此您不再需要访问真实的东西。为什么会更好？SV 不仅消除了过度约束系统的可用性冲突，而且虚拟环境还可以更可预测地模拟“未来”状态和场景数据，包括难以在现实世界中重现的边缘条件，从而获得更加一致的测试结果。
*   **欢迎我们的人工智能合作者。**称之为机器学习或增强智能，但我们开始看到一种新的人工智能驱动的测试，它可以视觉检测和识别屏幕上的元素，并理解人类用户与这些对象的交互是如何与应用逻辑联系在一起的。 [Tricentis](https://www.tricentis.com/?utm_content=inline-mention) 引入了 [Vision AI](https://www.tricentis.com/products/automate-continuous-testing-tosca/vision-ai/) ，这样功能、用例以及非功能测试可以保持有效和稳定，无需维护，即使表示层发生变化。这里没有“魔法”——团队仍然需要告诉 Vision AI 往哪里看——但一旦参与进来，这个认知引擎就能让自动化跟上软件变化的步伐，快速反馈与编码和测试工具保持一致。

## 智能带

考虑到现实世界中应用程序的混乱，过度工程化和过度自动化测试只是人类的自然反应。

测试自动化不一定会变得不健康。智能的、战略性的自动化既是最好的预防措施，也是解决软件交付问题的良药。具有平衡方法的适当激励的测试团队可以克服假阳性和假阴性，以及伴随不断扩展的测试自动化套件的数据和警报耗尽。

使用什么开发语言或工具不重要，交付什么基础设施也不重要。也不知道你的应用程序处于哪个开发阶段。

实现一个平衡的软件测试自动化实践，一个使用智能来关注关键挑战的实践，将解放人类的思想来关注创造性的解决方案和批判性思维——导致更少的风险、更多的产出和更多真正的创新。

*在 Tricentis 的[分析师研究图书馆](https://www.tricentis.com/resources/?tri-resource-type=analyst-research#archive-results)阅读这份报告的完整版本，以及来自 Intellyx 和其他分析师的更多信息。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>