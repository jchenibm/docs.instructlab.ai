# 贡献指南

👍🎉 首先，感谢你抽出时间做出贡献！🎉👍

以下是贡献指南。这些只是指导方针，而不是规则。请运用你的最佳判断，并随时通过拉取请求提出对本文档的修改建议。

## 开始之前需要了解的内容

### 行为准则

本项目遵守 [行为准则](./CODE_OF_CONDUCT.md)。通过参与，你应该遵守这个准则。

请向行为准则 [委员会成员][committee] 之一报告不可接受的行为。

### 相关仓库

除了本仓库外，InstructLab 还有两个相关仓库：

* [`ilab` 命令行界面 (CLI) 工具](https://github.com/instructlab/instructlab)。这个仓库负责 `ilab` 命令行界面 (CLI) 工具。
* [分类树](https://github.com/instructlab/taxonomy)。这个仓库负责分类树，它允许你创建用你的数据调优的模型。

以下部分提供了对任何 InstructLab 仓库做出贡献的一般概述。

## 贡献概述

参与 InstructLab 项目可以通过向任何一个仓库贡献来实现。以下工作流程旨在帮助你理解贡献的最佳实践，并帮助你开始你的贡献之旅。它将指导你创建和选择问题，处理问题，让你的工作得到审查，然后让你的拉取请求被合并。

开源项目总是欢迎帮助，总是有可以改进的地方。例如，文档（就像你现在正在阅读的文本）总是可以改进，代码总是可以澄清，变量或函数总是可以重命名或添加注释，总是需要更多的测试覆盖。如果你看到你认为应该修复的东西，请主动承担！

要贡献代码或文档，请向相关仓库提交拉取请求。请注意，对任何仓库的贡献都有其自己的要求和期望，用户在贡献之前应该熟悉这些期望。

### ilab 命令行界面 (CLI) 工具仓库

我们欢迎以拉取请求的形式贡献文档更新、代码贡献等。在贡献之前，用户应该熟悉 [`ilab` CLI 仓库贡献指南](https://github.com/instructlab/instructlab/blob/main/CONTRIBUTING/CONTRIBUTING.md)。

要向 `ilab` CLI 工具仓库提交拉取请求，请参见 [拉取请求页面](https://github.com/instructlab/instructlab/pulls)。

### 分类仓库

我们欢迎以拉取请求的形式贡献文档更新、技能贡献、知识贡献等。在贡献之前，用户应该熟悉 [分类仓库贡献指南](https://github.com/instructlab/taxonomy/blob/main/CONTRIBUTING.md)。

要向分类仓库提交拉取请求，请参见 [拉取请求页面](https://github.com/instructlab/taxonomy/pulls)。

### 社区

我们欢迎以拉取请求的形式贡献文档。要向社区仓库提交拉取请求，请参见 [拉取请求页面](https://github.com/instructlab/community/pulls)。

### 开始贡献

InstructLab 项目使用在许多开源仓库中常见的 _Fork and Pull_ 模型进行贡献；这需要多个步骤，包括分叉和克隆仓库、创建 _拉取请求_ (PR) 等。有关此过程的详细信息，请查看来自 Kubernetes 的 [GitHub 工作流指南](https://github.com/kubernetes/community/blob/master/contributors/guide/github-workflow.md)。

在你分叉和克隆仓库之后，你可以通过查看 [社区仓库](https://github.com/instructlab/community/pulls)、[CLI 仓库](https://github.com/instructlab/instructlab/issues) 或 [分类仓库](https://github.com/instructlab/taxonomy/issues) 的问题跟踪器开始贡献过程。然后，你可以通过在该问题上留下评论来接手问题，并在拉取请求 (PR) 中解决问题。在提交之前，确保你的更改通过格式化、代码检查和单元测试。此外，所有 PR 必须通过签署你的提交来同意 [开发者原创证书 (DCO)](https://developercertificate.org/) 的条款。只接受带有签署的提交的 PR。如果你在创建拉取请求之前没有签署你的提交，不用担心，你可以事后修复。有关此过程的更多信息，请参见 [开发者原创证书 (DCO)](#开发者原创证书-dco)。

然后，你可以提交 PR 进行审查。一般来说，我们遵循标准的 [GitHub 拉取请求](https://help.github.com/en/articles/about-pull-requests) 流程。按照 PR 上提供的模板为维护者提供有关你的拉取请求的详细信息。

> [!重要]
> 如果你想做出更大的贡献，比如引入新功能或功能，或重构代码库的重要部分以提高性能、可读性或可维护性，请在开始之前 [联系](#通信) 我们。这有助于确保你的时间不会浪费在开发人员不会接受到代码库中的更改上。

### 拉取请求审查

一旦你创建了拉取请求 (PR)，维护者将审查你的代码，并可能在合并之前提出修复建议。如果你在工作时考虑审查者遵循的标准，你的 PR 将更容易获得审查。记住要：

* 在本地运行测试并确保它们通过
* 遵循项目编码约定
* 写详细的提交消息
* 将大的更改分解成一系列逻辑上较小的补丁，这些补丁易于单独理解并组合起来解决更广泛的问题

有关维护者和分类者的列表，请参见 [MAINTAINERS.md](MAINTAINERS.md) 页面。

### 提出新功能

要提出新功能，最好在适当的仓库中提出问题：

* [InstructLab CLI 仓库](https://github.com/instructlab/instructlab/issues)
* [分类仓库](https://github.com/instructlab/taxonomy/issues)

这样，功能可以与项目维护者讨论，确保你的时间不会浪费在开发人员不会接受到代码库中的功能上。

### 提交或修复错误

要提交新的错误，在创建拉取请求之前，在适当的仓库中提出问题。这确保问题得到适当跟踪。

要修复现有错误，在你正在处理的问题上留下评论。然后，创建拉取请求并提交拉取请求进行审查。

## 法律

以下部分详细说明了在贡献之前应该查看的重要法律信息。

### 许可证和版权

在 [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0) 下分发。

SPDX-License-Identifier: [Apache-2.0](https://spdx.org/licenses/Apache-2.0)

如果你想查看详细的许可证，请点击 [这里](LICENSE)。

### 开发者原创证书 (DCO)

我们已经尽可能地使贡献变得容易。这适用于我们如何处理贡献的法律方面。我们使用与 Linux® 内核 [社区](https://docs.kernel.org/process/submitting-patches.html#sign-your-work-the-developer-s-certificate-of-origin) 用于管理代码贡献相同的方法 - [开发者原创证书 1.1 (DCO)](https://developercertificate.org/)。

我们要求在提交补丁进行审查时，开发者必须在提交消息中包含签署声明。如果你在 `git config` 文件中设置了 `user.name` 和 `user.email`，你可以通过使用以下命令自动签署你的提交：

```shell
git commit -s
```

以下示例包含一个 `Signed-off-by:` 行，表明提交者已接受 DCO：

```text
Signed-off-by: John Doe <john.doe@example.com>
```

我们会自动验证所有提交消息是否包含带有你的电子邮件地址的 `Signed-off-by:` 行。

#### 用于进行 DCO 签署的有用工具

有一些工具可以让开发者更容易管理 DCO 签署。

* DCO 命令行工具，让你可以对整个仓库进行单次签署 ( <https://github.com/coderanger/dco> )
* GitHub UI 集成，用于自动添加签署 ( <https://github.com/scottrigby/dco-gh-ui> )
* Chrome - <https://chrome.google.com/webstore/detail/dco-github-ui/onhgmjhnaeipfgacbglaphlmllkpoijo>
* Firefox - <https://addons.mozilla.org/en-US/firefox/addon/scott-rigby/?src=search>

## 通信

你可以加入 [InstructLab Slack 工作区](https://github.com/instructlab/community/blob/main/InstructLabSlackGuide.md) 与项目维护者和你的同伴用户交流。

## 其他资源

以下资源包括有关每个仓库的其他信息，如设置环境、测试环境、编码风格等。

### ilab CLI 工具其他资源

* [`ilab` CLI 工具 README.md](https://github.com/instructlab/instructlab/blob/main/README.md#)。这个资源提供了关于 `ilab` CLI 工具的信息，包括概述、入门、训练模型、提交拉取请求等。

* [`ilab` CLI 工具 CONTRIBUTING.md](https://github.com/instructlab/instructlab/blob/main/CONTRIBUTING/CONTRIBUTING.md)。这个资源提供了关于向 `ilab` CLI 工具仓库贡献的信息，报告错误、测试、编码风格等。

### 分类其他资源

* [分类 README.md](https://github.com/instructlab/taxonomy/blob/main/README.md)。这个资源提供了关于分类仓库的信息，包括入门、技能和知识拉取请求的 YAML 示例、如何贡献等。

* [分类 CONTRIBUTING.md](https://github.com/instructlab/taxonomy/blob/main/CONTRIBUTING.md)。这个资源包含了向分类仓库贡献的信息和最佳实践。

[committee]: https://github.com/instructlab/community/blob/main/CODE_OF_CONDUCT_COMMITTEE.md
