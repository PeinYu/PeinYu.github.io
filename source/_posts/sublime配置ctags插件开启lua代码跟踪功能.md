---
title: sublime配置ctags插件开启lua代码跟踪功能
date: 2018-04-19 11:49:19
tags:
categories:
---

sublime配置ctags插件开启lua代码跟踪功能

自从配好sublime代码跟踪，妈妈再也不用担心我另开codeide电脑会卡死了

环境：windows7
首先要有一个sublime Text软件，配置好lua环境
本文使用cocos2dx-3.x+lua作为开发环境。

- 安装Sublime text插件
    确认Sublime text已安装Install Package；
    按Ctrl+shift+P，输入Install Package回车；
    弹出下拉框后输入ctags回车进行下载

- 配置ctags插件追踪函数的快捷键（可省略）
1）进入如下图菜单：


2）弹出如下内容：默认为ctrl+shift+鼠标左键。


3）将其全选复制到如下图位置：


4）粘贴后修改并保存为如下图内容：


至此，插件安装部分完成。

- 下载ctags程序
http://prdownloads.sourceforge.net/ctags/
将文件夹中ctags.exe的目录加入到path环境变量中。
并在lua项目代码根目录中文件夹使用cmd打开终端命令行，运行命令①
‘’‘
ctags --langdef=MYLUA --langmap=MYLUA:.lua --regex-MYLUA="/^.*\s*function\s*(\w+):(\w+).*$/\2/f/" --regex-MYLUA="/^\s*(\w+)\s*=\s*[0-9]+.*$/\1/e/" --regex-MYLUA="/^.*\s*function\s*(\w+)\.(\w+).*$/\2/f/" --regex-MYLUA="/^.*\s*function\s*(\w+)\s*\(.*$/\1/f/" --regex-MYLUA="/^\s*(\w+)\s*=\s*\{.*$/\1/e/" --regex-MYLUA="/^\s*module\s+\"(\w+)\".*$/\1/m,module/" --regex-MYLUA="/^\s*module\s+\"[a-zA-Z0-9._]+\.(\w+)\".*$/\1/m,module/" --languages=MYLUA --excmd=number -R
’‘’
中间尝试运行过下面代码，但并不管用。
‘’‘
ctags -R -f .tags
’‘’
运行命令①后目录下会生成一个tags文件
之后打开sublime 选择打开文件夹，到lua所在的文件夹，右键选择

点击它，会在根目录下生成.tags和.tags_sorted_by_file两个文件，我们打开刚刚生成tag文件，复制里面的内容复制替换.tags里面的内容，之后，我们的lua编辑环境就搭建好了。

- 使用方法
使用快捷键： 修改后可使用ctrl+左键进行代码跳转，同时原来的ctrl+shift依然可以使用
使用键盘组合件 ctrl+t+t （按住ctrl连按两下t）也可以做到代码跳转
代码跳转返回到原代码页是ctrl+右键。

如果本文对你有点帮助，just let me know. :)


引用：
https://blog.csdn.net/xxhsu/article/details/30766675
https://blog.csdn.net/wd860011204/article/details/45190781
https://blog.csdn.net/zdl1016/article/details/9118579

