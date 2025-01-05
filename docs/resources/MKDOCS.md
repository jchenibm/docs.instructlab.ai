# mkdocs 示例

本页面包含一些使用 `mkdocs` 可以实现的巧妙技巧。有关完整的示例列表，请访问 [mkdocs 文档](https://squidfunk.github.io/mkdocs-material-insiders/reference/abbreviations/)。

## 代码

```python
print("hello world!")
```

## 带行号的代码

```python linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

## 带高亮的代码

```python hl_lines="2 3"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

## 带标签的代码

=== "标签标题"

    ```c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "另一个标签标题"

    ```c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

## 更多标签

=== "Windows"

    如果使用 Windows，下载 `Win32.zip` 文件并安装它。

=== "MacOS"

    运行 `brew install foo`。

=== "Linux"

    运行 `apt-get install foo`。

## 检查列表

* [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
* [ ] Vestibulum convallis sit amet nisi a tincidunt
* [x] In hac habitasse platea dictumst

## 添加按钮

[启动实验室](https://developer.ibm.com){: .md-button .md-button--primary }

[访问 IBM Developer](https://developer.ibm.com){: .md-button }

[注册！ :fontawesome-solid-paper-plane:](https://cloud.ibm.com){: .md-button .md-button--primary }

## 提示框

!!! tip
    你可以使用 `note`、`abstract`、`info`、`tip`、`success`、`question`、
    `warning`、`failure`、`danger`、`bug`、`quote` 或 `example`。

!!! note
    一个注释。

!!! abstract
    一个摘要。

!!! info
    一些信息。

!!! success
    一个成功。

!!! question
    一个问题。

!!! warning
    一个警告。

!!! danger
    一个危险。

!!! example
    一个示例。

!!! bug
    一个错误。

## 带代码的提示框

!!! note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

    ```python
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    Nunc eu odio eleifend, blandit leo a, volutpat sapien. Phasellus posuere in
    sem ut cursus. Nullam sit amet tincidunt ipsum, sit amet elementum turpis.
    Etiam ipsum quam, mattis in purus vitae, lacinia fermentum enim.

## 格式化

除了常用的 *斜体* 和 **粗体** 外，现在还支持：

* ==高亮==
* ^^下划线^^
* ~~删除线~~

## 表格

| **操作系统或应用** | **用户名** | **密码** |
| - | - | - |
| Windows VM | `Administrator` | `foo` |
| Linux VM | `root` | `bar` |

## 表情符号

是的，这些都可以使用。 :smiley: :+1:

## 图片

![图片](../images/ilab_dog.png)

Nunc eu odio eleifend, blandit leo a, volutpat sapien

## 右对齐图片

![占位图](../images/ilab_dog.png){: align=right }

Nunc eu odio eleifend, blandit leo a, volutpat sapien
