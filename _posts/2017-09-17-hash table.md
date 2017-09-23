---
'title': 'hash table'
'date': 2017-09-17
---
# hash table

今天终于主动去了解了一下散列表，拖了好久了。

记得刚开始学习 Python 时，首次接触字典的概念时，还不觉得字典有什么用。那时虽说在学编程，但对编程的认知太过肤浅，以为学好编程语言本身的语法就可以了。

真是幼稚啊。

Python 中的字典就是 hash table 的一个具体实现。hash table 就是一种存储键值对的数据结构，最大的特点是可以实现平均 O(1) 的查询复杂度。这意味着查询速度不会因为数据量增大而变慢，是一种对查询非常友好的数据结构类型。

键值对在抽象模型相当于把数组的索引替代为 key，同时 key 对应的值可以为任意的数据类型。

抽象意义如此，但具体实现不能以 key 为索引值，那样的话，查询速度太慢。

在计算机中，最快的查询速度必然是「根据内存地址直接索引」，因为这样可以直奔目标，而无需沿着某种结构去渐次搜寻。

那么，如何将键值对实现为按地址存取呢？

这就需要使用**hash 函数将 key 映射为某个 index 地址索引。**

具体的 hash 函数可以有多种实现，在实际使用中，因为一般都不是完美的 hash 函数，所以需要处理 撞脸 现象。

到这里，散列表 hash table 的实现流程就比较清晰了：

>  表面上键值对的存储，实际上是 index-value pair。
>  具体实现分为两步，一步是选取合适的 hash 函数利用 key 生成 index；另一步是选取合适方法处理 collision 问题。

关于 hash table，暂时先这样。