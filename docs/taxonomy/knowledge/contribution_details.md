---
title: 知识贡献指南
description: 🐶 InstructLab 的知识贡献指南概述
logo: images/ilab_dog.png
---

你可以在任何地方（GitLab、Gerrit 等）创建 Git 仓库来托管你的知识贡献，但在 GitHub 上创建可能更有利。以下说明向你展示如何在 GitHub 上创建知识仓库并向分类系统贡献。

## 先决条件

- 你有一个 GitHub 账户
- 你有 [taxonomy](https://github.com/instructlab/taxonomy/tree/main) 仓库的分叉副本
- 你已经验证模型还不知道你想提交的知识

## 创建你自己的知识仓库

要创建一个新的 GitHub 仓库，请按照 GitHub 文档中的 [创建新仓库](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository) 进行操作。

具体步骤如下：

1. 在你的 GitHub 个人资料页面，导航到仓库标签。你会看到一个搜索栏，你可以在那里搜索你的仓库或创建一个新的仓库。
2. 这会带你到一个标题为"创建新仓库"的页面。为你的仓库创建一个自定义名称，并添加一个 `README.md` 文件。例如，"knowlege_contributions" 可能是一个不错的仓库名称。
3. 准备就绪后点击"创建"。

## 将你的知识文档转换为 markdown

有许多在线工具可以帮助你将文档转换为 markdown。如果你使用 wiki 页面进行贡献，你可以使用 [pandocs](https://pandoc.org/try/) 来转换文档。对于 pandoc 的维基百科来源，使用 `from: mediawiki` 并转换 `to: markdown_strict` 以访问正确的 markdown 格式。

## 将 markdown 文件添加到你的仓库

要向你的 GitHub 仓库添加文件，请按照 GitHub 文档中的 [向仓库添加文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository) 进行操作。

具体步骤如下：

1. 导航到"添加文件"。如果你想手动添加你的 markdown 内容，点击"创建新文件"。如果你有要添加的本地文件，点击"上传文件"。
2. 添加描述并提交你的更改。

    由于这是你自己的仓库，你可以直接提交到 `main` 分支。

3. 然后你可以在你的仓库中看到你的新内容。

!!! important
    记下你的提交 SHA；你的 `qna.yaml` 会需要它。

## 在分类系统仓库中创建拉取请求

导航到你分叉的分类系统仓库并确保它是最新的。

创建拉取请求有几种方法：

- 有关本地流程的详细信息，请查看 Kubernetes 文档中的 [GitHub 工作流指南](https://github.com/kubernetes/community/blob/master/contributors/guide/github-workflow.md) 和 GitHub 文档中的 [GitHub flow](https://docs.github.com/en/get-started/using-github/github-flow)。
- 有关使用 GitHub 网页 UI 贡献的详细信息，请参见 [使用 GH UI 贡献](https://github.com/instructlab/taxonomy/docs/contributing_via_GH_UI.md) 或 GitHub 文档中的 [创建拉取请求](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request?tool=webui)。

## 验证

在寻求对你的贡献进行审查之前，这里有一些需要检查的事项：

- 你的 `qna.yaml` 遵循正确的格式。请参见 [知识：YAML 示例](https://github.com/instructlab/taxonomy/blob/main/README.md#knowledge-yaml-examples) 中的示例
- 确保所有参数都已设置。特别是 `document`、`repo`、`commit` 和 `pattern` 键；这些参数是特定于知识贡献的，需要更多分析。
- 包含一个 `attribution.txt` 文件来引用你的来源。更多信息请参见 [对于你的 attribution.txt 文件](https://github.com/instructlab/taxonomy/blob/main/CONTRIBUTING.md#for-your-attributiontxt-file)。

## PR 上游工作流程

下表概述了你提交的 PR 的预期时间。PR 会经过几个步骤和检查，但你应该能够将你的 `label` 映射到它所在的位置。

| 标签 | 执行者 | 操作 | 持续时间 |
| --- | --- | --- | --- |
| | 贡献者 | 提交 PR | - |
| | 贡献者 | 修复失败的 PR 检查 | - |
| https://github.com/instructlab/taxonomy/labels/triage-needed | 分类者 | 审查 PR，要求更改 | 天 |
| https://github.com/instructlab/taxonomy/labels/triage-requested-changes | 贡献者 | 进行请求的更改 | 天 |
| https://github.com/instructlab/taxonomy/labels/precheck-generate-ready | 分类者 | 运行预检查和生成 | 天 |
| https://github.com/instructlab/taxonomy/labels/community-build-ready | 后端 | 模型重新训练 | 周 |
| | 分类者 | 检查数字并合并或关闭 PR | - |
