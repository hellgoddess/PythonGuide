# Python连载系列：认识Python

## 认识Python

> 本章目录：

+ Python简介-历史/优缺点
+ 搭建编程环境
+ 第一个Python程序
+ 注释

#### Python起源

1. 1989 年的圣诞节期间，吉多·范罗苏姆为了在阿姆斯特丹打发时间，决心开发一个新的**解释程序**，作为 ABC 语言的一种继承（**感觉下什么叫牛人**）
2. ABC 是由吉多参加设计的一种教学语言，就吉多本人看来，ABC 这种语言非常优美和强大，是**专门为非专业程序员设计的**。但是 ABC 语言并没有成功，究其原因，吉多认为是**非开放**造成的。吉多决心在 Python 中避免这一错误，并获取了非常好的效果
3. 之所以选中 Python（蟒蛇） 作为程序的名字，是因为他是 BBC 电视剧——蒙提·派森的飞行马戏团（Monty Python's Flying Circus）的爱好者
4. 1991 年，第一个 Python **解释器** 诞生，它是用 C 语言实现的，并能够调用 C 语言的库文件

> 在这里我们要去了解一下什么是解析器

![image-20210331164735838](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331164735838.png)

- **编译型语言**：程序在执行之前需要一个专门的编译过程，把程序编译成为机器语言的文件，运行时不需要重新翻译，直接使用编译的结果就行了。程序执行效率高，依赖编译器，跨平台性差些。如 C、C++
- **解释型语言**：解释型语言编写的程序不进行预先编译，以文本方式存储程序代码，会将代码一句一句直接运行。在发布程序时，看起来省了道编译工序，但是在运行程序的时候，必须先解释再运行

#### 编译型语言和解释型语言对比

- **速度** —— 编译型语言比解释型语言执行速度快
- **跨平台性** —— 解释型语言比编译型语言跨平台性好

#### Python的特点

- Python 是

  完全面向对象的语言

  - **函数**、**模块**、**数字**、**字符串**都是对象，**在 Python 中一切皆对象**
  - 完全支持继承、重载、多重继承
  - 支持重载运算符，也支持泛型设计

- Python **拥有一个强大的标准库**，Python 语言的核心只包含 **数字**、**字符串**、**列表**、**字典**、**文件** 等常见类型和函数，而由 Python 标准库提供了 **系统管理**、**网络通信**、**文本处理**、**数据库接口**、**图形系统**、**XML 处理** 等额外的功能

- Python 社区提供了**大量的第三方模块**，使用方式与标准库类似。它们的功能覆盖 **科学计算**、**人工智能**、**机器学习**、**Web 开发**、**数据库接口**、**图形系统** 多个领域

#### Python的优缺点

Python的优点很多，简单的可以总结为以下几点。

1. 简单明了，学习曲线低，比很多编程语言都容易上手。
2. 开放源代码，拥有强大的社区和生态圈，尤其是在数据分析和机器学习领域。
3. 解释型语言，天生具有平台可移植性，代码可以工作于不同的操作系统。
4. 对两种主流的编程范式（面向对象编程和函数式编程）都提供了支持。
5. 代码规范程度高，可读性强，适合有代码洁癖和强迫症的人群。

Python的缺点主要集中在以下几点。

1. 执行效率稍低，对执行效率要求高的部分可以由其他语言（如：C、C++）编写。
2. 代码无法加密，但是现在很多公司都不销售卖软件而是销售服务，这个问题会被弱化。
3. 在开发时可以选择的框架太多（如Web框架就有100多个），有选择的地方就有错误。

#### Python的应用领域

Python在Web应用后端开发、云基础设施建设、DevOps、网络数据采集（爬虫）、自动化测试、数据分析、机器学习等领域都有着广泛的应用。

#### 搭建编译环境

> 介绍一下Python有什么解释器

**Python 的解释器** 如今有多个语言的实现，包括：

- `CPython` —— 官方版本的 C 语言实现
- `Jython` —— 可以运行在 Java 平台
- `IronPython` —— 可以运行在 .NET 和 Mono 平台
- `PyPy` —— Python 实现的，支持 JIT 即时编译

### 交互式运行 Python 程序

- 直接在终端中运行解释器，而不输入要执行的文件名
- 在 Python 的 `Shell` 中直接输入 **Python 的代码**，会立即看到程序执行结果

#### 1) 交互式运行 Python 的优缺点

##### 优点

- 适合于学习/验证 Python 语法或者局部代码

##### 缺点

- 代码不能保存
- 不适合运行太大的程序

#### Windows环境

> 安装



首先，检查你的系统是否安装了Python。为此，在“开始”菜单中输入command 并按回车以打开一个命令窗口；你也可按住Shift键并右击桌面，再选择“在此处打开命令窗口”。在终 

端窗口中输入python并按回车；如果出现了Python提示符（>>> ），就说明你的系统安装了Python。然而，你也可能会看到一条错误消息，指出python 是无法识别的命令。 

如果是这样，就需要下载Windows Python安装程序。为此，请访问http://python.org/downloads/ 。你将看到两个按钮，分别用于下载Python 3和Python 2。单击用于下载Python 3的按 

钮，这会根据你的系统自动下载正确的安装程序。下载安装程序后，运行它。请务必选中复选框Add Python to PATH（如图1-2所示），这让你能够更轻松地配置系统。 

![image-20210331174038790](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331174038790.png)



如果系统显示api-ms-win-crt*.dll文件缺失，可以参照[《api-ms-win-crt*.dll缺失原因分析和解决方法》](https://zhuanlan.zhihu.com/p/32087135)一文讲解的方法进行处理或者直接在[微软官网](https://www.microsoft.com/zh-cn/download/details.aspx?id=48145)下载Visual C++ Redistributable for Visual Studio 2015文件进行修复；如果是因为更新Windows的DirectX之后导致某些动态链接库文件缺失问题，可以下载一个[DirectX修复工具](https://dl.pconline.com.cn/download/360074-1.html)进行修复。

**2.**  启动Python终端

通过配置系统，让其能够在终端会话中运行Python，可简化文本编辑器的配置工作。打开一个命令窗口，并在其中执行命令python 。如果出现了Python提示符（>>> ），就说明 

Windows找到了你刚安装的Python版本。 

#### Linux环境

Linux环境自带了Python 2.x版本，但是如果要更新到3.x的版本，可以在[Python的官方网站](https://www.python.org/)下载Python的源代码并通过源代码构建安装的方式进行安装，具体的步骤如下所示（以CentOS为例）。

1. 安装依赖库（因为没有这些依赖库可能在源代码构件安装时因为缺失底层依赖库而失败）。

```
yum -y install wget gcc zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel
```

1. 下载Python源代码并解压缩到指定目录。

```
wget https://www.python.org/ftp/python/3.7.6/Python-3.7.6.tar.xz
xz -d Python-3.7.6.tar.xz
tar -xvf Python-3.7.6.tar
```

1. 切换至Python源代码目录并执行下面的命令进行配置和安装。

```
cd Python-3.7.6
./configure --prefix=/usr/local/python37 --enable-optimizations
make && make install
```

1. 修改用户主目录下名为.bash_profile的文件，配置PATH环境变量并使其生效。

```
cd ~
vim .bash_profile
# ... 此处省略上面的代码 ...

export PATH=$PATH:/usr/local/python37/bin

# ... 此处省略下面的代码 ...
```

1. 激活环境变量。

```
source .bash_profile
```

#### macOS环境

macOS也自带了Python 2.x版本，可以通过[Python的官方网站](https://www.python.org/)提供的安装文件（pkg文件）安装Python 3.x的版本。默认安装完成后，可以通过在终端执行`python`命令来启动2.x版本的Python解释器，启动3.x版本的Python解释器需要执行`python3`命令。

### 运行Python程序

#### 确认Python的版本

可以Windows的命令行提示符中键入下面的命令。

```
python --version
```

![image-20210331165308176](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331165308176.png)

在Linux或macOS系统的终端中键入下面的命令。

```
python3 --version
```

当然也可以先输入`python`或`python3`进入交互式环境，再执行以下的代码检查Python的版本。

```
import sys

print(sys.version_info)
print(sys.version)
```

![image-20210331165439132](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331165439132.png)

### 第一个Python程序

#### 我们可以现在Python自带的idle中写我们的代码

![image-20210331165938038](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331165938038.png)

#### PyCharm - Python开发神器

### 1） 集成开发环境（IDE）

集成开发环境（`IDE`，Integrated Development Environment）—— **集成了开发软件需要的所有工具**，一般包括以下工具：

- 图形用户界面
- 代码编辑器（支持 **代码补全**／**自动缩进**）
- 编译器／解释器
- 调试器（**断点**／**单步执行**）
- ……

### 2）PyCharm 介绍

- `PyCharm` 是 Python 的一款非常优秀的集成开发环境

- `PyCharm` 除了具有一般 IDE 所必备功能外，还可以在 `Windows`、`Linux`、`macOS` 下使用

- ```
  PyCharm
  ```

   

  适合开发大型项目

  - 一个项目通常会包含 **很多源文件**
  - 每个 **源文件** 的代码行数是有限的，通常在几百行之内
  - 每个 **源文件** 各司其职，共同完成复杂的业务功能

![image-20210331173353219](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331173353219.png)

- **文件导航区域** 能够 **浏览**／**定位**／**打开** 项目文件

- **文件编辑区域** 能够 **编辑** 当前打开的文件

- 控制台区域

   

  能够：

  - 输出程序执行内容
  - 跟踪调试代码的执行

- 右上角的 **工具栏** 能够 **执行(SHIFT + F10)** / **调试(SHIFT + F9)** 代码

![image-20210331173422242](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331173422242.png)

- 通过控制台上方的**单步执行按钮(F8)**，可以单步执行代码

![image-20210331173444243](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331173444243.png)



### 注释

- 注释的作用
- 单行注释（行注释）
- 多行注释（块注释）

## 01. 注释的作用

> 使用用自己熟悉的语言，在程序中对某些代码进行标注说明，增强程序的可读性

## 单行注释(行注释)

- 以 `#` 开头，`#` 右边的所有东西都被当做说明文字，而不是真正要执行的程序，只起到辅助说明作用
- 示例代码如下：

```
# 这是第一个单行注释
print("hello python")
```

> 为了保证代码的可读性，`#` 后面建议先添加一个空格，然后再编写相应的说明文字

### 在代码后面增加的单行注释

- 在程序开发时，同样可以使用 `#` 在代码的后面（旁边）增加说明性的文字
- 但是，需要注意的是，**为了保证代码的可读性**，**注释和代码之间** 至少要有 **两个空格**
- 示例代码如下：

```
print("hello python")  # 输出 `hello python`
```

## 多行注释（块注释）

- 如果希望编写的 **注释信息很多，一行无法显示**，就可以使用多行注释
- 要在 Python 程序中使用多行注释，可以用 **一对 连续的 三个 引号**(单引号和双引号都可以)
- 示例代码如下：

```
"""
这是一个多行注释

在多行注释之间，可以写很多很多的内容……
""" 
print("hello python")
```

### 什么时候需要使用注释？

1. **注释不是越多越好**，对于一目了然的代码，不需要添加注释
2. 对于 **复杂的操作**，应该在操作开始前写上若干行注释
3. 对于 **不是一目了然的代码**，应在其行尾添加注释（为了提高可读性，注释应该至少离开代码 2 个空格）
4. 绝不要描述代码，假设阅读代码的人比你更懂 Python，他只是不知道你的代码要做什么

> 在一些正规的开发团队，通常会有 **代码审核** 的惯例，就是一个团队中彼此阅读对方的代码

### 关于代码规范

- `Python` 官方提供有一系列 PEP（Python Enhancement Proposals） 文档
- 其中第 8 篇文档专门针对 **Python 的代码格式** 给出了建议，也就是俗称的 **PEP 8**
- 文档地址：https://www.python.org/dev/peps/pep-0008/
- 谷歌有对应的中文文档：http://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_style_rules/

> 任何语言的程序员，编写出符合规范的代码，是开始程序生涯的第一步





### 拓展 -- 认识一下一些错误

#### 关于错误

- 编写的程序**不能正常执行**，或者**执行的结果不是我们期望的**

- 俗称

   

  ```
  BUG
  ```

  ，是程序员在开发时非常常见的，初学者常见错误的原因包括：

  1. 手误
  2. 对已经学习过的知识理解还存在不足
  3. 对语言还有需要学习和提升的内容

- 在学习语言时，不仅要**学会语言的语法**，而且还要**学会如何认识错误和解决错误的方法**

> 每一个程序员都是在不断地修改错误中成长的

#### 第一个演练中的常见错误

- 1> **手误**，例如使用 `pirnt("Hello world")`

```
NameError: name 'pirnt' is not defined

名称错误：'pirnt' 名字没有定义
```

- 2> 将多条 `print` 写在一行

```
SyntaxError: invalid syntax

语法错误：语法无效
```

> 每行代码负责完成一个动作

- 3> 缩进错误

```
IndentationError: unexpected indent

缩进错误：不期望出现的缩进
```

> - Python 是一个格式非常严格的程序设计语言
> - 目前而言，大家记住每行代码前面都不要增加空格

#### 单词列表

```
* error 错误
* name 名字
* defined 已经定义
* syntax 语法
* invalid 无效
* Indentation 索引
* unexpected 意外的，不期望的
* character 字符
* line 行
* encoding 编码
* declared 声明
* details 细节，详细信息
* ASCII 一种字符编码
```





### 练习

让我们一起得到Python之禅

1.在Python交互式环境中输入下面的代码并查看结果

```
import this
```

![image-20210331173825828](https://gitee.com/chushi123/picgo/raw/master/picture/image-20210331173825828.png)

2. 学习使用turtle在屏幕上绘制图形。

> **说明**：turtle是Python内置的一个非常有趣的模块，特别适合对计算机程序设计进行初体验的小伙伴，它最早是Logo语言的一部分，Logo语言是Wally Feurzig和Seymour Papert在1966发明的编程语言。

```
import turtle

turtle.pensize(4)
turtle.pencolor('red')


turtle.right(90)

turtle.right(90)
turtle.forward(100)
turtle.right(90)
turtle.forward(100)

turtle.mainloop()
```

![名片](https://gitee.com/chushi123/picgo/raw/master/picture/名片.png)
