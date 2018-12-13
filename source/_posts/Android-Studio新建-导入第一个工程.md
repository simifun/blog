---
title: Android Studio新建/导入第一个工程
date: 2018-11-14 14:42:28
tags:
  - Android
  - 开发环境
categories:
  - Android 
  - Android Studio
---

终于可以大展身手了！本文着重讲解一下用Android Studio新建、导入工程项目、导入moudle等，可照目录按需查看。->->
<!-- more -->
# 新建一个工程目录
---
直接看图吧，图中有标注，按照步骤来一定错不了。  
![](1-1.png)
![](1-2.png)
![](1-3.png)
![](1-4.png)
![](1-5.png)
![](1-6.png)  
我们的新项目算是建立好了，现在我们来运行一下 
USB连接手机和电脑，手机在设置里打开“开发者选项”->“USB调试”。（不同的手机进入开发者选项有所区别，大家自行搜索）  
点击图中绿色三角图标，在弹出的窗口中选择刚刚连接到电脑的手机，点击ok，静静等候。手机会自动安装上app（有的手机需要手动确认安装），并自动打开。如图，可以看到熟悉的“Hello World!”。 （如果你的三角图标是灰色，请看本章[注意事项](#注意事项)）   
![](2-1.png)
![](2-2.jpg)  
大功告成，Android开发已经完全走通了一遍，接下来就看个人的发挥了！大家一起进步呀！。

# 导入Gradle项目
直接在Android Studio的工作页面点击File菜单，选择“New”->“import project”（当然欢迎页面也有这个选项）  
![](3-1.png) ![](3.png)  
选择你要导入的项目，点击OK，Android Studio会提示我们是在当前窗口打开，还是新建窗口打开，请自行定夺，之后就是等待了，倘若等待过久，一直卡在“Gradle Build Running”请看本章[注意事项](#注意事项)。  
![](3-2.png) 
# 导入moudle
当你需要引用别人的library怎么办呢？这里提供三种常用的方案：
> 1.通过gradle远程依赖下载Jar包，需连外网。gradle依赖可见build.gradle文件中的dependencies {}，implementation/api...等等不做赘述。 
> 2.直接导入下载好的Jar包。  
> 3.另外就是下载好Android项目，直接离线作为moudle导入。下面详细介绍一下这种导入方式。  

导入moudle有两种方式，一是通过AS的工具导入，二是改写配置代码。
* AS工具导入
  1. 点击File菜单，选择“New”->“import Moudle”。
  2. 选择要导入的moudle目录（若不确定被导入的目录是不是一个正确的mouble，你可以查看本站另一篇文章[Android Studo制作一个library moudle](https://blog.qsong.fun/2018/11/15/Android-Studo%E5%88%B6%E4%BD%9C%E4%B8%80%E4%B8%AAlibrary-moudle/)）。    
  ![](4-1.png) ![](4-2.png)  ![](4-3.png) ![](4-4.png)
  3. 打开工程结构窗口，选中当前项目下的主模块（一般默认是app）。切换到dependencies选项卡，点击图中的“+”选择“Module dependency”。  
  ![](4-5.png)
  4. 选择moudle，点击ok。成功导入!  
* 代码导入（**推荐**!!第一种方式的实质就是AS自动生成了代码）
  1. 首先打开工程根目录下的setting.gradle，按照下图改写。   
  ![](5-1.png)
  2. 打开当前项目下的主模块（一般默认是app）目录下的build.gradle文件，按照下图改写。  
  ![](5-2.png)
  
# 导入Eclipse工程
导入Eclipse工程，写起来的话，篇幅也很大，这里偷个懒，大家可以去看看这篇博客，写的挺详细的。
> [Android Studio导入Eclipse项目的两种方法](https://www.cnblogs.com/mstk/p/6307291.html)


# 注意事项
---
在新建和导入项目的时候，总会不是一帆风顺的，要么久久等候卡着不动、要么这里报错那里报错根本运行不起来……为了解决问题，我们需要打交道的文件总逃不出这几个。  
![](6-1.png)
下面是笔者收集的一些问题，大家可以对号入座。
[怎么解决Android studio导入项目卡死](https://www.jianshu.com/p/e1c0b46e317c)  
[Android Studio 编译时提示error please select android sdk](https://blog.csdn.net/csdnzzj255/article/details/78870891)  
[android studio的sdk所有方法报错，全部红色警告](https://blog.csdn.net/u010773839/article/details/53609473)
[安卓studio升级到3.0后，创建项目时报错](https://blog.csdn.net/zhangyanqiu12/article/details/80226289)