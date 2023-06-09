# 为什么云迁移会停滞或失败

> 原文：<https://acloudguru.com/blog/business/why-cloud-migrations-get-stuck>

让我们一开始就把这个放在桌面上:[许多云采用项目失败了——](https://esj.com/articles/2014/06/26/cloud-projects-fail.aspx)和[因为许多不同的原因](https://go.acloudguru.com/cloud-adoption-mistakes-ebook)。这并不是对云的攻击，这只是意料之中的事。IT 项目总是非常令人担忧。

在我的职业生涯中有一段时间，这让我困惑不已。一个充满聪明人的大公司，怀着最美好的愿望，着手实现一个显而易见的好处——现代化他们的 IT 基础设施——却在多年的努力后完全没有进展，这是怎么回事？

云迁移可能会很棘手。但是在与许多公司就云计划进行合作之后，我已经开始了解一些模式。看看您是否能在下面的图片中认出您自己的迁移项目:

##### **枯树修剪**

一些企业采用云只是为了更好地运行他们的遗留系统。也许他们是为了降低成本，或者退出数据中心游戏，或者缓解一些规模压力。这些组织希望在不改变其系统、架构或人员的情况下获得云的优势。

这些类型的迁移通常被称为[“提升并转移”](https://faasandfurious.com/33)，没有人将提升并转移作为最终目标。总有一种假设，更好的架构，v2，refactor，就在眼前。

但是，提升和转移迁移的惊人之处在于，它不一定是通向更好的云未来的垫脚石。就像修剪枯树一样，它实际上会让事情变得更糟。

*![Dead Tree](img/653da6df66a8885d29dc8ac56747d2ed.png)*

就像将应用程序原封不动地迁移到云中一样，修剪一棵枯树并不困难，你很快就能看到结果。坏消息是，这毫无意义，除非这是砍掉枯木，种下一棵全新的树的第一步。新树需要一段时间才能生长。

“搬来搬去”的迁移可能是一种延迟策略，而不是向前迈出的一步。而且延迟是昂贵的，尤其是当它们拖上几年的时候。随着坏习惯在云中积累以支持遗留系统，云本应提供的优势就像高高的树枝一样遥不可及。

##### **小行星农场**

小行星农民看起来比死去的树木修剪工更像云土著。他们甚至可能使用花哨的云计算工具和服务。一项小行星养殖业务将会有整队的人用无服务器、Kubernetes 和[还有 CNCF 昨天咳出的任何东西](https://www.cncf.io/sandbox-projects/)来建造。

但是当你仔细观察时，你会发现他们所有狂热的创新都发生在他们关键任务系统的外围。没有人努力将大型 Oracle 数据库从传统数据中心中取出，或者将大数据从 Oracle 数据库中取出。取而代之的是这种持续的项目边缘，这些项目将一些计算拉入云中进行报告，或者运行元工作负载来管理永远不会实现的未来状态系统。

![Asteroid](img/849fc4d290f4d5e7de1616e9feb1a3cc.png)

小行星农民积累了大量的云账单，并在尖端会议上发言，但最终几乎没有商业价值可言。因为什么都没有发生，最终那些在简历中添加了“云原生”项目的工程师们会继续做下一件事，而企业会退回到维护模式。

我看到许多小行星养殖公司对云有点失望。

##### **甜甜圈洞**

与小行星农民不同，甜甜圈洞带着严肃的战略意图进行云迁移。他们知道[建立云卓越中心](/blog/business/3-phases-of-cloud-adoption?_ga)是云成功的先决条件。因此他们建立了架构评审委员会和最佳实践。他们实施中央 CI/CD 管道和安全门。他们创建内部维基页面，解释整个企业应该如何采用云。然后他们坐下来，等待它发生。

![Donut](img/50d0cc60b5fcce9b65e13c2d2aeac66a.png)

然而，不知何故，当你快进几年时，企业作为一个整体并没有在采用云方面取得多大进展。每个人都在做他们的遗产。也许有些人对中央云团队的想法有所认同，但并没有紧迫感。云卓越中心最终被一个厚厚的，耐嚼的可怕的甜甜圈所包围，所有这些精心制定的计划甚至可能不存在。

##### **培养皿**

枯树果园、小行星农场和甜甜圈洞有什么共同点？他们都试图将云移植到现有的技术和组织结构上，而不承担修复结构本身的棘手工作。

对于我们这些经历过这些问题的人来说，诱惑是归咎于大组织本身的一些基本属性:政治、惰性、筒仓。但是筒仓并没有什么错:它们是优化职能部门以实现特定结果的有效方式。当旧的筒仓不再符合现实时，问题就来了，这就是你需要[转型变革](https://blog.container-solutions.com/a-cloud-native-transformation-scenario-to-avoid-lift-and-shift)的地方。

我见过的组织成功地采用了云—它们确实存在！—采取有机的方法来改变。是的，他们建立了卓越的云中心，但他们不会让它变得孤立。相反，它们在传统文化中培养向外传播的创新细胞，就像青霉素在培养皿中传播一样。

![Cloud Center](img/f37eea51b83a12b0e6a4b24a33d161b3.png)

这种方法没有捷径可走。你需要全面的教育、管理层的支持和清晰的成功标准，以及对过程混乱的容忍度，才能起步。但是，健康的云迁移需要的正是这些。

![Cloud Migration](img/6a0efa9268dfc8fed8a1bd2e1df29d5d.png)

* * *

##### 了解云专家如何转变您的文化，并引导您在云中取得成功。

* * *

*Forrest Brazeal 是 AWS 无服务器英雄* *和企业架构师，他领导了从初创公司到财富 50 强企业的云采用计划。*