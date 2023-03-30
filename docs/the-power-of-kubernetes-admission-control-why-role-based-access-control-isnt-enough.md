# Kubernetes 准入控制的力量:为什么基于角色的访问控制是不够的

> 原文：<https://thenewstack.io/the-power-of-kubernetes-admission-control-why-role-based-access-control-isnt-enough/>

Styra 赞助了这篇文章。

 [蒂姆·辛里奇斯

Tim Hinrichs 是开放政策代理项目的联合创始人，也是 Styra 的首席技术官。在此之前，他共同创立了 OpenStack Congress 项目，并且是 VMware 的一名软件工程师。Tim 花了 18 年的时间为不同的领域开发声明性语言，例如云计算、软件定义的网络、配置管理、web 安全和访问控制。他于 2008 年获得斯坦福大学计算机科学博士学位。](https://www.linkedin.com/in/timhinrichs/) 

今天，如果你在运行 Kubernetes，你就会知道安全性不是“内置的”。为了保护您的集群，您必须配置、添加或构建额外的控制。有些是 Kubernetes 的一部分，如基于角色的访问控制(RBAC)，但其他最佳实践包括为已知良好的容器指定可信存储库，然后在运行时扫描工具中分层。但事实是，在 Kubernetes，你可以“正确”地做所有这些事情，但一切仍可能出错。您的 RBAC 控制可以滴水不漏，您可以只使用可信和签名的映像，您可以扫描您的容器直到时间结束——但是，您的群集仍然可能中断或被破坏。换句话说，即使是干净可信的映像，如果部署不当，也会导致群集配置错误，从而导致返工、停机或(更糟糕的)数据丢失的风险。

然而，Kubernetes 的一个美妙之处在于它提供了一个优雅的控件来防止正确的事情以错误的方式发生。Kubernetes [准入控制](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/)允许开发者直接在他们的集群上实施安全策略，管理和控制可以部署的内容，以限制风险并防止出现许多安全问题。例如，这种策略可能会阻止软件以 root 用户身份运行，防止不必要的 web 入侵，或者确保新部署的容器无法从现有的互联网工作负载中窃取流量——所有潜在的安全问题都是 RBAC 或运行时安全等工具无法解决的。事实上，准入控制不仅强大，而且正在迅速成为保护 Kubernetes 的强制性工具。像 RBAC、可信存储库和运行时这样的策略——虽然它们本身很棒，也很必要——但还远远不够。

## **Kubernetes，就这样吧**

为了理解开发人员为什么需要准入控制，让我们先来看看 RBAC、可信存储库和运行时工具的局限性。这就需要我们看看这些工具的来源:前云时代的开发。在传统的 IT 安全模型中，开发人员评估的核心因素是:

*   身份和网络—谁可以访问什么？
*   已知漏洞—在我们的环境中可以利用哪些已知漏洞？

在 Kubernetes 中，这些概念非常接近于 RBAC 和容器中的代码扫描；在运行之前和运行期间。因此，有安全意识的团队自然会采用这些工具作为保护其集群的第一道防线。但是在完全软件定义的环境中，通过 Kubernetes 允许的粒度控制，传统方法本身会在这些云原生环境中留下不可避免的差距。

拿 **RBAC** 来说吧。RBAC 控制谁或者什么可以把代码放到你的集群中；通常，这些权限是通过 CI/CD 管道自动实现的。理论上，这意味着只有受信任的参与者才能将受信任或批准的映像放入您的集群。但是，由 CI/CD 流程大规模自动化的人为错误会带来大规模的问题。而且，因为 Kubernetes API 是基于意图的，并且需要检查 YAML 的任意一部分，RBAC 实际上在 Kubernetes 中提供的*控制比在其他系统中少得多。*

**可信存储库**，同时，确保图像永远不会来自未知或不可信的来源。它们包含已批准的图像，通常带有已扫描过漏洞的代码。然而，正如我们将看到的，即使是受信任的映像也可能以错误的方式部署。

**运行时**工具，最后，允许您监控您部署的环境。这些工具有助于检测异常活动，监控容器之间以及外部客户端和服务之间的通信，并发现新发现的漏洞。尽管如此，您的运行时环境可以是完全干净的、无漏洞的，但仍然会被破坏。

在实践中，传统工具无法解决天生的问题。例如，即使是干净可信的映像，如果部署不正确，也可能被恶意参与者用来横向移动到其他容器。或者，它可以以不应该的方式与互联网进行简单的对话。这些“干净的形象，糟糕的结果”场景是多方面的:

由正确的管道部署并持续扫描的干净映像可以:

*   允许从互联网意外流出；
*   无意中扩展以获取 CPU 资源并使其他进程崩溃；
*   特权运行，使其成为可妥协的、横向移动的风险；
*   与其名称空间之外的容器“对话”,并放置数据和风险；
*   被命名为“最新”并防止集群的回滚；
*   还有很多很多。

Kubernetes 准入控制提供了阻止这些不想要的场景的方法——您需要做的就是定义规则，允许什么是正确的，阻止什么是不正确的。更具体地说，您可以使用准入控制器来防止错误配置，以免造成问题。这是因为准入控制器是“有目的的瓶颈”,在它们被部署为 Kubernetes 中的对象之前，允许您拦截对 Kube API 的请求并在其上实施安全策略。

## **通过授予 Kubernetes 准入控制的权力**

我们从我们的开发人员社区听到了很多关于 Kubernetes 准入控制的内容，因为我们的开源策略引擎[开放策略代理](https://www.openpolicyagent.org/) (OPA)出乎意料地最受欢迎的用例之一就是作为 Kubernetes 准入控制器。OPA 非常适合准入控制，因为它允许您将企业安全策略(通常存储在 wikis、pdf 或人们的头脑中)转换为策略代码，并通过准入控制 webhook 直接在集群上实施。

不管您选择什么样的控制器(即使只是定制代码)，准入控制都可以用来防止各种各样的 Kubernetes 错误配置。例如，您可以创建策略来:

*   防止容器以 root 身份运行(只能以“非 root”身份运行)；
*   仅部署标记为发布的映像；
*   确保正确的标签/标记；
*   仅暴露某些 IP 和端口；
*   仅装载允许的文件系统。

同样重要的是，你还可以对你的容器周围的配置*实施策略。例如，您可以控制以下因素:*

*   自动复制。
*   阻止公众进入。
*   秘密。
*   最低可靠性(例如，要求运行三个副本)。

然而，在准入控制的世界里，可能性(或限制)的范围是无限的:你可以为运行在 Kubernetes 上的任何软件编写一个策略。关键的一点是，使用 Kubernetes 准入控制，您可以实施护栏，通过在错误配置发生之前阻止它们，基本上保证了安全性、合规性和操作安全性。

准入控制绝不是 Kubernetes 安全性的全部。事实上，这里讨论的工具，像 RBAC 和扫描，都是他们过去常说的“完整早餐的美味部分”。但简单地说，没有准入控制，它们是不够的。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>