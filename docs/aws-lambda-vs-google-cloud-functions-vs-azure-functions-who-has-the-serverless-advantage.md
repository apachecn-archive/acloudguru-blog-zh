# 无服务器对决:AWS Lambda vs Azure Functions vs Google Cloud Functions

> 原文：<https://acloudguru.com/blog/engineering/aws-lambda-vs-google-cloud-functions-vs-azure-functions-who-has-the-serverless-advantage>

### TL；速度三角形定位法(dead reckoning)

说到时髦的流行语，“无服务器”可能是最受欢迎的。

无服务器模式的核心是功能即服务(FaaS)模型，这是一种服务类别，它使在云中运行代码变得非常简单，无需配置任何计算基础架构。

FaaS 确实是一个游戏规则改变者:它大大加快了部署复杂后端服务的能力，并使应用程序开发民主化。公司需要投入资本和资源将想法推向市场的日子已经一去不复返了。现在，你需要的只是一个想法、好的代码和一个主要云提供商的账户。几分钟之内，您的应用程序就可以在托管基础架构上运行，为数百万个请求提供服务，并(虚拟地)无限扩展。

本文将比较亚马逊网络服务(AWS)、微软 Azure 和谷歌云平台(GCP)的 FaaS 服务，并对现代云时代最具变革性的技术之一提供一些见解！

## 背景

任何应用程序的核心都是组成其逻辑和功能的代码。无论是最新的手机游戏，还是你典型的无聊的企业财务软件，都有一行行(有时几千行)的代码需要在某个地方运行。这个“某个地方”通常是一台服务器或几组服务器，CPU 周期在这里执行为这些应用程序提供动力的逻辑。

但是服务器，即使是虚拟云服务器，也很昂贵，维护起来也很麻烦，通常需要训练有素、经验丰富的管理员来保护和管理它们。此外，当没有用户在玩游戏或使用财务软件时，这些昂贵的服务器会无所事事，几乎是无所事事，等待新的“工作”到来。

传统的计算基础设施可能非常低效，这正是 FaaS 如此吸引人的原因。

FaaS 不用搭建复杂的基础设施(服务器、负载平衡器等)，而是让你在一个托管的计算资源池上运行你的代码，同时只为执行的持续时间付费。

FaaS 函数是事件驱动的，这意味着它们响应某些事件而运行。虽然情况并非总是如此，但这些功能通常是短命的、短暂的、无状态的和单一目的的。

下表简要总结了 AWS、Azure 和 GCP 提供的 FaaS 服务:

| **服务** | **GA 自** | **地区供货情况** |
| 自动气象站λ | 2014 年 11 月 | 全球的 |
| Azure 函数 | 2016 年 3 月 | 全球的 |
| 谷歌云功能 | 2016 年 2 月 | 全球的 |

## 定价

FaaS 受欢迎的主要原因之一是成本:它非常便宜，而且在许多情况下，几乎是免费的。也就是说，就像云中的其他东西一样，随着规模的扩大，价格标签可能会发生巨大变化。

### FaaS 成本

FaaS 成本的两个主要来源是:

1.  请求数量:通常每月每百万次请求进行计费
2.  计算时间:这是对函数生命周期的持续时间和所提供的内存量的度量，以 GB 秒为单位(在相同的持续时间内，高内存执行的成本高于低内存执行)

此外，数据传输或存储成本等其他费用可能适用，但这些费用取决于具体的使用情形。

### 定价比较

所有三大提供商都有每月免费层配额，达到配额后会产生费用。如果您正在试验或构建一个概念验证，您很可能会被包含在免费层中。

下表比较了每个提供商提供的免费层配额，以及额外的使用成本。

| **供应商** | **每月免费时长(GB 秒)** | **每月免费请求** | **每增加 100 万个请求的成本** | **每增加 1 GB 秒的成本** | **持续时间四舍五入到最接近的** |
| 自动警报系统 | 400,000 | 一百万 | $0.20 | $0.000016 | 1 毫秒 |
| 蔚蓝的 | 400,000 | 一百万 | $0.20 | $0.000016 | 1 毫秒 |
| GCP | 400,000 | 两百万 | $0.40 | $0.0000125 | 100 毫秒 |

要点:三家供应商的定价结构几乎相同。

AWS 和 Azure 有相同的定价和每月免费配额，而 GCP 每月提供额外的 100 万个免费请求，并对额外的请求有可比的定价。AWS 和 Azure 都将其持续时间四舍五入到最接近的 1 毫秒，而 GCP 四舍五入到最接近的 100 毫秒增量，这可能会增加规模的总成本。

* * *

[**获得痛苦的云词典**](https://get.acloudguru.com/cloud-dictionary-of-pain)
说云不一定要努力。我们分析了数以百万计的回复，找出了最容易让人犯错的概念。抓住这个[云指南](https://get.acloudguru.com/cloud-dictionary-of-pain)获取一些最痛苦的云术语的简洁定义。

* * *

## 功能比较

### 语言支持

世界上的编程语言比《星球大战》续集、前传和衍生剧还要多。由于显而易见的原因，每种编程语言都有优点和缺点，所以需要为正确的工作选择正确的工具。大多数情况下，云提供商在其各自的 FaaS 产品中支持大多数流行语言。

### 可用运行时间

下表显示了 AWS、Azure 和 GCP 当前支持的 FaaS 运行时:

| **服务** | **支持的语言** |
| 自动气象站λ | C#，Go，Java，Node.js，PowerShell，Python，Ruby |
| Azure 函数 | C#、F#、Java、Node.js、PowerShell、Python、TypeScript |
| GCP 云函数 | C#，F#，Go，Java，Node.js，Python，Ruby，Visual Basic |

要点:三个主要提供商之间非常相似的语言支持，唯一明显的例外是 GCP 缺乏对 PowerShell 的支持，Azure 缺乏对 Go 的支持(考虑到 Go 是由 Google 开发的而 PowerShell 是由 Microsoft 开发的，这是一个相当有趣的观察结果！)

### 自定义运行时

如果您选择的语言没有在上面列出，仍然可以“自带运行时”，这允许您用任何编程语言实现提供商的 FaaS。有关当前对自定义运行时的支持，请参见下表。

| **供应商** | **支持自定义运行时间** |
| 自动气象站λ | 是的，使用定制部署包或 AWS Lambda 层 |
| Azure 函数 | 是的，使用 Azure 函数自定义处理程序 |
| GCP 云函数 | 是的，使用自定义 Docker 图像 |

## 可伸缩性、并发性和冷启动

在 FaaS 时代的早期，最常见的用例是在转向更成熟的解决方案之前“试一试”或“模仿一下”。那些日子已经一去不复返了，今天发现全球规模的生产应用完全运行在 FaaS 后端并不罕见。

为了实现这一点，了解云提供商如何扩展 FaaS 工作负载以应对不断增长的需求，以及他们如何处理并发请求非常重要。

### 可量测性

如前所述，FaaS 函数是事件驱动的，因此当接收到一个事件时，该函数的一个实例就会启动并处理请求。该实例保持活动状态以处理后续事件，如果在特定时间范围内没有接收到任何事件，它将被回收。

所有这三个提供商都宣传几乎无限制的自动扩展，尽管这里可能还有其他因素在起作用，这些因素将在下面讨论。

### 并发

当一个 FaaS 实例正在处理一个请求，并且收到另一个请求时，第二个实例会加速处理这个额外的请求(实例一次只处理一个请求。)并发性是在任何给定时间可以同时运行的功能的数量。

| **服务** | **并发** |
| 自动气象站λ | 标准:每个地区 1000(软限制)
保留:变化
供应:变化 |
| Azure 函数 | 没有公布的并发限制 |
| GCP 云函数 | 没有公布的并发限制 |

AWS 是唯一一个提供高度定制的并发管理选项的提供商，而 Azure 和 GCP 在如何处理并发执行方面有点模糊。

### 冷启动

鉴于 FaaS 作为一项技术相对年轻，它有许多诋毁者和反对者。到目前为止，他们最喜欢的批评是“冷启动”的概念。

那么，什么是冷启动呢？

想象一下这个熟悉的动作电影场景:我们的英雄以每小时 120 英里的速度在高速公路上行驶，可能是在拯救一些生命的路上，当他在休息时，看着报纸，从一名毫无防备的高速公路巡警身边飞驰而过。当骑警摸索着启动引擎，并以高速追赶时，我们的英雄已经在数英里之外了，骑警需要一些时间才能赶上。

同样，处于非活动状态的 FaaS 实例将需要一些额外的时间来响应请求。这种最初的延迟被称为冷启动。

与已经处于活动状态并接收到请求的 FaaS 实例相比，在这种情况下，没有初始延迟，实例几乎可以立即开始处理请求。以我们的例子来说，这就好比一名高速公路巡警在高速公路上以正常速度行驶时被一名超速行驶的司机超过。在这种情况下，士兵可以非常迅速地加速并在几秒钟内追上去。

虽然云提供商不公布他们的冷启动统计数据，但下表显示了行业分析师观察到的[估计平均值:](https://mikhail.io/serverless/coldstarts/big3/)

| **服务** | **平均冷启动时间(秒)** |
| 自动气象站λ | <1 |
| Azure Functions | > 5 |
| GCP 云函数 | 0.5 – 2 |

冷启动可能会影响对延迟非常敏感的 FaaS 工作负载的性能，但有一些方法可以减轻这种影响，并且它对 Azure 平台的影响似乎比它的两个竞争对手更大。此外，AWS 现在提供“供应并发”作为一种方法来消除 Lambda 的冷启动。我们将在本文后面更详细地讨论这个特性。

* * *

[**自动化 AWS 成本优化**](https://go.acloudguru.com/AWS-Cost-Optimization-Webinar)
AWS 为您的企业提供了前所未有的价值，但经济高效地使用它可能是一项挑战。在这个[免费点播的网络研讨会](https://go.acloudguru.com/AWS-Cost-Optimization-Webinar)中，您将了解 AWS 成本优化工具和策略的概况。

* * *

## 配置和性能

并非所有功能都是相同的，因此不同的工作负载可能需要不同的设置来优化性能。

### 记忆

根据代码对资源的需求程度，必须相应地调整内存。如果分配的内存太低，一个函数将需要更长的时间来执行，并可能超时，但如果内存设置得太高，您可能会为未使用的资源付出过多的代价。

云提供商提供不同的最大内存配置，而 CPU 能力是根据所选内存量线性自动配置的。

| **服务** | **内存** |
| 自动气象站λ | 128 MB–10240 MB |
| Azure 函数 | 128 MB–1500 MB(消费计划)
128 MB–14000 MB(高级和专用计划) |
| GCP 云函数 | 128 MB–4096 MB(128 MB 的倍数) |

值得注意的是 GCP 云功能可以配置的最大内存:4096 MB，这个限制比 AWS 和 Azure 提供的要低得多。

### 执行时间

FaaS 的另一个可配置方面是最大执行时间。虽然大多数功能只需几秒钟(或更短时间)即可执行，但一些密集型工作负载可能需要更长时间，大约几分钟甚至几小时(例如，密集型机器学习或数据分析工作负载)。

下表显示了每个云提供商提供的最大超时时间:

| **服务** | **最大超时** |
| 自动气象站λ | 15 分钟 |
| Azure 函数 | 5 分钟(消费计划)
30 分钟(高级和专用计划) |
| GCP 云函数 | 9 分钟 |

需要注意的是，增加超时时间并不总是解决问题的办法，应该结合调整内存来考虑。

* * *

[**后 COVID DevOps:加速未来**](https://get.acloudguru.com/post-covid-devops-accelerating-future-webinar) COVID 如何影响——甚至加速——工程团队的 DevOps 最佳实践？[观看这个免费的点播网络研讨会](https://get.acloudguru.com/post-covid-devops-accelerating-future-webinarhttps://get.acloudguru.com/post-covid-devops-accelerating-future-webinar)与 DevOps 领导者进行小组讨论，我们将在后 COVID 时代探索 DevOps。

* * *

## 管弦乐编曲

如前所述，部署在 FaaS 上的功能本质上是无状态的。换句话说，函数不知道其他函数或其他函数的执行结果。

甚至同一个函数的调用也是完全相互独立的。这种无状态范式使得 FaaS 如此可扩展和易于配置。

虽然无状态方法对于执行大量短期和单一用途的功能(例如，网站上的联系人表单)来说非常优秀，但它使得构建任何有意义的复杂应用程序(通常需要某种状态管理)变得非常困难。意识到这一点，云提供商构建了编排服务，将这些功能作为工作流中的“步骤”进行集成，其中一个步骤的输出可以作为输入传递给另一个步骤。这使得在完全无服务器的方法中构建相当复杂的工作流成为可能！

下表列出了每个提供商提供的业务流程服务。这些服务通常也非常具有可伸缩性，并且具有许多超出本文范围的特性:

| **供应商** | **编排服务** |
| 自动警报系统 | AWS 阶跃函数 |
| 蔚蓝的 | 持久的 Azure 功能 |
| GCP | GCP 工作流程 |

## HTTP 集成

FaaS 服务的强大之处在于它们是事件驱动的，这意味着某些“有趣的事件”可以触发函数的执行。

“有哪些有趣的事件？”你可能会问。

从简单的 cron 计划(例如:每天午夜运行该功能)到云提供商生态系统中的其他服务(例如，当文件上传到云存储时运行该功能)。但是最流行的场景之一是将 FaaS 与 HTTP 端点集成在一起。

具有集成 FaaS 后端的静态 web 前端(即 HTML/CSS/JavaScript)是构建无服务器 web 应用程序非常常见和流行的架构模式。

虽然这三个提供商都支持 HTTP 集成，但 AWS 需要提供和配置单独的资源 API Gateway，这也是单独计费的。Azure 和 GCP 有一个更加精简的 HTTP 集成。

| **服务** | **HTTP 集成支持** |
| 自动气象站λ | 是，需要 API 网关(单独计费) |
| Azure 函数 | 是的，开箱即用 |
| GCP 云函数 | 是的，开箱即用 |

## 托管计划

如前所述，考虑到可用性和延迟方面的各种需求，云提供商通过在其 FaaS 产品中提供不同级别的可用性来应对。

AWS Lambda 在历史上是作为一个基本的托管计划出现的，但最近 AWS 开始提供供应的并发性，这可以确保函数被初始化并准备好响应事件，将可怕的冷启动时间缩短到仅仅几毫秒。Azure 提供了更复杂的托管选择，而 GCP 只是提供了一个通用的方案。

| **服务** | **托管计划** |
| 自动气象站λ | 常规
供应并发 |
| Azure 函数 | 消费
溢价
专用 |
| GCP 云函数 | 一般 |

## 底线

当谈到比较三大云提供商的 FaaS 产品时，有一点是非常明显的:它们在功能和成本方面极其相似和可比。

虽然 AWS Lambda 是三者中更成熟和最受欢迎的，但 Azure Functions 似乎有一些非常相似的功能，在某些方面，有更多的选项来适应边缘情况。GCP 云函数少了一些花里胡哨的东西，但仍然可以与其他两个相媲美。

俗话说，细节决定成败。在比较这三种 FaaS 服务时，很可能还有其他因素需要考虑。但无论是哪种情况，这里的关键要点是，FaaS 将继续存在，它是一种真正的变革性技术，只会继续获得采用，所以如果你还没有，请确保你正在利用它！

* * *

**提升您的云计算生涯**

希望获得认证或提升您的云计算职业生涯？通过 ACG 的课程、实验室、学习路径和[沙盒软件](https://acloudguru.com/platform/cloud-sandbox-playgrounds)学习按需云技能。