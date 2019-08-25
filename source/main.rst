.. MYPYTHON documentation master file, created by
   sphinx-quickstart on Sat Jul 13 10:24:25 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.


.. role:: underline
    :class: underline

.. role:: line-through
    :class: line-through




1 Pyhton是当今最流行的编程语言
------------------------------


1-1 Python的诞生及发展
========================

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


2 Python语法
------------

总的来说Python的语法与C语言比较接近。
下文如无特别说明，都指Python3.
在进入语法部分之前，我们先简单说说Python的特点，让大家对Python有一个感性的了解。


编译型和解释型语言

    **编译型语言** 是针对特定平台（操作系统）将某种高级语言源代码，“翻译”成可被该平台软硬件执行的机器指令(操作码和操作数），并包装成该平台所能识别的可执行程序的格式。这种“翻译”只做一次，以后程序运行都不需要再“翻译”。
    (比如C/C++)

    **解释型语言** 则是在程序运行过程中由解释器逐句解释为特定平台的机器指令并立即执行。(比如Python/Ruby)

    因为解释型语言在执行前有所谓的“翻译”，所以性能要通常低于编译型语言，为改善解释型语言效率发展出了 **即时编译技术(JIT)**。
    它在程序执行前首先有编译器编译成字节码，执行过程中再由特定平台上的虚拟机将字节码转译为可以直接运行的机器指令。(比如JAVA/C#/Pypy)

强类型/弱类型/静态类型/动态类型

    这些概念不是一个明确的、严格的定义。
    
    知乎上有一个很好的 `讨论 <https://www.zhihu.com/question/19918532>`_ ，大家可以参考一下。

    强类型是指程序不会出现因变量类型而引起的应在设计阶段禁止的行为。弱类型则相反。
    比如C语言在运行时可能会出现一些由于强制类型转换而引起的缓冲区溢出。这种行为C语言本身无法避免，需要靠程序设计去弥补。
    所以C是弱类型语言。

    静态类型则是指在编译阶段拒绝所有类型相关的不合理行为。
    动态类型则是在运行阶段。

    Python是一个强类型，动态类型语言。

动态语言/静态语言

    指在运行时可以改变其结构的语言：例如新的函数、对象、甚至代码可以被引进，已有的函数可以被删除或是其他结构上的变化。
    这个概念也不是一个明确的严格性的定义。

    Python属于动态语言范畴。

胶水语言

    起初有人将Python称为胶水语言(glue language)。原因是Python提供与其他很多语言交互的功能。
    程序员可以轻松的使用Python连接项目中各个组件。

    最常用的就是Python调用C/C++的链接库。

多平台支持

    Python可以像Java那样同一份代码运行在不同的平台(Platform)上。官方解释器支持Windows/Linux/Mac/iOS/AIX/Solaris等。
    这个特性曾经被Java拿来做宣传，并帮助Java迅速吸引了大批程序员。

    不同平台对可执行程序的格式要求不同，提供的系统调用也不一样。
    所谓多平台支持，实际是依靠多平台的Python解释器实现的。
    在Python源码与系统调用/库函数之间增加了一层解释器，隔离底层对Python源码的影响。


2-1 交互式编程
==============

在命令行下启动Python解释器并输入命令的方式，称交互模式。
适合学习，小型演示等场合。


2-2 一个简单的Python程序
========================

Python例子：

.. code-block:: python
    :caption: sample.py
    :name: sample
    :emphasize-lines: 1
    :linenos:

    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-

    import platform

    print("Hello Python.")
    print("Power by ", end='')
    print(platform.platform(), platform.python_version())

    def fibonacci(max):
        """
        斐波那契数列生成。

        生成不超过参数max的斐波那契数列。
        """

        a, b = 0, 1
        # a = 0; b = 1  #此行分号不能省略
        while b <= max:
            print (b)
            a, b = b, a + b


    if __name__ == "__main__":
        print(fibonacci.__doc__)
        fibonacci(100)

2-2-1 前两行
~~~~~~~~~~~~

**#!** 是UNIX sh下用来指定脚本运行环境。
#与!之间不能有空格，改行必须以UNIX风格结尾，即 "\\n"。

Windows平台下没有此要求。

**# -*- coding: utf-8 -*-** 用来指定此文件的编码。
Python3默认以UTF8编码读取文件，如果文件被保存为UTF8以外的编码，必须指定相应的编码，否则可省略。
**"-*-"** 没有实际意义，可以省略，**":"** 也可以用 **"="** 取代：
::

    # coding=utf-8

为统一文件风格，希望大家都不要省略这两行。


2-2-2 注释
~~~~~~~~~~~

Python使用“#”注释单行语句，用法类似C语言的“//”。

对于多行注释，Python没有专用的语法，但可以采用变通的方法即使用连续的三个单引号或双引号, 如:
::

    '''this is a comment''' 或者 """this is a comment"""

但由于连续的三个引号有其它用途——文档字符串，所以不推荐用在一般注释中。

单引号与双引号在Python中的语义是相同的，当要描述一个含有引号的字符串时，可以像下面这样定义
::

    str = 'Hello my name is "Python".'

2-2-3 缩进
~~~~~~~~~~~~~

Python使用缩进来表示嵌套，在编写Python代码时，请使用带有空格/Tab提示的编辑器，防止此类问题带来的功能错误或解析错误。

`PEP8 <https://www.python.org/dev/peps/pep-0008/>`_ 规定使用4个空格作为每级缩进，其他空格数和Tab虽然可以被编译器识别，但不符合Python规范。

支持4个以外的空格数和Tab仅仅是因为兼容一些古老的代码和个别不智能的编辑器。

请注意，空格与Tab混用会解释器会报错(TabError)。

2-2-4 文档字符串
~~~~~~~~~~~~~~~~~~~

每个对象都有一个__doc__的属性，提供该对象的简单描述，称为文档字符串(DocStrings)。
在对象(一般是类或函数)的第一行以三个单引号引号 ''' 或三个双引号 """ 包裹起来，其内部文本格式会被保留。

一个使用惯例是： 它的首行简述对象功能，第二行空行，第三行为函数的具体描述。

2-2-5 换行
~~~~~~~~~~~

当语句太长一行写不下的时候，不能像C语言那样直接换行。
需要在行尾加上 **\\** :
::

    a = True
    b = \  # 本行不能加注释
    False  # 本行不需要缩进对齐

当换行处为某函数参数时(在括号内部时)，可以直接换行：
::

    fp = open("sample1.py",  # 本行可以加注释
        "r")                 # 本行不需要缩进对齐
    fp.close()

    print(a,
    b)

**\\** 可以认为将上下两行直接拼接到一起，而()更加灵活，推荐使用()的方式换行。

Python不推荐每行以分号 “；” 结束，但加上分号也是被允许的。

另外当你想在一行中执行多条语句时，可以使用分号。

::

    a = 1; b =2 #此行分号不能省略
    print(a, b)

2-2-6 __name__
~~~~~~~~~~~~~~~~~

Python中所有都被看做对象，每个对象都有自己的属性，以__XXXX__形式表示。（可以把属性看作是一些特殊的变量）

__name__就是对象(class/function/method/descriptor/generator instance)的属性之一。

在本例中可以看作是sample.py的属性，当该文件被Python解析器直接执行时，__name__被设置为__main__，否则将被设置为模块名称。

这个条件判断解析器是否从本文件开始解析。


2-3 变量和运算符
================

2-3-1 变量和基本数据类型
~~~~~~~~~~~~~~~~~~~~~~~~~~

变量使用前不需要声明，但试图读取未定义的变量将会引发错误(NameError)。

变量被定义后将由解释器识别出数据类型，并且该变量可以被 **重新赋值** 甚至 **改变类型** 。

可以调用 **del()** 这个内置函数来删除已经定义的变量。删除不存在的变量会引发错误(NameError)。


〇 Python内置如下 **基本数字类型**：
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

    a = 5
    b = 5.0
    print(a == b)

Python在比较两个数值大小的时候，实际是比较两个数值的 `hash <https://docs.python.org/zh-cn/3/library/functions.html#hash>`_ 是否相同。

〇 支持 **布尔** 类型：

- True
- False

〇 相比于C语言, Python没有提供字符变量类型，但提供了 **字符串** 类型：

- str

使用单引号 ' 或双引号 " 扩起来的即为字符串，单引号与双引号可以嵌套使用。
可以使用转移字符 \ 来转义引号内部的引号，单双引号混用时可省略转义符。
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

也可以用三引号来保持字符串的换行。

〇 Python3中新引入了 **bytes-字节序列(字节串)** 这一新的数据类型。

bytes是以字节为单位的序列。其特性和对象方法与字符串(str)非常接近。
bytes只允许ASCII字符作为其填充值，类似字符串的定义方法，加 **"b"** 前缀即可：

::

    a = b'I am a bytes.'
    print(a, type(a))

bytes 对象还可以通过其他几种方式来创建：

- 指定长度且以零值填充: bytes(10)
- 使用迭代器: bytes(range(20))
- 复制现有的二进制数据: bytes(obj)


在Python中，像字符串/字节串这种有一块连续的内存空间存放多个值，值以一定顺序/规则排列并可对其进行索引的结构称为 **序列(Sequences)** 。
字符串是一种序列，后面会再次介绍。元组，列表，字节序列(字节串)等数据结构也是序列的一种。

除此以外还有集合，映射(如字典)，可调用等类型。

〇 数据类型转换

Python属于强类型语言，不支持(倾向于不支持)隐式转换。

虽然变量被定义时不需指明类型，但程序员心里必须清楚变量所属类型。

数据类型出错时通常会报TypeError，比如会提示字符串与浮点型不能直接相连，
::

    cm = 170.0
    try:
        print("height: " + cm)
    except Exception as e:
        print(e)

此时我们应该使用str将cm转换为字符串：
::

    print("height: " + str(cm))


2-3-2 标识符规范及命名规则
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- 标识符由字符(A~Z/a~z)、下划线和数字组成(不能包含空格、@、%以及$等特殊字符)，首字符不能是数字
- 标识符字母严格区分大小写，即value和Value是不同的两个变量
- 以下划线开头的变量有特殊的含义，除非明确自己在做什么，否则不要使用该类名称
    + 单下划线开头表示类的属性，无法直接访问
    + 双下划线开头表示类的私有成员(非语法上的强制要求)
    + 双下划线开头和结尾的是内置专有标识符


我们甚至可以使用非ASCII字符（比如汉字）作为变量名称，但显然这并不推荐。
::

    性别="男"
    身高=180
    体重=70

    print(性别, 身高, 体重)

前文提到，Python的语法与C语言比较接近，那有没有类似C语言的指针呢？
很高兴的告诉我大家，Python里没有指针，变量的申请与释放也都是解释器自动完成的。
C语言中经常遇到的内存非法问题，在Python里基本不存在。

补充一下，对CPython，我们是可以使用 `id() <https://docs.python.org/zh-cn/3/library/functions.html#id>`_ 这个内置函数来获取变量的地址。

id()函数本身是返回该变量的标识符，在变量作用域内，该标识符是唯一的。
CPython借用了变量的内存地址唯一性来实现函数id()。

相应的，Python变量使用前不需要定义、变量名可以被覆盖的特性，也会带来了很多意外的问题。
一个好的命名习惯能极大避免此类问题。

- 避免与Python内建函数，变量的冲突
- 避免与引用的第三方库冲突
- 方便区分变量生命周期
- 区分变量的类型
- 提高可读性、降低维护成本等

命名规则有很多种，对于一个具体的项目应尽可能使用一种规则。

2-3-3 运算符
~~~~~~~~~~~~~

Python的运算符基本与C语言一致，不再重复介绍了。
需要注意的是下方逻辑运算：

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


2-4 字符串操作
==============

Python内置str类提供了 大小写/子串重复次数/编码变换/子串查找/格式化/字符类型判断/字符串拼接/子串替换/分割 等诸多功能。对字符串的处理是非常灵活的。

使用时请参考Python手册 `class str <https://docs.python.org/zh-cn/3/library/stdtypes.html?highlight=str#str>`_ .
我们这里介绍一些常用功能。

(1) 可以用“+”运算符将两个字符串连接到一起：

::

    a = "I am "
    b = "stupid."
    c = a + b
    print(c)

(2) 当两个字符串文本相邻时，自动被连接到一起：

::

    a = "You " "are " 'clever.'
    print(a)

    print("You " "are " 'clever.')
    print("You", "are", "clever.")

但这并不适用于字符串表达式，下方例子将会报错(SyntaxError)：
::

    b = a "very."

(3) 字符串可以由“*”表示重复：

::

    a = "bala" * 5
    print(a)

(4) 字符串是可以被 **索引** 的，可以用索引序号(下标)来访问字符串中的字符：

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


(5) 字符串支持 **切片**

切片即一个字符串的片段，可以让你获得字符串的子字符串：
::

    print(a[3:5], a[5:], a[:3], a[-2:])

一个错误的索引范围，不会报错，结果也符合逻辑：
::

    print(a[:100], a[100:], a[4:2])

实际上切片是序列类型支持的方法，不仅是字符串，列表，元组等也都支持切片。

切片的语法格式： **mystr[start:stop:step]**

- start: 起始索引，默认为0，即不指定的话从序列头开始。
- stop: 终止索引，默认为序列的长度，即不指定的话一直到序列结束。注意，切片结果不包含该终止位。
- step: 步长，默认为1，指截取时的跳跃步长。

::

    mystr = "abcdefg"
    print(mystr[2:2])
    print(mystr[::2])


(6) 与C语言的字符数组表达的字符串不同，尝试对字符串某个字符赋值将导致错误错误(TypeError)：
::

    a[3] = 0

因为在Python中，字符串一旦被定义就不可以被更改。
前面提到了两个字符串相加，实际是新建了一个字符串，该字符串的值是其它两个的串联。

(7) 可以使用内置函数 len() 返回字符串长度:
::

    print(len(a))


(8) 字符串格式化

str类提供了format函数支持字符串格式化。
::

    a = "{} wish {} have a {} day".format("I", "you", "nice")
    b = "{1} wish {0} have a {2} day".format("you", "I", "nice")
    c = "my name is {NAME}".format(NAME = "Veoneer")

Python也支持另一种%形式的字符串格式化，Python3中不推荐这个写法，我们只做了解：
::

    d = "my name is %s" % "Veoneer"

对于format的高阶用法，请参考 `格式规格迷你语言 <https://docs.python.org/zh-cn/3/library/string.html#formatspec>`_。
比如：
::

    e = "I am {0:d} or {0:b} years old".format(18)

    ipaddr = [192, 168, 0, 1]
    f = '{:02X}{:02X}{:02X}{:02X}'.format(*ipaddr)

Python还有一个同名的内置函数format，请大家不要混淆。

作为内置函数使用时：
::

    class mystr(str):
        def __format__(self, format_spec):
            return self.__str__().format(format_spec)

    template = mystr("I love you, do you love me? {0:s}?")
    format_spec = "what's up"
    g = format(template, format_spec)

在调用内置函数format(value, format_spec)时会转换成 type(value).__format__(value, format_spec)。
__format__是用户自定义方法，可以对类定义自己的格式化方法。

所以上面例子实际上相当于调用了str.format()。


2-5 内置数据结构
================

Python内置了功能强大数据结构。

2-5-1 列表 list
~~~~~~~~~~~~~~~~

列表可以用来存储多个数据。
从语法上看，列表会将所有元素都放在一对中括号 [] 中，相邻元素之间用逗号分隔。
列表可以同时存储不同的数据类型。

**新建一个列表**

可以直接对列表赋初值来新建。

::

    mylist = [] # 新建一个空列表
    mylist = [1, '2', ['3',]] # 使用[]新建列表
    print(type(mylist), mylist)
    for e in mylist:
        print(type(e), e)

也可以使用内置函数list来新建列表。list()函数可以接收元组、区间（range）等参数并将它转换为列表。

::

    mylist = list(range(1, 5)) #使用类的构造器新建列表
    print(mylist)

下面用来简化复杂列表创建的方法，称为 **列表推导式** ：
::

    mylist = [x**2 for x in range(5)]
    print(mylist)


**访问某一元素**

可以通过索引(下标)来访问列表中的元素。

::

    mylist = ["I am 1", "I am 2", "I am 3"]
    print(mylist[2])

列表属于序列的一种，也支持类似字符串的 **切片** 操作。请参考字符串章节。

**扩充/删减列表**

大家可以把列表想象成链表结构，可以在任意位置增加新的元素。

〇列表末尾追加元素： list.append(obj)

可以追加单个元素，也可以追加列表，元组等，追加的元素作为原来列表单独的元素存在。

::

    mylist = ['apple', 'grape']
    mylist.append('banana')
    mylist.append(['peach', 'pear'])
    print(mylist)

〇任意位置插入元素： list.insert(index, obj)

index是指将要插入的位置(索引)，同append，插入的元素将被视为一个整体放入原有列表中。

::

    mylist = [ 'wife', 'husband']
    mylist.insert(1, 'mistress')
    print(mylist)

〇根据索引值删除元素，del语句： del list[index]

::

    del mylist[1]
    print(mylist)

del也可以删除一段数据，del list[start, stop]
当索引超过数组界限时，会引发错误(IndexError).

〇根据元素值删除元素： list.remove(obj)

::

    mylist.remove('husband')
    print(mylist)

找不到要删除的元素时，会引发错误(ValueError).
所以在删除前应该判断该元素是否存在，或者加异常处理。

〇清空列表： list.clear()

该方法清空列表中所有元素，清空后列表为 []。

**修改列表元素**

可以对索引的列表对象直接赋值修改, 对修改前后的元素类型没有要求
::

    mylist = [1, 2, '3', 4,]
    mylist[2] = 3
    print(mylist)

也可以通过切片的方式，修改某范围的元素, 修改前后的元素个数不要求一致
::

    mylist = list(range(1, 10))
    mylist[2:5] = [0, 0]
    print(mylist)

**其它常用方法**

可以参考序列的语法手册，了解更多的方法: 
`Sequence Types <https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range>`_

- copy - 复制并返回新列表，为浅拷贝(一层深拷贝)， 深拷贝请使用copy.deepcopy()
- pop - 弹出列表末尾的元素
- reverse - 逆序列表元素
- count - 计算某元素在列表中出现的次数
- sort - 列表排序


2-5-2 元组 tuple
~~~~~~~~~~~~~~~~~~

元组与列表类似，也用来存储一组数据。但元组是不可更改的。
语法上，用一对小括号 () 将数据扩起来，相邻元素用逗号分隔。

**新建一个元组**

可以直接对元组赋初值来新建：
::

    mytuple = ('element1', 2) # 此时小括号是可以省略的，但不推荐
    print(type(mytuple), mytuple)

请注意当元组只有一个元素时，需要在元素后面补上逗号，否则将会被识别成其它类型数据。
::

    mytuple = ('only one') # 被识别成字符串
    print(type(mytuple), mytuple)

    mytuple = (1) # 被识别成整型
    print(type(mytuple), mytuple)

正确写法应该是：
::

    mytuple = ('only one',)
    print(type(mytuple), mytuple)

    mytuple = (1,)
    print(type(mytuple), mytuple)


也可以使用内置函数tuple来新建元组：
::

    mytuple = tuple('asdf') # 此时将字符串拆分成字符，每个字符作为元组的一个元素
    print(type(mytuple), mytuple)

**元组的元素的访问**

与列表相同，可以通过索引来访问元组元素。

**元组的更改和删除**

元组本身是不可更改的，下方例子是新建了一个元组，来存储两者的和。
::

    mytuple = mytuple + mytuple

不再使用的元组可以通过del语句删除：
::

    del(mytuple)

*可以将元组看成不可改变的列表，常用于存放静态数据，访问效率要高于列表*


2-5-3 字典 dict
~~~~~~~~~~~~~~~~

字典是以 **键值对(key-value)** 的形式存放数据的集合。

**新建一个字典**

字典中每个元素都包含 2 部分(key-value)，在创建字典时，key和value之间使用冒号分隔，相邻元素之间使用逗号分隔，所有元素放在大括号 {} 中。

::

    mydict = {'name':'ruhua', 'sex':'women', 'age':16}
    print(type(mydict), mydict)

    mydict = {}  # 新建了一个空字典
    print(type(mydict), mydict)

注意字典中的“key”必须是唯一且不可变的（数字，字符串或元组）。

::

    mydict = {'name':'ruhua', 'sex':'women', 'age':16, 'sex':'men'} # 出现同名key时，会覆盖当前已经存在的键值
    print(type(mydict), mydict)

    mydict = {'name':'ruhua', 'sex':'women', 'age':16, [1, 2]:''} # key为可变对象时，会报错(TypeError)
    print(type(mydict), mydict)

通过内置函数dict创建字典：

::

    mydict = dict(key1=10, key2=20, key3=30) # 注意此方法生成的key只能是字符串，且语法上不带引号
    print(mydict)

    mylist = [[1,10],[1,20]]
    mydict = dict(mylist) # dict的参数是列表或元组，列表会员组的成员又是含有两个元素的列表或元组
    print(mydict)

还可以使用dict类型的fromkeys()方法创建所有值为空的字典：
::

    keys = {'数学', '语文', '外语'} # 定义一个key的集合, 也可以是元组，列表或字符串
    mydict = dict.fromkeys(keys)
    print(mydict)

    # 猜猜看
    keys = 'ABCD'
    mydict = dict.fromkeys(keys)
    print(mydict)

**访问字典**

对于字典类型，经常使用key去获取对应的value：
::

    mydict = {'name':'ruhua', 'sex':'women', 16:'forever', }
    myvalue = mydict.get('name')
    print(myvalue)
    myvalue = mydict.get(16)
    print(myvalue)

当key值不存在时dict.get()返回NULL。
也可以指定当key不存在时的默认返回值：
::

    mydict = {'洗': 50, '剪': 100}
    myvalue = mydict.get('吹')
    print(myvalue)

    myvalue = mydict.get('吹', ‘不提供此服务’)
    print(myvalue)

注意，字典中各组数据是无序的，所以不能通过索引来访问字典，但可以使用类似的语法通过key来访问：mydict['洗']。


**字典元素的增加/更新/删除**

可以直接对现有字典的新key赋值即可增加字典元素：
::

    mydict = {'洗': 50, '剪': 100}
    mydict['吹'] = 500
    print(mydict)

对重名key进行赋值即可更新字典：
::

    mydict['吹'] = 5
    print(mydict)

使用del语句可以删除字典中某组数据：
::

    del(mydict['吹'])
    print(mydict)

如果要删除的key不存在于字典中，则会引发错误(KeyError).

可以通过 in 语句来判断key是否存在于某个字典：
::

    if '吹' in mydict:
        del(mydict['吹'])

**其它常用方法**

可以参考语法手册，了解更多的方法: 
`Mapping Types — dict <https://docs.python.org/3/library/stdtypes.html#dict>`_

- copy - 返回当前字典的备份，浅拷贝
- pop - 弹出指定key的一组数据，并将此组数据删除
- popitem - 随机弹出一组数据
- keys - 返回包含所有key的 Dictionary view obj
- values - 返回包含所有value的 Dictionary view obj
- items - 返回包含所有字典条目的 Dictionary view obj
- undate - 将一个字典的数据更新到另一个字典里
- setdefault - 获取指定key的value，当key不存在时，先将参数赋给该key，再返回。

有兴趣的话可以了解一下： Dictionary view obj。


2-5-4 集合 set
~~~~~~~~~~~~~~~

集合用来保存 **不重复** 的，**不可变** 的数据。
从语法上看，将所有元素放入一对大括号 {} 中，以逗号分隔不同元素。

`Set <https://docs.python.org/3/library/stdtypes.html#set>`_ 

*TODO*


2-5-5 Queue
~~~~~~~~~~~~

通过queue.py类提供队列支持。

支持同步，即多生产者多消费者。

`Queue <https://docs.python.org/3/library/queue.html?highlight=queue#module-queue>`_

*TODO*


2-5-6 Array
~~~~~~~~~~~~

第三方库支持的数据类型。

`Array <https://docs.python.org/3/library/array.html?highlight=array#module-array>`_

*TODO*



2-6 流程控制
============

同C语言一样，Python也支持顺序结构，选择结构，循环结构。

2-6-1 选择结构 if-elif-else
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

本节开始涉及代码块，语法上请注意 **保持同一代码块的缩进一致**。

首条语句使用if开始，接下来可以使用elif（有条件语句）和else（无条件语句）与if配合。

条件判断语句的末尾使用冒号 : 来开启下一个语句块。

条件判断语句可以用小括号（）扩起来，也可以不使用。

对于多个条件，使用 and 或 or 来链接。使用 not 对条件取反。

常使用 is 来比较对象的一致性，使用 in 来判断某元素是否属于某数据集的成员。

if 语句支持嵌套，使用方法同C语言一致。主要注意语句块缩进。

::

    print("请输入您的彩票号码：")
    numberstr = input()
    number = int(numberstr)

    if (number == 1): 
        print("恭喜您中了一等奖 500 万！！！")
    elif number == 2 :
        print("恭喜您中了二等奖 1万！")
    elif number > 0 and number < 10:
        print("您本次没有中奖。")
    else:
        print("彩票号码有误，请重新输入。")
        print("如发现有欺诈行为，欢迎拨打400电话举报。")

    print("欢迎再次购买本福利彩票！") # 此语句与if语句缩进一致，故不属于else的执行范围。

判断表达式不仅可以是布尔bool类型，实际上可以是任意类型。
从下面例子可知，0，“”， ()，[], {}, None都会被判定为否 Flase。

::

    condition = 0
    if condition :
        print(True, condition)
    else:
        print(False, condition)

    condition = ""
    if condition :
        print(True, condition)
    else:
        print(False, condition)

    condition = []
    if condition :
        print(True, condition)
    else:
        print(False, condition)

    condition = ()
    if condition :
        print(True, condition)
    else:
        print(False, condition)

    condition = {}
    if condition :
        print(True, condition)
    else:
        print(False, condition)

    condition = None
    if condition :
        print(True, condition)
    else:
        print(False, condition)


2-6-2 循环结构 while
~~~~~~~~~~~~~~~~~~~~

while语句用法也与C语言类似，语法：

**while 循环条件判定式 :**
    *代码块*

::

    mylist = ['A', 'B', 'C', 'D']

    while(len(mylist) > 0):
        print(mylist.pop())

Python中的while语句可以搭配else语句，来区分是条件终止还是break跳出:

::

    mylist = ['A', 'B', 'C', 'D']

    while len(mylist) > 0 :
        element = mylist.pop()
        if (element == 'C'):
            print(element)
            break
    else:
        print('list end.')


2-6-3 循环结构 for
~~~~~~~~~~~~~~~~~~

for语句相比于C语言有比较大的差异。

for在Python中更多用于对一个数据集的遍历。

这个数据集可以是已经存在于内存中的如字符串，列表等实际数据，也可以是一个生成器，可以把它们统称为可迭代对象。

语法如下：

**for 迭代变量item in 字符串|列表|元组|字典|集合|生成器：**  # 注意关键字in，以及不要遗忘冒号
    *代码块*

::

    mylist = [1, 2, 3, 4, 5, 6, 7, 8, 9]
    for element in mylist: # mylist 是一个已经存在的列表
        print(element)

尝试使用range语句来控制循环次数：

::

    for i in range(10): # range(10) 返回一个可迭代对象，此时数据并没有真实存在于内存中
        print(i)


:line-through:`了解可迭代对象和迭代器后，我们可以尝试分析`

for循环的本质就是先通过iter()函数获取可迭代对象(Iterable)的迭代器(Iterator)，然后对获取到的迭代器不断调用next()方法来获取下一个值并将其赋值给item，当遇到StopIteration的异常后循环结束。

比较下面两组代码的不同：
::

    for i in [x**2 for x in range(5)] :
        print(i)

::

    for i in (x**2 for x in range(5)) :
        print(i)


第一种写法[x**2 for x in range(5)]用列表推到式定义了一个列表，for的可迭代对象是一个存在于内存中的数据。
第二种写法(x**2 for x in range(5))只是一个表达式，没有新定义变量，它只返回一个生成器，该生成器可以生成一个可迭代对象。

验证一下我们所说的：
::

    from collections import Iterator, Iterable

    print(isinstance([x for x in range(10)], Iterator))
    print(isinstance([x for x in range(10)], Iterable))

    print(isinstance((x for x in range(10)), Iterator))
    print(isinstance((x for x in range(10)), Iterable))


再来看一个遍历字典的例子：

::

    mydict = {'数学': 90, '语文': 80, '外语': 60}

    for key, value in mydict.items():
        print('key:', key)
        print('value:', value)

    for key in mydict.keys():
        print('key:', key)

    for value in mydict.values():
        print('value:', value)

    # 可还记得mydict.items()/keys()/values()是什么类型？ 能从特性推断一下它属于哪种可迭代对象吗。
    print(type(mydict.items()), mydict.items())
    print(type(mydict.keys()), mydict.keys())
    print(type(mydict.values()), mydict.values())

- with as
- yield & return


2-7 函数和类
================

- lambada表达式
- 作用域
- 类及其实例
- 类的特殊成员
- __new__
- __init__


2-8 包及导入
============

- import * from ...
- __all__
- __doc__
- __file__
- __init__.py


2-9 常用模块
================

- sys
- os
- timeit
- time
- re
- pdb


2-10 文件处理
=============

2-11 网络编程
=============

2-12 异常处理
=============

2-13 多线程编程
===============

线程，进程，协程


2-14 生成器/迭代器/可迭代对象
===============================


2-15 装饰器@
=============


2-16 GUI编程
============

Tkinter

------

3 Python的明星应用
------------------

https://github.com/mahmoud/awesome-python-applications

- Django
- yum
- OpenStack
- Numpy
- Scrapy
- 

- Dropbox
- 豆瓣
- Youtobe
- 知乎
- 果壳

- 数学运算
- 人工智能
- 云计算
- 自动化运维


------

4 Python的生态圈
--------------------------

- Pip
- pyvenv & virtualenv
- Pypy
- reStructuredText


------

专题：关于Python的效率
----------------------

- 开发效率
- 执行效率


------

专题：万恶的self
----------------

**TODO**

------

专题：Python的哲学
-------------------

**TODO**

------

专题：Python2与Python3
----------------------

**TODO**

------

专题：Python程序启动阶段发生了什么
----------------------------------

.pyc













