---
title: "JavaScript基础"
description: "自学"
date: "2021-03-08 13:33:03"
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

* Function方法对象
  
  1. 创建方式
  
       ```javascript
       //形参不需要填写数据类型，返回值也可以省略
       let fun1=new function("a","b","alert(a+b)"); //第一种方式
       function fun2(a,b){
           alert(a+b);
       }; //第二种方式
       let fun3=function fun(a,b){
           alert(a+b);
       }; //第三种方式
       ```
  
  2. 重名及参数相同：方法重名且参数相同，方法会被覆盖。
  
  3. 方法调用：方法调用只与方法的名称有关，和参数列表无关。
  
  4. 传入参数：JS方法声明中有一个隐藏的内置对象（数组：arguments），封装所得的实际参数。
  
* Array数组对象

  1. 创建方式

     ```javascript
     //数组长度可变，若没有赋值，则为undefined
     let arr1=new Array(1,2,3); //1,2,3
     let arr2=new Array(4); //,,,
     let arr3=[1,2,3,"abc",true];//1,2,3,abc,true
     ```

  2. 方法
  
     ```javascript
     arr1.join(); //join(参数):按照指定字符串拼接数组。默认","
     arr2.push(); //push()：向数组末尾添加元素。
     ```
  
* Data日期对象

  1. 创建方式

     ```javascript
     let date=new Date();//默认美国时间格式
     ```

  2. 方法

     ```javascript
     toLocaleString();//toLocaleString()：转换为当地时间格式
     getTime();//获取毫秒值，与1970年1月1日比较
     ```

* Math数学对象

  1. 创建方式

     不需要创建，直接使用`Math.[方法名]`

  2. 方法

     ```javascript
     Math.PI;//获取π值
     Math.random();//反悔[o,1)之前的随机数
     Math.round(3.14);//3 四舍五入
     Math.ceil(3.14);//4 向上取整
     Math.floor(3.14);//3 向下取整
     ```

* RegExp正则表达式对象

  **正则表达式语法**

  1. 单个字符：[]

     ```javascript
     [a] //字符a
     [ab] //a或b
     [a-z] //任意小写字符
     \d //单个数字，同[0-9]
     \w //单个单词字符，同[a-zA-z0-9]
     ```

  2. 量词字符

     ```javascript
     ? //表示出现0次或1次
     * //表示出现0次或多次
     + //表示出现1次或多次
     {m,n} //表示 m<=次数<=n
     ```

  **正则表达式对象**

  1. 创建方式

     ```javascript
     let reg=new RegExp("^\w{6,12}$"); //表示6-12个字符
     let reg=/^\w{6,12}$/;
     ```

  2. 方法

     ```javascript
     reg.test("Tred0ff"); //测试字符串是否符合定义规则。
     ```

* Global对象

  全局对象，其中封装的方法不需要对象即可直接运行。

  1. 方法

     ```javascript
     encodeURI();//URL编码，一般只编码汉字
     decodeURI();//URL解码
     
     encodeURICompare();//URL编码,编码的字符更多，字符也编码
     decodeURICompare();//URL解码
     
     parseInt(); //逐一判断每一个字符是否是数字，知道不是数字为止。将前面数字转行为number
     
     isNaN(); //判断传入值是否是NaN
     
     eval(); //将javascript字符串转化为代码执行
     ```

## DOM

Document Object Model

* Document对象

* 事件

  1. 获取元素

     ```javascript
     let element=document.getElementById(); //通过元素ID获取Html元素
     element.src="img/1.jpg" //设置Html元素属性
     ```

  2. 事件绑定

     ```javascript
     //1.在Html标签元素中，指定时间属性
     <img id="car" src="img/car.jpg" onclick="functionName">
     //2.js获取标签元素，获取事件属性
     element.onclick= functionName;
     ```

## BOM

* Window：浏览器窗口对象

  1. 创建方式

     Window对象不需要创建。直接使用`window.方法名()`或者`方法名`使用。

  2. 方法

     ```javascript
     alert();//弹出提示框
     confirm();//弹出选择框，返回true或false
     prompt();//显示用户输入对话框，返回用户输入的内容
     
     open(); //前台新建浏览器标签页，并返回window对象
     close(); //关闭当前浏览器标签页
     
     setTimeout(); //指定毫秒数后，调用函数或者表达式。参数可以是方法或者代码片段
     clearTimeout(); //取消setTimeout()方法设置的Timeout
     setInterval(); //按照指定的周期（毫秒）调用函数计算。参数可以是方法或者代码片段
     setInterval(); //取消setInterval()设置的周期
     ```

  3. 可以获取下面BOM对象

     history、navigator、screen、location。

  4. 可获取下面DOM对象

     document

* Navigator：浏览器对象

* Screen：屏幕对象

* History：标签页历史记录对象

* Location：标签页地址对象 

  ```javascript
  reload(); // 刷新当前页面
  
  location.href;//url地址href属性
  ```

  



