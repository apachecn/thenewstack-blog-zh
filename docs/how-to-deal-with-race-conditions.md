# 如何处理竞态条件

> 原文：<https://thenewstack.io/how-to-deal-with-race-conditions/>

“竞争条件”是指由于多个操作的执行时间或顺序而发生的错误。这是一类相当广泛的错误，根据问题空间的不同，它们会以非常不同的方式出现。在许多情况下，它们可能难以识别和/或重现，即使解决方案可能很简单。

## **托头**

[“检查时间到使用时间”](https://en.wikipedia.org/wiki/Time-of-check_to_time-of-use) (TOCTOU)描述了当资源的状态在检查其状态和使用结果之间改变时发生的一种竞争条件。TOCTOU 通常是在文件系统操作的上下文中讨论的，但是在我们构建的系统的许多领域中可能会有变化。

TOCTOU 竞争条件的常见例子是检查文件是否可访问，然后读取它:

```
let exists  =  await fs.access(path_to_file)
if  (exists)  {
  const data  =  await fs.readFile(path_to_file)
  ...
}

```

如果文件在初始检查后被删除或修改，最多会出现一个无法处理的异常。在最坏的情况下，您可能会打开安全漏洞的大门。

***取而代之:**跳过访问检查，将 readFile 包装在 try/catch 中，并处理那里的任何错误。*

## **原子数**

通常我们在数据库系统的上下文中谈论“原子更新”。考虑下面这个虚构的例子:

```
const user  =  db.users.findOne(id)
if  (user.role  ===  'admin')  {
  user.superPowers  =  true
  user.save()
}

```

看到问题了吗？从数据库中获取用户，执行一些逻辑，然后执行一个查询来更新用户。但是，这是一个非原子操作，不能保证在检查和更新之间用户的角色仍然被设置为数据库中的“admin”。在这个假的例子中，结果可能是应用程序中的安全漏洞；在现实世界的场景中，根据系统的[复杂性](https://logdna.blogin.co/posts/99035)，可能更难注意到。

***相反:**创建一个原子更新查询，用一条语句执行更新。*

## **共享状态**

 [迈克·德尔·蒂托

Mike 是 LogDNA 的资深开发人员，在基于 web 的软件应用程序的开发中，拥有设计、交付和领导团队的丰富经验。](https://www.linkedin.com/in/mdeltito/) 

尽管 Node.js 是单线程的，但异步处理共享资源和数据结构需要与多线程系统中相同的关注级别。

这是另一个例子:

[https://repl.it/@MikeDel2/set-data-race?lite=true](https://repl.it/@MikeDel2/set-data-race?lite=true)

乍看之下，您可能认为它总是输出第一个值 1，但是程序每次都可以输出不同的值(试试看！).

即使在一个孤立的例子中很容易发现问题，考虑一个更复杂的并发程序，其类似的目标是仅在满足前提条件时做一些工作。您可能有多个异步工作人员需要:

*   打开特定文件的写入流，供所有工作线程写入。
*   如果数据库中没有记录，则创建一个。
*   记住一次昂贵手术的结果。

在所有这些场景中，您不能假设您正在使用的资源的状态在检查和使用之间保持不变。这种特定的“如果不存在就创建”竞争条件的变体最近在第三方代码甚至我们自己的代码中出现了几次。

## **应对措施**

避免竞态条件不仅需要考虑您的代码在做什么，还需要考虑系统的其他部分将如何使用您的代码。这里没有灵丹妙药，但是除了考虑并行设计之外，这里还有一些提示:

*   自动执行数据库更新。不要依赖以前查询的有关要更新的记录的信息来编写更新查询。
*   一般来说，尽可能避免共享“全局”状态，尤其是在并发的情况下。考虑一下同时访问数据结构的含义，以及这如何影响程序的逻辑或数据本身的正确性。
*   如果需要在并发例程之间共享状态，可以考虑引入互斥体(互斥的)或其他锁定机制来控制对共享资源的访问。这是以复杂性为代价的，但有时是不可避免的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>