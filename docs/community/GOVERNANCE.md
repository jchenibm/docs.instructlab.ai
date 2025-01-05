# InstructLab 治理

以下文档概述了 InstructLab 项目治理的运作方式。

## InstructLab 项目

InstructLab 由几个项目组成，这些项目被定义为具有不同发布周期的代码库和服务。这些项目共同支持大模型开发。目前，这些项目包括：

* [`ilab` 命令行界面 (CLI) 工具](https://github.com/instructlab/instructlab)。这个仓库负责 `ilab` 命令行界面 (CLI) 工具。
* [分类树](https://github.com/instructlab/taxonomy)。这个仓库负责分类树，它允许你创建用你的数据调优的模型。

## 治理结构和路线图

InstructLab 项目有一个两级治理结构，包括监督委员会和 [项目维护者](https://github.com/instructlab/community/blob/main/MAINTAINERS.md)。

除非另有说明，决策应该始终从项目治理的最本地级别开始。例如，只影响一个项目的决策，比如分类仓库而不是 `ilab` CLI 工具，可以在分类项目内进行。虽然不同项目团队之间的沟通很重要，因为它们都是相互关联的，但次要决策不需要组织范围的共识，可以在项目级别推进。

维护者身份的变更和其他治理变更目前在 InstructLab 社区 Discord 和 Slack 服务器上公布。加入 Discord 服务器的说明可以在 [这里](https://github.com/instructlab/community/blob/main/InstructLab_DISCORD_GUIDE.md) 找到，Slack 服务器的说明可以在 [这里](https://github.com/instructlab/community/blob/main/InstructLab_SLACK_GUIDE.md) 找到。变更也会通过 [公告邮件列表](https://github.com/instructlab/community/blob/main/Collaboration.md#email-lists) 公布。

## 项目维护者概述

项目维护者专注于单个代码库、一组相关代码库、服务（例如，网站）或支持其他项目的项目（如营销或社区管理）。

项目维护者负责围绕代码开发和发布的活动、他们拥有的任何服务的运营，或执行其项目所需的任务（例如，社区管理或设置活动展台）。代码的技术决策由项目维护者负责，除非有涉及多个维护者组且这些组无法解决的决策。这些情况可以上报给监督委员会。

要被视为 _活跃的项目维护者_，需要与至少一个活跃的、非归档的项目相关联。如果只列在归档项目中，他们将成为 _荣誉维护者_ 并不再有资格成为组织维护者。

项目维护者不需要是软件开发人员；但是，他们必须是重要的贡献者。例如，如果一个仓库是用于文档，那么项目维护者可以是编辑或技术作者。

晋升到项目维护者职位、移除或退出，以及职责的详细信息在 [贡献者角色](https://github.com/instructlab/community/blob/main/CONTRIBUTOR_ROLES.md) 中有详细说明。当前维护者的列表可以在 [这里](https://github.com/instructlab/community/blob/main/MAINTAINERS.md) 找到。

## InstructLab 监督委员会概述

项目启动时的初始监督委员会由 InstructLab 项目的创始赞助者任命。这个引导委员会将任职直到使用该组确定的流程和时间进行第一次监督委员会选举。

监督委员会成员的列表可以在 [MAINTAINERS.md](https://github.com/instructlab/community/blob/main/MAINTAINERS.md#oversight-committee) 中找到。

监督委员会由 3 到 7 名 InstructLab 项目的领导者组成。这些成员将负责监督整个项目及其健康状况。它还将包括一名选定的主席成员，负责设定议程和召集会议。这些会议可以根据监督委员会的决定公开或私密进行。

监督委员会负责以下职责：

* 维护项目的使命、愿景、价值观和范围
* 根据需要完善治理和章程
* 做出项目级决策，包括制定适用于所有组件的技术政策
* 解决负责团队被阻止时上报的项目决策
* 管理 InstructLab 品牌
* 控制对 InstructLab 资产的访问，如源代码仓库和托管
* 任命 [行为准则委员会][committee] 成员
* 决定哪些项目是 InstructLab 项目的一部分
* 监督安全问题的解决和披露
* 管理与项目相关的财务决策

### 监督委员会选举流程草案

!!! note
    本节是草案。初始监督委员会有责任最终确定这个流程。

监督委员会将使用以下流程选举和维护：

任何活跃（非归档）InstructLab 组织项目的项目维护者都有资格担任组织维护者。每年，监督委员会将重新选举。选举将包括提名期和选举期。任何对 [InstructLab GitHub](https://github.com/instructlab) 组织下的任何仓库做出贡献的人都可以提名一个活跃项目的合适项目维护者。

选举将按照以下流程进行：

1. 提名期将持续三周。这个期限从组织维护者职位空缺的第二天开始。

2. 提名必须在 InstructLab [社区邮件列表](https://github.com/instructlab/community/blob/main/Collaboration.md#email-lists) 上进行。

3. 在被提名的个人同意成为监督委员会候选人后，项目维护者将进行投票。投票期将开放至少三个工作日。它将保持开放直到 [超级多数](https://en.wikipedia.org/wiki/Supermajority#Two-thirds_vote) 的项目维护者投票。只有活跃项目的当前维护者有资格投票。

4. 当被提名的个人数量与空缺数量相匹配时，每个人必须从投票者中获得超级多数的 _赞成_ 票。

5. 当个人数量多于空缺职位时，投票将使用 _排序选择_ 投票方法，如 [康多塞](https://en.wikipedia.org/wiki/Condorcet_method)。

### 维护者或监督委员会角色的辞职或离职

项目维护者或监督委员会成员可以辞职或可能被开除，如下所示：

* 维护者或监督委员会成员可以通过电子邮件退出。在 7 个日历日内，将通过 InstructLab [社区邮件列表](https://github.com/instructlab/community/blob/main/Collaboration.md#email-lists) 通知组织贡献者和维护者。

* 在监督委员会成员退出后，他们成为荣誉维护者。

* 维护者和委员会成员必须在项目中保持活跃。如果监督委员会成员或维护者超过 3 个月无响应或不活跃，可以通过超级多数投票将其移除。

* 违反 [行为准则](https://github.com/instructlab/community/blob/main/CODE_OF_CONDUCT.md) 的维护者和监督委员会成员可以通过剩余监督委员会成员的超级多数投票将其移除。

## InstructLab 组织级别的决策制定

通常，InstructLab 项目有两种决策方法：通过懒惰共识或投票。

默认的决策过程是 [_懒惰共识_](http://communitymgt.wikia.com/wiki/Lazy_consensus)。这意味着只要没有人反对，任何决定都被认为得到了做出决定的团队的支持。在任何共识决定中，沉默就是隐含的同意，等同于明确的同意。可以随时表明明确的同意。

当无法达成共识时，维护者可以要求对决定进行 [多数](https://en.wikipedia.org/wiki/Majority) 投票。

许多日常项目维护可以通过懒惰共识模型完成。

第二种决策过程是通过投票完成。以下是必须由适当机构召集投票的示例项目：

* 任命或移除 [行为准则委员会][committee] 成员（监督委员会的超级多数）
* 执行需要严厉谴责的 [行为准则](https://github.com/instructlab/community/blob/main/CODE_OF_CONDUCT.md) 决定（行为准则委员会的多数）
* 因不活跃以外的任何原因移除 [维护者](https://github.com/instructlab/community/blob/main/MAINTAINERS.md)（监督委员会的超级多数）
* 对治理（本文档）的非琐碎更改（监督委员会的超级多数）
* 许可和知识产权更改，如新的标志或文字标记（监督委员会的多数）
* 添加、归档或移除项目（监督委员会的多数）

其他决定可以在 InstructLab [社区邮件列表](https://github.com/instructlab/community/blob/main/Collaboration.md#email-lists) 上提出并提交决定。任何人都可以随时这样做。默认情况下，任何被提交投票的决定都将由监督委员会进行 _简单多数_ 投票。

## 行为准则

InstructLab 的 [行为准则](https://github.com/instructlab/community/blob/main/CODE_OF_CONDUCT.md) 由 [行为准则委员会 (CoCC)][committee] 执行。该委员会将由监督委员会使用超级多数投票任命和移除。

CoCC 负责调查、评估和向适当机构建议已证实的行为准则事件的补救措施。CoCC 将根据恢复性正义而不是惩罚的原则来判断可能的违规行为。InstructLab 内的所有团队都有义务支持 CoCC 的补救建议。

当前的 CoCC 成员可以在 [行为准则委员会][committee] 页面上找到。

可能的行为准则违规应通过 [行为准则电子邮件别名](https://github.com/instructlab/community/blob/main/Collaboration.md#email-lists) 向行为准则委员会报告。

## 开发者原创证书 (DCO) 和许可证

InstructLab 项目将使用以下许可证和贡献者协议：

* [Apache 2.0](https://opensource.org/licenses/Apache-2.0) 用于代码
* [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode) 用于文档
* [开发者原创证书](https://developercertificate.org/) 用于新的贡献

## 对本治理的修改

本治理可以通过监督委员会的超级多数投票进行修改。

不引入政策变更的琐碎变更可以由监督委员会的两名成员批准。

[committee]: https://github.com/instructlab/community/blob/main/CODE_OF_CONDUCT_COMMITTEE.md
