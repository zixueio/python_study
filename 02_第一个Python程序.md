# 第一个Python程序
## 目标
- 执行`Python`程序的三种方式
	- 解释器——`python`/`python3`
	- 交互式——`ipython`
	- 集成开发环境——`PyCharm`
## 01.第一个程序
### 1.1Python源程序的基本概念
1. Python的源程序就是**一个特殊格式的文本文件**，可以**使用任意文本编辑软件**做`Python`的开发
2. Python源程序的**文件扩展名**通常都是`.py`
### 1.2演练步骤
>`print`函数的作用，可以把""内部的内容，输出到屏幕上
### 1.3认识错误（BUG）
#### 关于错误
- 编写的程序**不能正常执行**，或者**执行的结果不是我们期待的**
- 俗称`BUG`，而程序员在开发时非常常见的，初学者常见错误的原因包括：
	1. 手误
	2. 对已经学习过的知识理解还存在不足
	3. 对语言还需要学习和提升的内容
- 在学习语言时，不仅要**学会语言的语法**，而且还要**学会如何认识错误和解决错误的方法**
> 每一个程序员都是在不断地修改错误中成长的
#### 常见错误
- `NameError`：名称错误
```
pirnt("Hello world")
NameError: name 'pirnt' is not defined. Did you mean: 'print'?
```
- `invalid syntax`：语法无效
```
    print("hello") print("hello")
                   ^^^^^
SyntaxError: invalid syntax
```
> 每行代码负责完成一个动作
- `IndentationError: unexpected indent`：`缩进错误：不期望出现的缩进`
```
    print("hello")
IndentationError: unexpected indent
```
> - Python是一个格式非常严格的程序设计语言
> - 目前而言，大家记住每行代码前面都不要添加空格
- **python 2.x默认不支持中文**
目前市场上有两个Python的版本并存着，分别是`Python 2.x`和`Python 3.x`

- **Python 2.x默认不支持中文**，具体因为**字符编码**
- Python 2.x的解释器名称是**python**
- Python 3.x的解释器名称是**python3**
## 02.Python2.x与3.x版本简介
目前市场上有两个Python版本并存着，分别是`Python 2.x`和`Python 3.x`
> 新的Python程序建议使用`Python 3.x`版本的语法
- Python 2.x是**过去版本**
	- 解释器名称是 **python**
- Python 3.x是**现在和未来 主流的版本**
	- 解释器名称是**python3**
	- 相对于`Python`的早期版本，这是一个**较大的升级**
	- 为了不带入过多的累赘，`Python 3.0`在设计的时候**没有考虑向下兼容**
		- 许多早期`Python`版本设计的程序无法在`Python 3.0`上正常进行
- Python 3.0发布于**2008年**
- 到目前为止，Python 3.0的稳定版本已经有很多年了
	- Python 3.3发布于2012
	- Python 3.4发布于2014
	- Python 3.5发布于2015
	- Python 3.6发布于2016
- 为了照顾现有的程序，官方提供了一个过渡版本--**Pyhon 2.6**
	- 基本使用了`Python 2.x`的语法和库
	- 同时考虑了向`Python 3.0`的迁移，**允许部分使用**`Python 3.0`的语法与函数
	- 2010 年中推出的`Python 2.7`被确定为**最后一个Python2.x版本**
> 提示：如果开发时，无法立即使用Python 3.0（还有极少的第三方库不支持3.0的语法），建议
> - 先使用`Python 3.0`版本进行开发
> - 然后使用`Python 2.6`、`Python 2.7`来执行，并且做一些兼容性的处理
## 03.执行Python程序的三种方式
### 3.1.解释器python/python3
#### Python的解释器
```
# 使用 python 2.x 解释器
$ python xxx.py

# 使用 python 3.x 解释器
$ python3 xxx.py
```
#### 其他解释器
**Python的解释器**如今有多个语言的实现，包括：
- `CPython`--官方版本的C语言实现
- `Jython`--可以运行在Java平台
- `IronPython`--可以运行在.NET和Mono平台
- `PyPy`--Python实现的，支持JIT及时编译
### 3.2.交互式运行Python程序
- 直接在终端中运行解释器，而不输入要执行的文件名
- 在Python的`Shell`中直接输入**Python的代码**，会立即看到程序执行结果
#### 1)交互式运行Python的优缺点
**优点**
- 适用于学习/验证Python语法或者布局代码
**缺点**
- 代码不能保存
- 不适合运行太大的程序
#### 2)退出 官方的解释器
**1>**直接输入exit()
```
>>> exit()
```
**2>使用热键退出**
在Python解释器中，按热键`ctrl+d`可以退出解释器
#### 3)IPython
- IPython中的“i”代表**交互interactive**
**特点**
- IPython是一个python的**交互式shell**，比默认的`python shell`好用得多
	- 支持自动补全
	- 自动缩进
	- 支持`bash shell`命令
	- 内置了许多有很多有用的功能和函数
- IPython是基于BSD开源的
**版本**
- Python 2.x使用的解释器是**ipython**
- Python 3.x使用的解释器是**ipython3**
- 要退出解释器可以有以下两种方式：
**1>直接输入exit**
```
>>> exit
```
**2>使用热键退出**
在IPython解释器中，按下热键`ctrl+d`，`IPython`会询问是否退出解释器
### 3.3 Python的IDE——PyCharm
#### 1) 集成开发环境（IDE）
集成开发环境（`IDE`，Integrated Development Environment）——**集成了开发软件需要的所有工具**，一般包括以下工具：
- 图形用户界面
- 代码编辑器（支持 **代码补全/自动缩进**）
- 编译器/解释器
- 调试器（**断点/单步执行**）
#### 2) PyCharm介绍
- `PyCharm`是Python的一款非常优秀的集成开发环境
- `PyCharm`除了具有一般IDE所具备的功能外，还可以在`Windows`、`Linux`、`macOS`下使用
- `PyCharm`适合开发大型项目
	- 一个项目通常会包含**很多文件**
	- 每个**源文件**的代码行数是有限的，通常在几百行之内
	- 每个**源文件**各司其职，共同完成复杂的业务功能
#### 3) PyCharm快速体验
- **文件导航区域**能够**浏览/定位/打开**项目文件
- **文件编辑区域**能够**编辑**当前打开的文件
- **控制台区域**能够：
	- 输出程序执行内容
	- 跟踪调试代码的执行
- 右上角的**工具栏**能够**执行（SHIFT+f10）/调试（SHIFT+F9）**代码

