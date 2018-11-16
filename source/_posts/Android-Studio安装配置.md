---
title: Android Studio安装配置
date: 2018-11-13 16:50:04
tags:
  - Android
  - 开发环境
categories: 
  - Android
  - Android Studio
---

# 前言
---
Android SDK你装或者不装都可以进行Android Studio(简称AS)的安装配置。~~只不过装过SDK的且已经用过Android SDK Manager的同志在进行以下配置之后，可能也许大概会遇见一个问题，你会发现你的SDK Manager.exe程序再也打不开了，双击只会闪退~~。**这并不会影响AS的使用**，AS3.0之后完全取消了独立的SDK Manager，将其完全整合到内部，一切操作都可以在AS内部完成！Android SDK在AS内部的配置可以查看[Andorid Studio常用功能设置]()。  
废话说的有点多，下面正文开始。
<!-- more -->
# 下载安装
---
1. [点击链接](http://www.android-studio.org/)下载安装，目前最新版本3.2.0。默认是64位的，如果是要32位的，从“选择其他平台“中找到Windows(32-bit)。 
2. 下载完成之后，打开安装包首先会提示你选择要安装的组件，“Android Virtual Device”是Android虚拟机，我这里没有选择安装。  
![](12.png)
# 初次运行设置
---
1. 打开软件进行配置，会让你选择1.从现有的文件导入设置。2.不导入设置。这里我们选择默认选项（第二项），点击OK进行下一步。  
![](1.png)
2. 此时会提示你“访问不到SDK的位置”，此时点击cancel，有时会出现“Finding Available SDK...”提示框，请稍等一会进入第三步。  
![](20.png) ![](21.png)
3. 出现欢迎页面，点击next。  
![](3.png)
4. 提示选择你想要设置(安装)的类型。1.标准设置2.自定义设置。这里推荐选择第二项自定义设置，进入第5步。(`事实证明这一步无论选什么都会进入第五不、第六步`)。  
![](4.png)
5. 选择主题样式。这里笔者比较喜欢暗黑风格:-)  
![](5.png)
6. 自定义安装设置，Android SDK/Android SDK Platform这两项默认必选。然后设置一个Android SDK的目录，以后在AS中下载的SDK都会放在这个目录；后两项看情况勾选，一个是Intel硬件加速、一个是自带的安卓模拟器。(AS的模拟器有点慢，我没有安装，用模拟器的话可以看看[Android模拟器推荐]())  
![](6.png)
7. 最终的确认页面，点击Finish，等待安装配置完成。
![](7.png)
8. 出现这个页面，AS的安装就大功告成了！Congratulations!  
![](8.png)
---
>相关推荐[Android Studio新建/导入第一个工程](https://blog.qsong.fun/2018/11/14/Android-Studio%E6%96%B0%E5%BB%BA-%E5%AF%BC%E5%85%A5%E7%AC%AC%E4%B8%80%E4%B8%AA%E5%B7%A5%E7%A8%8B/)
