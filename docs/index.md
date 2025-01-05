---
title: 欢迎来到 InstructLab!
description: 🐶 InstructLab 项目概览
logo: images/ilab_dog.png
---
# 欢迎来到 🐶 InstructLab 项目

![Banner](images/instructlab-banner.png)

InstructLab 是一个与模型无关的开源 AI 项目，旨在促进对大语言模型(LLMs)的贡献。

我们的使命是通过一种可访问的方式让任何人都能够对现有的 LLMs 进行更新，从而参与塑造生成式 AI。

**我们的社区欢迎所有希望帮助实现人人参与塑造生成式 AI 未来这一目标的贡献者。**

## 为什么选择 InstructLab

目前有许多项目在快速采用和扩展开源许可的 AI 模型，但它们面临三个主要挑战：

* 无法直接对 LLMs 进行贡献。这些贡献只能以分支(fork)的形式出现，这迫使用户必须选择一个"最适合"的模型，而该模型难以扩展。同时，这些分支对模型创建者来说维护成本很高。
* 贡献想法的能力受限于 AI/ML 专业知识的缺乏。要实现一个想法，必须学习如何分支、训练和优化模型。这是一个很高的准入门槛。
* 在分支模型的审查、策划和分发方面，缺乏直接的社区治理或最佳实践。

**InstructLab 正是为解决这些问题而生。**

该项目使社区贡献者能够为特定模型添加额外的"技能"或"知识"。

InstructLab 的模型无关技术使具备足够基础设施资源的模型上游能够定期构建他们的开源许可模型，这不是通过重建和重新训练整个模型实现的，而是通过将新技能组合到其中来完成。

欢迎查看 [InstructLab Hugging Face 页面](https://huggingface.co/instructlab)上的"lab-enhanced"模型。

## 📋 系统要求

- **🍎 Apple M1/M2/M3 Mac 或 🐧 Linux 系统**（在 Fedora 上测试通过）。
  我们预计未来会支持更多操作系统。
- C++ 编译器
- Python 3.10 或 Python 3.11
- 约 60GB 磁盘空间（整个过程）

!!! note
    目前不支持 Python 3.12，因为某些依赖项尚未在 Python 3.12 上运行。目前我们仅支持 Python 3.10 或 Python 3.11（首选）。使用任何其他 Python 版本将安装旧版本的 InstructLab（如 0.17）。

!!! tip
    在 macOS 上安装 `ilab` CLI 时，您可能需要运行 `xcode-select --install` 命令，以安装前面列出的必需包。

