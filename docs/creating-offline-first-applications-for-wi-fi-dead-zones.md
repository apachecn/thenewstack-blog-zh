# 为 Wi-Fi 盲区创建“离线优先”应用

> 原文：<https://thenewstack.io/creating-offline-first-applications-for-wi-fi-dead-zones/>

“在田间”工作或者仅仅是在车间工作，过去意味着你也要靠自己。你所做的决定和你所能给出的建议都是基于你所携带的信息，无论是在你的头脑中，在纸上，或者，在某种数字设备上。

但那是在我们上网之前。现在，一系列移动和嵌入式设备以及无处不在的连接意味着我们应该能够利用云以及存储在其中的所有数据，无论我们在哪里，无论我们的任务是将百事可乐送到偏远的夫妻店，在海上钻探石油，甚至是进行最精密的整形外科手术。

当然，一代开发人员一直乐于使用 REST APIs 和云或远程数据中心来创建应用程序，以便让在现场工作的员工和设备——或者只是在车间走动——能够共享和更新数据，并开展业务。

但是后端连接不是免费的。将大量数据抽到云中、处理这些数据并再次发送出去是有成本的——环境成本、T2 成本、以及最终的性能和可用性成本。

甚至在美国，[的手机覆盖地图仍然显示出很大的差距。](https://fcc.maps.arcgis.com/apps/webappviewer/index.html?id=6c1b2e73d9d749cdb7bc88a0d1bdd25b)在这些空白空间之外，自然的力量仍然可以摧毁信号塔或切断数据中心。让我们不要忘记过度劳累的管理员或畸形的更新可能带来的混乱。

采取边缘优先的方法只能部分解决问题，因为我们正在谈论的是甚至在边缘之外发生的事情。这给开发者带来了一些真正的挑战。

根据市场情报公司 IDC 负责云和边缘基础设施服务的副总裁 Dave McCarthy 的说法，现代开发人员拥有“无限的资源，随时随地按需提供”。

但当涉及到开发将在[物联网(IoT)](https://thenewstack.io/key-concepts/iot-edge/) 或“现场环境”中运行的应用程序时，他们面临着一个冲击，在这些环境中，他们不能保证这些资源始终可用，他告诉新堆栈:“作为物联网开发人员，你学到的第一个词是‘受限’这个词。”"

然后，麦卡锡说，他们必须面对这样的问题，“当这些事情发生时，你如何保持你的应用程序的完整性？这些是你在数据中心或云中通常不会遇到的事情。”

因此，也许我们需要考虑的是“离线优先”的应用程序。但是离线优先实际上是什么样子的呢？

出发点是假设连接性不能总是得到保证，但“旨在确保无论你去哪里，事情都能正常运转”， [Couchbase 的](https://www.couchbase.com/products/capella?utm_content=inline-mention)产品和解决方案营销总监 [Mark Gamble，](https://www.linkedin.com/in/magamble/)告诉新堆栈。“如果你走进地铁，你仍然可以玩那个游戏，或者预约，或者卖那个东西。”

## 为什么离线缓存还不够

这种离线优先的应用构建方法假设数据(部分或全部)在移动或远程设备上保存和处理，而不是在云中或数据中心。

实现这一目标的一个选择是简单地在手机或设备上缓存数据，以便在互联网中断时保持应用程序运行，然后在连接恢复时同步数据。然而，Gamble 说，这让开发者面临更多的问题。本地缓存中存储的数据上限是多少？毕竟，设备断开的时间越长，存储的数据量就越大。洲际航班意味着长时间离线。

宝藏到底藏在哪里？它只是存在于内存中，并且很可能随着电池的耗尽而耗尽吗？还是执着？它在设备上和连接恢复后同步回云中时是否加密？

Gamble 认为:“离线缓存对于偶尔的短暂现象是有好处的。”“当您缓存太多时，问题就开始出现了，您开始超出缓存限制。这就是您开始面临数据丢失风险的地方。数据损坏是不好的，但是“它去哪里了？”更糟糕的是。"

或者，您可以考虑将完整的数据库嵌入到运行在设备本身上的应用程序中，这意味着完全不需要连接就可以查询和存储信息。一种选择是使用开源数据库平台，如 [SQLite、](https://thenewstack.io/the-origin-story-of-sqlite-the-worlds-most-widely-used-database-software/)来存储和处理设备上的数据。

但是“一个典型的应用程序不是一个人和一组数据永远独自工作，”Gamble 说。"最终，这些数据需要在生态系统中为其他用户共享."

这意味着开发人员仍然需要考虑如何将数据同步回云，以及运行该应用程序的其他设备，而 SQLite 没有将 sync 作为标准。这可能会导致开发人员通过定制代码或集成第三方技术来拼凑他们自己的堆栈。但是这可能非常耗时，并且会产生标准化、维护、更新和可重复性方面的问题。

Couchbase 的解决方案结合了自己的轻量级 NoSQL 数据库 Couchbase Lite，可以嵌入到设备上运行的应用程序中，但在有连接的情况下，也会与云中的 Couchbase 五车二同步。当没有连接时，应用程序仍将通过利用本地存储的数据来运行。

Gamble 说，此外，Couchbase 的同步服务名为五车二应用服务，允许应用程序只同步离线时发生变化的数据，而不是同步所有数据，减少了流量，加快了整体同步过程。这显然会更有效率。他补充说，它的同步是双向的。

“还有通过过滤器来引导同步流的概念——在大型零售连锁店中，你不希望将所有数据同步到每个商店；通过只同步每个商店所需的数据，最大限度地提高效率。”

## 现场同步

该平台还为开发人员提供了多种拓扑结构，具体取决于他们的工作环境。有了点对点同步，从云端断开的设备可以在没有中央控制点的情况下彼此同步。因此，用户或设备可以继续在本地共享数据，然后，当连接可用时，同步回云。

结合更广泛的 Couchbase 产品线，开发人员可以构建多层架构。

Couchbase 的一个客户是医疗设备制造商 Arthrex，该公司在手术中使用的一些关节镜设备中嵌入了数据库，以捕捉数据，然后这些数据可以与医院的内部系统同步，并最终传输到云中，外科医生可以访问这些数据以进行术后检查和提出建议。

同样，军事应用可以受益于在现场人员之间快速同步数据的能力，并可能同步到车辆、指挥中心及更高位置。但是，这种应用程序还需要能够在任何给定的层被破坏的情况下继续运行，并且必须让运营商相信，他们能够精确地控制正在传输的数据，并且这些数据是安全的。

拓扑的选择与用户体验交织在一起——最多是在应用程序被人使用的时候。如果商店或酒店员工使用平板电脑来查看库存或处理订单，他们需要快速获取信息，与访问本地存储的数据相比，往返云端可能需要太长时间。但应用程序必须足够快和直观，无论数据来自哪里，它都不会不必要地中断客户交互的流程。

麦卡锡说，最终，离线优先的方法解决了困扰第一波物联网类型应用的许多问题。从获取大量数据的角度来看，这是正确的意图，这些数据可用于调整算法和提供洞察力。但是，在将这些见解反馈给现场用户时，集中数据和处理会导致脱节的工作流和不完整的用户体验。

“战场”不仅仅是“敌对的”或偏远的环境。正如 McCarthy 指出的，零售商和酒店企业依赖多个系统来使店内体验堪比电子商务——从库存管理到推荐再到队列控制。

麦卡锡说:“我认为你肯定需要为离线能力而设计。”“因为，不管出于什么原因，如果商店无法与中央资源沟通，你不会想让所有顾客都回家。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>