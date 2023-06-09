# Netlify 首席执行官解释 Netlify Edge Functions 为何建立在 Deno 之上

> 原文：<https://thenewstack.io/netlify-ceo-on-why-netlify-edge-functions-was-built-on-deno/>

网络开发平台 Netlify 最近为那些在网络边缘工作的人增加了一个新产品。根据 Netlify 首席执行官[马特·比尔曼](https://www.linkedin.com/in/mathias-biilmann-christensen-a5a3805/)的说法，Netlify Edge 功能于 2019 年开始开发。在接受 New Stack 采访时，他描述了展望未来如何激发了该公司最新产品的愿景。

“随着我们构建我们的边缘网络，随着我们开始看到这一类别的成熟，随着人们在各种行业构建更复杂的项目，我相信我们会看到一个新的层面出现，开发人员可以轻松编写在边缘上运行的代码。一开始，我们不确定这个层看起来会是什么样子，或者它会做什么。我们花了很多时间研究 WebAssembly 作为运行时机制，但最终决定不采用它。2020 年，我们将我们的努力从 WASM 转移到我们自己的基于 JavaScript 的 edge 运行时。”

> “像 Node.js 这样的标准 JS 运行时并不是真正为在完全多租户环境或独特的进程隔离中运行而构建的，所以我们必须开始构建自己的运行时。”

马特·比尔曼，Netlify 首席执行官

一年前，Netlify 的第一个 Edge 函数版本(当时叫做 Edge Handlers)得到了测试开发人员不冷不热的回应。其他专有边缘计算解决方案面临的问题，如平滑集成，也是一个问题。

这导致了与开源 JavaScript 和类型脚本运行时 [Deno](https://deno.com/deploy) 合作的决定。让 edge 功能成为一项协作工作，让开发人员能够使用他们已经熟悉的 JavaScript 框架来构建和部署 Edge 功能。

## 开放的标准

Deno(由创建 Node.js 的同一个人创建， [Ryan Dahl](https://tinyclouds.org/) )除了是开源的，还是一个开放的标准。比尔曼说，Netlify 作为一家公司，是从互联网本身以及它如何不被任何人或任何一家企业所拥有的灵感开始的。因此，他说，他们对 web 开发社区的贡献应该是可共享的，而不是局限于一个所有者——即使是他们。

“支持开放标准对我们来说至关重要。我们想要的是基于开放标准而不是特定于供应商的所有者标准构建的东西。你继续在 Netlify 上运行它的原因应该是你的团队的开发经验和生产力如此之高，以至于你想留在我们这里——而不是你被锁在里面，”比尔曼解释道。

## 将开发者体验放在首位

从一开始，Edge Functions 就是为了迎合开发者的体验而构建的。比尔曼说，“我们想消除所有的摩擦。对于整个生态系统来说，开放运行时的出现非常重要，对于开发人员来说，编写全球分布式软件并不容易。”

他继续说，“我们想提供 Netlify 包，所有东西都在一个 Github 库中，你只需写一次代码，打开 pull 请求，我们会给你一个唯一的 URL，你可以在那里看到所有东西一起运行。我们在一个中央平台上为您提供观察和登录功能。您可以将这些日志发送给 DataDog、New Relic 等合作伙伴。”

然而，对于开发人员来说，一个好的编程环境不仅仅是速度和可访问性。Edge Functions 包含的功能使诊断和修复问题变得更加容易。“如果你犯了一个错误，运送了一些不起作用的东西，你可以在几毫秒内回到任何已知的状态，这给了团队运送的信心，并使公司有可能一天执行数百次发布，”Biilmann 补充道。

“我们仅仅是基础设施提供商是不够的；我们的整个价值主张就是让开发者工作得更快更好。在这个项目中，我们不得不在核心开发人员体验上花费大量时间。”

## 在边缘建立网站

对于一些开发者和消费者来说，网络边缘正变得越来越容易识别和受欢迎。Biilmann 说:“企业客户希望在边缘实现个性化，或者从边缘进行身份验证。

在网络边缘运行有很多好处，包括速度和安全性。“我们可以把你的网站分发给全世界的服务器，”比尔曼说。“通常情况下，如果你在东京，访问一个位于纽约服务器上的网站，在你的浏览器上发生任何事情之前，只需花一秒钟就可以获得第一条内容。我们可以把这个时间缩短到几毫秒。”

像大公司参与的大多数项目一样，构建 Edge 函数是一项艰巨的任务。比尔曼详细讲述了边缘函数诞生的过程。“创建这种解决方案总是很困难。我们运营着一个全球网络，为我们的客户提供大量的流量，我们在为 Netlify 构建任何东西时都必须考虑到这一点。要让这个系统变得强大、高效，并对其进行足够的扩展以处理我们的系统必须处理的流量，存在许多挑战。”

“写这个感觉如何？当你在你自己的机器上运行它，就像它在我们全球分布的网络上运行一样，我们如何让所有的东西在本地协同工作？我们如何将日志流式传输到我们的系统中，以便向开发人员展示他们的 edge 功能中发生了什么？这是一次沉重的工程提升。”

虽然 Edge Functions 推出的时间不长，但 Biilmann 表示，Netlify 正在积极推进它，并在开发新项目。“我们的团队有一整套想法，知道我们还能做些什么来减少开发人员的摩擦。我们一直在努力开发下一个可以整合的部分，以使体验更加无缝。我最兴奋的是看到这个社区将会用这个新的原始人建造什么。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>