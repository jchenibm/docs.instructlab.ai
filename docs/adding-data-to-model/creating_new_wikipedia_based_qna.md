在本教程中，我们将引导你构建一个新的 `qna.yaml`，以便为 `granite-7b-lab` 模型添加新的或更新的知识。让我们开始吧！

我们需要做的第一件事是创建一个新目录，以便有一个干净的工作空间并下载一些软件。大多数时候，更新模型中最简单的事情是 Wikipedia 条目，所以幸运的是，`erictherobot` 编写了一个有用的工具，为我们下载文章的 markdown 版本。

```bash
mkdir instructlab
cd instructlab
git clone git@github.com:erictherobot/wikipedia-markdown-generator.git
```

之后，克隆你的 instructlab 知识文档仓库。它可以命名为你喜欢的任何名称，但如果你使用我们的 https://ui.instructlab.ai，你会注意到你已经有 `instructlab-knowledge-docs`。

```bash
git clone git@github.com:<USERNAME>/instructlab-knowledge-docs.git
```

接下来，我们需要构建一个 Python 虚拟环境并安装依赖项以使其工作。这些命令进入目录，使用 python3.11 创建虚拟环境（你可能需要更改机器上的 Python 版本），激活虚拟环境，然后使用 pip 安装依赖项。
你会注意到 `Texas_Longhorns_football` 在那里，这是我想下载并创建 `qna.yaml` 的 Wikipedia 文章。你应该在这里选择你想要的新知识。

```bash
cd wikipedia-markdown-generator
python3.11 -m venv venv-md-gen
source venv-md-gen/bin/activate
pip install -r requirements.txt
python3 wiki-to-md.py Texas_Longhorns_football
```

接下来，我们继续将 markdown 复制到知识库中，并将其提交到我们的仓库并推送到 GitHub。

```bash
cp md_output/Texas_Longhorns_football.md ../instructlab-knowledge-docs/
cd ../instructlab-knowledge-docs
git add .
git commit -m "added markdown doc"
git push origin main
cd ..
```

接下来，我们拉取上游公共分类目录，并 `cd` 进入该目录。

```bash
git clone git@github.com:instructlab/taxonomy
cd taxonomy
```

下一步是为你提供 "尽力而为" 的机会。随着分类的增长，会有一些明显的选择，但如果你选择了一个尚未完善的树，你将不得不尽力思考在哪里可以找到 `qna.yaml`。在这种情况下，杜威十进制系统表示体育应该在艺术下；这是美国橄榄球，德克萨斯大学的大学级别。此外，请注意空格的下划线；这很重要。

```bash
mkdir -p knowledge/arts/sports/american_football/college/university_of_texas/
```

最后，你可以下载 `template_qna.yaml` 并填写所需的问题和答案。确保上下文的最大长度约为 500 Tokens，问题和答案约为 250 Tokens。

```bash
wget https://raw.githubusercontent.com/instructlab/taxonomy/main/docs/template_qna.yaml
mv template_qna.yaml knowledge/arts/sports/american_football/college/university_of_texas/qna.yaml
```

```
vim knowledge/arts/sports/american_football/college/university_of_texas/qna.yaml
```
