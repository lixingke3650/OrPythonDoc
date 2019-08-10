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

Python作者 `Guido von Rossum <https://en.wikipedia.org/wiki/Guido_van_Rossum>`_ 曾在ABC项目组中工作多年，Python的许多语法来自C，但也受ABC的强烈影响，比如用缩进表示代码嵌套，变量不需声明等。

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

#！
_*_coding: utf-8 _*_
__name__ == "__main__"

缩进::

    PEP8规定使用4个空格作为每级缩进，其他空格数和Tab虽然可以被编译器识别，但不符合Python规范。
    支持其他空格数和Tab仅仅是因为兼容一些古老的代码和个别不智能的编辑器。


斐波那契数列
pass语句


变量和运算符
============

字符串操作
==========

切片

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












