# Flink原理与实践

## 简介

麻烦路过的朋友给**点个星星（star）**,也算是对我分享的认可，谢谢了！

![《Flink原理与实践》](./book.jpeg)

本工程主要使用Java和Scala演示如何使用Flink（v1.12.4）。用户需要安装Intellij Idea和Maven。我未来将更新到Flink最新版本。

我也写了一本关于Flink的中文书：《Flink原理与实践》，购买请戳👉 [京东链接](https://item.jd.com/13154364.html)。书配合代码，学习效率更高。

我的网站[http://lulaoshi.info/](https://lulaoshi.info/flink/)有对Flink的详细图文教程。

大家也可以通过微信公众号找到我：

![公众号](http://aixingqiu-1258949597.cos.ap-beijing.myqcloud.com/2019-11-20-021810.png)


## 目录结构

### 电子书部分：`doc`

`doc` 为开源电子书部分。

### Flink 案例部分：`src`

`src` 为 Flink 案例源代码。

`chapter2_basics` gives some basic examples on overloading, types, functional programming.

`chapter4_api` shows Flink transformation APIs without time or state.

`chapter5_time` shows how to use time and window.

`chapter6_state` gives example on state.

`chapter7_connector` gives example on Connector (Source and Sink).

`chapter7_sql` shows Table API & SQL.

`exercise` are projects using Flink.

## 参与贡献

### 构建指南

本书电子书 `doc` 基于 [Jupyter Book](https://jupyterbook.org/) 的 Python 工具构建。本书主要内容使用 `.md` 文件保存。Jupyter Book 工具可以将 `.md` 文件转化为 HTML 格式。

### 文字与代码风格指南

#### 文件

当你编写了新的文档后，请正确存放你的文件，并在本地检查它。

- 页面划分：所有文档请存放在 `ch-xxx/` 目录下，ch 是 chapter 的简写，每章建一个目录，每节建立一个 `.md` 文件。

- 图片存放：图片文件保存在每章的 `img` 文件夹下，其中 `drawio` 为使用 [draw.io](https://www.drawio.com/) 软件绘制的原图，`png` 为最后生成的图。[draw.io](https://www.drawio.com/) 可以 [在线](https://app.diagrams.net/) 绘制。

- 目录名与文件名字应简洁直观，间隔使用减号式（-）连接，小写。
    > 例 python-ecosystem.svg
    > 例 ch-python-lang

#### 文字

本教程面向针对初学者，文字风格请保持简洁高效，易于理解。任何有助于读者理解的文字，标识都是有帮助的。

- 首次出现的英文单词，应使用括号解释中文，下文可以继续使用该英文。
    >例 Deep Learning （深度学习）

- 首次出现的缩写，应使用括号解释全称和中文，下文可继续使用缩写。
    >例 API（Application Programming Interface，应用程序编程接口）

- 请在所有中文文字和半角的英文、数字、符号、链接前后插入空白，可以使用一些插件帮助进行空格的排版，比如 [VSCode pangu](https://marketplace.visualstudio.com/items?itemName=baurine.vscode-pangu)，或者安装 Python 版的 pangu 插件：`pip install -U pangu`。详情参考 [pangu](https://github.com/vinta/pangu.js)
  >例 欢迎star本仓库 --> 欢迎 star 本仓库

#### 代码

请尽可能的使你的代码有更强的可读性。

- 变量名应尽量使用有一定含义的 `英文` 单词，而不是拼音。

- 变量名尽量有意义，驼峰式命名，并保持可读性。除非简单示例中可以使用 `a = xx`，`b = xx` 外，建议复杂逻辑中不要出现 `a`，`b`，`c` 为名的的变量。可以使用 `i` ，`j` 这样的计数器。

- 函数名应使用下划线式命名，小写。
    >例 hello_world()

- 类名应大写，复杂类名应采用驼峰式命名。
    >例 class HelloWorld

### 电子书环境配置

准备环境：

* 选择一个包管理工具，比如 `conda`。
* 安装 Python >= 3.8
* 安装 requirements.txt 中的各个依赖。包括本书各个案例所需要的工具 pandas 等，以及本电子书构建工具 Jupyter Book：

```bash
conda create -n dispy
source activate dispy
conda install python=3.11 anaconda::graphviz
pip install -r requirements.txt
```

### 构建 HTML 格式

进入该项目文件夹，对项目进行构建：

```bash
cd doc
sh build.sh
```

### 启动 HTTP Server

构建好 HTML 文件后，如果是在自己的个人电脑，可以使用 Python 自带的 HTTP Server，并在浏览器里打开 http://127.0.0.1:8000 查看效果：

```bash
cd doc/_build/html
python -m http.server 8000
```

之后会在 `doc/_build/html` 目录下生成各类网页相关文件。