

1:基本概念

为什么需要__init__.py
__init__.py文件用于组织包（package）。这里首先需要明确包（package）的概念。什么是包（package）？
简单来说，包是含有python模块的文件夹。一个python模块（module）为一个py文件，里面写有函数和类。
包（package）是为了更好的管理模块（module）,相当于多个模块的父节点。

一个包是一个带有特殊文件 __init__.py 的目录。__init__.py 文件定义了包的属性和方法。
其实它可以什么也不定义；可以只是一个空文件，但是必须存在。
如果 __init__.py 不存在，这个目录就仅仅是一个目录，而不是一个包，它就不能被导入或者包含其它的模块和嵌套包。

当文件夹下有__init__.py时，表示当前文件夹是一个package，其下的多个module统一构成一个整体。这些module都可以通过同一个package引入代码中。

__init__.py文件怎么写
可以什么都不写，但如果想使用from package1 import * 这种写法的话，需要在__init__.py中加上：

__all__ = ['file1','file2'] #package1下有file1.py,file2.py


2：具体用法

__init__.py 控制着包的导入行为。假如 __init__.py 为空，那么仅仅导入包是什么都做不了的。

>>> import Package1

>>> Package1.Module1
Traceback (most recent call last):
  File "D:/Work Space/Python practice/MyPractice/src/test.py", line 8, in <module>
    aa=Package1.Module1
AttributeError: 'module' object has no attribute 'Module1'

我们需要在 __init__.py 里把 Module1 预先导入：

#文件 __init__.py

import Module1

测试：

>>> import Package1
>>> aa=Package1.Module1
>>> print aa


__init__.py 中还有一个重要的变量，叫做 __all__。我们有时会使出一招“全部导入”，也就是这样：

from PackageName import *

这时 import 就会把注册在包 __init__.py 文件中 __all__ 列表中的子模块和子包导入到当前作用域中来。比如：

#文件 __init__.py

__all__ = ["Module1", "Module2", "subPackage1", "subPackage2"]

测试：

>>> from Package1 import *

>>>

test1111111111111111111111
test222222

__init__.py 文件会在导入时被执行。



3，个人总结：


__init__为空时；此时代表这个文件夹为一个包，但在导入时与没有__init__文件无区别，

__init__中包含  __all__ = [.....]：此时可以使用import * 用法

__init__中包含 import 。。。。： 常见，此时可直接使用package.mthod方法调用package中的method








