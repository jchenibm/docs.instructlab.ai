# InstructLab 常见问题解答

最后更新：2024 年 10 月

> [!TIP]
> AI 是一个快速发展的领域，包含许多专业术语。在开始阅读文档之前，你可能希望先阅读 [术语表](https://docs.instructlab.ai/community/FAQ/#glossary)。

## 目录

- [文档概述](#document-summary)
- [常见问题](#general-faq)
  - [什么是 InstructLab？](#what-is-instructlab)
  - [什么是 LAB？](#what-is-lab)
  - [InstructLab 是如何工作的？](#how-does-instructlab-work)
  - [InstructLab 项目的目标是什么？](#what-are-the-goals-of-the-instructlab-project)
  - [我如何贡献？](#how-can-i-contribute)
  - [我在使用 `ilab` CLI 工具时遇到问题。我该怎么办？](#im-having-problems-with-the-ilab-cli-tool-what-should-i-do)
  - [为什么我要贡献？](#why-should-i-contribute)
  - [通过 InstructLab 项目，我在为哪些大语言模型 (LLM) 做贡献？](#what-large-language-models-llms-am-i-contributing-to-through-the-instructlab-project)
  - [什么是 Merlinite-7b？](#what-is-merlinite-7b)
  - [什么是 Granite-7b-lab？](#what-is-granite-7-lab)
  - [什么是"技能"？](#what-is-a-skill)
  - [什么是"知识"？](#what-is-knowledge)
  - [项目是否在寻找特定类型的技能贡献？](#is-the-project-looking-for-certain-types-of-skill-contributions)
  - [技能提交的接受标准是什么？](#what-are-the-acceptance-criteria-for-a-skills-submission)
  - [知识提交的接受标准是什么？](#what-are-the-acceptance-criteria-for-a-knowledge-submission)
  - [我如何提交技能或知识？](#how-can-i-submit-a-skill-or-knowledge)
  - [提交拉取请求后会发生什么？](#what-happens-after-you-submit-a-pull-request)
  - [如何审查提交？](#how-are-submissions-reviewed)
  - [我的拉取请求需要多长时间才能被审查？](#how-long-will-it-take-for-my-pull-request-to-be-reviewed)
  - [如果我的拉取请求被接受，我的更改需要多长时间才能出现在下一个模型更新中？](#if-my-pull-request-is-accepted-how-long-will-it-take-for-my-changes-to-appear-in-the-next-model-update)
  - [InstructLab 的软件许可证是什么？](#what-is-the-software-license-for-instructlab)
  - [我是否必须根据 Apache 2.0 许可证授权代码提交给 InstructLab？](#am-i-required-to-license-code-submissions-to-instructlab-under-the-apache-20-license)
  - [我的贡献需要提交数据和代码。什么数据是允许包含的？](#my-contribution-requires-submitting-data-along-with-code-what-data-is-permissible-to-include)
  - [在哪里可以下载 InstructLab 的更新模型？](#where-can-i-download-updated-models-of-instructlab)
  - [我有关于项目的问题。我应该去哪里？](#i-have-a-question-about-the-project-where-should-i-go)
  - [使用 InstructLab 的软件和硬件要求是什么？](#what-are-the-software-and-hardware-requirements-for-using-instructlab)
- [术语表](#glossary)
- [其他资源](#additional-resources)

## 文档概述

本页面作为 InstructLab 项目的综合常见问题解答，详细说明了它如何工作、如何开始贡献以及项目背后的目标。主要信息包括：

- **InstructLab 概述**：这个开源项目允许用户通过贡献技能和知识来与 Granite-7b 社区 AI 大语言模型 (LLM) 进行交互和训练。
- **LAB 方法**：一种基于合成数据的大语言模型调优方法，包括分类驱动的数据管理流程、合成数据生成器和带有重放缓冲区的两阶段训练。在概述该方法的 [Large-Scale Alignment for ChatBots](https://arxiv.org/abs/2403.01081) 论文中了解更多信息。
- **贡献流程**：[贡献者可以通过创建 YAML 文件并在本地测试更改来为大语言模型添加技能或知识](https://docs.instructlab.ai/taxonomy/)，然后向 InstructLab 的 GitHub 分类仓库提交拉取请求。贡献者也可以 [为 InstructLab 工具](https://github.com/instructlab/instructlab/blob/main/CONTRIBUTING/CONTRIBUTING.md) 和库代码库做出贡献。
- **项目目标**：实现 AI 和大语言模型贡献的民主化。

## 文档免责声明

目前有三个仓库包含对用户开始使用项目至关重要的文档：

- [Community](https://github.com/instructlab/community) 这个仓库分享了 InstructLab 在社区中的活动和协作细节，包括关于项目、沟通渠道和人员流程的最新信息。
- [`ilab` 命令行界面 (CLI) 工具](https://github.com/instructlab/instructlab)。这个仓库负责 `ilab` CLI 工具。它提供了如何下载 `ilab` CLI、如何为 `ilab` CLI 工具做贡献等信息。
- [分类树](https://github.com/instructlab/taxonomy)。这个仓库负责分类树，它允许你创建用你的数据调优的模型。它提供了关于什么是技能和知识、如何创建拉取请求以贡献给 AI 模型，以及对拉取请求审查的期望等信息。

随着项目的发展，文档及其组织方式将会发生变化。项目成员将会被告知文档的重大变更和更新。

除非另有说明，InstructLab 项目的所有文档都在 [CC-BY-4.0 许可证](https://creativecommons.org/licenses/by/4.0/deed.en) 下授权。

## 常见问题

### 什么是 InstructLab？

InstructLab (**L**arge-scale **A**lignment for chat**B**ots) 是一个开源计划，通过使用 `ilab` 命令行界面 (CLI) 工具提供了一个易于与 AI 大语言模型 (LLM) 交互的平台。你可以使用 CLI 与 Granite-7b 一起工作来测试新的技能和知识，例如，让它写会议记录摘要或回答关于特定主题的问题。然后，用户可以通过在 GitHub 上创建拉取请求，将他们测试过的技能和知识提交到项目的分类仓库，从而增强 LLM 的能力。这种方法通过协作贡献鼓励社区驱动的增强，无需复杂的模型分叉或微调，从而促进快速发展。

> [!IMPORTANT]
> 在消费级硬件上使用量化模型通过 `ilab` CLI 本地构建模型并不是为了生产级模型创建。`ilab` 桌面配置旨在在已经训练和量化的模型之上测试单个知识或技能贡献。它不适用于构建完整的生产级模型。对于完整的 InstructLab 生产级模型构建过程，需要多 GPU 硬件配置，并且学生模型必须是未经训练的、未量化的基础模型。

### 什么是 LAB？

LAB (**L**arge-scale **A**lignment for chat**B**ots) 是 IBM Research 开发的一种新型基于合成数据的对齐调优方法，用于大语言模型。它由三个组件组成：

1. 一个分类驱动的数据管理流程
2. 一个大规模合成数据生成器
3. 带有重放缓冲区的多阶段训练

LAB 方法允许在不出现灾难性遗忘的情况下，向已经预训练的模型增量添加新的知识和技能。

更多关于 LAB 方法的信息可以在 [Hugging Face 项目页面](https://huggingface.co/instructlab) 上找到。

### InstructLab 是如何工作的？

InstructLab 由分类驱动，通过让用户向预训练的大语言模型添加新的 [_技能_ 和 _知识_](https://github.com/instructlab/community/blob/main/docs/README.md) 来工作。

### InstructLab 项目的目标是什么？

InstructLab 项目的目标是实现 AI 和大语言模型贡献的民主化。我们的社区通过两种方式实现这一目标：

* 通过 [项目的 _分类_ 仓库](https://github.com/instructlab/taxonomy) 实现对大语言模型 (LLM) 的协作贡献。当用户向这个仓库贡献时，项目会重新合成其开源训练数据。然后我们的社区 Granite 基础模型会被重新训练，确保社区贡献得到整合，同时随着时间推移丰富模型的能力。

* 提供开源工具以启用 InstructLab 方法，并根据开源项目原则支持社区对这些工具集的贡献。这些工具包括 [InstructLab 核心引擎和 CLI](https://github.com/instructlab/instructlab) 以及诸如 [sdg](https://github.com/instructlab/sdg)、[training](https://github.com/instructlab/training) 和 [evaluation](https://github.com/instructlab/eval) 等库。

### 我如何贡献？

你可以通过阅读 [贡献](https://github.com/instruct-lab/community/blob/main/CONTRIBUTING.md) 指南并加入 [社区 Discord 服务器](https://instructlab.ai/discord) 或 [社区 Slack 频道](https://github.com/instructlab/community/blob/main/InstructLabSlackGuide.md) 开始你的贡献之旅。

当你准备开始贡献时，你可以按照 [入门](https://github.com/instruct-lab/community/blob/main/README.md#getting-started-with-the-instructlab-project-workstreams) 指南进行操作。该指南向你展示如何：

- 安装 `ilab` CLI
- 在本地部署大语言模型
- 添加技能或知识并用你的数据训练本地大语言模型
- 创建拉取请求并将你的信息添加到 InstructLab 分类中
- 获取拉取请求的审查

### 我在使用 `ilab` CLI 工具时遇到问题。我该怎么办？

关于下载 `ilab` CLI 工具时常见问题的列表可以在 [CLI 仓库的讨论板](https://github.com/instruct-lab/instructlab/discussions) 中找到。

### 为什么我要贡献？

InstructLab 旨在实现围绕 InstructLab Granite 模型的协作，这些是贡献者可以通过 [Hugging Face](https://huggingface.co/instructlab) 访问的开源许可大语言模型。参与是一个不论技术背景如何都能为开源 AI 做出贡献的机会。

当贡献者编写对现有分类的补充内容，提交拉取请求，并获得审查和合并后，他们的更改会在下一次构建中发布。这种更新策略加快了模型能力的提升，并允许贡献者比其他大语言模型更快地看到他们对模型产生的影响。

### 通过 InstructLab 项目，我在为哪些大语言模型 (LLM) 做贡献？

通过 InstructLab 项目的贡献包括对 Granite-7b 这个开源许可大语言模型的微调。贡献者可以通过 [Hugging Face](https://huggingface.co/instructlab) 直接访问他们正在改进的模型。

### 什么是 Granite-7b-lab？

Granite-7b-lab 是由 IBM 从头开始构建并使用 LAB (**L**arge-scale **A**lignment for chat**B**ots) 方法进行微调的模型。

更多关于 Granite-7b 的信息可以在 [Hugging Face 项目页面](https://huggingface.co/instructlab/granite-7b-lab) 上找到。

### 什么是"技能"？

在 InstructLab 的上下文中，[_技能_](https://github.com/instructlab/taxonomy/blob/main/README.md#getting-started-with-skill-contributions) 是由贡献者提交的能力领域，旨在训练 AI 模型掌握所提交的信息。换句话说，当你提交一个技能时，你是在教 AI 模型 _如何做某事_。

InstructLab 的技能分为两个主要类别，组合型和基础型：

- [**组合型技能**](https://github.com/instructlab/taxonomy/blob/main/docs/SKILLS_GUIDE.md#compositional-skills) 组合或 _表现型_ 技能允许 AI 模型执行特定任务或功能。在 InstructLab 中，有两种类型的组合技能：
  - [**自由形式组合技能**](https://github.com/instructlab/taxonomy/blob/main/docs/SKILLS_GUIDE.md#freeform-compositional-skills) 是不需要额外上下文的表现型技能。例如，要训练 AI 模型写诗，你需要提供诗歌示例。
  - [**基于上下文的组合技能**](https://github.com/instructlab/taxonomy/blob/main/docs/SKILLS_GUIDE.md#grounded-compositional-skills) 是需要额外上下文的表现型技能。一个例子是 AI 模型如何读取表格布局中的单元格值。要创建读取 Markdown 格式表格的基于上下文的技能，额外的上下文可能是一个示例表格布局。
- **基础技能** 基础技能是像数学、推理和编程这样的技能。
**注意**：目前不接受基础技能。

技能以 YAML 文件的形式编写并提交给 InstructLab 上游项目进行审查。请参见 [技能：YAML 示例](https://github.com/instructlab/taxonomy/blob/main/README.md#skills-yaml-examples) 了解不同类型的示例。

### 什么是"知识"？

[_知识_](https://github.com/instructlab/taxonomy/blob/main/README.md#getting-started-with-knowledge-contributions) 由数据和事实组成。当为 AI 模型创建知识时，你是在为它提供额外的数据和信息，以便更准确地回答问题。而技能是训练 AI 模型如何做某事的信息，知识则基于 AI 模型回答涉及事实、数据或参考的问题的能力。

与技能一样，知识提交以 YAML 格式提交给 InstructLab 上游项目进行审查。请参见 [知识：YAML 示例](https://github.com/instruct-lab/taxonomy/blob/main/README.md#knowledge-yaml-examples) 了解不同类型的示例。

### 项目是否在寻找特定类型的技能贡献？

目前，InstructLab 只接受组合型（_自由形式_ 和 _基于上下文的_）技能和知识。然而，可以提交任何类型的自由形式或基于上下文的技能。某些技能可能不会被添加到分类仓库中，原因包括重复、提交模型已经做得很好的技能，或提交有争议的技能。

目前不接受基础技能。

有关已接受技能的列表，请参见 [已接受的技能](https://github.com/instructlab/taxonomy/blob/main/docs/SKILLS_GUIDE.md#accepted-skills)。

### 技能提交的接受标准是什么？

技能应该旨在为 AI 模型添加能力或知识领域；换句话说，技能提交应该教会 AI 模型 _如何做某事_，而不是提供 _关于某事的信息_。一个好的技能提交可能会解决 AI 模型做得不好的事情，并试图提升其执行该能力的水平。有关常见接受的技能列表，请参见 [已接受的技能](https://github.com/instructlab/taxonomy/blob/main/docs/SKILLS_GUIDE.md#accepted-skills)。

不太可能被接受的技能提交包括：提交知识请求而不是技能请求、提交模型已经做得很好的技能、提交有争议的技能，或提交不执行纯数学或编码的技能。有关应避免提交的技能列表，请参见 [应避免的技能](https://github.com/instructlab/taxonomy/blob/main/docs/SKILLS_GUIDE.md#skills-to-avoid)。

### 知识提交的接受标准是什么？

知识提交的要求可以在 [知识贡献入门](https://github.com/instructlab/taxonomy?tab=readme-ov-file#getting-started-with-knowledge-contributions) 指南中找到。

### 我如何提交技能或知识？

有关在确定差距后如何提交技能的信息，请参见 [贡献方式指南](https://github.com/instruct-lab/taxonomy?tab=readme-ov-file#ways-to-contribute)。

### 提交拉取请求后会发生什么？

提交拉取请求后，分类分类团队和分类审批团队都会进行审查，以确保它们相关、可操作，并具有成为 AI 模型有价值补充所需的所有必要信息。分类者可能会提供反馈并使用标签来管理提交的拉取请求的状态。分类者还可能提供信息性反馈和有用的评论来改进提交。在拉取请求获得批准后，分类审批者会合并该技能。

有关基本审查问题、主观审查问题、标签以及批准、进一步审查要求或拒绝原因的更多信息，可以在 GitHub 仓库的 [分类贡献](https://github.com/instructlab/taxonomy/blob/main/docs/triaging/triaging-contributions.md) 页面上找到。

### 如何审查提交？

对于代码审查，项目维护者在代码审查的评论中使用 LGTM（Looks Good to Me，看起来不错）来表示接受。一个更改需要两个维护者的 LGTM。

对于技能和知识的拉取请求，你的拉取请求将被检查以确保它相关、可操作，并具有审批团队审查和合并所需的所有信息。分类团队将使用标签来管理拉取请求的状态和操作，并根据以下审查指南向贡献者提供反馈：

- 拉取请求是否填写了拉取请求模板信息？
- 所有拉取请求检查是否通过？
- 技能是否有三个或更多示例？
- YAML 字段是否正确？
- 内容中没有个人身份信息
- 这些内容是否包含项目的 [避免这些主题](https://github.com/instruct-lab/community/blob/main/docs/README.md#avoid-these-topics) 指南中记录的任何内容？
- 是否遵守 [行为准则](https://github.com/instruct-lab/taxonomy/blob/main/CONTRIBUTING.md#code-of-conduct) 指南？
- 响应是否明显由大语言模型生成？

### 我的拉取请求需要多长时间才能被审查？

由于目前收到的贡献数量很大，很难提供审查拉取请求的确切时间表。

### 如果我的拉取请求被接受，我的更改需要多长时间才能出现在下一个模型更新中？

拉取请求被接受后，更改会定期整合到 InstructLab 中。

### InstructLab 的软件许可证是什么？

InstructLab 项目以及 Granite-7b 模型都在 [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0) 下分发。

### InstructLab 文档的内容许可证是什么？

除非另有说明，InstructLab 的所有文档都在 [Creative Commons 的 CC-BY-4.0 许可证](https://creativecommons.org/licenses/by/4.0/) 下授权。

### 我是否必须根据 Apache 2.0 许可证授权代码提交给 InstructLab？

是的。对 InstructLab 项目的代码贡献受 Apache 2.0 许可证的条款和条件约束。

### 我的贡献需要提交数据和代码。什么数据是允许包含的？

建议第三方内容使用不限制商业使用或创建衍生作品的开放数据许可证，包括以下许可证：

- CC0
- CDLA-Permissive
- CC-BY-4.0
- CC-BY-4.0 SA
- Apache 2.0
- MIT

### 项目的提交是否需要某种贡献者许可协议？

InstructLab 项目遵循与 [Linux 内核社区使用的](https://docs.kernel.org/process/submitting-patches.html#sign-your-work-the-developer-s-certificate-of-origin) 相同的方法（[开发者原创证书 1.1 (DCO)](https://developercertificate.org/)）来管理代码贡献。除非文件另有说明，对于本项目，相关的开源许可证是 [Apache License, Version 2.0](https://github.com/instruct-lab/taxonomy/blob/main/LICENSE)。在提交补丁进行审查时，你必须在提交消息中包含签署声明。请参见贡献文档的 ["法律"](https://github.com/instruct-lab/taxonomy/blob/main/CONTRIBUTING.md#legal) 部分。

你可以在我们的 [社区贡献指南](https://github.com/instructlab/community/blob/main/CONTRIBUTING.md#developer-certificate-of-origin-dco) 中找到更多关于管理 DCO 签署的有用工具的信息。

### 在哪里可以下载 InstructLab 的更新模型？

可以使用 `ilab download` CLI 命令以及从 [Hugging Face 上的 InstructLab](https://huggingface.co/instructlab) 下载 InstructLab 的最新版本。

### 我有关于项目的问题。我应该去哪里？

目前，与同行和项目维护者交流的最佳方式是在社区 Discord/Slack 服务器中。访问我们的 [InstructLab Discord 工作区指南](https://github.com/instructlab/community/blob/main/InstructLab_DISCORD_GUIDE.md)、[InstructLab Slack 工作区指南](https://github.com/instructlab/community/blob/main/InstructLab_SLACK_GUIDE.md) 了解如何加入。

请参阅我们的 [社区协作页面](https://github.com/instructlab/community/blob/main/Collaboration.md)，其中包括有关我们的邮件列表、会议和与社区互动的其他方式的信息。

### 使用 InstructLab 的软件和硬件要求是什么？

本地训练是这个过程中最需要硬件资源的部分。你的硬件决定了本地训练模型的速度快慢。

要在本地运行和训练 InstructLab，你必须满足以下要求：

- 支持的操作系统
  - 基于 Linux 的操作系统
  - Apple Silicon M1、M2 或 M3 系统
  - 带有 WSL (Windows Subsystem for Linux) 的 Windows 系统
- Python 3.9 或更高版本，包括开发头文件
- 大约 10GB 的可用磁盘空间用于完成 `ilab generate` 步骤
- 在 Apple 硬件上运行整个过程需要大约 60GB 的可用磁盘空间
- 约 32GB RAM

> [!IMPORTANT]
> 我们的一些社区成员报告在使用 Windows 和 WSL 时遇到了 InstructLab 支持方面的挑战。如果可能的话，你可能想使用 Linux 或 Mac 来获得最流畅的体验。我们正在继续改进我们支持的操作系统上的本地桌面 InstructLab 工具体验。

## 术语表

| 术语 | 解释 | 其他参考 |
| --- | --- | --- |
| Checkpoints | 训练过程中的快照。它们会被单独评分，选择最好的一个。 | N/A |
| CUDA | "Compute Unified Device Architecture" - NVIDIA 的用于 GPU 通用计算的并行计算平台和 API。 | [参考](https://www.nvidia.com/en-us/geforce/technologies/cuda/) |
| DeepSpeed | PyTorch 的深度学习优化库 | [参考](https://www.deepspeed.ai/) |
| Granite | IBM 发布的开源许可大语言模型 | [参考](https://huggingface.co/ibm-granite) |
| FSDP | "Full Sharded Data Parallel" - 用于在数据并行工作者之间分片模块参数的包装器，用于 [PyTorch](https://pytorch.org/) | [参考](https://pytorch.org/docs/stable/fsdp.html) |
| LAB | "Large-Scale Alignment for ChatBots" | [参考](https://arxiv.org/abs/2403.01081) |
| Labradorite | LAB 增强的 Llama2 模型 | N/A |
| Llama | Meta 发布的大语言模型 | N/A |
| Llama CPP | 用于 Llama 模型推理的 C++ 库，类似于 [vLLM](https://docs.vllm.ai/en/stable/) | [参考](https://github.com/ggerganov/llama.cpp) |
| LoRA | "Low Rank Adapter" - 用于 PyTorch 的微调算法 | [参考](https://github.com/microsoft/LoRA) |
| Merlinite | IBM 开发的 LAB 增强的 Mistral 模型 | N/A |
| Mistral | Mistral AI 发布的大语言模型 | N/A |
| Mixtral | Mistral AI 使用专家混合的大语言模型 | N/A |
| MMLU | "Massive Multitask Language Understanding" - 用于知识基准测试的评估方案 | [参考](https://en.wikipedia.org/wiki/MMLU) |
| MLX | 用于 Apple Silicon 芯片上机器学习研究的数组框架 | [参考](https://github.com/ml-explore/mlx) |
| MPS | "Metal Performance Shaders" - MacOS 硬件加速器，类似于 CUDA 内核 | N/A |
| MT-Bench | "Multi-turn benchmark" - 用于技能基准测试的评估方案 | [参考](https://arxiv.org/abs/2306.05685) |
| PEFT | "Parameter Efficient Fine-Tuning" | N/A |
| PR-bench | 用于技能 PR 基准测试的评估方案 | N/A |
| PR-mmlu | 用于知识 PR 基准测试的评估方案 | N/A |
| PyTorch | 支持 Python 中张量和动态神经网络的库，具有强大的 GPU 加速 | [参考](https://pytorch.org/) |
| QLoRA | "Quantized Low Rank Adapter" - 用于 PyTorch 的微调算法 | [参考](https://wandb.ai/sauravmaheshkar/QLoRA/reports/What-is-QLoRA---Vmlldzo2MTI2OTc5) |
| Quantization | 通过减少数据类型的范围来减少模型资源需求的过程 | [参考](https://huggingface.co/docs/optimum/en/concept_guides/quantization) |
| SDG | "Synthetic Data Generation" - 模型基于提供的示例人工生成数据的过程。 | N/A |
| vLLM | 用于大语言模型推理和服务的库，类似于 Llama CPP。提供 OpenAI 兼容的 API。 | [参考](https://docs.vllm.ai/) |

## 其他资源

其他资源，包括行为准则、行为准则委员会成员、如何贡献、如何加入 Discord 或 Slack 服务器等，可以在以下仓库中找到：

[InstructLab 分类仓库](https://github.com/instructlab/taxonomy)

[InstructLab CLI 仓库](https://github.com/instructlab/instructlab)

[InstructLab 社区仓库](https://github.com/instructlab/community)

Discord 和通信

- [加入 Discord 服务器](https://github.com/instructlab/community/blob/main/InstructLab_DISCORD_GUIDE.md)
- [Discord 审核](https://github.com/instructlab/community/blob/main/InstructLab_DISCORD_MODERATION_GUIDE.md)

Slack 和通信

- [加入 Slack 频道](https://github.com/instructlab/community/blob/main/InstructLabSlackGuide.md)
- [Slack 审核](https://github.com/instructlab/community/blob/main/InstructLabSlackModerationGuide.md)
