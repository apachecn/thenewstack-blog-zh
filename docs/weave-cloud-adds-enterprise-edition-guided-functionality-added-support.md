# Weave Cloud 的新企业版具有引导功能和额外支持

> 原文：<https://thenewstack.io/weave-cloud-adds-enterprise-edition-guided-functionality-added-support/>

就在 Docker Inc .[为其集装箱化套件推出支持丰富的企业版](https://thenewstack.io/docker-launches-enterprise-edition-refines-market-strategy/) (EE)几周后， [WeaveWorks](https://www.weave.works/) 为本周在柏林举行的 Kubecon Kubernetes 用户大会推出了其 [Weave Cloud](https://cloud.weave.works/) 微服务部署平台的企业版。

正如 WeaveWorks 的首席执行官 Alexis Richardson 告诉我们的，该公司的目标是提供一种更具指导性的方法来部署新类别的工作负载。

“我们发现，许多团队不想要 100%的日志功能和 100%的监控功能，”Richardson 说，他指的是 Weave 云平台的两个主要组件。“他们想要的是百分之八十，或者说*广度*，而不是*深度*。

“所以我们要做的是把整个事情颠倒过来。我们将坚持己见并围绕运营能力进行协调，为您提供足够的*云原生监控和一些针对不同情况的真正有用的现成解决方案，但让您自己决定在什么应用平台上运行……事实上，开发人员可能会先选择应用平台，然后再运行 Weave，反之亦然。”*

通常情况下，当一个供应商在一个生态系统中发挥作用时，它会向客户提供一系列类似应用商店的选择，同时给他一个虚拟市场的外观。本月早些时候，我们看到 Mesosphere 通过其数据中心操作系统(DC/OS)做出了这样的举动。Richardson 坚持认为，Weave Cloud 不会出现这种情况。虽然该平台将继续支持客户对容器协调器的选择( [Kubernetes](/category/kubernetes/) 、Docker Swarm、[亚马逊弹性容器服务](https://aws.amazon.com/ecs/)、Apache Mesos 或 Mesosphere DC/OS)，但 WeaveWorks 不会假装是苹果或谷歌，并像一个支持或被支持的产品一样运行，就像一个可安装的应用程序。

“我们没有严格基于功能的 EE，”他解释道。“企业客户想要的是更多的手握，更确定的结果。他们不一定想有很多新功能，因为实际上，他们对我们标准版中的功能非常满意，”理查森说。

他承认，情况可能并不总是如此。然而，他补充说，就目前而言，WeaveWorks 吹捧的企业版的进步实际上也添加到了标准添加中，只是增加了支持和一些其他便利，如长期数据存储的扩展条款。

这些扩展术语的一个很好的理由是，EE 推出的企业版和标准版都增加了一个功能，这听起来应该会吸引 it 管理员和 DevOps 专业人员:*历史审计日志记录*。理查森解释说，这是一种扩展 Weave Cloud 已经在做的记录类型的方式，使其更具功能性。

“目前，我们正在记录我们所能记录的一切，”他告诉我们，“这是非常昂贵的，也是在企业层更慷慨地分配数据存储的另一个原因……这种审计日志记录将是未来基于云的应用程序的基础，并且对于合规性也是必不可少的。因此，如果你是企业用户，你需要更多的数据存储。然而，如果你是一个小的开发公司，你可能会想，“坦白地说，如果它发生在一个多月前，我不在乎。”"

Richardson 继续说，有了足够的基于云的数据存储，Weave Cloud 应该能够捕获每个应用程序的完整性能历史，因为它运行在客户选择的平台上。

我指出，一个平台提供商可能很难推出像“审计日志”这样的功能，在公告列表的旁边打一个星号，并期望客户立即知道提供商在说什么。然而，如果提供商提高存储限制，然后展示新空间的一些有趣用途，例如审计日志记录，企业客户可能更有可能注册。

Alexis Richardson 告诉 New Stack 说:“审计的主要好处总是验证你的系统相对于过去是否正确。“如果使用正确的工具和起点，建立一个正确的系统是很容易的。难的是保持这种状态。”

理查森回答说，这里有两种可能的方法。配置管理方法将建立正确性模型，然后在活动配置偏离模型时发出警报。另一种方法 Richardson 向他的 EE 用户建议——是收集关于应用程序当前状态和性能的大量细节，并将该状态与以前的状态进行比较。

这是一种脚本化程度更低、更面向数据库的应用管理方法。虽然它并不适合所有人(Richardson 承认，在内部，WeaveWorks 依赖于配置管理)，但对于企业来说，这种方法的步骤可能很少。这就是我们在企业中使用容器化的情况，因为它的架构现在已经基本定型:找到更多的方法来进入中型数据中心。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>