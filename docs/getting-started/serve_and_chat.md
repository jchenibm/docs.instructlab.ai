---
title: 模型部署与对话
description: 如何部署模型并与之进行对话的步骤说明
logo: images/ilab_dog.png
---

# 🍴 部署模型

运行以下命令来部署模型：

```shell
ilab model serve
```

如需部署非默认模型，请使用以下命令：

```shell
ilab model serve --model-path models/granite-7b-instruct.GGUF
```

*模型成功部署的输出示例*

```shell
(venv) $ ilab model serve
INFO 2024-03-02 02:21:11,352 lab.py:201 Using model 'models/ggml-merlinite-7b-lab-Q4_K_M.gguf' with -1 gpu-layers and 4096 max context size.
Starting server process
After application startup complete see http://127.0.0.1:8000/docs for API.
Press CTRL+C to shut down the server.
```

!!! note
    如果多个 `ilab` 客户端同时尝试连接到同一个 InstructLab 服务器，第一个客户端将成功连接到服务器，而其他客户端将启动各自的临时服务器。这将需要主机上的额外系统资源。

部署非默认的 Safetensors 模型（例如 granite-7b-lab）。注意：此操作需要 GPU 支持。

a. 首先确保已安装 vllm：

```shell
pip show vllm
```

b. 如果未安装，请运行：

```shell
pip install vllm@git+https://github.com/opendatahub-io/vllm@2024.08.01
```

```shell
ilab model serve --model-path ~/.cache/instructlab/models/instructlab/granite-7b-lab
```

# 📣 与模型对话（可选）

由于您在一个终端窗口中已经部署了模型，因此需要打开一个新的终端窗口并重新激活 Python 虚拟环境来运行 `ilab model chat` 命令：

```shell
source venv/bin/activate
ilab model chat
```

如需与非默认模型对话（例如 Mixtral-8x7B-Instruct-v0.1）：

```shell
source venv/bin/activate
ilab model chat --model models/mixtral-8x7b-instruct-v0.1.Q4_K_M.gguf
```

请注意，使用 `--model` 参数时要求现有服务器已具备该模型。如果没有，您必须先退出服务器。如果指定端口上没有运行服务器，`ilab model chat` 中的 `--model` 参数可以自动为您启动一个带有指定模型的服务器。

在开始向模型添加新的技能和知识之前，您可以通过询问诸如"加拿大的首都是什么？"这样的问题来测试其基础性能。

!!! note
    模型需要使用生成的合成数据进行训练后，才能使用任何新添加的技能或知识。


```shell
(venv) $ ilab model chat
╭────────────────────────────────────────────────────────────────────────────────────────────────────────────────── system ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ Welcome to InstructLab Chat w/ GGML-MERLINITE-7B-lab-Q4_K_M (type /h for help)                                                                                                                                                                    │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
>>> what is the capital of Canada                                                                                                                                                                                                 [S][default]
╭────────────────────────────────────────────────────────────────────────────────────────────────────── ggml-merlinite-7b-lab-Q4_K_M ───────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ The capital city of Canada is Ottawa. It is located in the province of Ontario, on the southern banks of the Ottawa River in the eastern portion of southern Ontario. The city serves as the political center for Canada, as it is home to │
│ Parliament Hill, which houses the House of Commons, Senate, Supreme Court, and Cabinet of Canada. Ottawa has a rich history and cultural significance, making it an essential part of Canada's identity.                                   │
╰─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────── elapsed 12.008 seconds ─╯
```