为什么需要__init__.py
__init__.py文件用于组织包（package）。这里首先需要明确包（package）的概念。什么是包（package）？
简单来说，包是含有python模块的文件夹。一个python模块（module）为一个py文件，里面写有函数和类。
包（package）是为了更好的管理模块（module）,相当于多个模块的父节点。

当文件夹下有__init__.py时，表示当前文件夹是一个package，其下的多个module统一构成一个整体。这些module都可以通过同一个package引入代码中。

__init__.py文件怎么写
可以什么都不写，但如果想使用from package1 import * 这种写法的话，需要在__init__.py中加上：

__all__ = ['file1','file2'] #package1下有file1.py,file2.py


