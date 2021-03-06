---
title: 计算密集型 vs. IO密集型
date: 2017-11-16 21:56:44
tags: [基础]
---

> 计算密集型任务

计算密集型任务主要消耗CPU资源，需要进行大量的计算，如计算圆周率或对视频进行高清的解码等，全靠CPU的运算能力。
这种任务虽然可以利用多任务去完成，但是任务越多，花在任务切换上的时间就会越多，那么CPU的执行效率就会越低，
所以，要高效的利用CPU，计算密集型任务同时进行的数量应当等于CPU的核心数，尽量减少CPU在任务间的切换时间。

> IO密集型任务

一般涉及到网络、磁盘IO的任务都是IO密集型任务，这类任务的特点就是CPU消耗很少，任务的大部分时间都花在等待IO操作的完成。
由于IO的速度远远低于CPU和内存的速度，所以IO密集型任务的数量越多，CPU的效率就会越高，但是也会有一定的限度。
常见的大部分任务都是IO密集型任务，比如Web应用。

IO密集型任务执行期间，99%的时间都花在IO上，花在CPU上的时间很少，因此，用运行速度极快的C语言替换Python这样运行速度极低的脚本语言，
也完全无法提升运行效率。对于IO密集型任务，最合适的语言就是开发效率最高，代码量最少的语言，脚本语言是首选，C语言最差。

> 总结

计算密集型程序适合C语言多线程
IO密集型程序适合脚本语言开发的多线程
