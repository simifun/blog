---
title: Java开发环境配置
date: 2018-11-13 14:17:59
tags:
  - Java
  - Android
categories: 
  - Java
---

# <span id="preface">前言</span>
---
在Java中，类库以包（package）的形式提供，不同版本的Java提供不同的包，以面向特定的应用。
Java2平台包括标准版（J2SE）、企业版（J2EE）和微缩版（J2ME）三个版本。
>Java SE(Java Platform,Standard Edition)。JavaSE以前称为J2SE.它允许开发和部署在桌面、服务器、嵌入式环境和实施环境中使用的Java应用程序。JavaSE 包括支持Java　Ｗeb服务开发的类，并为Java Platform,Enterprise Edition(Java EE)提供基础。

>Java EE(Java Platform.Enterprise Edition)。这个版本以前被称为J2EE.企业版本帮助开发和部署可移植、健壮、可伸缩切安全的服务端Java应用。Java EE是在JavaSE的基础上构建的他提供Web 服务、组建模型、管理和通信API.可以用来实现企业级的面向服务体系结构(service-oriented architecture,SOA)和web2.0应用程序。

>Java ME(Java Platform,Micro Edition)。Java ME为在移动设备和嵌入式设备（比如手机、PDA、电视机顶盒和打印机）上运行的应用程序提供一个健壮且灵活的环境。Java ME包括灵活的用户界面、健壮的安全模式、许多内置的网络协议以及对于动态下载的连网和离线应用程序的丰富支持。基于Java ME规范的应用程序只需要编写一次，就可以用于许多设备，而且可以利用每个设备的本级功能。

搭建Java开发环境一般需要同时安装JDK和JRE。  
>JDK：指Java开发工具包Java Development Kit，开发Java程序时必需，JDK里包含一部分公共JRE。  
JRE：一个Java运行环境Java Runtime Environment，运行已开发的Java程序时所用。

**请按照需求安装，本文选取JavaSE JDK8 进行Windows10环境下的安装演示。**

# <span id="install">下载安装</span>
---
点击[下载链接](https://www.oracle.com/technetwork/java/javase/downloads/index.html)，进入官网下载页面。
依次点击下图中的下载按钮下载JDK。（64位操作系统可安装x86版、x64版，32位操作系统只能安装x86版）。  
![](1.png)  ![](2.png)  
下载完成后，请自行安装，安装过程中的JDK和JRE的路径请务必记住，在后续的环境配置中需要用到，路径如下图。  
![](3.png)  ![](4.png)
# <span id="environment">配置环境变量</span>
---
Java环境变量涉及到三个名词：JAVA_HOME、path、classpath。  
>JAVA_HOME代表JDK安装主目录，path代表JDK下可执行文件目录，classpath代表运行java程序时需要查找class文件的目录。  

依据上面的安装步骤，应该这样设置：
* 依次点击“右键我的电脑” -> “属性” -> “高级系统设置” -> “高级” -> “环境变量”，打开环境变量设置窗口。以下各项，有已存在的环境变量，直接编辑其值，切勿全盘覆盖；不存在的自己新建。
* JAVA_HOME：D:\DevelopTools\JAVA\JDK
* path：%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;（`注意其中的分号，Windows10有“新建”按钮可忽略分号`）
* classpath：.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;（`注意最前面的点代表当前路径，JDK1.5之后classpath可忽略`）
至此，我们已经完成了Java开发环境的安装和配置。

# <span id="test">测试</span>
---
最后，我们来测试一下以上操作是否都已成功生效。打开命令行终端，PowerShell或者CMD等都行。(win+X,A)  
输入`java -version`回车、`javac`等等只要有窗口有类似的输出，即说明我们已经成功了！Congratulations!  
![](5.png)
