# 您应该为您的开源数据库使用哪种 AWS 技术？

> 原文：<https://thenewstack.io/which-aws-technology-should-you-use-for-your-open-source-database/>

[](http://www.percona.com)

[Max Bubenick](http://www.percona.com)

[Max Bubenick 是 Percona 的托管服务平台负责人。他从事 MySQL 已经超过 10 年了。在 2013 年加入 Percona 之前，他是当时最大的社交游戏公司之一的首席数据库管理员。他还维护我的翻斗车。](http://www.percona.com)

[](http://www.percona.com)[](http://www.percona.com)

许多企业正在转向云，以此作为控制成本、降低复杂性、实现新业务目标以及更快将产品和服务推向市场的一种方式。平台即服务(PaaS)、基础设施即服务(IaaS)和软件即服务(SaaS)等新的基础设施模式不仅变得越来越普遍，而且事实上正在成为正常的运营方式。

迁移到云使得企业可以更少地关注运营管理，而更多地关注产品开发和生产。

许多企业正在采用的云服务之一是数据库即服务(DBaaS)，或者将数据库的基础架构、管理和维护卸载给云提供商。

亚马逊网络服务(AWS)是最知名、最值得信赖的云提供商之一。AWS 有许多云服务选项，其中三个最相关的是 Amazon RDS for MySQL(或其他开源数据库)、Amazon Aurora 和 Amazon EC2(或者，实际上，是一种自主安排)。

在本文中，我们将研究这些选项，并提出对于各种架构和用例场景，您选择其中一个而不是另一个的原因。

## Amazon RDS for MySQL(或其他开源 SQL 数据库)

 [泰特·麦克丹尼尔

Tate McDaniel 是 Percona 托管服务部门的高级 MySQL DBA，该公司提供企业级 MySQL、MariaDB 和 MongoDB、PostgreSQL 以及其他开源数据库解决方案和服务。他拥有超过 10 年的 MySQL 和运营管理经验。他最喜欢的是应用程序查询调优。](http://www.percona.com) 

亚马逊关系数据库服务(Amazon RDS)是一种 web 服务，旨在建立、管理和扩展云中的关系数据库。 [Amazon RDS](https://aws.amazon.com/rds/) 负责一些与 MySQL 数据库相关的日常管理和维护任务。这包括:

*   备份
*   软件补丁
*   自动故障检测
*   恢复

通过购买托管服务器的硬件，您购买的是固定数量的 CPU、内存、存储和 IOPS。这些最终会变得过时(或者随着时间的推移而分解)。借助亚马逊 RDS 云产品，资源可以独立扩展(扩大或缩小)。

Amazon RDS 不提供对特定数据库实例的访问，并且限制对一些需要高级(超级)权限的系统过程和表的访问。您可以手动创建备份快照或自动执行备份过程，以便在紧急情况下用于恢复数据库。

有了亚马逊 RDS，可以使用 MySQL 之外的其他开源数据库软件(MariaDB、PostgreSQL)以及商业软件(Oracle、Microsoft SQL Server)。你也可以使用亚马逊的兼容 MySQL 的 Amazon Aurora DB 引擎(下面会详细讨论)。

除了数据库包中的安全性，您还可以通过使用 AWS 身份和访问管理(IAM)来定义用户和权限，从而帮助控制谁可以访问您的 Amazon RDS 数据库。您还可以通过将数据库放在虚拟私有云来帮助保护数据库。

### 使用 Amazon RDS for MySQL 扩展读取

许多企业面临的一个更大的问题是扩展数据库读取以匹配应用程序的使用(而不影响性能)。随着应用程序使用的增加，对数据库的调用越来越多，如果数据库没有正确配置来处理增加的负载，它会降低应用程序的响应时间。这可能会影响用户体验。

对于 Amazon RDS，扩展通过以下方式解决:

*   提供多达五个读取副本
*   两层(每层有 30 个读取副本)
*   正常异步复制

然而，Amazon RDS 不允许将读取和写入分成单独的实例，也不允许提供流量负载平衡。Percona 对如何使用 ProxySQL 或 HAProxy 实现这一点有一些建议——在这里阅读:[如何使用 AWS Aurora 实现 proxy SQL](https://www.percona.com/blog/2018/04/03/how-to-implement-proxysql-with-aws-aurora/)。

### 亚马逊 RDS 备份

拥有可靠的备份策略是持续业务成功的关键。在 Amazon RDS for MySQL 中，您可以构建安全高效的备份和恢复解决方案，利用 AWS 云的规模。亚马逊简单存储服务(亚马逊 S3)、亚马逊 S3 标准-不频繁访问(S3 标准-IA)和亚马逊冰川通过自动化策略和数据恢复来促进备份，并减少调配和维护内部基础架构的需求。

### 亚马逊 RDS 高可用性

高可用性对于对您的业务成功至关重要的应用程序至关重要。这些应用程序必须始终可供客户使用和访问。高可用性通常以“9”来衡量，它代表数据库运行的总时间的百分比:99%是两个 9，99.9%是三个 9，99.99%是四个 9，等等。目标是尽可能接近 100%的正常运行时间(或者考虑到应用程序的功能是必要的；请参见 [MySQL 高可用性内部部署:地理上分布的场景](https://www.percona.com/blog/2018/11/15/mysql-high-availability-on-premises-a-geographically-distributed-scenario/)了解有关“9s”正常运行时间的更多信息。

您的数据库也可以用高可用性架构来设置。这包括设置一个主数据库实例和一个同步辅助实例，当主数据库实例出现故障时，辅助实例将接管工作。

Amazon RDS 使用常见的故障转移技术以及可用性区域(AZ)的概念来确保数据库正常运行。可用性区域是位于不同地理位置的数据中心，当一个或多个数据中心出现故障(由于自然灾害、停电等)时，这些数据中心可以接管。).多 AZ 架构确保数据库在某个地方启动并运行。

但是，副本和 az 之间的故障切换可能需要一分钟或更长时间。

### 亚马逊 RDS 安全性

当您迁移到云时，数据的安全性变得更加重要。AWS 数据中心和网络架构旨在满足对安全性高度敏感的组织的要求。您可以获得一些工具和服务，使您能够获得比许多内部环境更好的安全状况。AWS 实例可以按需扩展和缩减，通过利用现收现付定价，您无需任何前期硬件投资即可获得所需的安全环境。

### 亚马逊 RDS 性能

Amazon RDS 的性能可与独立的 MySQL 实例相媲美。主要的区别在于，在 Amazon RDS 中，如果您遇到性能限制，您将受限于 Amazon RDS 允许您在它们的实例中配置什么来调优性能。您唯一的其他选择是扩展实例的数量。

### 亚马逊 RDS 的优势、局限性和使用案例

迁移到 Amazon RDS 可以为在云中部署数据库提供许多明显的好处。它可以根据需要轻松打开、关闭和扩展实例。它消除了数据库管理员日常的大量手动数据库任务，包括设置、管理、维护(包括修补和升级)和资源调配。

然而，也有一些限制。您没有配置单个 MySQL 数据库实例的超级权限，也不允许配置操作系统和其他平台配置参数来满足特定的应用程序需求(事实上，有超过 70 个参数是您无法更改的)。

您也不能直接访问实例日志来进行监控和记账。就 DBA 团队的开销而言，您不负责补丁和版本升级可能是一个好处，但这也意味着您不得不按照 AWS 的计划进行这种类型的维护。

然而，有充分的理由和许多具体的使用案例表明选择 Amazon RDS 是一个明智的选择。一般来说，如果您的应用程序不会因为一些数据库复制延迟而受到影响，故障转移时间超过一分钟，或者丢失最多五分钟的事务是可以接受的，那么 Amazon RDS 不会立即遇到重大障碍。

使用 Amazon RDS 的其他合格因素:

*   您有一个“简单”的工作负载，并且它将保持简单
*   当您需要卸载“操作”时
*   您不需要使用具有超级权限要求的工具
*   您需要针对特定事件(如黑色星期五、友谊日等)快速调整阅读量。)

## 亚马逊极光

Amazon Aurora 是一个关系数据库引擎，在适当的条件下，它可以提供超过标准 MySQL 和 PostgreSQL 的高吞吐量。Aurora 基于 MySQL，旨在兼容 MySQL 和 PostgreSQL。这意味着使用 MySQL 和 PostgreSQL 或用 MySQL 和 PostgreSQL 开发的应用程序和工具无需修改即可运行。由于它使用 Amazon RDS，它也擅长减少耗时的管理任务(如上所述)。

Amazon Aurora 在构建时就考虑到了高可用性，并与 SSD 支持的虚拟化存储层相集成。Amazon Aurora 旨在检测数据库崩溃并重启，而无需崩溃恢复或重建数据库缓存。

Amazon Aurora 自动扩展存储并重新平衡 I/o，以提供一致的性能，而无需过度配置。

### 使用 Amazon Aurora 扩展读取

同样，与 Amazon RDS 一样，伸缩性通常是一个重要的考虑因素。有了 Amazon Aurora，您的扩展能力可以达到 15 个实例。您可以设置负载平衡(与 RDS 一样)，但也减少了延迟和一些自动伸缩。

### 亚马逊极光高可用性

Amazon Aurora 还使用常见的故障转移技术以及可用性区域(AZ)的概念来确保数据库正常运行。此外，它还有以下选项:

*   连接端点
*   存储:6 份，3 份
*   自动故障检测
*   副本已升级
*   故障转移需要几秒钟

### 亚马逊极光性能

说到性能，在有利的条件下，使用相同的基准(每秒 500，000 次选择和每秒 100，000 次更新)，Amazon Aurora 可以超过 MySQL。在较大的实例上，这种性能改进变得更加明显。

需要注意的是，工作负载热点会降低性能。

### Amazon Aurora 的优势/限制/用途

转移到 Amazon Aurora 的许多原因与转移到 Amazon RDS 的原因相同。它提供了一个稳定、高度可用的数据库环境，免去了 DBA 的大量日常维护工作。然而，也存在许多相同的限制—随着手动任务集的减少，对配置选项的访问也相应减少。

对 Amazon Aurora 来说，一个值得注意的警告是，虽然它是基于 MySQL 的一个分支，但它不是 MySQL，也不一定像 MySQL 那样工作。

下面是一个快速列表，列出了优势、局限性以及您选择 Amazon Aurora 而不是其他选项的可能原因。

亚马逊 Aurora 的其他优势:

*   极低延迟复制
*   数据大小高达 64 TB
*   尤其是高并发性、大型实例

亚马逊 Aurora 的其他限制:

*   对于小型工作负载，速度较慢(写入延迟)
*   仅 InnoDB
*   只有一份数据的逻辑副本
*   没有 performance_schema(目前针对 5.7)

一般来说，您选择 Amazon RDS 的原因与选择 Amazon Aurora 的原因相同，只是 Aurora 的配置选项比 RDS 更少。

如果您的应用程序不会因为一些数据库复制延迟、故障转移时间超过一分钟或者丢失最多五分钟的事务而受到影响，那么 Amazon Aurora 不会立即遇到重大障碍。

选择亚马逊 Aurora 的其他理由:

*   您有高度并发的工作负载
*   当您需要卸载更多“操作”时

## 亚马逊 EC2(自己卷)

亚马逊弹性计算云(Amazon EC2)在 AWS 云中提供可扩展的计算能力。Amazon EC2 实际上只是购买云中的基础设施，它消除了您预先投资硬件的需要。这使您能够专注于更快地开发和部署应用程序，并在竞争对手之前将产品推向市场。

一旦您购买了 Amazon EC2 实例，您就可以使用它们来启动任意多的虚拟服务器。您负责配置安全性、网络和存储。Amazon EC2 使您能够扩大或缩小规模，以应对需求的变化或人气的飙升，从而减少您预测流量的需求。

### 使用 Amazon EC2 扩展读取

同样，对于云中的任何数据库部署，伸缩性通常都是一个问题。EC2 也不例外。因为 EC2 在如何部署数据库环境方面提供了更大的自由度，所以在如何处理可伸缩性问题上有许多选择。然而，这种自由也允许您创建和使用任何可用的解决方案。

*   缩放取决于您的实现
*   创建/添加/删除任意数量的副本和级别
*   添加集群节点相对简单(尽管这不是真正的“扩展”)
*   您可以使用第三方软件，如 ProxySQL，进行读写分离和负载平衡

### 亚马逊 EC2 高可用性

Amazon EC2 本质上也允许您按照自己的选择设置高可用性选项。它还允许您使用整个 AWS 架构固有的 AZ 配置。其他选项包括:

*   [Percona XtraDB 星团](https://www.percona.com/software/mysql-database/percona-xtradb-cluster) (Galera 星团)
*   同步复制到其他节点
*   节点故障不会造成数据丢失
*   使用 ProxySQL 进行自动故障检测
*   管弦乐队或 MHA

### 亚马逊 EC2 性能

由于您可以设置自己的环境并根据需要进行调整，EC2 性能测量和比较很难与其他 AWS 解决方案进行比较。然而，在 Percona，我们已经在类似的系统上进行了一些测试。你可以在这里找到一个这样的比较:

[AWS 极光标杆](https://www.percona.com/blog/2016/05/26/aws-aurora-benchmarking-part-2/)

其中，Percona 高可用性实践经理 Marco Tusa 介绍了 Aurora 与定制设置的对比。

对于我们关于 Amazon EC2 的其余讨论，我们将使用以下配置作为比较的基准配置:

*   [亚马逊 EC2 上的 Percona XtraDB 集群](https://www.percona.com/software/mysql-database/percona-xtradb-cluster)
*   使用节点 AMI (SST)进行自动配置
*   应用节点上的 ProxySQL
*   自动故障转移
*   读/写拆分
*   自动缩放
*   用于监控的 PMM
*   自动化备份并不难

### 亚马逊 EC2 的优势/限制/用途

在 Amazon EC2 环境中，除了硬件问题之外，您要负责许多与内部环境相同的方面。您可以自主安装从操作系统开始的所有东西:您决定何时打补丁、升级或安装安全补丁。诸如备份和配置更改之类的事情都在您的控制之内。您还可以访问所有常规的 MySQL 和 OS 配置设置(就像您的数据库环境是本地的一样)。

这种控制带来了维护、管理和配置您的环境的责任。您可以更好地调整数据库以满足应用程序的需求，但随之而来的是日常任务的开销，否则这些任务将由 Amazon RDS 或 Amazon Aurora 处理。

亚马逊 EC2 的其他优势:

*   您可以更深入地了解数据库软件和操作系统以及模式的性能
*   访问操作系统指标

亚马逊 EC2 的其他限制:

*   比 RDS 或 Aurora 更难设置和维护
*   取决于您选择的架构

选择 EC2 的其他原因:

*   您不需要依赖外部运营资源和专业知识，您的数据库管理员知识渊博，能够解决和配置数据库性能
*   你重视灵活性
*   你想使用具有超级权限的工具
*   你想读二进制日志

## 结论

当谈到将 AWS 云服务与您的开源数据库软件一起使用时，您有不同的选择。最常见的选择是亚马逊 RDS、亚马逊 Aurora 和亚马逊 EC2。它们都有优点和缺点，但实际上这些取决于您的需求和应用要求。

来自 Pixabay 的 Pete Linforth 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>