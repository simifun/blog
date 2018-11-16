---
title: Android SDK安装配置
date: 2018-11-14 11:56:11
tags:
  - Android
  - 开发环境
categories:
  - Android
---
# 概念
---
* `SDK tools` SDK tools即Google官方推出的SDK工具集合，有安装版和解压版。一个纯净的SDk tools目录如下图，**此目录就是Android Studio等IDE要配置的SDK根目录**，但是此目录还缺少一些东西，需要SDK Manager和AVD Manager去下载安装。以下介绍的都是SDK的子工具包，将所有的子包综合起来就是名副其实的Android SDK(安卓开发工具集)了。  
![最初的SDK目录](1.png "最初的SDK目录")
* `tools` 针对pc平台下使用的工具：比如模拟器，.9patch工具，性能追踪可视化工具traceview；还有Android系统api，针对不同的系统api，对接口和性能做了调整，是Android sdk的核心，所以有时也认为tools就是上面所说的SDK tools（傻傻分不清楚），在SDK Manager中对应图中标记①。
* `platform-tools` 针对pc端和移动端进行交互的一些工具：比如adb工具（通过该工具pc端获取移动端log信息），sqlite3工具（通过该工具查询移动端数据库信息），在SDK Manager中对应图中标记②。
* `build tools`  aapt工具，aidl工具和打包工具（apkbuilder,dex工具），在SDK Manager中对应图中标记③。
<!-- more -->
```
aapt编译资源文件得到二进制xml和R.Java  
aidl工具将aidl文件--Java interface  
javac：R.java +java interface + application source code+thrid jar->class.dex文件  
apkbuilder：class.dex+binary resouce+other resouce--->xx.apk  
```
![SDK Manager示例1](2.png "SDK Manager示例1")
* `platform` 所有版本的API都存放在这里，统一命名为android-xx。你在写Android代码时调用的android包下的API都来自此。如图中标记④。
* `source` 各版本的API源代码，目录下文件命名与platform一致并与其一一对应⑤。

![SDK Manager示例2](3.png "SDK Manager示例2")

# 下载安装
---
1. [点击下载](http://tools.android-studio.org/index.php/sdk)，Windows系统下有安装版和解压版，选择一种下载。安装版请点击exe程序完成安装，解压版直接解压到一个目录即可。此目录就是Android SDK目录了。
2. 上面下载的工具包还需要完善一下，接下来打开SDK Manager安装一些Android开发必要的资源。哪些必需安装、哪些不必要安装见下图。  

**>>看不清的图片可在新标签打开查看大图**   
![SDK必要工具包一览](4.png "SDK必要工具包一览")
# Android Studio对SDK根目录的改动
---
有些细心的同学在使用Android Studio编辑工具一段时间后，去手动打开SDK Manager.exe之后会发现它会闪退，怎么都打不开，别慌，这是因为Android Studio对你的sdk目录做了一些改动，尤其是tools目录下的东西。这里大家可以去查看一下这篇博客，有对应的解决方案。
> [android SDK SDK Manager.exe 无法打开，一闪而过最终解决办法](https://blog.csdn.net/wang295689649/article/details/60960953)