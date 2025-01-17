---
title: 知识指南
description: 🐶 InstructLab 知识概述
logo: images/ilab_dog.png
---
# 什么是"知识"？

知识由数据和事实组成，并由文档支持。当你为模型创建知识时，你是在为它提供额外的数据以更准确地回答问题。

本项目中的知识贡献包含以下几个部分：

- 一个存储你的信息的 git 仓库文件。例如，这些仓库可以包含以下信息的 markdown 版本：2024 年奥斯卡获奖者、法律书籍、莎士比亚、体育、化学等。
- 一个 `qna.yaml` 文件，用于提出和回答关于 git 仓库中信息的问题。
- 一个 `attribution.txt` 文件，包含 `qna.yaml` 中使用的信息来源。

你可以在 [知识贡献入门](https://github.com/instructlab/taxonomy/blob/main/README.md#getting-started-with-knowledge-contributions) 中了解更多关于知识结构的信息。

## 接受的知识

!!! important
    我们目前只在有限的私有测试版中接受知识贡献，并且来源将限制在维基百科的文章。

以下是我们目前接受知识贡献的主要知识领域：艺术、工程、地理、历史、语言学、数学、哲学、宗教、科学和技术。

## 避免这些主题

虽然调优过程最终可能会从帮助模型处理复杂的社会主题中受益，但目前这是一个我们不想轻易处理的活跃研究领域。因此，请避免在你的提交中包含以下主题：

- PII (个人身份信息) 或任何侵犯个人隐私权的内容
- 暴力，包括自残
- 网络欺凌
- 内部文档或其他对你的雇主或组织保密的信息，如商业机密
- 歧视
- 宗教
  - 诸如"[根据 2011 年人口普查，基督教是尼泊尔第五大宗教，有 375,699 名信徒，占人口的 1.4%](https://en.wikipedia.org/wiki/Christianity_in_Nepal)"这样的事实作为知识贡献是可以的。但是，支持或反对任何宗教信仰都是不可接受的。
- 医疗或健康信息
  - 诸如"[在哺乳动物中，肺部通气是通过吸气 (呼吸) 实现的](https://opentextbc.ca/biology/chapter/11-3-circulatory-and-respiratory-systems/)"这样的事实作为知识贡献是可以的。但是，定制的医疗/健康建议是不可接受的。
- 金融信息
  - 诸如"[自由放任经济学...认为市场力量应该单独驱动经济，政府应该避免直接干预或调节经济系统](https://openstax.org/books/world-history-volume-2/pages/6-3-capitalism-and-the-first-industrial-revolution)"这样的事实作为知识贡献是可以的。但是，定制的金融建议是不可接受的。
- 法律和解或缓解措施
- 性别偏见
- 敌对语言、威胁、诽谤以及贬低或不敏感的笑话或评论
- 亵渎
- 色情和性暗示或性挑逗内容
- 任何允许进行影响个人权利或福祉的自动化决策的贡献，如社会评分
- 任何参与政治竞选或游说的贡献

我们也不接受以下内容的提交：

- 代码
  - 任何可以追溯到计算机代码的代码相关内容。不限于 `sed` 或 `bash` 或用于 OpenShift 或 Kubernetes 的 `yaml`，到 `python` 片段到 `Java` 建议。有专门针对这个领域的模型，目前这个模型不接受这类内容。
- 笑话
- 诗歌

我们在项目开始时收到了许多笑话和诗歌提交，由于笑话和诗歌是"仁者见仁"的，而双关语对英语母语者来说需要细微的理解，我们意识到我们可能在无意中给我们的模型带来了偏见。我们发现处理这两个主题都有其自身的挑战，如果我们想要一些通用的东西，找到共识是不成功的。目前，我们不接受额外的笑话和诗歌提交。

## 建立你的大语言模型直觉

大语言模型有其固有的限制，使得某些任务极其困难，比如做数学题。它们在其他任务上表现出色，比如创意写作。而在逻辑推理等方面还可以做得更好。

具有知识的大语言模型可以帮助它创建一个可以学习的信息基础，然后你可以通过 `qna.yaml` 文件教它使用这些知识。

例如，你可以给大语言模型整个元素周期表，然后在 `qna.yaml` 中添加类似这样的内容：

```yaml
question: 氯的符号和原子序数是什么？
answer: |
  氯的符号是 Cl，原子序数是 17。
```

通过几个这样的问答，模型将学习元素周期表，因为它有知识数据。

### 大语言模型擅长的领域

大语言模型擅长以下方面：

- 头脑风暴
- 创造力
- 连接信息
- 跨语言行为

然而，对于这些方面，大语言模型通常已经有出色的表现。在构建你的提交之前，请在 `lab chat` 中尝试 3-5 个示例来确认模型的不足，然后在你的拉取请求 (PR) 中分享这些示例。

### 大语言模型需要帮助的领域

大语言模型需要在以下方面得到帮助：

- 推理链
- 分析
- 故事情节
- 重组信息
- 有效和简洁的总结

大语言模型在这些类型的主题中的行为对模型来说很难正确处理。尝试几个示例来理解模型在执行这些类型任务时的能力的细微差别，然后考虑在你的调优过程中使用对结果的纠正。

### 大语言模型不太擅长的领域

大语言模型在以下方面表现不佳：

- 数学
- 计算
- "图灵完备"类型的任务
- 仅生成真实世界的信息 (它们容易产生幻觉)

大语言模型可能在解决数学和计算问题时遇到困难。也就是说，改进其中一些基础技能可能是这项工作将来要解决的问题，但目前还不是时候。
