# 容器映像注册表安全性最佳实践

> 原文：<https://thenewstack.io/container-image-registry-security-best-practices/>

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助了这篇帖子。

如果您的组织正在从单一应用程序转移到基于容器的[微服务](https://www.twistlock.com/2017/03/20/microsecurity-for-microservices-2/)，不用说，有足够多的主要问题让您和您的团队忙碌起来——从整体架构到部署细节。

在这个过程中容易被忽略的一个细节是[集装箱登记处](https://www.twistlock.com/2017/02/21/integral-container-security/)的安全。虽然您可能会花费一些精力来保护您的容器，但是您是否考虑过如何保证注册中心的安全呢？如果没有，这篇文章是给你的。请继续阅读容器注册安全最佳实践。

## 什么是容器注册中心？

您不存储用于部署的容器——您存储容器映像，并根据需要从这些映像生成容器。每个容器都是图像的一个实例。单个容器可能来来去去，并且在某些情况下可能会发生变化，但是容器映像就像一个保存在存储中的模板，不会发生变化。

存储容器图像的储存库通常被称为注册中心。有几个公共注册表，其中一些包含非常大量的图像。像其他主要的开放源代码库一样，这些注册中心是不可或缺的资源，以现成的容器映像的形式提供对重要软件包、实用程序和服务的访问。

## 扫描和审核容器注册表

如果容器映像包含漏洞，则使用该映像生成的每个容器也将包含该漏洞。虽然容器映像被设计成[不可变的](https://www.twistlock.com/2017/02/01/intent-based-security/)，但是容器注册中心不是。开发人员可能会频繁上传新容器和现有容器的新版本。每一个变化都有可能带来新的漏洞，而且往往是由于使用过时的软件包而产生的旧漏洞。

### **扫描…**

您需要安排定期扫描您的存储库，以便检测此类漏洞。大多数维护主要公共注册表的组织(如 Docker)都提供自己的扫描服务。对于私有注册中心，安全提供者如 [Twistlock](https://www.twistlock.com/) 提供了扩展的扫描能力，具有扫描结果警报等关键功能，并自动阻止不可信的图像被使用。

### **…还有更多**

除了扫描漏洞之外，您还可以(也应该)审核图像的年龄以及过期的包。您可以将较旧的映像和具有较旧依赖关系的映像标记为过时，并安排它们进行更新。采用定期更新和刷新旧映像的策略可以更容易地消除可能未被检测到的漏洞。

### **精心打造**

容器不是黑盒。容器内部发生的事情会对安全性产生影响，而您如何让它发生会产生更大的影响。

## 从源代码构建

简单地从可信的公共注册中心克隆带有标准开源包的容器，并把它们放在私有注册中心，或者使用公共注册中心的映像，这可能很有诱惑力。然而，在您的私有注册表中从源代码构建映像是一个更好的实践，因为这使您能够更好地控制映像和影响其安全性的条件。当您控制构建过程时，漏洞或利用就很难不被注意地溜进容器。

## 限制资源

 [本·伯恩斯坦

本·伯恩斯坦(Ben Bernstein)于 2015 年联合创立了 Twistlock，并担任其首席执行官。Ben 在企业安全和操作系统领域拥有超过 14 年的经验。他是微软的资深员工，在软件开发和产品管理方面都有丰富的经验。本是以色列情报局的老兵。他以优异成绩获得了以色列 Technion 大学的计算机科学文学学士学位，并获得了以色列跨学科中心的 MBA 优秀奖学金。](https://www.paloaltonetworks.com/prisma/cloud) 

容器被设计成在非常有限的域内操作；它提供由一个任务或一组任务组成的服务，它需要的唯一资源是执行这些任务、与主机操作系统交互以及与其他容器通信所需的资源。如果容器不需要包含给定的资源，它就不应该包含该资源。

这不仅仅是让你的集装箱保持轻便的问题。每个资源、每个软件包——就此而言，您包含的每一行代码——都是潜在的攻击面。以裸机或虚拟机为目标的攻击者很可能会认为有一组标准的系统资源可用，因为目标系统通常至少包含完整操作系统的基本版本。

容器不需要(也不应该)是这种情况。理想情况下，任何攻击都应该由于被访问的容器中缺少必要的资源而失败，而不是从一个容器跳到下一个容器并在所有容器中找到相同的目标资源集。

## 限制用户权限

容器内的用户权限应始终限于执行所需任务所必需的权限。不应给入侵者任何提升权限或突破容器的机会。这意味着，除了其他事情之外，定期检查您的容器中包含的任何包的默认用户权限，以及您的注册表中包含的任何开源容器映像。

这也意味着当你为你的微服务设计容器时，你应该密切跟踪它们实际需要的特权。例如，当您访问数据库时，只有那些读写数据库的容器才需要那些任务所需的特权。在检索数据后使用数据的容器不应该具有对数据库的读/写访问权限。

不用说，您永远不应该允许用户在容器内进行 root 访问。如果您需要允许 root 访问来执行任务，请返回并查看您的设计。如果可能的话，在没有 root 访问权限的情况下重新设计它。

## 班长

容器就像任何其他种类的软件一样——为了完全安全，您需要在它们运行时对它们进行监控。Twistlock 提供的容器安全服务使这一点变得很容易。一个好的监控服务应该能够自动检测各种异常行为模式，这些异常行为模式可以指示受损的容器或入侵企图，并在检测到此类异常时发出警报。

当然，任何推荐的最佳实践列表都必须是通用的。没有一个这样的列表是万无一失的，和往常一样，您将需要根据您的软件的需求和它运行的环境来调整这些建议。其中一些可能与您的运营极其相关，而其他一些可能根本不适用。但是，通过使用这个列表作为起点，您很有可能避免容器部署中最常见的安全隐患。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>