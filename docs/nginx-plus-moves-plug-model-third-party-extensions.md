# NGINX Plus 转向第三方扩展的插件模型

> 原文：<https://thenewstack.io/nginx-plus-moves-plug-model-third-party-extensions/>

随着新发布的第 9 版， [NGINX Plus](https://www.nginx.com/products/) ，开源 NGINX Web 服务器软件的商业版本，正在转向一个插件系统，其中扩展的功能——例如，编程语言，包括 Lua、JavaScript 和 clo jure——可以按需附加。

NGINX Inc .的产品负责人欧文·加勒特(Owen Garrett)说:“我们正在创建一个模块库，我们已经测试了这些模块，并证明它们可以在 NGINX Plus 中正常工作，我们将继续维护这个库。这意味着，任何使用我们受支持产品的人都将能够依赖我们已经测试过的第三方扩展库，我们也将尽最大努力提供支持。”

## 有机生长与嫁接

到目前为止，该公司为客户提供附加服务的首选方法是创建预配置的捆绑包，其中包括六个选定的项目和预编译的 NGINX，附带这些捆绑包，该公司称之为“NGINX Plus Extras”。Web 应用防火墙是目前焊接在 NGINX Plus 上最常见的附加组件之一。

“但这变得不可持续，”这位产品负责人承认。如果您试图在中编译太多模块，则存在二进制文件变得太大和潜在不稳定的风险，因为它们并不总是设计为一起工作

这种新方法为用户提供了挑选他们想要包含的模块的选项。

Garrett 告诉我们，随着扩展现在被视为扩展，他的公司现在可以开放其存储库来支持商业扩展，希望在未来几个月内实现。如果成功的话，NGINX 最终可以超越“平台”，开始指代一个合法的“生态系统”。

“如果有客户需求，或者如果有机会与合作伙伴合作来帮助推广他们的解决方案，那么我们可以非常容易地将他们的模块添加到我们的存储库中，用户将能够挑选和选择他们使用的模块，”Garrett 说。

这是否意味着对支持模块的更新可以立即在 NGINX 存储库中实现？“差不多了，”加勒特回答道。NGINX 将使用回购系统，非常类似于 Ubuntu 的 Apt 或 Red Hat 的 Yum，他告诉我们。每当 NGINX 收到一个模块的更新时，它将重建整个模块，并通过存储库提供产品作为升级。用户将下载完全重建的模块，而不是已安装模块的补丁。

## 避免膨胀

Garrett 承认“膨胀的二进制文件”可能会有问题，NGINX 节点会加载附加组件。他说，对于服务运营商来说，这应该不是一个问题，因为组织围绕 NGINX 设计他们的服务是作为一个单点联系，而不是多个点，并且通过给用户提供明智选择的方法。到目前为止，对于“Extras”系统，可能已经有太多臃肿的部署了。

“我们正在收紧人们使用的 API，使模块更难相互干扰，”加勒特说，“这样它们运行起来更安全、更可靠。我们正在投资一个开发者关系团队；我们正在为 API 构建文档，并与第三方和商业模块开发人员合作，以帮助他们移植到新的动态模块接口，并了解设计他们正在构建的模块的最佳方式。”

通过“收紧”，Garrett 澄清说，现有的 API 文档相当简陋，尤其是在区分内部 API 函数和公共函数时。他说，对于未来的文件，我们应该期待更大的一致性和清晰度。

## 现在使用 UDP

除了 TCP 和 HTTP 之外，Release 9 现在还增加了处理 UDP(用户数据报协议)流量的功能。UDP 协议主要由 DNS 服务、NTP 时间协议以及越来越多的物联网设备使用，这些设备需要比全面的 Web 服务器所需的协议更轻量级的协议。

Garrett 解释说:“负载平衡器能够处理的协议越多，它作为[*单一*]入口点的效率就越高。“这为您带来了运营效率；它降低了你的成本；它使诊断、性能调整和应用安全规则变得更加容易。通过将 UDP 负载平衡添加到 NGINX 和 NGINX Plus 中，我们帮助组织整合他们不同的负载平衡层。”

专题图片:旧金山，斯科特·m·富尔顿三世

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>