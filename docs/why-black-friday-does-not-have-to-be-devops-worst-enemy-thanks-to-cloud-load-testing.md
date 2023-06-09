# Flood Element:一个浏览器级的云负载测试工具

> 原文：<https://thenewstack.io/why-black-friday-does-not-have-to-be-devops-worst-enemy-thanks-to-cloud-load-testing/>

Tricentis 赞助了这篇文章。

 [凯文·邓恩

Kevin Dunne 是 Tricentis Flood 的总经理，确保他的团队继续致力于创新，并为创建可扩展的软件提供工具。由于对软件开发和测试的新兴趋势有浓厚的兴趣，Kevin 致力于与这一领域的思想领袖合作。此前，Kevin 在德勤工作，负责管理大型政府和财富 500 强企业的测试，交付企业资源规划(ERP)实施和定制软件开发。](https://www.linkedin.com/in/kevindunneqa) 

黑色星期五很快就要到了，任何在过去为这场零售业末日做好准备的人都知道它来得很匆忙。随着全球电子商务团队开始为这一至关重要的销售做准备，Flood 团队已准备好利用新的云负载测试功能来减轻您的痛苦，帮助您打造有史以来最棒的黑色星期五。

今年早些时候，[我们宣布了 Flood Element](https://flood.io/blog/tricentis-announces-official-launch-of-flood-element/) 的正式发布，这是一个可以显著减少复杂场景脚本编写时间的工具。在这一年中，我们看到它被用来测试世界上的一切:从简单的网站到最复杂的基于网络的 ERP 系统，测试支持多达 100，000 名用户甚至更多。此外，团队开始运行元素测试以及他们传统的基于协议的负载测试工具。

在本文中，我解释了 Flood Element 如何改进传统的负载测试工具，以简化脚本编写和维护，让您的生活更加轻松。我希望这个令人兴奋的新工具将减少你在这个假期经历的头痛数量，并帮助你释放你的应用程序的全部潜力！

## 现有的负载测试工具如何工作

大多数现有的负载测试工具，如 [LoadRunner](https://www.microfocus.com/en-us/products/loadrunner-load-testing/overview?gclid=EAIaIQobChMI8dCu68qC5AIVQ_7jBx2imQFSEAAYASAAEgKmovD_BwE) 、 [JMeter](http://jmeter.apache.org) 和 [Gatling](http://gatling.io) 通过特定于每种应用类型的各种协议进行交互。协议是允许实体相互通信的一组规则。例如，考虑语言。如果你想用西班牙语与人交流，你必须知道适用于该语言的规则。电子设备也是如此:它们需要建立一个带有相关规则的协议来传输和控制数据流。因此，这些协议级负载测试工具更像是两个系统通信时的模拟交互，而不是模拟真实的用户行为。

## 协议级测试工具在哪些方面有优势？

协议级测试意味着您需要在一个工具中定义最终用户任务，以在网络通信级别上模拟与目标服务器的通信。大多数工具要么编译要么解释指定的例程，并使用不是真正浏览器的小而有效的引擎。结果，模拟用户的成本很低。像 JMeter 或 Gatling 这样支持大多数常用测试协议(HTTP、HTTPS、LDAP、JMS 和 JDBC)的工具通常可以在一个通用负载生成器上实现 1000 个以上的虚拟用户。然而，编写脚本需要深入了解应用程序架构，以创建和维护有代表性的脚本。

## 除了协议级工具，还有哪些选择？

对于那些不喜欢用协议级测试工具进行测试的人来说，一种新的浏览器级负载测试工具正在出现。浏览器级测试允许您像用户一样定义动作，通过与真实浏览器中呈现的网页内的可定位对象进行交互。这些工具的例子包括 [Selenium](http://seleniumhq.org) 或 [Flood Element](https://element.flood.io) (基于谷歌的[木偶师](https://developers.google.com/web/tools/puppeteer/))，它们能够管理[最常见的浏览器](https://en.wikipedia.org/wiki/Usage_share_of_web_browsers) Chrome 或 Firefox。

在这个假期，您想知道哪种类型的负载测试工具适合您吗？当然，这完全取决于你的要求。如果您的需求包括页面呈现时间，那么您肯定会更喜欢浏览器级别的工具来模拟真实的用户。另一方面，如果您需要测试数百万并发用户，协议级工具将为这种大规模模拟提供更合理的成本。

让我们来看看这两类工具的优缺点:

乍一看，浏览器级工具似乎是负载测试的领导者。当然，任何入门级或初学者测试人员都会更喜欢这些工具，因为获得准确结果所需的技能很少。当测试端到端业务场景时，许多更高级的测试人员会倾向于协议级工具。为什么？因为这些 E2E 测试需要你与应用程序的不同层进行交互，包括 API、web、mobile 等等。然而，许多团队现在发现混合协议和浏览器级别的用户可以获得最完整的测试结果。

几年前，当我在世界上最大的银行之一工作时，我们创造了一个类似的浏览器+协议级用户选项，我们称之为“Gomez”Gomez 是一个自动化的浏览器测试，它与协议级负载测试一起推出，以测量更多以用户为中心的响应时间。我们发现，这种混合方法允许我们以低成本生成非常高的负载水平，同时测量比单独的协议级工具更准确的用户响应时间。

## 为什么两个工具比一个好

答案很简单:用最低的成本和努力获得最好的性能测试。单独的协议级测试将是执行成本最低的——但是它将花费最长的时间来创建，并且它可能不会提供真实的结果。浏览器级测试构建起来更快、更准确，但执行起来更昂贵。因此，问题仍然存在:在这种混合模拟中，我们如何确定用浏览器级用户与协议级用户来模拟多少用户？

首先，让我们看看每种类型的用户今天的成本。例如，你可以花 700 美元用 10，000 个带有 Flood Element(木偶师)的真实浏览器测试 1 小时。相比之下，像 JMeter 或 Gatling 这样的协议级工具能够以相同的价格同时运行 20 万个线程。因此，对于 10，000 个用户以下的测试，您可能应该只对浏览器级别的用户进行测试，以省去编写和维护协议级别脚本的麻烦。然而，对于 50，000 到 100，000 或更多的用户，很明显，编写一个额外的协议级脚本与浏览器级测试一起运行可以节省大量的资源。

## 把所有的放在一起

浏览器级和协议级测试工具各有其独特的功能。最终，两者的结合可能是你这个假期的最佳选择。您可以尝试基于浏览器的工具，如 Element 或 Selenium，以及协议级工具，如 JMeter 或 Gatling，来评估您个人对这两种工具的喜好。一旦你决定了混合负载测试的正确工具，你就可以前往[注册免费试用](https://flood.io/sign-up)。在那里，您将获得五个免费节点小时的奖励，可以用来执行混合负载测试，并在黑色星期五大规模下降之前轻松评估您的网站的性能！。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>