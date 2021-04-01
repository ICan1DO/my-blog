---
title: "Tomcat项目部署"
description: "Tomcat部署简介"
date: "2021-04-01 20:36:13"
slug: "Tomcat-setup-webapps"
image: ""
categories:
    - Coding
    - Java
tags:
    - Java
---

# Tomcat项目部署

## 部署方式

1. 直接将项目文件放置在`webapps`目录下。

   * /example：项目的访问路径-->虚拟目录
   * 可将项目打包成`.war`格式，然后放置本目录下，Tomcat会自动解压

2. 配置`conf/sever.xml`

   在`<Host>`标签中配置

   ```xml
   <Context docBase="C:\example" path="/example">
   <!--docBase:项目存放的路径
   	path:虚拟目录-->
   ```

   

3. 在`conf/Catalina/localhost`中创建xml文件（例如：`example.xml`）。

   ```xml
   <Context docBase="C:\example">
       <!--虚拟目录：xml的文件名称(example)-->
   ```

## 项目目录简介

含静态项目和动态项目

```
example //项目根目录
	|_ WEB-INF
		|_ web.xml //web项目核心配置文件
		|_ classes //放置字节码文件的目录
		|_ lib //放置依赖的jar包
```