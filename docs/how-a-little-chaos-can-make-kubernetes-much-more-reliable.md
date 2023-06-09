# 一点混乱就能让 Kubernetes 变得更可靠

> 原文：<https://thenewstack.io/how-a-little-chaos-can-make-kubernetes-much-more-reliable/>

KubeCon + CloudNativeCon 赞助了这篇文章，期待在阿姆斯特丹举办 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。

 [安德烈·纽曼

Andre 是 Gremlin 的技术作家，他在那里写了关于混沌工程的好处和应用。在加入 Gremlin 之前，他是初创公司和 SaaS 提供商的顾问，撰写了关于 DevOps、observability、SIEM 和微服务的文章。他曾被《DZone》、《StatusCode Weekly》和《下一个城市》刊登。](https://www.linkedin.com/in/andrenewman/) 

中断是 Kubernetes 的生活现实。硬件故障、Pod 中断和资源耗尽甚至会威胁到管理最完善的集群。虽然 Kubernetes 提供了一些恢复功能，但没有一个系统是完美的，尤其是像这样复杂和动态的系统。

你不需要去寻找 Kubernetes 灾难性失败的例子。2019 年，Grafana 在意外抢占了属于生产部署的 pod 后经历了停机。同年，Target 升级了其开发环境的 OpenStack 基础设施，结果却导致了自动配置 4.1 万个新节点的级联故障。就像 Ravelin 发现的那样，当 Kubernetes 在向 Pod 发送 SIGTERM 后继续向它们发送入口流量时，即使像关闭 Pod 这样简单的事情也会导致问题。

使用传统的测试，这样的场景很难被发现。Kubernetes 组件可以以许多不可预测的方式交互，从而导致紧急行为。随着部署规模的增长，这些组件之间可能的交互数量也在增长。站点可靠性工程师(sre)需要一种新的方法来测试他们的集群的弹性，而唯一的方法就是稍微混乱一下。

## 什么是混沌工程？

混沌工程是测试系统故障的一种严格的科学方法。它为 sre 提供了一个框架来验证其系统的可靠性、测试恢复机制并获得对其应用程序和基础架构的重要见解。sre 可以使用混沌工程实践来识别风险和可能的故障点，以免它们成为生产中断。

虽然“混沌”意味着无序和混乱，但混沌工程实际上定义了一种系统化和结构化的方法。目标是帮助团队理解他们的系统如何对导致失败的情况做出反应，并且导致随机的失败除了将这些系统置于风险中之外没有什么作用。混沌实验从小规模开始，用的是不重要的、容易恢复的成分。一旦您对您的系统及其恢复机制有了更好的理解，您就可以扩大您的实验来测试这些机制，并确保它们按预期工作。

使用 Kubernetes，可以很容易地对您的系统在特定场景下的行为做出假设。例如，如果一个节点耗尽了资源，您会希望 Kubernetes 将新的 Pods 调度到另一个节点上。然而，我们不能总是相信这些假设:Kubernetes 可能会驱逐正在运行的 Pod，由于节点污染而拒绝调度 Pod，或者无法将 Pod 连接到服务网格。混沌工程将这些机制推向极限，这样你就可以观察它们的反应，并确定如何使它们更有弹性。

## 哪些混沌实验对 Kubernetes 有用？

混沌实验可以用来模拟导致故障的条件，或者直接制造故障。下面是一些可以考虑在集群上运行的场景。

### **模拟负载以测试自动扩展能力**

您可以做的最有效的实验之一是测试您的集群的自动伸缩能力。这可以确保您的集群快速有效地响应需求变化，而不会导致调度错误或驱逐 pod。

例如，增加部署上的负载应该会触发水平单元自动缩放器，以增加复制集中单元的数量。当集群接近其资源限制时，集群自动缩放器应该会自动配置一个新节点。如果这两种情况都没有发生，请考虑微调您的部署配置和自动缩放阈值。

### 注入延迟以测试响应能力和上游影响

延迟会对其他服务的性能产生级联效应。即使只有 100 毫秒的响应时间延迟也可能阻塞上游 pod，导致超时并导致应用程序故障。延迟测试可以帮助您确定应用程序的性能限制，调整您的负载平衡策略，并优化您的应用程序和网络架构。

### 测试复制和恢复的故障组件

Kubernetes 可以从大多数常见的组件故障中恢复，但是如果不测试这个功能，您就无法知道实际上会发生什么。故意导致失败可能看起来违反直觉，但它提供了关于您的恢复策略是否按预期工作的明确答案。

对于 Kubernetes 不能自动恢复的情况，注入故障是测试灾难恢复计划的一个机会。例如，如果您的非托管集群耗尽了它的资源，或者一个主节点出现故障，或者一名工程师意外删除了一个副本集，会发生什么情况？有了这些经验，当生产中发生严重故障时，您就能更加熟练地应对。

## 开始制造混乱

测试系统弹性的唯一方法是进行实验。虽然在测试和试运行中的试验可以产生有用的见解，但这些环境永远无法真正复制生产。生产失败听起来像是最坏的情况，但这是真正了解系统弹性的唯一方法。也就是说，有一些方法可以安全地进行测试，其中一种方法就是使用 canary 部署。

Canary 部署允许您在现有版本的基础上部署新版本的应用程序。在完全铺开之前，Kubernetes 将一小部分生产流量路由到 canary。这为您提供了一个运行混沌实验的生产环境，而不会将整个应用程序置于风险之中，从而提供了两全其美的效果。如果金丝雀不能从故障中恢复，Kubernetes 可以将流量重定向回稳定部署。一旦您解释了失败并实现了修复，您就可以部署一个更新的金丝雀并重复这个实验。

这种实验、观察和实施修复的循环将使您的系统逐渐变得更有弹性。最终，注入失败应该对您的用户体验没有影响，但是达到这个目标的唯一方法是从小规模实验开始，并随着时间的推移扩大范围。

构建弹性 Kubernetes 集群极具挑战性。生产中没有什么是可以预测的，失败是生活的现实。Chaos Engineering 通过让您安全地测试故障场景、检测弱点、改进您的恢复策略并增强对停机的恢复能力，帮助您走在意外事件的前面。

*要了解更多关于集装箱化基础设施和云原生技术的信息，请考虑参加今年晚些时候在阿姆斯特丹举办的 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。*

管理 KubeCon + CloudNativeCon 的 Cloud Native Computing Foundation 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>