.. MYPYTHON documentation master file, created by
   sphinx-quickstart on Sat Jul 13 10:24:25 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.


Pyhton是当今最流行的编程语言
----------------------------


Python的诞生及发展
====================

在Python主页上有这样一句话来介绍它：
::

    Python is a programming language that lets you work more quickly and integrate your systems more effectively.

**让你的工作更高效**，实际上Python就是在一个这样一个明确的目标下被创建的，经过30年的不断发展，简洁，高效的特色帮助她成为当今最流行的编程语言之一。


Python不是一个从零开始的项目，她继承于 `ABC语言 <https://abclang.com>`_ 。

Python作者 `Guido von Rossum <https://en.wikipedia.org/wiki/Guido_van_Rossum>`_ 曾在ABC项目组中工作多年，Python的许多语法来自C，同时受到ABC的强烈影响。比如用缩进表示代码嵌套，变量不需声明等。

ABC语言主要用于教学及原型设计，其设计又受 `SETL语言 <https://setl.org/setl/>`_ 启发。
Python开发过程中还受到 `Modula-3语言 <http://modula3.org>`_ 的影响。

.. image:: ./_static/guido01.jpg
  :width: 640 px
  :height: 427 px

Guido von Rossum（吉多·范罗苏姆）, 1956年1月31日出生于荷兰Haarlem，在阿姆斯特丹大学获得数学和计算机科学硕士学位。曾在在多个研究机构工作，包括在荷兰阿姆斯特丹的国家数学和计算机科学研究学会（CWI），马里兰州Gaithersburg的国家标准及技术研究所（NIST），维珍尼亚州Reston的国家创新研究公司（CNRI）。

**1989年** 的圣诞假期成为Guido创立Python的起点(在此之前已经有了相关的构想)。后来他又明确了Python的目标：
::

    An easy and intuitive language just as powerful as major competitors
    一门简单直观的语言并与主要竞争者一样强大

    Open source, so anyone can contribute to its development
    开源，以便任何人都可以为它做贡献

    Code that is as understandable as plain English
    代码像纯英语那样容易理解

    Suitability for everyday tasks, allowing for short development times
    适用于短期开发及日常任务


从语言设计角度来看，Python将许多机器层面上的细节隐藏，交给解析器处理，并凸显出逻辑层面的编程思考。Python程序员可以花更多的时间用于思考程序的逻辑，而不是具体的实现细节。这个特性得到程序员的关注，Python开始流行。

1991年，第一个Python解释器诞生，用C语言实现，也称CPython。如今，官方的解释器仍然使用C实现，但类似JPython（JAVA），Pypy（JIT），IronPython（.net）等也解释器也有各自适合的使用场景。

2000年，Python2发布，支持垃圾回收，Unicode等新特性。最新声明中，Python2将于2020年停止维护。

2008年，Python3发布。Python3的解释器并非完全兼容Python2，但提供了2to3的工具将Python2的代码转换为Python3。

时至今日，Python已成为众多热门领域如人工智能，大数据，科学计算等的必备技术。有许多优秀稳定的资源库共开发者免费使用。可以说是一门非常成功的编程语言。

------


Python语法
----------

动态类型语言
============



交互式编程
==========



一个简单的Python程序
====================

Python例子：

.. code-block:: python
    :caption: sample.py
    :name: sample
    :emphasize-lines: 1
    :linenos:

    #!/usr/bin/python
    # -*- coding: utf-8 -*-

    import platform

    print("Hello Python.")
    print("Power by ", end='')
    print(platform.platform(), platform.python_version())

    def Fibonacci(max):
        """
        斐波那契数列生成

        生成不超过参数max的斐波那契数列。
        """

        a, b = 0, 1
        # a = 0; b = 1  #此行分号不能省略
        while b <= max:
            print (b)
            a, b = b, a + b


    if __name__ == "__main__":
        print(Fibonacci.__doc__)
        Fibonacci(100)

注释
~~~~

Python使用“#”注释单行语句，用法类似C语言的“//”。

对于多行注释，Python没有专用的语法，但可以采用变通的方法即使用连续的三个单引号或双引号, 如'''this is a comment''' 或者 \"""this is a comment\"""。
但由于连续的三个引号有其它用途——文档字符串，所以不推荐用在一般注释中。

单引号与双引号在Python中的语义是相同的，当要描述一个含有引号的字符串时，可以像下面这样定义
::

    str = 'Hello my name is "Python".'

缩进
~~~~~~

Python使用缩进来描述嵌套，在编写Python代码时，请使用带有空格/Tab提示的编辑器，防止此类问题带来的功能错误。

PEP8规定使用4个空格作为每级缩进，其他空格数和Tab虽然可以被编译器识别，但不符合Python规范。
支持其他空格数和Tab仅仅是因为兼容一些古老的代码和个别不智能的编辑器。

请注意，空格与Tab混用会解释器会报错(TabError)。

文档字符串
~~~~~~~~~~~~

每个对象都有一个__doc__的属性，提供该对象的简单描述，以三引号'''或"""包裹起来，其内部文本格式会被保留。

换行
~~~~

Python不要求每行以分号；结束，但加上分号也是被允许的。
当想在一行中执行多条语句时，可以使用分号。
从Python风格角度来说，不推荐以分号作为行结束符。
::

    a = 1; b =2 #此行分号不能省略
    print(a, b)

__name__
~~~~~~~~~~

Python中所有都被看做对象，每个对象都有自己的属性，以__XXXX__形式表示。（可以把属性看作是一些特殊的变量）

__name__就是对象(class/function/method/descriptor/generator instance)的属性之一。

在本例中可以看作是sample.py的属性，当该文件被Python解析器直接执行时，__name__被设置为__main__，否则将被设置为模块名称。


变量和运算符
============

变量和基本数据类型
~~~~~~~~~~~~~~~~~~~~

变量使用前不需要声明，但试图读取未定义的变量将会引发错误(NameError)。
同时Python的变量属于弱类型，即变量使用不需要指定类型。
变量被定义后将由解释器给出数据类型，并且该变量可以被重新赋值甚至改变类型。

Python内置如下基本数字类型：
::

    int
    float
    complex (虚数)

运行一些例子：

::

    a = 128
    print(a, type(a))

    a = "256"
    print(a, type(a))

    a = 3.14
    print(a, type(a))


相比于C语言, Python没有提供字符变量类型，但提供了字符串类型：
::

    str

使用单引号或双引号定义字符串，''与""可以嵌套使用。
可以使用转移字符“ \\ ” 来转义引号内部的引号，单双引号混用时可省略转义符。
::

    print('what\'s up!')
    print("what's up!")

实际使用中经常需要对转义字符进行转义，比如表示某个文件路径： “C:\\Tools\\Git”
可以使用两个并列的转义字符或简单的在引号前加上“r”

尝试一下输出结果：
::

    print('C:\Tools\notepad++')
    print('C:\\Tools\\notepad++')
    print(r'C:\Tools\notepad++')

也可以可以用三引号来保持字符串的换行。
字符串会有单独章节来介绍。

运算符
~~~~~~

Python的运算符基本与C语言一致，需要注意的是下方逻辑运算：

::

    或： or
    与： and
    非： not
    对象标识： is/is not
    幂方： **

除此以外，各个类型也会定义属于自己的特殊运算符，比如__eq__。

::

    print(True or True)
    print(True and False)
    print(not False)
    print(2**4)
    a = 1
    b = 2
    print(a.__eq__(b))


字符串操作
==========

Python中对字符串的处理是非常灵活的。

1.可以用“+”运算符将两个字符串连接到一起：

::

    a = "I am "
    b = "stupid."
    c = a + b
    print(c)

2.当两个字符串文本相邻时，自动被连接到一起：

::

    a = "You " "are " 'clever.'
    print(a)

    print("You " "are " 'clever.')
    print("You", "are", "clever.")

但这并不适用于字符串表达式，下方例子将会报错(SyntaxError)：
::

    b = a "very."

3.字符串可以由“*”表示重复：

::

    a = "bala" * 5
    print(a)

4.字符串是可以被 **索引** 的，可以用索引序号(下标)来访问字符串中的字符：

::

    a = "0123456789"
    print(a[0], a[5])

当下标超出字符串长度，会报错(IndexError)。

下标也可以是负数，这会导致从右边开始索引字符串：

::

    print(a[-1], a[-9], a[-0], a[-10])

猜猜下面的输出结果：
::

    a = "你好, Python."
    print(a[0], a[1], a[2], a[3], a[4], a[5], a[6], a[7], a[8], a[9], a[10])


5.字符串支持 **切片**

切片即一个字符串的片段，可以让你获得字符串的子字符串：

::

    print(a[3:5], a[5:], a[:3], a[-2:])

一个错误的索引范围，不会报错，结果也符合逻辑：

::

    print(a[:100], a[100:], a[4:2])

6.与C语言的字符数组表达的字符串不同，尝试对字符串某个字符赋值将导致错误错误(TypeError)：
::

    a[3] = 0


因为在Python中，字符串一旦被定义就不可以被更改。
前面提到了两个字符串相加，实际是新建了一个字符串，该字符串的值是其它两个的串联。

7.可以使用内置函数 len() 返回字符串长度:
::

    print(len(a))

Python内置str类提供了 大小写/子串重复次数/编码变换/子串查找/格式化/字符类型判断/字符串拼接/子串替换/分割等诸多功能。使用时请参考Python手册- `class str <https://docs.python.org/zh-cn/3/library/stdtypes.html?highlight=str#str>`_ .


内置数据结构
============

元组
列表
字典
集合

流程控制
========

if-elif-else
while
for
with as

函数和类
============

lambada表达式
作用域
类及其实例
类的特殊成员
__init__



包及导入
========

import * from ...
__all__
__doc__
__file__
__init__.py



常见内置模块
============

sys
os
set
queue
re


文件处理
========

网络编程
========

异常处理
========

多线程编程
==========

线程，进程，协程


生成器与迭代器
==============


装饰器@
========


GUI编程
=======



Python的明星应用
----------------

https://github.com/mahmoud/awesome-python-applications

Django
yum
OpenStack
Scrapy

Dropbox
豆瓣
Youtobe
知乎
果壳

数学运算
人工智能
云计算
自动化运维



Python的生态圈
------------------------

Pip
pyvenv & virtualenv
Cython
Pypy
reStructuredText


专题：胶水语言与脚本语言
------------------------


专题：关于Python的效率
----------------------

开发效率
执行效率


专题：万恶的self
----------------


专题：Python的哲学
-------------------


专题：Python2与Python3
----------------------


专题：Python程序启动阶段发生了什么
----------------------------------

.pyc











