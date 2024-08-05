class: middle, center

# Python

---
# Python 入门

斯坦福 CS231n Python 和 Numpy 入门

[Python + Numpy + Matplotlib Tutorial](http://cs231n.github.io/python-numpy-tutorial/) 

---
# 示范

打开 https://www.marscode.cn/dashboard

下载 [jupyter-notebook-tutorial.ipynb](../zip/jupyter-notebook-tutorial.ipynb)

上传后，运行

---
# Jupyter Notebook 介绍

两种 Cell
- Code cell
  - Python
  - 如果是命令行的话，前面加感叹号 !
- Markdown cell
  - Markdown 语法，支持 Latex

---
# 运行 Jupyter Notebook

- 用鼠标点击 Code Cell 左边的小三角运行
- 选择 Python 环境
  - 选“Recommended”（推荐的）就行
- 如果出错，不要紧张，仔细看看提示
  - 如果是：没有发现 xx Module，那么就是因为没有安装这个库
- 两种安装库的方法
  - 在 Terminal 里，pip install xx
  - 在 Code Cell 里，! pip install xx
- 安装成功后，再运行即可

---
# Python 入门

- Python versions
- Basic data types
- Containers
  - Lists
  - Dictionaries
  - Sets
  - Tuples
- Functions
- Classes

---
# Numpy 入门
- Arrays
- Array indexing
- Datatypes
- Array math
- Broadcasting
- Numpy Documentation

---
# SciPy 入门
- Image operations
- MATLAB files
- Distance between points

---
# Matplotlib 入门
- Plotting
- Subplots
- Images

下载图片 https://cs231n.github.io/assets/cat_tinted_imshow.png

上传，修改名字

---
class: middle, center
# 课后练习

---

# 课后练习 1: Duke 大学 Sta663

访问 https://github.com/cliburn/bios-823-2021/tree/main/notebooks

完成下面的练习

很多有趣的 Python 功能，强烈推荐

即使你很熟悉 Python 语言，也建议再练习练习

---
# 练习 I：Python

A01_Python_Concepts
- Python as a language
- Coding in Python

---
# 练习 II: NumPy

A02_Numpy_Concepts

- NDArray
- Indexing and slices
- Matrix multiplication
- Conditional replacement with where
- Array creating functions
- Reductions (margins)

---
# 练习 II: NumPy

A02_Numpy_Concepts

- Broadcasting
- Universal functions (ufunc)
- Einstein summation notation
- Random module (c.f. Scipy)
- Linear algebra submodule (c.f. Scipy)
- Masked array
- Memory mapping

---
class: middle, center

# 作业

---
# 作业 I：职场练习

- 你心仪职位的职责中，有没有需要用 Python 进行工作的地方？请举一个例子
- 针对上述例子，基于课上和课后练习的代码和数据，构造示例数据，实现对应的程序，并测试通过。简述设计思路。
- 按 STAR 原则，就上述工作写作 50 字的简历内容。简历内容需要言简意赅，很有吸引力。具体要求请参见《AI 帮工作 1：求职和申请》教程的 7-11 页，[链接](https://yishuai.github.io/talk/ai-career/index.html?p=4-1-apply.md#7)

---
# 作业提交链接

[【腾讯文档】作业：Python 编程](https://docs.qq.com/form/page/DT1ZwTlpvY3BjQ1lE)

???

课后练习 1：DS 100 Lab 1

- Jupyter Notebook
- Python
- Numpy
- Matplotlib

/Users/yishuai/Documents/Course/1-bigdata/研究生新课程/bigalgo/2-ds100/sp24/sp24-student-main/lab/lab01/lab01.ipynb

要编程

Python:

[Python Tutorial](https://docs.python.org/3.5/tutorial/): Teach yourself python. This is a pretty comprehensive tutorial.
[Python 101](http://nbviewer.jupyter.org/urls/bitbucket.org/hrojas/learn-pandas/raw/master/lessons/Python_101.ipynb): A notebook demonstrating a lot of python functionality with some (minimal explanation).

Python 资源

- [Official Python 3 Tutorial](https://docs.python.org/3/tutorial/)
- [Online, Interactive Python Interpreter](https://replit.com/)
- [Beginner's Python Guide (Python Like You Mean It)](https://www.pythonlikeyoumeanit.com/)
- [Beginner's Python Cheatsheet (PDF)](https://github.com/ehmatthes/pcc/releases/download/v1.0.0/beginners_python_cheat_sheet_pcc_all.pdf)
- [Vector/Matrix Operations in Numpy](https://cheatsheets.quantecon.org/)

???

编码约定

- Avoid magic numbers
  - 避免直接使用未经解释的常数值
  - 使用具有描述性名称的常量或变量来代替这些数字
  - 代码更容易理解，修改方便
- 避免复制和粘贴
  - 避免代码重复：DRY（Don't Repeat Yourself）原则
  - 将通用功能提取到函数中
- [PEP 8](https://peps.python.org/pep-0008/)

???

JupyterLab functionality 介绍视频

A quickest intro is this great 2-minute overview by Serena Bonaretti.
    https://www.youtube.com/watch?v=KyrJBlJB_po
    Note: Unlike Serena’s example, in our course we’re using JupyterLab notebooks hosted on the internet, not on your own local computer. 

The interface overview from the official docs has more details and short, embedded videos.
    https://jupyterlab.readthedocs.io/en/stable/user/interface.html

A more detailed discussion from a bio/data angle: ~45 minute video.
    https://www.youtube.com/watch?v=MAwgy1su75o

Full ~3h in-depth tutorial is available from the core team.
    https://www.youtube.com/watch?v=RFabWieskak

---
# 练习

[Kaggle 在线 Python 教程](https://www.kaggle.com/learn)

.center[.width-100[![](./kaggle.png)]]
