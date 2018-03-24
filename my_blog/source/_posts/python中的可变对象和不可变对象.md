---

date: 2017-5-20 18:34:12
title: python中的可变对象和不可变对象
tags: python
categories: python

---


python中可变对象和不可变对象的理解

在python中字符串，元组，数字，都是不可修改的对象。
可变的对象有：列表，字典，

在理解python数据类型不可变的时候有点理解不深，特写此文，来提醒自己

python中字符串是不可变的对象，可以理解为：如果修改了字符串以及不可变的对象，则会开辟新的内存空间，id()是最好的证明：

1.不可变对象（这里以字符串为例）
---------------

字符串是没有修改的方法的，如果说一定有，那么肯定会有赋值的过程，例如：

    In [10]: sr = 'hello world'
    
    In [11]: sr
    Out[11]: 'hello world'
    
    In [12]: sr + 'HELO'
    Out[12]: 'hello worldHELO'
    
    In [13]: sr
    Out[13]: 'hello world'
    
字符串拼接的方法并没有更改原来的字符串。他是产生了一个新的字符串。
再看：replace方法

    In [14]: sr
    Out[14]: 'hello world'
    
    In [15]: sr.replace('h','H')
    Out[15]: 'Hello world'
    
    In [16]: sr
    Out[16]: 'hello world'

这个例子同样也是产生新的字符串，字符串sr本身并没有发生改变。

再看下面这个例子：

    In [17]: sr += 'HHH'
    
    In [18]: sr
    Out[18]: 'hello worldHHH'
这里尽管说字符串sr发生了改变，我们来看看他的id，

    In [26]: sr = 'hello world'
    
    In [27]: sr
    Out[27]: 'hello world'
    
    In [28]: id(sr)
    Out[28]: 117969520L     #对比此处的id
    
    In [29]: sr += 'HHH'
    
    In [30]: sr
    Out[30]: 'hello worldHHH'
    
    In [31]: id(sr)
    Out[31]: 117970768L     #id发生了变化

2.可变对象（这里以列表为例）
---------------

    In [32]: li = [1,2,3,'hello','world']
    
    In [33]: li
    Out[33]: [1, 2, 3, 'hello', 'world']
    
    In [34]: id(li)
    Out[34]: 120335944L         #######
    
    In [35]: li.append('HHHHH')
    
    In [36]: li
    Out[36]: [1, 2, 3, 'hello', 'world', 'HHHHH']
    
    In [37]: id(li)
    Out[37]: 120335944L         #######
    
    In [38]: li += '11111'
    
    In [39]: li
    Out[39]: [1, 2, 3, 'hello', 'world', 'HHHHH', '1', '1', '1', '1', '1']
    
    In [40]: id(li)
    Out[40]: 120335944L         #######
这里列表无论怎么操作，都不会改变他的id。
