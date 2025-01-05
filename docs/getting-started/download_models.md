---
title: 下载语言模型
description: 使用 `ilab` 下载模型的步骤说明
logo: images/ilab_dog.png
---

# 📥 下载模型

1) 运行 ilab 模型下载命令，从 HuggingFace 下载 `granite-7b-lab-GGUF`、`merlinite-7b-lab-GGUF` 和 `Mistral-7B-Instruct-v0.2-GGUF` 模型的精简预训练版本（每个约 4.4G）。

```shell
ilab model download
```

`ilab model download` 命令会从 HuggingFace 下载[模型](https://huggingface.co/instructlab/)的精简预训练版本（约 4.4G）：

*模型下载输出示例*

```shell
Downloading model from Hugging Face:
    Model: instructlab/granite-7b-lab-GGUF@main
    Destination: /Users/<user>/.cache/instructlab/models
Downloading model from Hugging Face:
    Model: instructlab/merlinite-7b-lab-GGUF@main
    Destination: /Users/<user>/.cache/instructlab/models
Downloading model from Hugging Face:
    Model: TheBloke/Mistral-7B-Instruct-v0.2-GGUF@main
    Destination: /Users/<user>/.cache/instructlab/models

TheBloke/Mistral-7B-Instruct-v0.2-GGUF requires a HF Token to be set.
Please use '--hf-token' or 'export HF_TOKEN' to download all necessary models.
```

a) 下载 `Mistral-7B-Instruct-v0.2-GGUF` 模型时，系统可能会提示您使用 Hugging Face 令牌。

```shell
ilab model download --hf-token <your-huggingface-token>
```

!!! note
    ⏳ 该命令的运行时间可能从几分钟到立即完成不等。速度取决于您的网络连接和模型是否已被缓存。如果连接 Hugging Face 时遇到问题，请参考 [Hugging Face 讨论论坛](https://discuss.huggingface.co/)获取更多详情。

## 下载完整的 Hugging Face 仓库（Safetensors 模型）

1) 指定仓库，必要时提供 Hugging Face 令牌。例如：

```shell
ilab model download --repository instructlab/granite-7b-lab-GGUF --filename granite-7b-lab-Q4_K_M.gguf --hf-token <your-huggingface-token>
```

这类模型适用于启用 GPU 的系统或任何希望使用 vLLM 部署模型的用户。InstructLab 在 HuggingFace 上提供了我们的 Granite 模型的 Safetensor 版本。

## 列出已下载的模型

可以使用 `ilab model list` 命令查看所有已下载的模型。

```shell
ilab model list
```

*执行 `ilab model list` 后的输出示例*

```shell
(venv) $ ilab model list
+-------------------------------------+---------------------+--------+
| Model Name                          | Last Modified       | Size   |
+-------------------------------------+---------------------+--------+
| granite-7b-lab-Q4_K_M.gguf          | 2024-08-01 15:05:48 | 4.1 GB |
| merlinite-7b-lab-Q4_K_M.gguf        | 2024-08-01 15:05:48 | 4.1 GB |
| mistral-7b-instruct-v0.2.Q4_K_M.gguf| 2024-08-01 15:05:48 | 4.1 GB |
+-------------------------------------+---------------------+--------+
```
