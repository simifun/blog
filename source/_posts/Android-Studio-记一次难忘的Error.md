---
title: 'Android Studio,记一次难忘的Error: Could not find method ?apply() for arguments'
date: 2018-01-31 15:28:06
tags: 
  - Could not find method
  - Gradle DSL method not found
categories: 
  - Android
  - Android Studio
copyright: true
---
今天打开上周才运行过的Android项目,意想不到的错误出现了：
> Could not find method ?apply() 
for arguments [{plugin=com.android.application}]  
……

同样的
> Gradle报错:Gradle DSL method not found: 'apply()'  
……

当时的环境及版本信息：
- Android Studio版本3.0
- build.gradle(工程根目录) 版本3.0.0
- gradle-wrapper.properties:distributionUrl=https\://services.gradle.org/distributions/gradle-4.1-all.zip`


点击Message定位到某module下的build.gradle文件的第一行:apply plugin: 'com.android.application'

本来以为靠着万能的google就能很快解决问题，结果莫名其妙就耽误了半个下午.

尝试过的解决方案：

- 删除allprojects后边的生成的多余android {……}，dependencies{……}
- 更改根目录下build.gradle中的classpath的gradle版本
- svn diff/svn update
- 将Android studio版本降到2.4再尝试上述过程
- ……

全军覆没，就差最后一步delete之，然后svn checkout重建项目了。

现在想想真是浪费时间啊，为了增强一下记忆，我把这个错误记下来分享一下。

究极解决方案就是

> 复制对应moudle下的build.gradle内容，删除掉该build.gradle文件，新建之，粘贴之,最后rebuild一下，应该就没有什么问题了。
