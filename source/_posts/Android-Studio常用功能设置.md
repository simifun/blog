---
title: Android Studio常用功能设置
date: 2018-11-15 17:16:17
tags:
 - Android
 - Android Studio
 - 设置
categories:
 - Andoird 
 - Andoird Studio
---

本篇文章主要记录一下Android Studio这款IDE的一些常用的功能设置，包括但不局限于自动包管理、热调试、字体大小颜色配置等。

<!--more -->
File->Settings打开设置窗口，快捷键是ctrl+alt+S  
![](setting.png)
# 自动包管理
自动导入缺失包、删除无用包
![](autoimport.png)
# 热调试
快速调试，无需每次重新打包安装
![](instantrun.png)
# 软件主题、字体设置
![](theme.png)
# 开启文档提示
![](doc.png)
# 显示行号
![](lines.png)
# 自动折叠
![](collapse.png)
# 代码字体、配色设置
![](code_1.png)  ![](code_2.png)  ![](code_3.png)  
编写Android程序最常用的是Java语言，所以这里特意说下Java的配色：![](java.png)  
另外注意还有几个配色经常用到如下图：  
  ![](color.png)
# 编码设置  
编码的设置非常重要。这里建议所用的编译器均设置为UTF-8编码，以兼容中文，否则出现乱码。
像Eclipse系列的编译器默认是GBK编码，如果直接移植到默认编码是UTF-8的AndroidStudio上，就会出现中文乱码。
  ![](encode.png)

# 工具栏功能按钮设置
 如果想便捷地在工具栏直接使用功能，可以参考如下设置：
* 添加一个自带默认图标的功能按钮，以设置按钮为例：
  1. 右键工具栏空白处，在弹出的窗口里选择自定义...
    ![](toolbar_1.png)
  2. 可以看到我那个设置按钮已经存在了，现在为了示范，我在那个安卓小绿人后面再添加一个设置按钮：
   ![](toolbar_2.png)  
* 添加无默认图标的功能按钮
有些功能系统是没有预置图标的，添加时，操作步骤大体与s上面一致，唯一不同的是，这里需要给你添加的按钮设置一个很小的图标，图标路径可以自定。

