# 揭穿无模式化的神话

> 原文：<https://thenewstack.io/debunking-the-myth-of-going-schemaless/>

[](https://www.mongodb.com/developer/author/john-page/)

 [约翰·佩奇

约翰·佩奇是一名文档数据库老手，在为情报界构建全栈文档数据库技术 18 年后，他加入了 MongoDB。他现在制造机器人是为了好玩，并测试和编写数据库来支付机器人零件的费用。](https://www.mongodb.com/developer/author/john-page/) [](https://www.mongodb.com/developer/author/john-page/)

各地的开发人员都接受了文档数据库。但在很多情况下，是因为错误的原因。以目前关于无模式的宣传为例——在文档数据库中存储任意的 JSON 或 XML 几乎太容易了。但是如果你期望高效地过滤、修改和检索，你可能会让自己失望。

虽然文档数据库确实允许您在不定义数据是什么的情况下存储数据，但是如果您计划做的不仅仅是通过键检索整个文档，那么数据的形状就很重要。

如果您忽略了模式设计，只是简单地存储预先存在的文档，那么您可能不需要文档数据库，只需要一个简单的键值存储。

## **文档模式设计与关系设计**

关系数据库旨在为所有用户提供一种定义好的、一致的、安全的数据交互方式。你组织数据的方式与它将被使用的方式没有任何关系。它不能。毕竟，当不同的需求出现时，谁能预测不同的用户将如何访问数据的一个副本呢？

因此建立了规范化的模式设计，其中关系是由数据本身定义的，而不是数据最终将如何被使用。这使得数据建模更加可预测。给定相同的数据集来建模，任何有能力的架构师创建一个模式都会得到相同的结果。但是可预测性也意味着更少的灵活性。

文档设计产生于 20 世纪 60 年代，大约与面向对象编程同时。但是计算用了几十年才发展到可以理解文档模型灵活性的程度。

对于文档数据库，模式设计基于数据的访问方式，而不是数据本身。开发人员最了解他们的应用程序将如何访问数据。如果没有用户如何访问数据的计划，就不可能优化模式。当然，您可以只是持久化数据，而不计划用户将如何访问它。文档模型允许这种类型的灵活性。但是您可以并且应该在以后优化模式。

## **更好模式的好处**

初学者喜欢文档数据库，因为他们可以持久化对象而无需预先定义它们。通过最少的培训，几乎任何人都可以在不理解文档模式设计的情况下构建可信的应用程序。

然而，在某一点上，知道如何正确地设计您的模式可以让您用更少的服务器硬件获得更多。在当今按需付费的云定价模式下，这一点非常重要。通过减少计算、I/O 操作和用户之间的争用，文档模式可以提高给定硬件集的性能。

文档数据库缺乏预先模式实施的想法是不正确的。

文档数据库可以像关系数据库一样实施模式。无模式设计在文档数据库中可能很常见，但这并不是它们的同义词。现代文档数据库还具有强类型数据、丰富的数据操作语言(DML)、多个基于 BTree 的复合索引、ACID 事务和数据库内聚合计算。文档数据库也与 Postgres、MySQL 和其他关系数据库共享相同的底层存储引擎。

文档数据库与关系数据库的真正区别在于能够在原子存储单元中共同定位相关数据，因此单个*记录*连续存储在磁盘和内存中，而不是分成行并独立存储。

简单地说，在文档数据库中，一个属性的多个值可以存在于单个记录中。如果一个人有多个电话号码，你不需要一个不同的表来存储它们。您不需要为每个数字定义单独的字段。您可以简单地拥有一个电话号码或数字对象的数组。这就像在存储层将一个表中的行嵌入到另一个表中。

```
{
  name:  "john",
  phones:  [  {  type:  "cell",  number:  4475566218},
 {  type:  "cell",  number:  4479927716},
 {  type:  "voip",  number:  17035551234}]
}

```

这种协同定位数据以减少 I/O 的想法多年来一直是数据库实施的基本原则。在关系数据库中，数据库管理员使用“索引组织存储”的概念来共同定位预期同时被访问的行。但这是事后的事。值得注意的是，它不允许您将不同表中的数据放在一起，以降低检索复杂记录的成本。

## **文档如何减少计算和 I/O**

当您查询一个数据库时，您要过滤掉数据的一个子集，要么以原始形式检索它，要么计算某种汇总。如果您想要的数据在单个行中，而您的查询从单个表中获取它，那么关系数据库或列存储可能会更有效。

另一方面，一旦需要将表连接在一起以执行查询，查找多个索引和合并结果的额外计算工作就会抵消这一优势。您需要访问的每一个额外的行都会增加 I/O 操作。I/O 发生得很慢。加快速度代价高昂。

在具有适当设计的模式的文档数据库中——因为整个业务记录都包含在一个文档中——过滤和检索所需的所有数据都可以用最少的计算开销和一次 I/O 操作获得。这可以大大加快查找和检索数据的速度。

对于无法放入单个文档的任何内容，您将需要多种记录类型，并且可能需要查询相关的组。幸运的是，成熟的文档数据库也提供了一个或多个连接选项，尽管应该谨慎使用。

## **文档如何减少争用**

数据库必须允许多个用户或进程编辑相同的记录，而不会覆盖彼此的更改。我们不能有这样的情况，两个用户修改相同的数据，其中一个最后写的覆盖了另一个的修改。如果您处理过 git 冲突，您就会知道解决这些变化有多重要。一致的数据需要一种比试图合并冲突的变更更好的方法。

在数据库中解决这个问题的方法是锁定，这需要:

1.  找到符合您的变更标准的记录。
2.  锁定它，这样其他人就不能修改它。
3.  验证它在查找和锁定之间没有改变。
4.  应用更改。
5.  打开它。

对每个更改都这样做可以序列化更改并保持数据的正确性。例如，如果两个进程同时找到库存中的最后一件商品，并对其进行修改以将其放入购物车，那么应该只有一个进程成功。在这种情况下，对单个记录的所有修改都发生在单个锁中，并且该锁只需要在应用检查和更改的时间内持续，通常是几微秒。

在文档数据库中，一次只需要更新一个文档的记录编辑是一个非常低争用的操作。该应用程序可以支持大量并发用户。

这种短暂的、低争用的变化需要一种丰富的查询语言，能够完全在服务器端执行相关的更新。如果您被迫检索记录，在客户机上对其进行更改，然后将其发送回来，这意味着需要进行两次编辑来创建并释放长期锁，否则您将面临被覆盖的风险。来自客户端的两次数据库调用之间的时间是存在争用的地方，这可能是实质性的。

发送指令将字段设置为特定值非常简单。但是文档数据库需要支持逻辑上复杂得多的修改。假设您正在构建一个高分表，为了加快检索速度，将前五个分数存储为一个文档。您可能会看到如下内容:

```
{  
  game:  "super_kong",
  highscores:  [{  name:  "joe",  score:  118231},
              {  name:  "amy",  score:  75651},
 {  name:  "chloe",  score:  62352},
 {  name:  "bryan",  score:  54524},  
              {  name:  "dwayne",  score:  41654}]
}

```

您需要能够做的是向服务器发送一个命令，告诉服务器“如果高分包含一个小于 X 的分数，那么在一次操作中，将 X 添加到高分中，按分数对高分数组进行排序，然后只保留前五项 *MongoDB 支持这种丰富的编辑功能。*

 *那么，当需要同时更新多个离散项来更新一条记录时，会发生什么情况呢？这在关系数据库中太常见了，在关系数据库中，对记录的编辑意味着更改多行。

解决方案是 ACID 事务。当您修改项目时，ACID 事务会锁定每个项目。然后，当提交事务时，它会解锁所有这些文件。这通常是在多次调用服务器之后，这意味着文档实际上会被锁定更长的时间，包括网络和客户端时间。这是高吞吐量关系数据库负载中争用和性能问题的典型原因。

使用文档数据库，您可以在相同的场景中结束。但是一个设计良好的文档模式可以防止这种情况发生。而且，如果您绝对必须编辑多个文档，像 MongoDB 这样的文档数据库提供了与 ACID 事务中完全相同的`BEGIN TRANSACTION COMMIT`语义。因为它仍然会引入与关系数据库相同的争用问题，所以最好创建一个模式来避免修改多个文档，或者提供一种方法来执行编辑而不破坏数据库一致性。

## **文档模式设计中的权衡**

模式设计没有完美的答案。文档模型假设读取多于写入。往往更多。相对于在更新期间可能写入更多数据，优化读取速度是一个不错的选择。除非系统只是简单地记录或审核数据，否则可以放心地假设，写入的每一位数据都至少会被读取一次，甚至可能不止一次。

对于文档设计，可以对域表进行反规范化，或者对某些数据项拥有多个副本。如果您有一个很少更改的国家列表，存储国家名称而不是域表的键并处理国家名称更改的后果是一个可以接受的折衷方案。

对于其他记录，很可能有数据的最终副本。对于客户记录，通常每个客户有一个文档。但是为了加快阅读速度，在编写时可能会将一些字段复制到其他文档中。

例如，您可能决定将客户的姓名、地址和唯一标识符复制到他们的每个发票记录中。这减少了检索发票所需的时间。如果客户更改了他们的姓名或地址，您可以就地修改这些发票记录。

文档数据库还鼓励您考虑使用幂等的、可重试的操作，并且在出现错误时总是前滚而不是后滚。想象一下，我们需要给每个人加薪 10%。我们可以将它包装在一个事务中，但是无论需要多长时间，它都会锁定我们的 employee 表。可能要几个小时。

或者，我们可以只要求数据库增加每个人的工资，并且作为更新每个记录的一部分，添加一个新的临时字段`got_payraise`。如果中途失败，那么它应该再试一次。但是这一次，它应该只在`got_payraise`字段不存在的情况下加薪，因此没有人获得两次加薪，并且重复直到每个人都获得加薪。此时我们可以删除所有的`got_payraise`字段。这种模式几乎消除了不奖励某人或不知道某人是否加薪的所有争议和风险。这就是模式设计的灵活性真正发挥作用的地方。

## **付诸实践**

与关系数据库不同，文档数据库要求设计者或开发者考虑正确性、争用和性能。但作为回报，它给你更好的性能和控制。在关系世界中，一个人对数据建模，其他人用它构建应用程序，然后 DBA 试图优化它的工作方式，与此不同，文档数据库将开发人员放在创建良好数据库的前端和中心。当从关系数据库转移时，这可能需要组织或过程的调整。

一旦你理解了基本原理——你需要一个模式，什么样的模式好，什么样的模式不好——那么你就可以在不同的选项中进行选择，并且理解什么正在发生，什么没有发生。在教授这些课程多年后，我经常听到开发人员说，他们不知道通过文档数据库中的模式设计可以获得这么多。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*