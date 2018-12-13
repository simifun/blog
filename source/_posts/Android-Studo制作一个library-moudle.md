---
title: 'Android Studo制作一个moudle library'
date: 2018-11-15 17:17:36
tags:
 - Andoird 
 - Andoird Studio
 - moudle
categories:
 - Android 
 - Android Studio
---

Android开发过程中，我们或多或少会引用第三方library，那如果我想把自己写的Android库公开，为开源做出一点贡献该怎么办呢？一般有两种方式，一种就是制作一个线上依赖：就像我们常用的gradle依赖，complie 'xxx'（Android Studio 3.0之后建议使用implementation或api等）；另一种就是将要开源的项目做成一个moudle library直接上传到开源仓库，供别人下载导入，懒人开源，下面简单的介绍一下这种方式（开发IDE为Android Studio）。

<!-- more -->

假设你的Android工程的可执行程序包名是app（默认都是app），你想将这个app改造成一个library供别人使用，首先进入app目录，打开的build.gradle文件（不是工程根目录下的build.gradle文件），找到如图中的两处。  
![图片描述](1.png)

* 将apply plugin: 'com.android.application'修改为apply plugin: 'com.android.library'。
* 将android->defaultConfig下的applicationId "xxx"删除。
* 删除其他不必要的配置，比如打包、签名等。必要的几项如下图。  

![图片描述](2.png)  
此外，你可以将app目录下的build文件、*.iml等临时文件编译删除，然后将整个app目录从工程中移出去，一个新的moudle就诞生了。

>PS：本文中的app目录只是假设举例，你可以自由修改这个目录。

>相关推荐》[Android Studio导入module](https://blog.qsong.fun/2018/11/14/Android-Studio新建-导入第一个工程#导入moudle)