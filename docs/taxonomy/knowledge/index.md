---
title: 知识贡献入门
description: 向 🐶 InstructLab 添加知识
logo: images/ilab_dog.png
---
## 知识贡献入门

与技能相比，知识更多地基于回答涉及事实、数据或参考资料的问题。

知识需要文档支持，如教科书、技术手册、百科全书、期刊或杂志。

分类树中的知识包含比技能更多的元素：

- 树中的每个知识节点都有一个 `qna.yaml`，格式类似于技能的 `qna.yaml`。
- ⭐ 知识提交需要你创建一个 Git 仓库 (可以是 GitHub)，其中包含你的知识贡献的 markdown 文件。这些仓库中的贡献必须使用 markdown (`.md`) 格式。
- `qna.yaml` 包含来自你的仓库的信息参数。

!!! tip
    知识贡献指南

    - 提交文档的最新版本
    - 所有提交必须是文本；图片将被忽略
    - 不要在你的 markdown 自由格式贡献中使用表格

`qna.yaml` 格式必须包含以下字段：

- `version`：`qna.yaml` 文件的版本；这是用于 SDG 的文件格式。值必须是数字 3。
- `created_by`：你的 GitHub 用户名。
- `domain`：指定知识的类别。
- `seed_examples`：键/值条目的集合。
  - `context`：来自知识文档的信息块。每个 `qna.yaml` 需要五个 `context` 块。context 的最大 token 数为 500 个。此外，每个 `context` 块应至少有 3 个问答对，所有 3 个问答对的最大 token 数为 250。
  - `questions_and_answers`：保存你的问题和答案的参数。
    - `question`：为模型指定一个问题。每个 `qna.yaml` 文件每个 `context` 块需要至少三个问答对。
    - `answer`：指定模型的期望答案。每个 `qna.yaml` 文件每个 `context` 块需要至少三个问答对。
- `document_outline`：描述你提交的文档概述。
- `document`：你的知识贡献的来源。
  - `repo`：存放你的知识 markdown 文件的仓库的 URL。
  - `commit`：你的仓库中包含知识 markdown 文件的提交的 SHA。
  - `patterns`：指定仓库中 markdown 文件的 glob 模式列表。任何以 `*` 开头的 glob 模式，如 `*.md`，由于 YAML 规则必须用引号括起来。例如，`"*.md"`。

### 知识：YAML 示例

*`qna.yaml` 文件示例*

```yaml
version: 3
domain: astronomy
created_by: juliadenham
seed_examples:
  - context: |
      **Phoenix** 是南天的一个小星座。它以神话中的凤凰命名，首次出现在 Johann Bayer 1603 年的
      *Uranometria* 星图集中。法国探险家和天文学家 Nicolas Louis de
      Lacaille 在 1756 年绘制了较亮的恒星并给出了它们的拜耳命名。
      这个星座的赤纬范围大约在 -39 度到 -57 度之间，赤经范围在 23.5h 到 2.5h 之间。
      凤凰座、天鹤座和孔雀座被称为南天鸟星座。
    questions_and_answers:
      - question: |
          什么是凤凰座？
        answer: |
          凤凰座是南天的一个小星座。
      - question: |
          谁绘制了凤凰座？
        answer: |
          凤凰座是由法国探险家和天文学家 Nicolas Louis de Lacaille 绘制的。
      - question: |
          凤凰座的范围有多大？
        answer: |
          凤凰座的赤纬范围大约在 -39° 到 -57° 之间，赤经范围在 23.5h 到 2.5h 之间。
  - context: |
      凤凰座是 Petrus Plancius 根据 Pieter Dirkszoon Keyser 和 Frederick de
      Houtman 的观测建立的 12 个星座中最大的一个。它首次出现在 Plancius 和 Jodocus Hondius
      于 1597 年 (或 1598 年) 在阿姆斯特丹出版的直径 35 厘米的天球仪上。这个星座首次在天图集中的
      描绘是在 Johann Bayer 1603 年的 *Uranometria* 中。De Houtman 在同年的南天星表中以荷兰语
      *Den voghel Fenicx*，"凤凰鸟"命名，象征着古典神话中的凤凰。最亮星 Alpha
      Phoenicis 的一个名字—Ankaa—源自阿拉伯语：العنقاء，罗马化：al-'anqā'，
      意为"凤凰"，这个名字是在 1800 年之后根据这个星座而创造的。
    questions_and_answers:
      - question: |
          凤凰座最亮的星星叫什么？
        answer: |
          凤凰座最亮的星星是 Alpha Phoenicis 或 Ankaa。
      - question: 凤凰座首次出现在哪里？
        answer: |
          凤凰座首次出现在 Plancius 和 Jodocus Hondius 于 1597 年 (或 1598 年) 在
          阿姆斯特丹出版的直径 35 厘米的天球仪上。
      - question: |
          "凤凰鸟"象征着什么？
        answer: |
          "凤凰鸟"象征着古典神话中的凤凰。
  - context: |
      凤凰座是一个小星座，北面是天炉座和玉夫座，西面是天鹤座，南面是杜鹃座，
      与南面的水蛇座相接，东面和东南面是波江座。附近有明亮的水委星。
      这个星座的三字母缩写是"Phe"，由国际天文联合会于 1922 年采用。由比利时天文学家
      Eugène Delporte 于 1930 年确定的官方星座边界由 10 段多边形定义。在赤道坐标系中，
      这些边界的赤经坐标在 23h 26.5m 和 02h 25.0m 之间，而赤纬坐标在 -39.31° 和 -57.84° 之间。
      这意味着对于生活在北半球 40 度纬线以北的人来说，它始终在地平线以下，对于生活在赤道以北的人来说，
      它在天空中的位置始终很低。它在南半球春季末期从澳大利亚和南非等地区最容易看到。
      大部分星座位于明亮的水委星、北落师门和参宿七形成的三角形内，并可以通过这个三角形找到位置
      —Ankaa 大致位于这个三角形的中心。
    questions_and_answers:
      - question: 凤凰座有什么特点？
        answer: |
          凤凰座是一个小星座，北面是天炉座和玉夫座，西面是天鹤座，南面是杜鹃座，
          与南面的水蛇座相接，东面和东南面是波江座。附近有明亮的水委星。
      - question: |
          凤凰座什么时候最容易看到？
        answer: |
          凤凰座在南半球春季末期从澳大利亚和南非等地区最容易看到。
      - question: |
          凤凰座的边界是什么？
        answer: |
          凤凰座的官方边界由比利时天文学家 Eugène Delporte 于 1930 年确定，
          由 10 段多边形定义。
  - context: |
      迄今为止，已发现十颗恒星有行星，其中四个行星系统是通过 SuperWASP 项目发现的。
      HD 142 是一颗视星等为 5.7 的黄巨星，它有一颗质量是木星 1.36 倍的行星 HD 142b，
      轨道周期为 328 天。HD 2039 是一颗距离约 330 光年的视星等为 9.0 的黄亚巨星，
      它有一颗质量是木星 6 倍的行星 HD 2039 b。WASP-18 是一颗视星等为 9.29 的恒星，
      发现它有一颗类木星行星，绕恒星一圈的时间不到一天。这颗行星被怀疑导致 WASP-18 看起来
      比实际年龄更老。WASP-4 和 WASP-5 是距离约 1000 光年、视星等为 13 等的太阳型黄色恒星，
      每颗恒星都有一颗比木星大的行星。WASP-29 是一颗光谱型为 K4V、视星等为 11.3 的橙矮星，
      它有一颗大小和质量与土星相似的伴星。这颗行星每 3.9 天完成一次轨道运行。
    questions_and_answers:
      - question: 在凤凰座中，有多少颗恒星有行星？
        answer: |
          在凤凰座中，迄今为止已发现十颗恒星有行星，其中四个行星系统是通过
          SuperWASP 项目发现的。
      - question: |
          什么是 HD 142？
        answer: |
          HD 142 是一颗视星等为 5.7 的黄巨星，它有一颗质量是木星 1.36 倍的行星
          (HD 142 b)，轨道周期为 328 天。
      - question: |
          WASP-4 和 WASP-5 是太阳型黄色恒星吗？
        answer: |
          是的，WASP-4 和 WASP-5 是距离约 1000 光年、视星等为 13 等的太阳型黄色恒星，
          每颗恒星都有一颗比木星大的行星。
  - context: |
      这个星座不在银河系的银道面上，也没有显著的星团。NGC 625 是一个视星等为 11.0、
      距离约 1270 万光年的不规则矮星系。它的直径只有 24000 光年，是玉夫座星系群的
      外围成员。NGC 625 被认为经历过碰撞，正在经历一次剧烈的恒星形成。NGC 37 是一个
      视星等为 14.66 的透镜状星系。它的直径约为 42 千秒差距，年龄约为 129 亿年。
      罗伯特四重星系 (包括不规则星系 NGC 87 和三个螺旋星系 NGC 88 和 NGC 92) 是一组
      距离约 1.6 亿光年的四个星系，它们正在发生碰撞和合并。它们位于半径为 1.6 角分的圆内，
      相当于约 75,000 光年。在星系 ESO 243-49 中有一个 HLX-1，这是一个中等质量黑洞
      intermediate-mass_black_hole —第一个被确认的此类黑洞。它被认为是一个矮星系在与
      ESO 243-49 碰撞时被吸收的残余。在它被发现之前，这类黑洞只是一个假设。
    questions_and_answers:
      - question: |
          凤凰座是银河系的一部分吗？
        answer: |
          凤凰座不在银河系的银道面上，也没有显著的星团。
      - question: |
          NGC 625 有多远？
        answer: |
          NGC 625 的直径为 24000 光年，是玉夫座星系群的外围成员。
      - question: |
          罗伯特四重星系由什么组成？
        answer: |
          罗伯特四重星系由不规则星系 NGC 87 和三个螺旋星系 NGC 88、NGC 89 和 NGC 92 组成。
document_outline: |
  关于凤凰座的信息，包括该星座的历史、特征和其中恒星的特点。
document:
    repo: https://github.com/juliadenham/Summit_knowledge
    commit: 0a1f2672b9b90582e6115333e3ed62fd628f1c0f
    patterns:
      - phoenix_constellation.md
```

*`attribution.txt` 文件示例*

```text
作品标题：Phoenix (constellation)
作品链接：https://en.wikipedia.org/wiki/Phoenix_(constellation)
修订版本：https://en.wikipedia.org/w/index.php?title=Phoenix_(constellation)&oldid=1237187773
作品许可证：CC-BY-SA-4.0
创作者姓名：Wikipedia Authors
```

有关在 `attribution.txt` 文件中应包含什么的更多信息，请参见 CONTRIBUTING.md 中的 [对于你的 attribution.txt 文件](https://github.com/instructlab/taxonomy/blob/main/CONTRIBUTING.md#for-your-attributiontxt-file)。

### 知识：Markdown 文件示例

前面的知识示例引用了一个 markdown 文件：`phoenix_constellation.md`。你也可以为知识贡献添加多个 markdown 文件。

!!! note
    由于内容量较大，**知识贡献拉取请求的接受时间自然会比技能拉取请求更长**。
    较小的拉取请求更简单，需要的审查时间和精力更少。

这些 markdown 文件可能是什么样的？它们可以是自由格式的。以下是你的 Git 仓库中 `phoenix_constellation.md` 的一个片段示例。

*`.md` 文件示例*

```markdown
# Phoenix (constellation)

**Phoenix** 是南天的一个小星座。它以神话中的凤凰命名，首次出现在 Johann Bayer 1603 年的
*Uranometria* 星图集中。法国探险家和天文学家 Nicolas Louis de
Lacaille 在 1756 年绘制了较亮的恒星并给出了它们的拜耳命名。
这个星座的赤纬范围大约在 -39 度到 -57 度之间，赤经范围在 23.5h 到 2.5h 之间。
凤凰座、天鹤座和孔雀座被称为南天鸟星座。

最亮的恒星 Alpha Phoenicis 被命名为 Ankaa，这是一个意为"凤凰"的阿拉伯语单词。
它是一颗视星等为 2.4 的橙色巨星。其次是 Beta Phoenicis，实际上是一个由两颗黄色巨星组成的
双星系统，合并视星等为 3.3。Nu Phoenicis 有一个尘埃盘，而这个星座有十个已知有行星的恒星系统
和最近发现的星系团 El Gordo 和凤凰星系团—分别位于 72 亿和 57 亿光年之外，是可见宇宙中最大的
天体之一。凤凰座是两个年度流星雨的辐射点：12 月的凤凰座流星雨和 7 月凤凰座流星雨。
```

你可以按照自己的方式组织你的仓库中的知识 markdown 文件。你只需要确保 YAML 指向正确的文件。

### 知识：目录树示例

在分类系统仓库中，前面提到的知识在树中的位置可能如下所示：

```ascii
[...]

└── knowledge
    └── science
        ├── astronomy
        │ └── constellations
        │     └── Phoenix <=== 就在这里 :)
        │     |    └── qna.yaml
        |     |        attribution.txt
        │     └── Orion
        │          └── qna.yaml
        |              attribution.txt
[...]
```
