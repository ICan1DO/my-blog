---
title: "Java集合"
description: "自学"
date: "2021-03-14 17:14:03"
slug: "post"
image: ""
categories:
  - 编程
	- 自学
tags:
    - Java
---

# Java集合

* Collection

  集合接口层级的底层。Java平台并不提供任何对Collection接口的直接实现，但是提供更加详细的对子接口的实现，诸如Set和List接口。

  ```Java
  //基本操作方法
  size(); //返回集合中元素个数
  isEmpty(); //判断集合是否为空
  contains(); //是否包含某个元素
  add(); //添加元素，成功返回True
  remove(); //移除元素
  iterator(); //迭代器
  hasNext(); //是有含有下一个元素，并且返回下一个元素
  
  collection.removeAll(Collection.singleton()); //Collections.singleton是一个静态工厂方法，返回一个只包含指定元素的不可变的Set集合。例如Collections.Singleton(e)方法返回只包含元素e的Set集合，然后集合c调用removeAll方法删除c中所有元素e的实例。同样，Collections.Singleton(null)方法返回只包含元素null的Set集合，然后集合c调用removeAll方法删除c中所有null元素。
  
  toArray(); //方法主要是作为集合和老的期望输入数组的API之间的桥梁。数组操作允许Collection中的内容被转换到一个数组中去
  ```

  

  * Set

    不能包含重复元素的集合

    * SortedSet

      元素按升序排列的Set。
      
    * HashSet

      HashSet，将其元素存储在一个哈希表中，它具有最好的性能实现；然而它不保证迭代的顺序。

    * TreeSet

      TreeSet，将其元素存储在一个红黑树中，按元素的值顺序排列；本质上它比HashSet要慢。

    * LinkedHashSet

      LinkedHashSet，是作为一个哈希表实现的，用链表连接这些元素，按元素的插入顺序排列。

  * List

    一个有序的集合。List可以包含重复的元素，并且List中的元素是有序排列的。

    * ArrayList

      通常有较好的性能实现

    * LinkedList

      在一定条件下提供较好的执行性能

  * Queue

    是一个其元素带有先后处理顺序的集合。队列通常（但不是必需的）以一种FIFO（先进先出）的形式管理元素。

* Map

  一个将键映射到值的对象。Map不能包含重复的键；每个键最多能映射到一个值（值之间可以重复）。

  * SortMap

    映射关系按键的升序排列的Map。

