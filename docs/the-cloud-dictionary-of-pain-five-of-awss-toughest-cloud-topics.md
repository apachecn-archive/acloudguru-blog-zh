# 痛苦的云词典:AWS 最棘手的五个云话题

> 原文：<https://acloudguru.com/blog/engineering/the-cloud-dictionary-of-pain-five-of-awss-toughest-cloud-topics>

大家早上好；上课了！请坐好，系好安全带。

今天，我们来谈谈术语。亚马逊、谷歌和微软已经建立了足够多的云产品，如果你需要做一些与你的业务相关的事情，很有可能你可以在云上完成。但是伴随着这一系列全面的产品而来的是另一个挑战，不仅仅是知道何时何地使用它们:它们被称为什么，它们最初是做什么的。

确保团队中的每个人都能“谈论云”或对云有基本的了解可能是公司面临的最大挑战之一。我们将帮助您和您的团队实现基准云流畅度。为了做到这一点，我们建立了一个云词典，收录了您将遇到的一些最具挑战性的主题。鉴于这里的困难，我们决定将它命名为疼痛的[云字典*。*](https://get.acloudguru.com/cloud-dictionary-of-pain?cpn=7013u000000VDht)

[![Cloud Dictionary](img/93ebf63b88ab7fbd48705a01952ba688.png)](https://get.acloudguru.com/cloud-dictionary-of-pain)

[**获取痛苦全云词典**](https://get.acloudguru.com/cloud-dictionary-of-pain)
*说云不一定要硬。在我们的[云指南](https://get.acloudguru.com/cloud-dictionary-of-pain)中，你会找到一些最痛苦的云概念的简明定义的完整列表。*

* * *

我们分析了我们平台上数千个测验问题的 270 万份回复，以确定一些最具挑战性的云基础架构主题。我们寻找学习者成功率低于 60%的问题，并根据这些问题中的主题，概述了 20 多个具有挑战性的主题，学习者有时可能难以解开——至少在一些特定的场景中。

今天我们将讨论五个最具挑战性的话题:亚马逊 SQS、弹性负载平衡、AWS VPCs、AWS Lambda 和子网。这个列表是我们在所有三个主要云平台上攻击的几十个术语和主题的子集:AWS、Microsoft Azure 和 Google Cloud。你可以在[痛苦的完整云词典](https://get.acloudguru.com/cloud-dictionary-of-pain?cpn=7013u000000VDht)中找到我们对亚马逊棘手话题的完整演练。

所有这些都解决了，让我们开始吧！

[![AWS predictions for 2021](img/f3059c0c5d8e71851de270031ddaa224.png)](https://acloudguru.com/course/aws-certified-advanced-networking-specialty-2)

### **什么是 AWS VPCs？**

可以将 VPC 想象为云中的虚拟数据中心。您的数据中心可能有可直接访问互联网的公共 web 服务器，以及一组只能通过直接连接或 VPN 访问的更专用的服务器。如果您正在处理特别敏感的客户信息(如受监管的信息)，您可能会希望进一步隔离这些数据。

VPC 允许您提供 AWS 的一个隔离部分，您可以在您定义的位置启动资源。所以你可以把它想成一种处理你的私人信息的方式，而不会让这些机密信息接触到互联网。VPC 是放置您的数据库、应用程序服务器、后端报告流程的地方——任何您不希望直接暴露给任何有互联网连接的人的东西。

VPC 允许您设置 IP 范围、创建子网以及配置根表和网络网关。您可以创建一个连接到 web 的面向公众的子网，而您的后端系统是孤立的，根本没有连接到 internet。多层安全可以帮助您控制对每个子网的访问，这就是所谓的“深度防御”。每个 AWS 帐户都会为您提供一个现成的默认 VPC，但您可能会想要设置自己的帐户以提高安全性并进行自定义。

### **为什么很难？**

你基本上是在试图保持一些信息的安全和远离互联网，同时将面向互联网的服务连接到网络上的这些信息。那就复杂了！请看这个流程图:

![](img/0d30356733715b317ff806cea11f59cf.png)

好的，这是很多。

我们才刚刚开始。所有这些因素都是为了保护你的信息。但是有了这些箭头，你可以看到有很多地方会出问题。当你在配置一个定制的 VPC，但没有很多网络方面的专业知识时，整个过程会变得特别棘手；例如，[在亚马逊 VPC](https://acloudguru.com/blog/engineering/adding-support-for-vpc-build-a-serverless-multi-region-active-active-backend-solution) (虚拟私有云)内部署无服务器的多区域、主动-主动后端。

仅举一个例子:VPC 之间没有可传递的对等关系。你可以让一个 VPC 人和另一个 VPC 人谈话，但是如果那个 VPC 人和第三个人谈话，第一个人就不能和第三个人谈话。如果 VPC A 能和 VPC B 说话，B 能和 C 说话，A 还是不能和 C 说话！越来越多的人开始质疑他们是否需要一个 VPC。毕竟，“零信任”网络和无服务器架构的兴起已经将更多的工作负载移出了专用网络，转而依赖良好的授权策略(如 AWS IAM)。

但现实是，任何试图将传统服务连接到云的人都可能需要实现 VPC(T1)，毕竟这是唯一与旧数据中心(T3)中的私有网络(T2)对话的方式。

我们的学习者错过了 50.3%与 VPC 相关的难题。

**给我来个硬的！**

您的公司希望其附近分支机构的内部网络安全地连接到其总部的 amazon 虚拟专用云 VPC 环境中启动的实例。以下哪个建议的解决方案是正确的？

27%的学习者答对了这道题。下一个！

[![](img/f4043984f71252c8108078d137398991.png)](https://acloudguru.com/course/building-a-full-stack-serverless-application-on-aws)

### **什么是 AWS LAMBDA？**

AWS Lambda 允许您在一个称为“执行环境”的小型计算设备上运行代码，甚至比 EC2 实例更抽象。(这就是为什么基于 Lambda 的系统通常被称为“无服务器的”:那里的某个地方仍然有服务器，只是你不必知道或关心它们。)

您可以通过点击网站上的按钮或上传照片(或者云专家讲座)等事件来触发功能。例如，当你与 Alexa 交谈时，你的问题可能不是查询特定的关系数据库来检查响应。相反，它可能通过 AWS API 网关向 Lambda 函数传递请求。这些 Lambda 函数可以触发另一个 Lambda 函数。再一次，在非常经典的 AWS 时尚中，它是一路向下的 Lambdas。

明确地说，如果用户分布在多台服务器上，这种扩展不同于自动扩展。一百万用户访问你的网站可能会引发一百万个 Lambda 事件。1 个用户和 100 万个用户调用该动作之间的差异是成本的函数，而不是速度的函数。您只需在应用程序执行代码时支付费用。

### **为什么很难？**

这是一个完全不同的范例！

[Lambda 函数的运行时间限制很短](https://acloudguru.com/blog/engineering/whats-the-friction-with-serverless)，严重依赖事件驱动的编程，并且与一些遗留技术不兼容。[然而许多人认为无服务器架构是应用程序的未来。](https://acloudguru.com/blog/engineering/serverless-is-eating-the-stack-and-people-are-freaking-out-and-they-should-be)出现这种情况有很多原因。但是从商业角度来看(特别是如果你有团队公司卡)，主要原因是无服务器架构可以极大地节省成本。

Lambda 呼叫在 100 万次请求内是免费的，此后每 100 万次请求只需 20 美分。这还不包括您释放的所有系统管理员时间。从这个角度来看:通过在后端使用无服务器和 Lambda，我们在一个云专家这里为数百万用户提供服务的计算成本变成了一个舍入误差。如果你因为任何原因看到了将部分业务转移给 Lambda 的机会，你很有可能应该这么做。

我们的学习者 48%的时间错过了与 Lambda 和无服务器相关的难题。

![optimize cloud bill](img/90314d46b0fe39dceabd4184833de9eb.png)

## 弹性负载平衡

### **什么是弹性负载均衡？**

这就像它听起来的那样:一个物理或虚拟设备，旨在帮助您平衡多台服务器之间的网络负载。您有多种方法来规划自动缩放，通常有三种选择:

1.  应用程序负载平衡器可以看到应用程序内部及其发出的请求。应用程序负载平衡器非常适合于为您做出明智决策的扩展引擎。
2.  当您需要关注性能时，网络负载平衡器工作得最好。这些负载平衡器在连接级别运行。
3.  经典负载平衡器只是传统的弹性负载平衡器。如果你不在乎 AWS 如何路由你的流量，这是一个便宜的选择。(亚马逊很大程度上反对这些。)

### **为什么很难？**

两个原因:

*   您首先必须选择最佳的负载平衡器，然后您可以启用许多特定的功能来使这些负载平衡器更加高效。一如既往，会有权衡。挑战在于最大化您从云配置中获得的价值。应用程序负载平衡器最适合运行在第七层的 HTTP 和 HTTPS 流量。应用程序使用网络负载平衡器来平衡 TCP 流量，在连接层(第四层)工作。传统的平衡器可以为 HTTP/HTTPS 应用程序使用第七层特定的特性，但是它不是应用程序感知的。
*   一旦您选择了一个负载平衡器，您就必须解决如何将您的流量路由到您的各种 EC2 实例。这些实例可能跨越 AWS 疼痛字典的多个可用性区域，并与不同的负载平衡器相关联。但是可以智能地路由流量，以优化每个 EC2 实例的性能。

以下是您必须解决的一些顶级配置:

*   **STICKY SESSIONS:** 您可能希望确保一个用户只绑定到一个 EC2 实例——比如他们正在将信息保存到磁盘。但是通过使用粘性会话，您也可能最终得到未使用的 EC2 实例。
*   **跨区域负载平衡**:您可能希望自动平衡所有 EC2 实例的传入流量，而不管您当前使用的可用区域。如果使用跨区域负载平衡，您可能会因为将流量发送到不同的地理区域而牺牲一些性能。
*   **路径模式**:你可以根据 URL 路径智能地路由你的流量，比如 myurl.com/images.，但这也可能无法解释特定页面的流量激增——比如说，一些名人在你的图片页面上发布了一张图片。

我们的学习者有 53%的时间错过了与负载平衡器相关的棘手问题。

[![Using SQS with Lambda | AWS DevOps Pro](img/a45c06f2ec18211c5aa78385a0843dbe.png)](https://acloudguru.com/course/aws-certified-solutions-architect-associate-saa-c02)

### **什么是 AWS SQS？**

SQS 是 AWS 历史最悠久的服务之一，于 2004 年首次宣布。它允许您在等待计算机处理消息时访问消息队列来存储消息。亚马逊 SQS 使你能够分离应用程序的组件，并让它们异步通信(按照它们自己的时间表)。[每条消息都被发送到一个服务，比如 Lambda 函数或 EC2 实例](https://acloudguru.com/blog/engineering/event-driven-architecture-with-sqs-and-aws-lambda)。

那些解耦的组件可以将它们的消息存储在一个等待计算的防故障队列中。例如，如果您因为某种原因失去了一个可用区域，这将非常有用。如果一个 EC2 实例出现故障，该消息在队列中变得可用，从而使其他 EC2 实例能够接替这个空闲时间。

### **为什么很难？**

如果你构建在 SQS 之上，你就在定义上创建了一个分布式应用程序:一个通过解耦的部分跨网络工作的应用程序。这带来了全新的设计和操作层面的考虑。您可以选择是创建标准队列还是 FIFO(先进先出)队列。两者都有一些优点:标准队列确保您的消息至少传递一次，并尽最大努力按照接收的顺序排列它们。但这是最大的努力，你不应该假定秩序！FIFO 队列按照收到消息的确切顺序传递消息。

消息被传递并保持可用，直到消费者处理并删除它。在这种情况下，队列中不允许出现重复项。SQS 还实现了可见性超时——实质上是队列在对下一个用户可用之前等待一个用户的时间。例如，假设一条消息对一个 EC2 实例可用，但在某个目标时间内没有被执行。然后，另一个 EC2 实例可以获取并运行该消息。但这也意味着 SQS 可能不止一次传递你的信息。

我们的学习者 49%的时间错过了与 SQS **相关的难题。**

[![](img/ac9d1669c2368b58f63889902de53fb0.png)](https://acloudguru.com/course/subnetting-fundamentals)

### **什么是 AWS 子网？**

子网的简称，子网只是网络的一部分。创建 VPC 时，您将拥有一系列与特定可用性区域内的所有应用程序相关联的子网。我们将在特定的子网内配置资源，如 EC2 实例或 RDS 数据库，这些子网可以是公共的，也可以是私有的。公共子网有一个与互联网网关相关联的通往互联网的路由。公共子网也可以与其他公共子网通信。私有子网没有通往 internet 的路径，但是它们可以连接到 VPC 内的公共子网。

### **为什么很难？**

一个子网不能跨越多个可用性区域。您可能会听到类似“一个子网等于一个可用区域”这样的话假设您决定在某个特定地区推出 VPC，在该地区，AWS 提供了一组可用区域。如果您希望保持某些信息的私密性，例如 RDS 数据库中的一组客户信息，您可以在一个可用性区域内启动一个私密子网。

但是，假设您想要在不同的可用性区域内启动一个子网(比如寻找一些冗余)。在这种情况下，该子网将无法与不同可用性区域中的专用子网通信。您的专用子网不会跨越多个可用性区域。因此，在确定如何处理灾难恢复时，这是一个重要的考虑因素。

我们的学习者有 49.1%的时间错过了与子网相关的难题。

#### **我们希望**在看完这些例子后，你会体会到云有多危险。它有自己的自定义词典，以配合其庞大的城市产品环境。

我们可以理解云有多复杂，并希望我们能提供一些指导。话说回来，我们没有写下规则。(嗯，问题是我们写的——对此我们真的很抱歉。)

你可以在[痛苦的完整云词典](https://get.acloudguru.com/cloud-dictionary-of-pain?cpn=7013u000000VDht)中找到我们对亚马逊棘手话题的完整演练。你还可以在我们的 Azure 和谷歌云痛苦字典中找到它们的对等词——以及是什么让 Azure 和 GCP 变得如此独特曲折。您还会发现我们完整的方法。

* * *

希望提升您的云计算职业生涯？[从云计算专家那里开始](https://acloudguru.com/pricing),看看实践如何帮助你掌握现代技术技能。