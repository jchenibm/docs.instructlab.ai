# docs.instructlab.ai

# 欢迎来到 🐶 InstructLab 项目

![Banner](docs/images/instructlab-banner.png)

InstructLab 是一个与模型无关的开源 AI 项目，旨在促进对大语言模型(LLMs)的贡献。

我们的使命是通过一种可访问的方式让任何人都能够对现有的 LLMs 进行更新，从而参与塑造生成式 AI。

InstructLab 的文档可以访问 [docs/index.md](docs/index.md)

## 如何在本地构建 InstructLab 的文档

要在本地测试文档更改，你需要在Python环境中安装`mkdocs`和相关依赖。

我们提供了一个服务器启动脚本以便使用。

## 开始使用

1. 为你的安装创建一个虚拟环境。

```bash
python -m venv venv-ilab-docs
source venv-ilab-docs/bin/activate
```

2. 启动服务器。

这将会：
* 安装 mkdocs
* 安装 PyPI 依赖
* 在本地启动 mkdocs 服务器

```bash
./launch_server.sh
```

3. 访问 [https://127.0.0.1:8000/](https://127.0.0.1:8000/) 在浏览器中查看你的更改。
