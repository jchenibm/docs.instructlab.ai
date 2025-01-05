---
title: 技能贡献入门
description: 向 🐶 InstructLab 添加技能
logo: images/ilab_dog.png
---
## 技能贡献入门

与知识贡献相比，技能贡献需要的内容量要小得多。整个技能贡献到分类树可能只需要在 `qna.yaml` 文件（"qna" 是 "questions and answers" 的缩写）中写几行 YAML 代码，以及一个用于引用来源的 `attribution.txt` 文件。

你的技能贡献拉取请求必须包含以下内容：

- 一个包含以下键的键/值条目集合的 `qna.yaml`
  - 每个 `qna.yaml` 文件至少需要五个问答对。
- 一个包含 `qna.yaml` 中使用的信息来源的 `attribution.txt`

!!! tip
    技能分类结构的用途有几个：

    1. 用于选择正确的分类子集来生成数据。
    2. 用于确定人类贡献者和维护者的可解释性。
    3. 作为用于生成合成样本的 LLM 提示的一部分。


!!! important
    模型处理问答对中的内容量是有限制的。因此，在 `qna.yaml` 文件中的问答种子示例对中最多只能添加约 2300 个单词。

组合技能可以是有基础的（包含上下文）或无基础的（不包含上下文）。有基础或无基础在分类树中声明，例如：`linguistics/writing/poetry/haiku/`（无基础）或 `grounded/linguistics/grammar`（有基础）。`qna.yaml` 位于最终节点中。

分类技能文件必须是一个名为 `qna.yaml` 的有效 [YAML](https://yaml.org/) 文件。每个 `qna.yaml` 文件包含一组具有以下键的键/值条目：

- `version`：值必须为数字 2。**必需**
- `task_description`：技能的描述。**必需**
- `created_by`：贡献者的 GitHub 用户名。**必需**
- `seed_examples`：键/值条目的集合。新提交应至少有五个条目，但旧文件可能较少。**必需**
  - `context`：有基础的技能需要用户提供上下文，其中包含模型在处理过程中需要考虑的信息。这与知识不同，在知识中，模型需要从调优过程中获取事实和背景知识。上下文键不应用于无基础的技能。
  - `question`：给模型的问题。**必需**
  - `answer`：模型的期望响应。**必需**

目前忽略任何级别的其他键。

### 技能：YAML 示例

为了使 `qna.yaml` 文件更容易和更快地被人类阅读，建议首先指定 `version`，然后是 `task_description`，接着是 `created_by`，最后是 `seed_examples`。
在 `seed_examples` 中，建议首先指定 `context`（如果适用），然后是 `question` 和 `answer`。

*示例 `qna.yaml`*

```yaml
version: 2
task_description: <string>
created_by: <string>
seed_examples:
  - question: <string>
    answer: |
      <multi-line string>
  - context: |
      <multi-line string>
    question: <string>
    answer: |
      <multi-line string>
  ...
```

然后，你需要创建一个包含你的信息来源的 `attribution.txt` 文件。这些也可以是自己创作的来源。

*示例 `attribution.txt`*

```text
[链接到来源]
[链接到作品]
[作品许可证]
[创作者姓名]
```

有关在 `attribution.txt` 文件中应包含什么的更多信息，请参见 CONTRIBUTING.md 中的 [对于你的 attribution.txt 文件](https://github.com/instructlab/taxonomy/blob/main/CONTRIBUTING.md#for-your-attributiontxt-file)。

如果你以前没有写过 YAML，不要害怕 - 它只是文本。

!!! tip

    - YAML 中的空格和缩进很重要。使用两个空格进行缩进。
    - 不要使用制表符！
    - 注意不要在行尾有尾随空格。
    - `seed_examples` 中的每个示例都以 "-" 开头。将此 "-" 放在第一个字段（`question` 或 `context`）前面。示例中的其余键不应有此 "-"。
    - 一些特殊字符（如 " 和 '）需要用反斜杠转义。这就是为什么示例 YAML 中某些键的行以 '|' 字符开始，后面跟着新行，然后是缩进的多行字符串。
    此字符禁用该键的值中的所有特殊字符。
    你可能还想为多行字符串使用 '|' 字符。
    - 考虑用 " 引用所有值，以避免 YAML 解析器的意外行为
    （例如，Yes 答案可能被解析器解释为 `True` 布尔值，除非 "Yes" 被引用。）
    - 更多信息请参见 https://yaml-multiline.info/。

建议你使用工具对 YAML 进行**检查**或验证。一个检查选项是 [yamllint.com](https://yamllint.com)。你可以将你的 YAML 复制/粘贴到框中，然后点击 **Go** 让它分析你的 YAML 并提出建议。像 [prettified](https://onlineyamltools.com/prettify-yaml) 和 [yaml-validator](https://jsonformatter.org/yaml-validator) 这样的在线工具可以自动重新格式化你的 YAML，以符合我们的 `yamllint` PR 检查，例如将超过 120 个字符的行分行。

#### 无基础组合技能：YAML 示例

```yaml
version: 2
task_description: '教模型如何押韵。'
created_by: juliadenham
seed_examples:
  - question: 有哪 5 个词与 horn 押韵？
    answer: warn、torn、born、thorn 和 corn。
  - question: 有哪 5 个词与 cat 押韵？
    answer: bat、gnat、rat、vat 和 mat。
  - question: 有哪 5 个词与 poor 押韵？
    answer: door、shore、core、bore 和 tore。
  - question: 有哪 5 个词与 bank 押韵？
    answer: tank、rank、prank、sank 和 drank。
  - question: 有哪 5 个词与 bake 押韵？
    answer: wake、lake、steak、make 和 quake。
```

就是这样。

这是该 YAML 在分类树中的位置。注意，就分类贡献而言，YAML 文件本身加上包含该文件的任何添加目录就是技能的全部内容：

#### 无基础组合技能：目录树示例

```ascii
[...]

└── writing
    └── poetry
    |   └── haiku <=== 就在这里 :)
    |   |   └── qna.yaml
    |   |       attribution.txt
        [...]
    └── prose
    |   └── debate
    |   |   └── qna.yaml
    |   |       attribution.txt
    [...]

[...]
```

#### 有基础组合技能：YAML 示例

请记住，[有基础组合技能](skills_guide.md#grounded-compositional-skills) 需要额外的上下文，并包含一个 `context` 字段。

这个示例片段假设 GitHub 用户名为 `mairin`，并显示了实际文件中存在的一些问答对：


```yaml
version: 2
task_description: |
    此技能提供读取 markdown 格式表格的能力。
created_by: mairin # 使用你的 GitHub 用户名；仅支持一个创建者
seed_examples:
  - context: |
      | **品种**      | **体型**     | **吠叫** | **精力** |
      |----------------|--------------|-------------|------------|
      | 阿富汗猎犬   | 25-27 英寸     | 3/5         | 4/5        |
      | 拉布拉多       | 22.5-24.5 英寸 | 3/5         | 5/5        |
      | 可卡犬 | 14.5-15.5 英寸 | 3/5         | 4/5        |
      | 玩具贵宾犬   | <= 10 英寸     | 4/5         | 4/5        |
    question: |
      哪个品种精力最充沛？
    answer: |
      精力最充沛的品种是拉布拉多。
  - context: |
      | **姓名** | **日期** | **颜色** | **字母** | **数字** |
      |----------|----------|-----------|------------|------------|
      | George   | 3月5日    | 绿色     | A          | 1          |
      | Gráinne  | 12月31日   | 红色       | B          | 2          |
      | Abigail  | 1月17日   | 黄色    | C          | 3          |
      | Bhavna   | 4月29日   | 紫色    | D          | 4          |
      | Rémy     | 9月9日    | 蓝色      | E          | 5          |
    question: |
      Gráinne 的字母是什么，她的颜色是什么？
    answer: |
      Gráinne 的字母是 B，她的颜色是红色。
  - context: |
      | 香蕉 | 苹果      | 蓝莓 | 草莓 |
      |--------|------------|-----------|------------|
      | 黄色 | 红色、绿色 | 蓝色      | 红色        |
      | 大  | 中等     | 小     | 小      |
      | 有皮   | 有皮       | 无皮   | 无皮    |
    question: |
      哪种水果是蓝色的、小的，而且没有皮？
    answer: |
      蓝莓是蓝色的、小的，而且没有皮。
```

#### 有基础组合技能：目录树示例

```ascii
[...]

grounded
└── technology
    └── machine_learning
        └── natural_language_processing
    |   |     └── information_extraction
    |            └── inference
    |   |            └── qualitative
    |   |               ├── sentiment
    |   |               |     └── qna.yaml
    |   |               |         attribution.txt
    │                   ├── quantitative
    │   │                   ├── table_analysis <=== 就在这里 :)
    │   |   |               |     └── qna.yaml
    │   │   │               |         attribution.txt

[...]
```

