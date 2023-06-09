# 微服务的十诫

> 原文：<https://thenewstack.io/ten-commandments-microservices/>

微服务标志着分布式计算新时代的开始。

随着容器的出现，部署单元逐渐开始远离 VM 模型。Linux 容器技术，如 LXC、Docker、runC 和 rkt，使得在同一个 VM 中运行多个容器成为可能，允许 [DevOps](https://thenewstack.io/tns-research-devops-factions-software-development-world/) 将每个应用组件或应用模块打包在一个专用容器中。每个容器都有一切——从操作系统到运行时、框架和代码——组件需要作为独立单元运行。

这些容器的组合可以在逻辑上形成一个应用程序。应用程序的焦点变成了编排多个容器以实现期望的输出。

然而，有一种误解，认为将传统的整体应用程序迁移到容器中会自动将整体系统转变为微服务。容器化不会立即将应用程序转变为基于微服务的应用程序。

[cyclone slider id = " ebook-2-赞助商"]

理解这一概念的最佳方式是考虑虚拟化和云。在 IaaS 的最初几天，许多首席信息官声称他们运行的是私有云；但是，实际上，他们只是在实施虚拟化。同样，虽然微服务可能使用容器化，但并不是每个容器化的应用程序都是微服务。

以下是架构师在转向微服务时应该考虑的一些其他方面:

## 1.无状态和有状态服务的清晰分离

由微服务组成的应用程序包含无状态和有状态服务。理解实现有状态服务的约束和限制是很重要的。如果服务依赖于状态，那么它应该被分离到一个易于访问的专用容器中。

微服务的关键优势之一是快速扩展的能力。像其他分布式计算架构一样，微服务在无状态时可以更好地扩展。在几秒钟内，可以跨多个主机启动多个容器。运行服务的每个容器都是自治的，不承认其他服务的存在。这使得精确扩展所需的服务而不是扩展虚拟机成为可能。为了让这种模式无缝工作，服务应该是无状态的。容器是短暂的，因此成为微服务的理想选择。

基于微服务的应用程序可能包含关系数据库管理系统(RDBMS)、NoSQL 数据库和文件系统形式的有状态服务。它们被打包成具有独特属性的容器。通常，有状态服务将持久性卸载到主机，这使得很难将容器从一个主机移植到另一个主机。诸如 Flocker 和 Docker volume plugins 之类的技术通过创建一个独立的不依赖于主机的持久层来解决这个问题。

通常，有状态服务将持久性卸载到主机，或者使用高度可用的云数据存储来提供持久层。这两种方法都引入了复杂性:卸载到主机使得很难将容器从一个主机移植到另一个主机，并且高可用性数据存储以一致性换取可用性，这意味着我们必须在我们的数据模型中设计最终的一致性。

像 [Flocker](https://thenewstack.io/flocker-a-nascent-docker-service-for-making-containers-portable-data-and-all/) 这样的技术，通过创建一个独立的不依赖于主机的持久层来帮助解决主机可移植性问题。新的云数据存储，如 Redis、Cassandra 和 IBM 的 Cloudant，以最小的一致性延迟最大化了可用性。

随着容器技术的发展，解决有状态服务问题将变得更加容易。

## 2.不要共享库或 SDK

微服务的前提是基于自治的细粒度代码单元，这些单元只做一件事。这与“不要重复自己”(DRY)的原则密切相关，该原则指出，每项知识都必须在系统中有一个单一的、明确的、权威的表示。

每个服务都是一个独立的单元，包括操作系统、运行时、框架、第三方库和代码。当一个或多个容器依赖于同一个库时，通过在主机上集中配置它们来共享依赖关系可能很有诱惑力。从长远来看，这种模式带来了复杂性。它不仅带来了主机亲和力，还打破了 CI/CD 管道。升级库或 SDK 可能会导致服务中断。每个服务都应该完全独立于其他服务。

在某些场景中，可以将常用的库和 SDK 移动到可以独立管理的专用服务中，使服务不可变。

## 3.避免宿主亲缘关系

这一点已经在共享库的上下文中简要讨论过了。无法对运行服务的主机做出任何假设。主机包括目录、IP 地址、端口号、操作系统的特定发行版和版本，以及特定文件、库和 SDK 的可用性。

每个服务都可以在集群中满足预定义要求的任何可用主机上启动。这些要求更符合规范，如 CPU 类型、存储类型、区域和可用性区域，而不是软件配置。服务应该独立于部署它们的主机运行。

在有状态服务的情况下，应该考虑专用的持久(数据量)容器。

## 4.专注于服务，心中只有一个任务

每个服务在设计时都必须考虑一个任务。它可以映射到一个函数或一个具有明确边界的模块。这意味着每个容器也可能有一个进程，但并不总是这样。

Docker 鼓励每个容器运行一个后台进程/守护进程的模式。这使得容器从根本上不同于虚拟机。虽然虚拟机可以运行整个堆栈，但容器拥有堆栈的一个子集。例如，在为微服务重构 LAMP web 应用程序时，使用 Apache 的 web 层运行在专用容器中，而 MySQL 则移动到另一个容器中。

微服务是模块化、可组合和细粒度的单元，只做一件事。

## 5.使用轻量级消息协议进行通信

对于微服务如何相互对话，没有硬性规定。他们可以通过任何平台无关的协议使用同步或异步通道。每个服务实现一个简单的请求和响应机制。微服务公开众所周知的 HTTP 端点是很常见的，这些端点可以通过 REST API 调用来调用。

虽然 HTTP 和 REST 是同步通信的首选，但是在微服务之间使用异步通信变得越来越流行。在这方面，许多人认为高级消息队列协议(AMQP)标准是首选协议。使用异步通信模型开发微服务，虽然有时会稍微复杂一点，但在最小化延迟和支持与应用程序的事件驱动交互方面有很大的优势。

目前市场上， [RabbitMQ](http://www.rabbitmq.com/) 和 [Apache Kafka](https://thenewstack.io/confluent-2-0-bringing-kafka-0-9-features-enterprise/) 都是微服务间异步通信常用的消息总线技术。此外，如果消息传递在同一个主机上完成，那么容器可以通过系统调用的方式相互通信，因为它们都共享同一个内核。

## 6.设计一个定义明确的入口点和出口点

在大多数情况下，微服务被视为一个黑盒，对实际实现的可见性较低。入口点和出口点不一致，开发一个组合应用程序将是一场噩梦。

类似于 COM 和 CORBA 中的接口定义，微服务应该公开一个定义良好、文档完备的契约。这将使服务能够无缝地相互对话。

即使不期望微服务返回显式值，发送成功/失败标志也可能很重要。实现单一出口点使得调试和维护代码变得容易。

## 7.实施自我注册和发现机制

微服务的一个关键方面是消费者发现服务。维护一个中央注册表，用于查找所有可用的服务。

每个微服务处理中央服务注册中心内的注册。它们通常在启动时注册，并定期用当前信息更新注册表。当微服务终止时，需要将其从注册表中注销。注册中心在协调微服务方面发挥着关键作用。

[领事](https://www.consul.io/)、 [etcd](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/) 和[阿帕奇动物园管理员](https://zookeeper.apache.org/)就是微服务常用注册表的例子。网飞 [Eureka](https://github.com/Netflix/eureka/wiki/Eureka-at-a-glance) 是另一个流行的注册中心，它向服务公开注册 API，用于注册和注销。

## 8.显式检查规则和约束

在部署期间，微服务可能需要考虑影响性能的特殊要求和约束。例如，内存缓存服务需要与 web API 服务位于同一主机上。数据库微服务可能必须部署在具有固态硬盘(SSD)存储的主机上。数据库的主容器和从容器不能存在于同一主机上。这些约束通常是在服务设计期间确定的。

如果 SysOps 团队没有考虑规则和约束，服务可能需要发出警报或记录适当的消息，警告可能的影响和副作用。在极端条件下，如果在部署时没有遵守强制规则，微服务可能必须关闭。

## 9.首选多语而非单栈

使用微服务的一个优势是能够选择最佳的操作系统、语言、运行时和库。比如聊天微服务可以在 Node.js 中实现，公开 websocketsweb API 服务可以用 Python 和 Django 编写；图像处理服务可以是 Javaweb 前端可以用 Ruby on Rails 实现。

只要每个服务公开一个与其他服务一致的定义良好的接口，就可以使用最佳的技术栈来实现。

随着微软在 Windows 中增加了对本地容器的支持，将 Linux 容器与 Win32 和。同一环境中的. NET 容器。

## 10.维护独立的修订和构建环境

微服务的另一个好处是能够独立编码和维护每个服务。

尽管每个微服务都是大型复合应用程序的一部分，但从开发人员的角度来看，将每个服务视为一个独立的代码单元是很重要的。每个服务都需要在源代码控制系统中单独进行版本控制和维护。这使得在不中断应用程序的情况下部署新版本的服务成为可能。CI/CD 管道应该设计为利用独立的版本控制。

这种机制使得在推出产品版本之前实现每个服务的蓝/绿测试成为可能。

## 发布

虽然系统和应用程序需求在不断发展，但是我们解决这些问题的方法通常是基于旧的模型和模式。如前所述，微服务架构植根于 COM、COBRA、EJB 和 SOA 等模型，但在利用当前技术创建微服务时，仍有一些规则需要遵循。虽然我们在这里列出的十个最佳实践并不全面，但它们是创建、迁移和管理微服务的核心策略。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>