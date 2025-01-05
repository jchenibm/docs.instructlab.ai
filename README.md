# docs.instructlab.ai

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
