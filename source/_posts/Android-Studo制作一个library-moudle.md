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

Android开发过程中，我们或多或少会引用第三方library，那如果我想把自己写的Android库公开，为开源做出一点贡献该怎么办呢？一般有两种方式，一种就是制作一个线上依赖：就像我们常用的gradle依赖，complie 'xxx'（Android Studio 3.0之后建议使用implementation或api等）；另一种就是将要开源的项目做成一个moudle library直接上传到开源仓库，供别人下载导入，懒人开源。下面我们着重介绍一下后者。

<!-- more -->

