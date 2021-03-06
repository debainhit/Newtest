# Newtest 
关于python语言的语法及函数说明（机器学习实战中代码的深挖）

Python 可迭代对象：Iterable，Iterator

python中接触过的基本类型包括：集合数据类型 list/tuple/dict/set/str等，数字

2个概念：可迭代对象和迭代器


1.Iterable
可以直接作用于for循环的对象成为迭代对象：Iterable，可以使用isinstance()判断一个对象是否是Iterable
包括：
     一.基本类型中的list/tuple/dict/set/str等
     二.generator，包括生成器和带yield的generator function
>>> from collections import Iterable
>>> isinstance([], Iterable)
True
>>> isinstance({}, Iterable)
True
>>> isinstance('abc', Iterable)
True
>>> isinstance((x for x in range(10)), Iterable)
True
>>> isinstance(100, Iterable)
False

2. Iterator
可以被next()函数调用并不断返回下一个值的对象成为迭代器：Iterator
包括：生成器和yield的generator function
不包括：list/dict/str等，但是可以通过iter()函数成为Iterator对象

原因：这是因为Python的Iterator对象表示的是一个数据流，Iterator对象可以被next()函数调用并不断返回下一个数据，直到没有数据时抛出StopIteration错误。可以把这个数据流看作是一个有序序列，但我们却不能提前知道序列的长度，只能不断通过next()函数实现按需计算下一个数据，所以Iterator的计算是惰性的，只有在需要返回下一个数据时它才会计算。

Iterator甚至可以表示一个无限大的数据流，例如全体自然数。而使用list是永远不可能存储全体自然数的

参考资料：
http://blog.csdn.net/yizheyouye/article/details/50649974
http://www.oschina.net/translate/improve-your-python-yield-and-generators-explained



