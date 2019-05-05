---
title: 简单聊聊ThreadLocal
date: 2018-12-14 15:38:30
  - ThreadLocal
categories: 
  - Java
---

下图为ThreadLocal的内部结构图
![](1.webp)
<!-- more -->
关于ThreadLocal的一些知识点，我主要是研读了这一篇博客，写得很详细，对比了一些其他的博客，其文中的知识点确信度也较高——[ThreadLocal-面试必问深度解析](https://www.jianshu.com/p/98b68c97df9b)

# 个人总结
概念什么的我就不赘述了，这里主要记录一下个人心得。
## 什么时候适用ThreadLocal？
* ThreadLocal的应用场合，我觉得最适合的是n线程对n实例（每个线程对应一个实例，不是1对n也不是n对1）的对象的访问，且这个对象很多地方都要用到。

## 使用ThreadLocal需要注意什么？
* 首先，`ThreadLocal 不是用来解决共享对象的多线程访问问题的`，一般情况下，通过ThreadLocal.set() 到线程中的对象是该线程自己使用的对象，其他线程是不需要访问的，也访问不到的。如果ThreadLocal.set()进去的东西本来就是多个线程共享的同一个对象，那么多个线程的ThreadLocal.get()取得的还是这个共享对象本身，还是`存在并发访问问题`。  
* 这里推荐最适合的使用场景是每个线程只声明一个ThreadLocal，清楚了解了ThreadLocal的数据结构之后，可以知道每个线程里的ThreadLocalMap解决Hash冲突的方式并非链表的方式，而是采用线性探测的方式Hash冲突的效率很低，如果有大量不同的ThreadLocal对象放入map中时发送冲突，或者发生二次冲突，则效率很低。
所以这里引出的良好建议是：`每个线程只创建一个ThreadLocal只存一个变量`，如果一个线程要保存多个变量，就需要创建多个ThreadLocal，多个ThreadLocal放入Map中时会极大的增加Hash冲突的可能。

## ThreadLocal引发的内存泄漏
![](2.png)
使用Threadlocal一定要关注一下内存泄漏问题，我的理解是，使用ThreadLocal会有有两个地方可能导致内存泄漏——
* 一是ThreadLocal对象无法回收引发的内存泄漏，这里ThreadLocal的作者考虑到这一点，将ThreadLocalMap中的Entry对象的key设置为指向ThreadLocal对象的弱引用，只要我们能确保当前线程无需使用ThreadLocal时能够解除对ThreadLocal对象的强引用即可（建议手动将Threadlocal对象的轻引用指向null），在下一次gc时JVM会自动回收只存在一个弱引用的ThreadLocal对象，第一个问题解决。
* 二是ThreadLocalMap存储的无用entry无法回收引发的内存泄漏。第二个问题，需要使用者显示调用ThreadLocal.remove()方法，解除ThreadLocalMap对Entry的强引用，如此无用entry就会被正常回收了。