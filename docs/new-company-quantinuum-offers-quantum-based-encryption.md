# 新公司 Quantinuum 提供基于量子的加密技术

> 原文：<https://thenewstack.io/new-company-quantinuum-offers-quantum-based-encryption/>

由霍尼韦尔的量子计算部门和初创公司[剑桥量子](https://thenewstack.io/lambeq-a-toolkit-for-quantum-natural-language-processing/)合并而成的新公司 quantinum，推出了一项服务来解决加密密钥这一棘手的网络安全问题。

这家新公司最近推出了量子起源(Quantum Origin)，这是一项[商业服务](https://thenewstack.io/quantum-computings-challenging-liftoff-to-commercialization/)，它利用剑桥量子公司和霍尼韦尔一岁大的 H1 量子计算机开发的软件来生成加密密钥的数字，这些数字的随机性超过了传统方法，只能由量子系统创建。

“量子起源将代表世界上第一个真正利用量子计算机的输出来做经典计算机根本无法做的事情的商业产品，”剑桥量子公司(现在是 Quantinuum 的全资子公司)的量子网络安全负责人[邓肯·琼斯](https://www.linkedin.com/in/duncanjones/)告诉新堆栈。“Quantum Origin 所做的是，它是一个基于云的平台，可以生成我们见过的最强的密钥。”

## **不是你生成密钥的老方法**

琼斯说，Quantinuum 提供的东西不同于经典计算机使用的随机数生成器(RNG ),甚至不同于过去使用的量子 RNG。

“因为我们使用的是量子计算机，我们受益于量子力学的属性，如纠缠，我们能够产生随机性，我们可以证明这是……尽可能接近完美，”他说。“这与之前所有的尝试都有很大的不同，主要是因为其他产生随机性的方法无法达到我们所拥有的质量。”

加密密钥生成的随机性对于确保[加密数据](https://thenewstack.io/enable-end-to-end-encryption-between-nextcloud-and-your-desktop-client/)免受网络威胁至关重要。当前的方法在长串数字中提供了一定程度的随机性，但不完善的硬件和影响量子电路的不断变化的操作条件等缺点使得不良行为者和政府有可能检测到模式，并利用算法破解密钥和解密数据。

琼斯说，目前的 RNG 方法也无法准确验证所产生数字的随机性，这表明这些数字并不像预测的那样随机。

## **“现在破解，以后解密”的威胁**

另一个威胁即将出现:网络罪犯和民族国家最终能够利用量子计算技术在未来更容易地破解加密代码。这导致不良行为者现在窃取数据，并计划在以后可能时解密，这被称为“现在攻击，以后解密”攻击。

企业越来越担心新兴技术带来的威胁。根据剑桥量子公司(Cambridge Quantum)本周发布的一份报告，今年早些时候对 600 多名网络安全专业人士进行的调查发现，70%的受访者预计此类技术将损害现有的加密方法，60%的人说这最早将在 2023 年发生。此外，75%的人表示量子攻击将击败当前的加密技术。

只有 21%的被调查者认为已经为这种新的加密攻击做好了准备，另外 38%的人表示他们的组织将在两年内做好准备。20%的人说他们的组织正在拨款解决这个问题。

## **现在和未来的数据保护**

琼斯说，Quantinuum 的量子 RNG 服务将帮助组织保护现在的数据，并随着更新的技术出现。

“我们不仅将带来世界上第一个量子计算能力产品，而且我们还将最终解决密码学中的一个长期问题，即如何生成我们需要的完全不可预测的随机性，以便生成我们可以信任的加密密钥？”他说。

这项服务将由霍尼韦尔的 10 量子比特 H1 量子计算机提供动力，该计算机使用一种捕获离子的方式来产生量子比特。剑桥量子将直接或通过与该公司合作的网络安全供应商向客户提供量子起源平台生成的加密密钥。他们将根据每月生成的密钥数量按密钥收费。

## **从一个 API 调用开始**

希望利用量子 RNG 服务的组织可以进行 API 调用，Quantum Origin 将使用传输密钥生成并加密密钥。加密密钥将被安全地发送给组织。然后，Quantum Origin 将测试和验证每个密钥的随机性。

密钥以一种可以在运行传统网络安全解决方案的传统计算机上运行的格式交付。该服务支持 RSA 和 AES 等传统加密标准使用的算法，以及由国家标准与技术研究所(NIST)标准化的后量子密码算法。

Cambridge Quantum 最初向金融服务公司和网络安全供应商提供 Quantum Origin，并计划扩展到能源、制造、国防、政府和电信等其他高优先级行业。正在设计第一个商业空间站的 Axiom Space 使用国际空间站和地球之间的后量子加密通信的 Quantum Origin 进行了一次测试，发送了一条消息，内容是“你好，量子世界”。

富士通还将 Quantum Origin 集成到其软件定义的广域网(SD-WAN)技术中，使用量子增强密钥和传统算法。

## **网络安全是一个唾手可得的果实**

琼斯表示，剑桥量子公司将网络安全作为其第一款产品的目标，因为这是该公司可以用量子计算机解决的第一个问题，而经典系统无法解决这个问题。另一个原因是当前网络攻击越来越复杂，正如那些涉及殖民管道和[网络安全管理软件产品](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)的攻击所示。

“坦率地说，我们看到了一个有点害怕的市场，它真的希望确保自己了解网络安全堆栈中的每一层，并加强每一层，”他说。“到目前为止，密码术一直是一个相当不透明的、只信任我们的层。你买了一些设备，希望它能永远工作。我们现在可以说，我们可以为您提供可证明安全的密钥，抵御今天和明天的威胁。”

## **量子诞生**

霍尼韦尔和剑桥量子公司(Cambridge Quantum)在 6 月份宣布了将霍尼韦尔的量子业务与这家初创公司合并的计划，此举旨在整合领先的量子硬件和软件组合，并在快速增长的量子计算领域创建一家 400 人的公司。

从霍尼韦尔(Honeywell)来到该公司的 Quantinuum 总裁兼首席运营官托尼·乌特利(Tony Uttley)告诉新的 Stack，新公司的规模和产品范围将成为整个 quantum 生态系统的“重心”，并计划在硬件和软件产品上与产品无关，与该领域的其他供应商合作。剑桥量子公司在合并前是霍尼韦尔 H-1 系统的用户，也是 IBM 的[合作伙伴——量子计算领域的另一个重要人物 Quantinuum 将继续与 IBM 保持合作关系。](https://thenewstack.io/ibm-quera-ramp-up-qubit-count-for-quantum-computing/)

“我们谈论自己是这家综合公司的原因之一是，我们今天确实有量子产品，”Uttley 说。“这些量子产品位于专门为这些产品设计的软件平台中。【有】中间件层，叫做 TKET。有一个开源中间件，它既是一个优化器，而且非常重要的是，它使世界各地的开发人员正在使用或开发的算法可移植，因此他们可以使用多个不同的量子计算机作为 TKET 平台的后端。我们还在构建一个操作系统，一个真正的量子操作系统，这就是我们的 H 系列硬件的用武之地。”

霍尼韦尔拥有 Quantinuum 约 40%的股份，但他表示，新公司正在与其他潜在的战略和金融投资者进行谈判。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>