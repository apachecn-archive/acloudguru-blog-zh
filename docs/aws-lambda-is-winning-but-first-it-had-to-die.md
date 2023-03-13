# AWS Lambda 赢了，但首先它得死|一个云专家

> 原文：<https://acloudguru.com/blog/engineering/aws-lambda-is-winning-but-first-it-had-to-die>

*主要特性的变化已经成功地将 Lambda 工作负载推向了主流，即使 FaaS 纯粹主义者感觉被背叛了*

无服务器赢了吗？

如果你问 AWS，他们会说*肯定是*。今年在亚马逊内部构建的所有新应用程序中，将近一半是运行在 Lambda T3 上的[。Andy Jassy 在他的 re:Invent keynote 中花了一些时间来号召数千家现在在生产中运行 Lambda 工作负载的企业，但也许最有趣的是，今年新的无服务器功能发布升级到了 Jassy 的 keynote-这通常是为今年最闪亮、最具战略意义的揭示保留的位置。至少 AWS 明确认为，无服务器现在是其云的主要卖点之一。](https://siliconangle.com/2020/11/30/exclusive-aws-chief-andy-jassy-wakeup-call-cloud-adoption/)

(另一方面，有一篇奇怪的文章[，它花了大部分篇幅展示 FaaS 的增长，但却被冠以“无服务器采用停滞”的标题，因为……Kubernetes 团队说他们没有使用同样多的 Lambda？在其他新闻中，猫报告吃更少的蔬菜。)](https://thenewstack.io/adoption-of-aws-lambda-serverless-stalls/)

没有争议的是，Lambda 仍然是 900 磅重的 FaaS 大猩猩，今天看起来与 2015 年正式上市时有很大不同。早期购买无服务器系统的工程师总是对好的无服务器系统有[非常具体的想法](https://twitter.com/PaulDJohnston/status/1336765475615879181)…最近，Lambda 一直在质疑他们的假设。

## 无服务器宣言的衰亡

FaaS 纯度的那些最初的理想不是凭空出现的。就在 2016 年，AWS 无服务器领导层还在谈论他们所谓的无服务器计算宣言。这是一个关于功能即服务应该如何运作的激进愿景。宣言出现在各种会谈中，包括 T2 在 ACG 的无服务器会议上。以下是它的主要原则:

***《无服务器计算宣言》(约 2016)***

*   *功能是部署和扩展的单位*
*   *编程模型中没有可见的机器、虚拟机或容器*
*   *永久存储生活在别处*
*   *每个请求的规模；用户不能过度或不足配置容量*
*   *永远不要为闲置(无冷服务器/容器或其成本)付费*
*   *隐式容错，因为函数可以在任何地方运行*

这个宣言为如何构建和部署软件形成了一个令人震惊的和高度反文化的蓝图。它吸引了一个人数不多但充满活力的真正信徒群体，以及一群人数更多、声音更大的怀疑论者。

但是回过头来看，无服务器计算宣言很难超越那个小而忙碌的核心。大胆的愿景只是遗漏了太多现有的遗留工作负载和团队。

因此，渐渐地，就像奥威尔的*动物农场中的戒律一样，* AWS 的无服务器计算的不可协商性开始改变。让我们浏览一下宣言的每一点，看看 Lambda 是否仍然坚持它。

**功能是部署和扩展的单位？**

算是吧，但不完全是。你可以部署多功能的 Lambda 层来管理大型二进制文件，或者(现在在预览版中)部署 Lambda 扩展来插入第三方代理，我被告知这些代理绝对不应该被认为是“Lambda 的旁门左道”。查看这篇关于将 flask 应用程序迁移到 AWS Lambda 的[教程！](https://acloudguru.com/blog/engineering/adventures-in-migrating-to-serverless)

编程模型中没有可见的机器、虚拟机或容器？

*不再真实。*从 2020 年开始，Lambda [现在允许你自带容器](https://acloudguru.com/blog/engineering/packaging-aws-lambda-functions-as-container-images)，而不仅仅是运送一个 ZIP 文件的代码。

**永久储存在别处的生命？**

*未必。Lambda 现在与 EFS 集成在一起，我猜从技术上来说是“在别处”,但并不比任何其他连接到服务器的 NFS 共享“在别处”更重要。它是安装在您计算机上的持久文件系统。*

**每个请求的秤？**

*是的！*既然 Lambda 可以运行容器，我相信请求模型现在是 Lambda 和 AWS Fargate 之类的托管容器服务之间最大的[概念差异。Lambda 为每个并发请求提供了一个新的执行环境，而类似 Fargate 的服务仍然会在同一个(长期)容器上处理多个并发请求。](https://acloudguru.com/blog/engineering/serverless-is-eating-the-stack-and-people-are-freaking-out-and-they-should-be)

**用户不能过度配置或配置不足容量？**

*不再真实。*满足供应的容量，这将您的冷启动问题转换为热成本问题。(我对此嗤之以鼻，但调配容量要比运行自己的 Lambda 预热工作好得多，很多人过去都是这样做的。)

**从不为闲置(没有冷服务器/容器或其成本)买单？**

*不再正确—*无论如何，如果您使用调配的容量或 EFS，情况就不会如此。

**隐式容错是因为函数可以在任何地方运行？**

*Ehhhh。*这是关于抽象出可用性区域，除了 Lambda(包括 Fargate！)现在做。也就是说，我们开始听到更多来自 AWS 的[指导，实际上，你需要考虑的错误领域是区域。没错:区域是新的可用性区域，正如我们所说的，精明的 Lambda 开发人员正在开发他们自己的(非常不受管理的)多区域架构。](https://acloudguru.com/blog/engineering/why-serverless-with-aws-is-a-game-changer)

为了加强这一趋势，让我们来看看 Lambda 的另外两个定义性的早期特性:

**有意的时空限制？**

*越来越不真实*。功能磁盘大小、运行时间限制以及 CPU 和内存大小在过去 5 年中稳步增长。今天，你可以用 10 GB 的内存和 6 个 vCPUs 运行一个 Lambda 函数 15 分钟——这是一个足够大的计算量，足以让你认真考虑多线程、多用途函数和其他与 FaaS 的旧理想相悖的东西。

**零信任网络？**

如果你想要的话。在过去，Lambda 架构严重偏向于 IAM 安全，而不是使用 VPCs，这部分是出于意识形态的原因，但也因为将功能附加到自定义 Eni 会增加巨大的冷启动开销。今天，AWS 的创新使得客户管理的 VPC 与 Lambda 更加兼容。

所以我们现在有一个更新的宣言，看起来像这样:

***《无服务器计算宣言》(大约 2020 年)***

*   *~~功能是单位的调配和伸缩~~*
*   *~~编程模型中没有可见的机器、虚拟机或容器~~*
*   *~~永久储存在别处的生命~~*
*   *每个请求的规模；* *~~用户不能超量或欠配容量~~*
*   *~~【从不为闲置买单(没有冷服务器/容器或其成本)~~*
*   *~~隐式容错因为函数可以在任何地方运行~~*
*   *~~有意的时间和空间约束~~*
*   *~~零信任网络~~*

我觉得自己就像巧克力工厂之旅结束时的威利·旺卡，环顾四周，看看孩子们都去了哪里。在所有这些意识形态原则中，那些沙上的线，*每请求缩放是唯一剩下的东西。*

当然，您仍然可以根据最初的无服务器宣言来构建。但是这项服务并不要求你这样做。

如果你必须将 Lambda 的修正价值主张浓缩成一句格言，*动物农场-* 风格，你会说什么？"*所有工作负载都得到管理，但有些工作负载比其他工作负载更容易管理？*

## 无人服务器的兴起

这似乎是澄清我最喜欢 Lambda 的补充的恰当时机。我认为它们是必要的，而且在许多情况下，是一种纯粹的好东西。

四年前我不会这么说。那时我更像是一个 FaaS 纯粹主义者。改变我想法的是多年来从工程团队那里听到的一种非常特殊的陈述，以不同的形式一遍又一遍地重复:

***我喜欢使用 Lambda，如果它……****【连接回我的本地 VPC，足够大以运行我的工作负载，让我使用与我的其他系统相同的语言或开发工具，总是温暖的，支持某种形式的共享存储，等等】*

*我对这些陈述的第一反应是:如果你不能或者不愿意接受无状态、无容器、规模到零的函数，为什么还要使用 Lambda 呢？这就是 Lambda 的整个*点*。在我听来，这就像新的 Stack 调查中的那些 Kubernetes 猫，说他们真的很喜欢吃蔬菜，如果它们只含有更多的肉。*

*但我后来明白了，这句话真正有力的部分是开头部分。这是渴望的表现。*

**我很乐意使用 Lambda，只要……**

*Lambda 和一般的无服务器计算是什么激发了这么多人的这种反应？为什么一种全新的婴儿计算范式会在各地引发如此强烈的兴趣，从小型创业公司到大型传统企业？*

*因为与任何具体的技术细节相比，无服务器计算是一种理念。用一句简单的话来表达一个想法:拥有更少，建造更多。所有的无服务器主义，所有的技术指导都归结于这个目标。Lambda 是一种令人向往的生活方式。*

*大约在 2016 年，Lambda 大大领先于其时代，在某种程度上仍然如此。但是由于新特性的增加，包括容器支持，使得更多的构建者比以前更容易获得*拥有更少，构建更多*的身份。*

*AWS 正在做的是，一个接一个地拿走*，如果只有* s *的话。*他们通过为需要的团队提供放心的选项(共享存储、调配容量)来消除对无服务器的本能异议。*我喜欢用 Lambda！**

## *指引未来*

*一些团队是否会出于困惑或惰性而使用这些特性，没有意识到他们可以构建一些更激进、更像宣言的东西？是的，我认为这是 AWS 可以提供更多帮助的领域。*

*看，Lambda 控制台一团糟——你知道，我知道，AWS 也知道。它比 2001 年的 VCR 有更多的附加功能蠕变和不连贯的 UX 路径。不管你怎么说基础设施即代码，控制台仍然是人们探索新服务的方式。这是他们如何形成他们想成为什么样的建设者的感觉。*

*控制台的重新设计是肯定需要的，但不仅仅是随意的翻新。我们需要一个支持原始宣言的 Lambda 特性的前景:代码级编程抽象、函数级部署。然后，当你挑战宣言的极限或你自己的组织约束时，仔细揭示渐进的复杂性。(有没有“回归复杂性”这种东西？因为那是当前的控制台。)*

*你想让建筑商在每次开始一个新项目时，面对更简单、更易于管理的选择。随着时间的推移，这改变了人们的看法。它不断地向他们呈现“无服务器方式”:嘿，我可以使用事件来构建它！我不需要把这个函数放在 VPC 里！违约很重要。我期待着看到 AWS 如何继续引导其客户走向成功。*

*与此同时，Lambda 最终获得了认真的采用，最终取得了胜利，因为它摆脱了标志着其早期的 FaaS 纯粹主义——而没有损害其真正的价值支柱，即*拥有更少，建造更多的进步承诺。*无服务器计算宣言必须消亡，这样无服务器的承诺才能最终实现。*