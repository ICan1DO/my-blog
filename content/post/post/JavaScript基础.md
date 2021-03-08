---
title: "JavaScript基础"
description: "自学之路"
date: "2021-03-08 17:14:03"
slug: "post"
image: ""
categories:
    - 编程
	- 自学
tags:
    - JavaScript
---

# JavaScript基础

## 数据类型

* 原始数据类型（基本数据类型）
  1. number：数字。整数/小数/NaN（not a number）
  2. string：字符串
  3. boolean：true/false
  4. null：false
  5. undefined：false 
* 引用数据类型：对象

## 变量

var 变量名 = 初始化值;

typeof(变量名)：获取变量的数据类型

## 类型转换

1. number：0或NaN为false，其他为true
2. string：“”为false，其他为true
3. null：false
4. undefined：false
5. 对象：所有对象都为true

## 对象

* Function对象
  
  1. 创建方式
  
       ```javascript
       //形参不需要填写数据类型，返回值也可以省略
       var fun1=new function("a","b","alert(a+b)"); //第一种方式
       function fun2(a,b){
           alert(a+b);
       }; //第二种方式
       var fun3=function fun(a,b){
           alert(a+b);
       }; //第三种方式
       ```
  
  2. 重名及参数相同：方法重名且参数相同，方法会被覆盖。
  
  3. 方法调用：方法调用只与方法的名称有关，和参数列表无关。
  
  4. 传入参数：JS方法声明中有一个隐藏的内置对象（数组：arguments），封装所得的实际参数。