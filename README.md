# algorithm_in_c 

C语言的数据结构和算法实现 - 代码中几乎每一行都添加了注释，通过这种甚至有点啰嗦的方式，希望让人们能够容易的掌握数据结构和算法

一开始我们不太懂，所以需要了解这些数据结构和算法，

渐渐地我们可以实现这些数据结构和算法，

但是实现之后不要忘了，我们应该对我们的实现进行评估，并且对结构和算法本身有一定的认识才行

如果对数据结构和算法有热情或者其他疑问，欢迎加入QQ群: 530133597

### TODO - 有太多要做的事情，这里也只是罗列出一部分

- 编写非递归的方案
- 编写单元测试
- 重写和封装链表，栈，堆，树等结构
- 更直观的GUI来展示算法
- 完善各个数据结构和算法的数学推导


## 目录

**[Installation Instructions](#installation-instructions)**

- [x] [冒泡排序]
- [x] [直接插入排序](#1.2)
- [x] [希尔排序](#1.3)
- [x] [二分查找插入排序](#1.4)
- [x] [选择排序](#1.5)
- [x] [快速排序](#1.6)
- [x] [归并排序](#1.7)
- [ ] [堆排序](#1.8)

### [查找](#Search)
- [x] [二分查找](#2.1)

### [数据结构](#data_structure)
- [x] [单向链表](#3.1)
- [x] [双向链表](#3.2)
- [x] [单向循环链表](#3.3)
- [x] [双向循环链表](#3.4)
- [x] [栈 - 通过数组实现](#3.5)
- [x] [栈 - 通过双向链表实现](#3.6)
- [x] [队列 - 使用双向链表实现](#3.7)
- [x] [优先级队列 - 使用双向链表实现](#3.8)
- [ ] [优先级队列 - 使用堆实现](#3.9)
- [x] [哈希表 - 使用拉链法处理哈希冲突的实现](#3.10)
- [ ] [堆](#3.11)

### [Tree - 树](#Tree)
- [x] [树 - 二叉查找树(BST)](#3.12)
- [x] [树 - 平衡二叉树(AVL)](#3.13)
- [x] [树 - 红黑树(RBT)](#3.14)
- [x] [树 - B树](#3.15)
- [ ] [树 - B+树](#3.16)
- [ ] [树 - B*树](#3.17)
- [ ] [树 - Trie树](#3.18)
- [ ] [树 - SB树 - Size Balanced Tree](#3.19)
- [ ] [树 - Merkle Tree - Dynamo中用来同步数据一致性的算法](#3.20)

## 使用方法:

> 进入各个目录执行make即可编译文件，之后运行文件即可

## Installation Instructions

<span id="1.1">BubbleSort 冒泡排序</span>  
<span id="1.2">InsertSort - Direct Insert Sort 插入排序(直接插入排序)</span>  
<span id="1.3">ShellSort 希尔排序</span>  
<span id="1.4">BinInsertSort 二分查找插入排序</span>  

> 直接插入排序对于大部分有序的序列排序时速度快。<br/>
> 二分插入排序在直接插入的基本上改变了查找元素插入位置的方法，对于完全无序的序列来说，速度会变快，但是对开大部分有序的序列反而会更慢。<br/>
> 希尔排序则利用直接插入排序对于大部分有序的序列速度快的特点，先让大部分序列有序，以此来提高排序效率。<br/>

<span id="1.5">SelectSort 选择排序</span>  
<span id="1.6">QuickSort 快速排序</span>  
<span id="1.7">MergeSort 归并排序</span>  

####Search - 查找   
<span id="查找">Search-查找</span>  

<span id="2.1">BinarySearch 二分查找</span>  

####data_structure - 数据结构   

<span id="3.1">SingleLinkedList 单向链表</span>  
<span id="3.2">DoubleLinkedList 双向链表</span>  
<span id="3.3">SingleCircularLinkedList 单向循环链表</span>  
<span id="3.4">DoubleCircularLinkedList 双向循环链表</span>  
<span id="3.5">StackByArr 通过数组实现的栈</span>  
<span id="3.6">StackByDoubleLinkedList 通过双向链表实现的栈</span>  
<span id="3.7">Queue 通过双向链表实现的队列</span>  
<span id="3.8">PriorityQueue 通过双向链表实现的优先级队列</span>  
<span id="3.9">PriorityQueue 通过堆表实现的优先级队列</span>  
<span id="3.10">HashTable 哈希表</span>  

> 哈希表的主要问题在于设计好的哈希函数(可以得到均匀分布的key)和如何处理哈希冲突(hash collision)

- 哈希表的长度应该是质数（也成为素数）

- 哈希表一直在避免的就是过多的聚集

- 哈希表处理冲突的主要三个方式是：

	1. 线性再散列，就是如果冲突则按照步长一直找（步长与哈希表长度应该是互质的），找到一个空槽（slot）为止

	2. 非线性再散列，如果冲突，则重新计算出一个哈希值

		以上两种再散列法的特点为：

		- 再散列法都不能删除元素，否则会导致元素找不到（因为每一个元素都可能发生过冲突，而如果这个元素被删除，那么跟其发生过冲突并且再散列的元素就找不到了）
		- 当散列表负载因子（插入表中的元素个数/可用槽的总数）增大时，再散列花费的时间也会越长
		- 表的大小就是所能容纳的元素的大小

	3. 拉链法（是解决哈希冲突的最常用方法），在发生冲突的槽中使用链表存放冲突元素，也就是使用链表数组来解决冲突

####Tree - 树  
<span id="3.12">BinarySearchTree 	二叉查找树</span>  
<span id="3.13">BalancedBinaryTree 	平衡二叉树 - 又称为AVL树，因其作者（Adelson-Velskii and Landis）而得名</span>  
<span id="3.14">RedBlackTree		红黑树 - 通过为节点着色并且为色彩赋予一定的规则来实现平衡</span>  
<span id="3.15">BTree				B树 - 又称为Balanced Tree，一棵多路搜索树，用途很广，几乎是所有数据库的默认索引结构</span>  