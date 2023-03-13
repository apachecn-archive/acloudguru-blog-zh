# 云成本管理:如何减少和控制云支出

> 原文：<https://acloudguru.com/blog/business/cloud-cost-management>

***更新于:***2022 年 11 月 17 日

随着预算季节的临近，云支出问题成为焦点。根据 Gartner 的数据，[云支出](https://www.gartner.com/en/newsroom/press-releases/2022-04-19-gartner-forecasts-worldwide-public-cloud-end-user-spending-to-reach-nearly-500-billion-in-2022)正以每年 20%的速度增长，但并非所有组织都获得了投资回报。

* * *

## 目录

* * *

## 什么是云成本管理？

顾名思义，云成本管理(CCM)就是通过监控和集中化来有效管理云成本。它包括检查您的云成本(即内存、存储、流量等。)并定期优化它们以尽可能减少支出。这也被称为云成本优化。

那么，*为什么*这很重要呢？嗯，如果你曾经不幸发现，[云成本会很快失控](https://acloudguru.com/blog/business/cloud-cost-optimization)，尤其是在没有集中管理系统的情况下！这可能发生在个人在不同的团队中创建实例的业务中。有些东西被遗漏了，成本迅速膨胀，等到有人注意到的时候，企业已经背负了一大笔账单。哎哟！

与大多数事情一样，预防是最好的治疗方法，这正是云成本管理策略能够扭转局面的地方。除了帮助阐明工具和服务的最佳实践之外，一个好的 CCM 策略还可以帮助您监控您所有的花费都到哪里去了。这允许你不断地重新评估，这样你就可以在控制成本的同时最大限度地利用你的资源。

* * *

## **改变职业，改变企业**

学得更快。动作快点。借助 AWS、Microsoft Azure、Google Cloud 等领域的课程和实际动手实验室，立即实现转型。

* * *

### 有哪些云成本模型？

云成本模型是指跨云平台及其服务使用的不同定价模型。有许多不同的模式，但它们可以很容易地分为四种类型:**现收现付**(也称为按需)、**基于订阅的**、**预约实例**和**现场实例**。

很可能你会使用这些的组合，因为每一个都有自己的优点和缺点。因此，让我们仔细看看每种云成本模型！诚然，这不是一个引人入胜的话题，但它们值得你花时间和金钱去了解。

#### 现收现付/按需付费

这种云成本模式是按使用量收费的。这意味着你要为每单位计算能力、存储、网络或其他资源付费。如果您需要灵活性，这可能非常有用，因为您可以轻松地扩展和缩减您的资源。但是，随着您继续添加资源，成本会很快变得令人望而却步。

#### 基于订阅

云平台可以在一段时间内为预先确定的工具和服务包提供固定或预付费订阅。这通常适用于较大的公司，如果承诺更长的时间，可以获得更大的折扣。

这种模式对于结合了多种硬件和软件工具和服务的公司来说最有意义。如果您持续达到使用容量，您将从中获得最大收益。然而，如果你经常做不到这一点，最好还是寻找另一种选择。

#### 保留实例

保留实例为长期(通常为一年或三年)使用特定计算能力提供了大幅折扣。这可以比按需购买的价格低 70%,因此当您很好地了解在可预见的未来您将需要多少计算时，这是一个很好的选择。

此外，您只需支付总容量，而不是实例数量，因此这意味着您可以根据需要在同一系列中更改实例大小。

对于您的容量需求可能会定期变化的服务，不建议这样做，但是对于那些日常的核心系统负载，使用保留的实例可能会很有用，并且可能会与那些峰值负载的按需服务结合使用。

* * *

[![Complete guide to the Cloud and Dictionary ](img/93ebf63b88ab7fbd48705a01952ba688.png)](https://get.acloudguru.com/cloud-dictionary-of-pain)

[**获得痛苦的云词典**](https://get.acloudguru.com/cloud-dictionary-of-pain)
说云不一定要努力。我们分析了数以百万计的回复，找出了最容易让人犯错的概念。抓住这个[云指南](https://get.acloudguru.com/cloud-dictionary-of-pain)获取一些最痛苦的云术语的简洁定义。

* * *

#### 储蓄计划

Azure、AWS 和 GCP 与 reserved instances 并非完全不同，它们都提供自己的储蓄计划，需要一年或三年的使用承诺。他们都为计算服务提供了这些，AWS 也为 EC2 实例和 SageMaker 提供了这些。

值得注意的是，GCP 的版本被称为承诺使用折扣(CUD)，但遵循与其他提供商类似的承诺时间表和百分比折扣。

#### 定点实例

你会得到类似的高折扣，有时甚至更高(高达 90%)。然而，有一个陷阱！这些都是云提供商廉价出售闲置产能的时候，但是*可以随时*停止。正因为如此，它们只对那些可以无问题中断的进程有意义，或者如果你想做，比如说，一天的高负载处理。

* * *

云成本管理工具可帮助您监控云服务的使用情况和支出，其中一些工具会就权限、安全性和削减成本的方式提出建议。每个主要的云提供商都有自己的免费服务，以及对多云设置有意义的付费第三方选项。

### 亚马逊云观察

Amazon CloudWatch 是一款 AWS 云成本管理工具，可以监控您的整个堆栈，包括应用程序、基础架构和服务。它提供自动和自定义日志，并提供可操作的见解，您可以使用这些见解来降低成本和使用量。它还有许多可以采取的自动操作，比如自动缩放，或者基于操作变化和警报的规则。

[了解更多关于亚马逊 CloudWatch 的信息。](https://aws.amazon.com/cloudwatch/)

### Azure 成本管理和计费

Azure 云管理工具是微软成本管理和计费。它的工作方式与 CloudWatch 非常相似，因为它是一套工具，可以帮助报告和分析您的成本。您还可以使用预算警报、异常警报和计划警报等警报来监控您的成本。你将通过诸如 [Azure 价格计算器](https://azure.microsoft.com/pricing/calculator/)或 [Azure 顾问成本建议等工具获得如何优化成本的建议。](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-opt-recommendations)

[了解有关微软成本管理和计费的更多信息。](https://learn.microsoft.com/en-us/azure/cost-management-billing/cost-management-billing-overview)

GCP 成本管理

与其他云平台一样富有想象力，GCPs 成本管理工具被称为…成本管理。除了报告、仪表板、预算和警报，您还可以使用该工具来构建和组织您的资源和权限。您还将获得[智能建议](https://cloud.google.com/recommender)，以优化您的成本和使用。

### 了解更多关于 GCP 成本管理的信息。

来自 VMWare 的云健康

由 VMware 提供的 CloudHealth 是一款第三方工具，可提供与云提供商成本管理工具类似的服务。主要区别在于，它支持所有主要的云提供商，以及 Oracle 云和 VMware(当然)。

### 与其他人一样，您可以收集报告，其中包含优化使用和成本的建议，您可以自动执行任务，并且可以通过权限加强安全性。如果你是一家多云公司，你可能会选择像 CloudHealth 这样的第三方提供商，这在最近变得越来越普遍。

[了解更多关于 CloudHealth 的信息。](https://cloudhealth.vmware.com/)

还有很多其他的第三方云成本管理工具，比如 [CloudZero](https://www.cloudzero.com/) 、[density](https://www.densify.com/solutions/cloud-cost-optimization)、 [Virtana Optimize](https://www.virtana.com/products/optimize/) 等等。如果您有一个多云设置，这些可能值得检查和比较特性。

[**自动化 AWS 成本优化**](https://go.acloudguru.com/AWS-Cost-Optimization-Webinar)
经济高效地使用 AWS 可能是一项挑战。在这个[免费点播的网络研讨会](https://go.acloudguru.com/AWS-Cost-Optimization-Webinar)中，您将了解 AWS 成本优化工具和策略的概况，如[数据存储优化](https://acloudguru.com/course/introduction-to-optimizing-data-storage-in-aws)。

您如何降低云成本？

* * *

有许多方法可以降低您的云成本:自动扩展您的实例，为大折扣预留容量，识别并删除未使用的实例，以及合理调整计算服务的规模。大多数云成本管理工具可以帮助解决其中的许多问题，并且有一个良好的云成本管理策略。

* * *

## 让我们来看看这些降低成本的选择吧！

自由层

许多云提供商提供免费的工具和服务层，你可以在承诺之前免费试用这些工具和服务，或者每月(或其他时间段)免费试用一定数量的工具和服务。这是在购买前尝试的好方法，或者如果对您的工作负载有意义的话，围绕空闲层限制来规划您的使用。

### 自动缩放

这基本上允许你在需要的时候[扩大资源](https://acloudguru.com/blog/engineering/scalability-cloud-computing)，在不需要的时候再缩小。这有助于减少您的支出，尤其是那些现收现付的资源。

### 为更高的折扣预留容量

尽可能使用预订或现货(如上所述),可以为您节省高达 90%的常规金额。这对于所有的服务来说是不可能的，但是对于长期运行且使用一致的服务来说，它可以很好地工作。

### 删除未使用的实例

这听起来很简单，删除任何没有被充分利用或者根本没有被使用的实例。尽管有时识别这些实例可能不那么简单，尤其是在大型组织中。这就是成本管理工具发挥作用的地方——这将在下面讨论。

### 电力调度

这是指在不需要的时候关闭不必要的实例。您可能有一些 24/7 全天候运行的应用程序，但是值得深入研究一下，看看这是否适合您的所有实例。从长远来看，即使只有少数几个实例能够支持 power schedule，也可以为您节省大量资金。

### 合理确定资源规模

合理调整计算等资源的规模，意味着确保您选择的实例能够满足您的需求。随着时间的推移监视使用情况将有助于您了解您是否未充分利用实例，然后您可以用更合适的实例来替换它们，从而节省资金。

### 自动化这些成本降低方法的一个很好的方法是使用云成本管理工具，就像上面讨论的那些。它们提供的报告将允许您确定可以通过调整规模甚至完全删除来优化的资源。它们可以自动扩展您的实例，并在运行不顺利时提醒您。最重要的是，它们通常可以免费使用。

云成本管理战略

为您的组织创建云成本管理策略是阻止成本失控的一个好方法。它应该包括权限层次结构的最佳实践、设置新实例和资源、报告和分析计划以及其他相关策略，以帮助集中和监控您的使用和支出。确保你的战略具有良好的可扩展性也是很好的，因为组织很少会永远保持相同的规模。

### 云成本管理的更多资源

如果您希望了解更多关于 CCM 的信息，我们强烈建议您查看以下资源:

## Further resources for cloud cost management

If you’re looking to learn more about CCM, we highly recommend checking out the following resources: