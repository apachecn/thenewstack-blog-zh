# 公钥基础设施需要发展以支持云本地计算

> 原文：<https://thenewstack.io/public-key-infrastructure-needs-to-evolve-to-support-cloud-native-computing/>

云这个，云那个——这已经成了陈词滥调。尽管如此，对于云安全的某些方面，问题仍在解决中——公钥基础设施(PKI)就是其中之一。

手头的一个问题是 PKI 如何适应基于微服务的架构和云环境？

如果没有公钥加密和 PKI，我们将无法去我们最喜欢的网上商店购买我们的下一代产品。然而，PKI 是在 70 年代中期建立的，并在 90 年代末基本完成了它的发展。问题是——它现在有多重要？

## PKI 的基础知识

 [本·赫希伯格

Ben Hirschberg 是 R&D 的副总裁和 Cyber Armor 的联合创始人，Cyber Armor 使 DevOps 能够跨环境无缝部署零信任工作负载和数据保护，消除了开发和安全之间的摩擦](https://www.armosec.io/) 

PKI 的一般思想是每个计算实体都有自己的加密身份，由两个元素组成:

首先，一个私钥——假设只对给定的计算实体可用。

第二个是公共证书，它包含一个公钥以及关于实体的其他信息:名称、到期数据等。该证书由受信任的证书颁发机构进行数字签名；因此，我们可以证明名称和信息确实与正确的实体相关联。这就像你的驾照被国家认可一样。

这个私钥/公钥对是 PKI 认证协议的核心。当一个实体需要被认证时，会发生两件事:

1.  验证者可以通过对照授权的认证机构检查公共证书的签名来验证公共证书。
2.  验证者得到实体实际拥有私钥的证据。该协议确保这可以在不通过网络发送实际私钥的情况下完成。

在过去的 20 年里，PKI 的加密模式没有太大的变化。像 RSA 和哈希函数这样的算法已经有了可靠的记录，并且仍然在提供坚实的基础设施——即使我们使用更大的密钥大小和更复杂的哈希函数。

体系结构的最新变化，如微服务的引入，给传统的 PKI 范式带来了新的挑战。

## PKI 挑战

PKI 本身的主要挑战是密钥和证书的管理和保护。为 PKI 准备实体时，需要执行以下步骤:

*   生成私钥-公钥对
*   创建证书签名请求
*   请求签名机构签署证书

完成这些步骤后，给定的机器可以开始使用 PKI 标识。鉴于 SSL/TLS 身份信任基于 PKI (X.509)，这是计算机网络上最安全协议的先决条件。

在微服务中，我们可能有数百个实体需要认证，安全有效地分发这对密钥可能会成为一个挑战。

最重要的是，对于使用 PKI 的计算实体来说，它不仅需要持有私钥，还需要能够保护它。这个私钥必须保密；如果它被盗，攻击者可以冒充该实体。

PKI 有一个名为证书撤销的特性，理论上它可以通知其他 PKI 用户身份泄露。但是，它没有得到很好的实施和维护，并且无法管理全球范围内成千上万的微服务

## 基础设施的云化

让我们看看今天的基础设施。随着云的出现，服务器作为“硬件”组件已经开始消失。现在，服务器只是运行云应用、数据库节点或[微服务](https://thenewstack.io/category/microservices/)的裸机。

容器技术及其管理系统，加上对计算基础设施的简化访问，带来了一个新时代。我们创建了更小的、独立的、可以扩展的服务，而不是单一的服务器。一台物理机器可以运行数十项服务，而一个服务集群可以分布在数十台甚至数百台机器上。我们跑步的地方和物理基础设施现在是商品，就像为它们提供动力的电力一样。

## 在新环境中使用旧的安全性

我们仍然希望用 TLS 连接我们的服务和节点。虽然一些 TLS 问题确实不时出现，像降级攻击，但一般来说，它被认为是一个安全的渠道。

现在，考虑对发布 REST API 的服务“A”的保护。TLS 要求没有改变——服务“A”需要有私钥，或者至少能够访问私钥操作。它需要一个由证书颁发机构签名的证书和一个将证书绑定到网络标识符的服务器名称。

如果您直接使用私钥，最简单的方法是将私钥和证书直接添加到服务“a”的容器映像中。这不是最明智的想法—您只是将 PKI 身份的根秘密添加到映像中，使其与私钥本身一样敏感。

现在，您需要对一个完整的容器图像保密，而不是保护一个大约 1Kb 的密钥，这个图像很容易超过 100Mb。这也意味着给定的容器映像被绑定到一个且仅一个加密身份；这可能有利于内部分发，但不利于当前实践中的多部署映像。

## 弱外部安装方法

另一种解决方案是从外部卷将私钥安装到容器中。因此，部署实体需要创建私钥和证书，并将其添加到运行该映像的每个容器主机中。问题是它打破了图像自包含的规则；这也意味着私钥与其他可能不相关的 docker 映像部署在同一台机器上。

要向您的 Kubernetes 集群添加一个新的 worker 节点，您需要提前安装所有的私钥和证书；否则 Kubernetes 将无法生成新的容器实例。这对于容器即服务用例来说是站不住脚的。

在这种情况下，另一个实体持有您的服务器的加密身份；整个防御基于文件系统权限标志，这意味着保护非常薄弱。

## 环境变量也不好

私钥和证书可以注入到环境变量中。尽管从部署的角度来看，它有特定的优势——它是自包含的，并且映像保持通用——但它有自己的安全问题。

环境变量是在脚本、YAML 文件和其他编排工具中定义的，因此底层容器技术实现本身可能存在问题。一个环境变量在链接的容器之间共享。其次，其他进程以及同一容器中的所有进程都可以从主机上查看环境变量，这使得保护变得非常薄弱。

## 软件安全的昂贵硬件解决方案

“原样”密钥管理系统(KMS)并没有为密钥保护增加多少内容。它们确实提供了一种在容器映像之外存储键的方法，通过 API 在应用程序级别将它们提供给正在运行的容器。但是，请求需要某种令牌——凭证或 API 密钥。因此，要检索一个秘密，您需要在容器中保存另一个秘密，这就产生了永久的安全风险。

在云环境中，就像在本地一样，硬件安全模块(HSM)——包含高级硬件保护的专用计算机——可以保存私钥。它不是公开密钥，而是使用秘密密钥提供加密操作。理论上，攻击者无法访问密钥本身；该密钥可以访问使用它的操作。但是，HSM 也使用安全令牌对加密操作请求进行身份验证，所以同样需要在容器映像中嵌入一些秘密。此外，HSM 不容易扩展，而且价格昂贵，您需要部署足够的 HSM 设备来服务您的应用程序。

## 用微服务身份解决安全问题

在此解决方案中，系统用于将软件身份添加到解决方案库中，以加密方式验证它所保护的软件，并围绕它创建软件身份。独立的密钥分发系统使软件能够自由扩展，同时消除了任何软件的 DevOps 等式中令人头痛的单个密钥分发和保护问题。

每个软件实例都获得一个唯一且安全的加密身份，而不管它在哪里以及如何运行。该身份由运行时保护机制验证，并向后端证明，然后后端将密码材料分配给软件进程。加密材料绝不会传递给不可信的软件，而且软件过程会不断受到监视以防攻击。

它可以跨混合环境和云环境提供更强大的保护，而无需额外的硬件投资。

随着云原生技术的发展，安全基础架构需要跟上步伐，以确保数据和工作负载始终受到保护。PKI 再也不能解决这个问题了。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>