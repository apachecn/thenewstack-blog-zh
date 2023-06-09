# 云分布式缓存

> 原文：<https://thenewstack.io/distributed-caching-on-cloud/>

分布式缓存是基于云的应用程序的一个重要方面，无论是对于内部、公共还是混合云环境。它有助于增量扩展，允许缓存增长并纳入数据增长。在本帖中，我们将探讨云上的分布式缓存，以及为什么它对高数据量和高负载的环境有用。这篇文章将涵盖:

*   传统缓存面临的挑战
*   什么是分布式缓存
*   云上分布式缓存的优势
*   推荐的分布式缓存数据库工具
*   在云上部署分布式缓存的方法

## **传统缓存挑战**

 [拉吉夫·斯里瓦斯塔瓦

Rajiv 是云原生现代应用技术博客网站 cloudificationzone.com 的创始人。他是 Wells Fargo 的首席架构师和现代应用专家，在软件开发和建筑设计方面拥有超过 17 年的工作经验。他还是 BPB 出版社出版的《Spring 和 Kubernetes 的云原生微服务》一书的作者。](https://www.linkedin.com/in/rajivkumarsrivastava/?originalSubdomain=in) 

传统的缓存服务器通常部署有限的存储和 CPU 速度。这些缓存基础架构通常位于内部的数据中心。我指的是非分布式缓存服务器。传统的分布式缓存面临诸多挑战，例如:

*   非云节点服务器上难以扩展的缓存存储和 CPU 速度。
*   管理基础架构和未使用的硬件资源的运营成本高。
*   传统的分布式缓存不是容器化的。这就是为什么它不具有可扩展性、弹性和自我管理能力。
*   如果客户端负载高于实际负载，服务器可能会崩溃。
*   在与多个数据中心服务器进行程序同步的过程中，出现陈旧数据的可能性。
*   服务器和各种数据中心之间的数据同步缓慢。

## **什么是分布式缓存**

缓存是一种将数据状态存储在主存储器之外，并将其存储在高速存储器中以提高性能的技术。在微服务环境中，所有应用都部署了多个实例，这些实例跨混合云上的各种服务器/容器。在云上的多集群 Kubernetes 环境中，需要一个单独的缓存源来集中保存数据，并在自己的缓存集群上复制数据。它将作为分布式环境中缓存数据的单一存储点。

## **云上分布式缓存的优势**

*   经常使用的 read REST API 响应的定期缓存确保了更快的 API 读取性能。
*   通过直接从分布式缓存数据库访问缓存数据，减少了数据库网络调用。
*   通过在集群中的各种缓存数据库中维护多个数据副本来实现弹性和容错。
*   通过基于负载或客户端请求自动扩展缓存数据库来实现高可用性。
*   存储会话秘密令牌，如 JSON Web 令牌(ID/JWT ),用于微服务应用容器的身份验证和授权。
*   如果将它用作高负载关键任务应用程序的专用数据库解决方案，则可以更快地读写内存。
*   避免对持久数据库的不必要的往返数据调用。
*   可自动扩展的云基础架构部署。
*   分布式缓存库/解决方案的容器化。
*   从任何同步连接的缓存数据中心一致读取数据。
*   最大限度地减少停机，缓存数据的高可用性。
*   缓存数据服务器之间更快的数据同步。

## **推荐的分布式缓存数据库工具**

以下是业界公认的流行缓存服务器:

*   雷迪斯
*   Memcache
*   GemFire
*   Hazelcast 数据库

**Redis:** 这是最流行的分布式缓存服务之一，它支持不同的数据结构。它是一个开源的内存数据存储，被数百万开发者用作数据库、缓存、流媒体引擎和消息代理。它还有一个企业版。它可以部署在私有、公共和混合云等的容器中。，并在不同的数据中心之间提供一致且更快的数据同步。

**Hazelcast:** Hazelcast 是一个分布式计算和存储平台，针对事件流和传统数据源进行一致的低延迟查询、聚合和有状态计算。它允许您快速构建资源高效的实时应用程序。从小型边缘设备到大型云实例集群，您可以任意规模部署它。Hazelcast 节点集群共享数据存储和计算负载，可以动态扩展和缩减。向群集中添加新节点时，数据会在整个群集中自动重新平衡。当前处于运行状态的计算任务(作业)会对其状态进行快照，并在保证处理的情况下进行扩展。

Memcached: 它是一个开源、高性能、分布式内存对象缓存系统。它本质上是通用的，但旨在通过减轻数据库负载来加速动态 web 应用程序。Memcached 是内存中的键值存储，用于存储来自数据库调用、API 调用或页面呈现结果的小块任意数据(字符串、对象)。Memcached 简单而强大。其简单的设计促进了简单、快速的部署和开发。它解决了许多数据缓存问题，并且该 API 有多种常用语言版本。

GemFire: 它提供分布式内存数据网格缓存，由 Apache Geode 开源提供支持。它按需扩展数据服务以支持高性能。它是一个键值存储，可以快速执行读写操作。它提供高度可用的并行消息队列、连续可用性和事件驱动的体系结构，可在不停机的情况下动态扩展。

它提供多站点复制。随着支持高性能、实时应用的数据量需求增加，it 可以轻松实现线性扩展。应用程序获得对数据访问请求的低延迟响应，并总是返回新数据。它跨分布式节点维护事务完整性，并支持应用程序的高并发性、低延迟数据操作。它还提供节点故障转移和跨数据中心或多数据中心复制，以确保应用程序具有弹性，无论是在本地还是在云中。

## **在混合云上部署分布式缓存的方法**

以下是部署和设置分布式缓存的推荐方法，无论是在公共云还是混合云上:

*   传统虚拟机实例上的开源分布式缓存。
*   Kubernetes 容器上的开源分布式缓存。我建议在 Kubernetes 容器上部署，以获得高可用性、弹性、可伸缩性和更快的性能。
*   虚拟机和容器上的企业商业现成分布式缓存部署。我会推荐企业版，因为他们将提供额外的功能和支持。
*   公有云为 Redis、Hazelcast 和 Memcache 等开源企业工具提供分布式缓存的托管服务。
*   缓存服务器可以部署在多个源上，如内部和公共云、公共服务器或不同可用性区域中的一个公共服务器。

## **结论**

在混合云的分布式部署环境中，分布式缓存现在是分布式微服务应用的实际需求。它解决了一些重要用例中的问题，如在 web 浏览器上禁用 cookies 时维护用户会话、提高 API 查询读取性能、避免相同类型请求的操作成本和数据库命中、管理用于身份验证和授权的秘密令牌等。

分布式缓存自动同步混合云上的数据，无需任何手动操作，并始终提供最新数据。我会推荐行业标准的分布式缓存解决方案 Redis、Hazelcast、Memcached 和 GemFire。我们需要根据用例在云中选择更好的分布式缓存技术。

[*Squadcast*](https://www.squadcast.com/) *是一款专为现场可靠性工程打造的事件管理工具。清除不想要的提醒，接收相关通知，并与流行的 ChatOps 工具集成。使用虚拟事件作战室进行协作，并使用自动化来消除繁重的工作。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>