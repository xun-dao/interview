# 改善python代码的91个建议

```python
"""
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
"""
```



## 1. 理解Pythonic概念

```python
# (1) 充分体现 python 特色的风格 例如：
x,y = y,x
a = 'hello {name}, you are a {type}'.format(name='Jack', type='boy')
# (2) 包和模块命名采用小写，单数形式，简短。包通常仅作为命名空间
```

## 2. 编写 Pythonic 代码

```python
# 阅读 flask 源码
```

## 3. 理解 Python 与 C 语言的不同之处

## 4. 在代码中适当添加注释

```python
# (1) 使用行注释或者块注释来注释复杂的操作，算法以及不够一目了然的技巧或代码
# (2) 注释和代码要隔开一定距离，在块注释之后空几行再写代码
# (3) 给外部可访问的函数和方法添加文档注释，注释要说明：
#         <1> 方法功能
#         <2> 参数说明
#         <3> 返回值说明
#         <4> 异常说明
# (4) 头文件中包含copyright 申明、模块描述等
# (5) 注释应该用来解释代码的想法、原因以及功能，而不是对代码的解释
```

## 5. 通过适当添加空行使代码布局更为优雅、合理

```python
"""
(1) 在一组代码表达完一个完整的思想后，应该用空行分隔
(2) 尽量保持上下文语义易理解
(3) 避免过长的代码行
(4) 二元运算符左右两边应该有空格
(5) 逗号和分号前不要使用空格
(6) 函数名和'('，序列索引和'['，函数默认参数两侧不需要空格
(7) 强调前面的操作符的时候需要使用空格，如：-2 - 5
"""
```

## 6. 编写函数的4个原则

```python
# 1. 函数设计尽量短小，潜逃层次不宜过深
# 2. 函数申明应该做到合理、简单、易于使用，参数个数不宜过多
# 3. 函数设计应该考虑向下兼容
# 4. 一个函数只做一件事
```

## 7. 将常量集中到一个文件

```python

```





































































