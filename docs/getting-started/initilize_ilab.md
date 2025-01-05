---
title: 初始化 InstructLab
description: 在本地机器上初始化 InstructLab 的步骤
logo: images/ilab_dog.png
---

# 🏗️ 初始化 `ilab`

1) 运行以下命令初始化 `ilab`：

```shell
ilab config init
```

2) 当出现提示时，按**回车键**将 `https://github.com/instructlab/taxonomy.git` 仓库克隆到当前目录

   **可选**：如果您想指向已有的 `taxonomy` 仓库本地克隆，可以通过交互方式输入路径，或者使用 `--taxonomy-path` 参数。

   除非另有指定，`ilab` 将使用默认配置文件。您可以在任何 `ilab` 命令中使用 `--config` 参数来覆盖此行为。

3) 当出现提示时，提供默认模型的路径。否则，将使用量化版的 [Merlinite](https://huggingface.co/instructlab/merlinite-7b-lab-GGUF) 模型作为默认值。

*步骤 1-3 的输出示例*
```shell
----------------------------------------------------
         欢迎使用 InstructLab CLI
本指南将帮助您设置环境
----------------------------------------------------

请提供以下值以初始化环境 [按回车键使用默认值]：
taxonomy 仓库路径 [/Users/<user>/.local/share/instructlab/taxonomy]:
模型路径 [/Users/<user>/.cache/instructlab/models/merlinite-7b-lab-Q4_K_M.gguf]:
```

您也可以使用 `ilab model download` 命令下载此模型。

4) InstructLab CLI 会自动检测您的硬件并选择与您的机器完全匹配的系统配置文件。系统配置文件会根据检测到的 GPU 类型和可用显存，在 `config.yaml` 文件中填入适当的参数值。

*配置文件自动检测的输出示例*

```shell
生成配置文件和配置文件：
/home/user/.config/instructlab/config.yaml
/home/user/.local/share/instructlab/internal/train_configuration/profiles

我们检测到 AMD CPU 配置文件与您的系统完全匹配。

--------------------------------------------
   初始化成功完成！
   您可以开始使用 `ilab` 了。祝您使用愉快！
--------------------------------------------
``` 

5) 如果没有与您的系统完全匹配的配置文件，您可以在出现提示时手动选择系统配置文件。您可以使用各种参数来配合 `ilab` 命令，以便在适用的情况下利用您的 GPU。

*选择系统配置文件的输出示例*

```shell
请选择要使用的系统配置文件。
系统配置文件适用于配置文件的所有部分，并为每个命令设置特定于硬件的默认值。
首先，请选择您的系统所属的硬件供应商
[1] APPLE
[2] INTEL
[3] AMD
[4] NVIDIA
请输入您的选择编号 [0]: 1
您选择了：APPLE
接下来，请选择最接近您系统的具体硬件配置。
[0] 无系统配置文件
[1] APPLE M1 ULTRA
[2] APPLE M1 MAX
[3] APPLE M2 MAX
[4] APPLE M2 ULTRA
[5] APPLE M2 PRO
[6] APPLE M2
[7] APPLE M3 MAX
[8] APPLE M3 PRO
[9] APPLE M3
请输入您的选择编号 [按回车键使用硬件默认值] [0]: 8
您选择了：/Users/kellybrown/.local/share/instructlab/internal/system_profiles/apple/m3/m3_pro.yaml

--------------------------------------------
   初始化成功完成！
您可以开始使用 `ilab` 了。祝您使用愉快！
--------------------------------------------
```

GPU 配置文件按 GPU 类型和数量列出。如果您的 GPU 配置与上述任何配置文件的显存容量相似，欢迎尝试使用它们！

### 初始化系统后的 `ilab` 目录结构

运行 `ilab config init` 后，在 Linux 系统上的目录结构如下：

```shell
├─ ~/.cache/instructlab/models/ (1)
├─ ~/.local/share/instructlab/datasets (2)
├─ ~/.local/share/instructlab/taxonomy (3)
├─ ~/.local/share/instructlab/checkpoints (4)
```

1) `~/.cache/instructlab/models/`：包含所有下载的大语言模型，以及您使用 ilab 生成的模型输出。

2) `~/.local/share/instructlab/datasets/`：包含基于 taxonomy 仓库修改而生成的 SDG 阶段数据输出。

3) `~/.local/share/instructlab/taxonomy/`：包含技能和知识数据。

4) `~/.local/share/instructlab/checkpoints/`：包含训练过程的输出。
