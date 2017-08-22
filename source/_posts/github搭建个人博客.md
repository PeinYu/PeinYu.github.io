---
title: github搭建个人博客
date: 2017-08-22 13:50:19
tags:
---
github搭建博客

####  日常写博客流程：
- 在本地博客代码路径 （E:\blgo\peinyu.github.io 默认是hexos分支）下右键召唤出git bash
键入hexo n “新博客名” 来创建新博客。

 
- 在本地Markdown编辑器下编辑博客，文章根目录为 E:\blgo\peinyu.github.io\source\_posts。
- 依次执行git add .、git commit -m “add”、git push origin hexo指令将改动推送到GitHub（此时当前分支应为hexos）；
- 然后才执行hexo generate -d发布网站到master分支上（hexo配置文件中设置分支为master）。

#### 两个分支
master分支
hexos命令生成博客存放分支 文章以html形式体现。

hexos分支
hexos源文件，文章以.md形式体现，也是日常编辑文章分支。


#### hexo命令
hexo n “博客名”   创建新博客 hexo new
hexo g                 生成静态页面  hexo generate 
hexo d                 部署  hexo deploy
hexo g -d             生成并部署



#### 引用：
日常写博客路程：
http://crazymilk.github.io/2015/12/28/GitHub-Pages-Hexo搭建博客/#more
换了电脑怎么更新博客:
https://www.zhihu.com/question/21193762
hexo常用命令：
http://blog.csdn.net/qq_26975307/article/details/62447489

