---
title: "Hugo博客搭建"
description: "初学者尝试自己搭建，主要记录一些踩过的坑。"
date: "2021-02-01 00:00:00+0200"
slug: "post"
image: ""
categories:
    - 博客
tags:
    - Hugo
---

# HUGO博客搭建

本博客搭建参照少数派[Elizen](https://sspai.com/u/elizen/updates)的文章[《使用 Hugo 从 0 到 1 搭建个人博客》](https://sspai.com/post/64639)

HUGO主题下载：[主题](https://themes.gohugo.io/)	本博客使用的主题为：[stack](https://themes.gohugo.io/hugo-theme-stack/)

* 更换博客主题

  1. 按照上述文章搭建完成后，如果需要更换主题，把下载完成的主题解压至博客文件路径，目录`*/temes`下，文件夹名称可修改，这里博主改为`stack`。

     ![image-20210208141813462](https://gitee.com/Dontao/imgbed/raw/master/imgs/image-20210208141813462.png)

  2. 打开主题文件夹，进入`exampleSite`，将文件夹内的所有文件复制到伯博客文件夹主目录下并替换（红框中的文件建议必选，其中`congfig.yaml`主题配置文件）。

     ![image-20210208142119064](https://gitee.com/Dontao/imgbed/raw/master/imgs/image-20210208142119064.png)

  3. 回到主目录删除除`congfig.yaml`外的其他格式配置文件。然后打开文件该文件，修改博客地址、主题文件夹名称（博主为`stack`）。

     ![image-20210208142459809](https://gitee.com/Dontao/imgbed/raw/master/imgs/image-20210208142459809.png)

     其余配置文件信息，参考主题说明文档。stack主题文档地址：https://docs.stack.jimmycai.com/v/zh-cn/

  4. 修改完成后，先保存、上传。等待自动化运行完成后，打开博客地址，如果没有问题，即完成博客创建。

     

     **如果打开存在未编码完全的情况，请参照下面的步骤。**

     

  5. 我们打卡GitHub博客项目，打开`.github/workflows`

     ![image-20210208143255123](https://gitee.com/Dontao/imgbed/raw/master/imgs/image-20210208143255123.png)

  6. 打开`***.yml`文件，也就是你之前创建的自动化文件。添加`extended: true`，因为部分主题需要用到hugo的extented版本才可编译成功。

     ![image-20210208143949046](https://gitee.com/Dontao/imgbed/raw/master/imgs/image-20210208143949046.png)

     ```
     name: Update Hugo
     
     on:
       push:
         branches:
           - master   # master 更新触发
     
     jobs:
       build-deploy:
         runs-on: ubuntu-18.04
         steps:
           - uses: actions/checkout@v2
     
           - name: Setup Hugo
             uses: peaceiris/actions-hugo@v2
             with:
               hugo-version: latest
               extended: true
     
           - name: Build 
             run: hugo
     
           - name: Deploy
             uses: peaceiris/actions-gh-pages@v3
             with:
               personal_token: ${{ secrets.personal_token }} # 填写你自己的 personal_token
               PUBLISH_BRANCH: gh-pages  # 推送到当前 gh-pages 分支
               PUBLISH_DIR: ./public  # hugo 生成到 public 作为跟目录
               commit_message: ${{ github.event.head_commit.message }}
     ```

  7. 最后，重新运行workflow，再次打开博客即可。
