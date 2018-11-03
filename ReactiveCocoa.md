# 函数式编程 - ReactiveCocoa+RXSwift+MVVM

## 引入

学习函数响应式编程已经接近两个月的时间。说实话坚持下来实在不易。两个月的时间看过近150篇博文，算下来啃下来一本千页的技术书籍也差不多。不过随着知识面的拓广，学习起来也更加顺利。本篇文章主要整理下自己收集的学习路线。其中包括了函数式编程的思想，ReactiveCocoa2.x(主要是Objective-C部分的函数响应式编程框架)，ReactiveCocoa4.x(扩充了Swift部分的支持)，RXSwift(ReactiveX系列)，加上函数式编程对MVVM架构的帮助和影响。

面向对象编程是一个被大众易于接受的方式，也就意味着更容易协同工作。函式响应式编程虽然不是一个新的话题，但是引入iOS项目实际开发还是要抱谨慎态度，毕竟学习函数式编程的路线还是比较陡峭，这就意味者在团队开发中，需要斟酌如何引用，如何培养新手，如何控制对框架的不良使用在项目中蔓延。

MVC是一个非常成熟的架构，在业务开始复杂的时候，合理的将网络请求，数据持久化等相关与控制器耦合不严重的公共抽取出来，足够满足日常开发需求。 对MVVM的理解的差异性也会写出让团队成员写出截然不同的风格。

## 知识必备

需要你对Objective-C，block有比较清晰的了解,由于后面部分代码是由Swift实现，建议你掌握Swift，(由于Swift的特性，对于函数式编程更容易实现，也更好理解，毕竟你看写博文的作者几乎每个都掌握的，所以去学习吧。)，如果你用过Swift的高阶函数，map，FlatMap，reduce，Filter等，会更加容易理解。

## 思想的建立

这部份主要奠定自己的函数式思想的建立，对函数(闭包，block)作为一等公民有新的理解。这一部分可能学习的时间最久，需要的知识面也可能更广，也最容易让人放弃，因为你不知道你花了大把时间学习的是什么(jb玩意)。不过坚持下来，你将会更加理解函数式编程，在学习接下来的ReactiveCocoa和RXSwift的时候只是把思想代码化。

## 初始了解函数式编程的演变

- [从函数调用到函数式编程](https://link.jianshu.com?t=http://valiantcat.com/2016/06/03/%E4%BB%8E%E5%87%BD%E6%95%B0%E8%B0%83%E7%94%A8%E5%88%B0%E5%87%BD%E6%95%B0%E5%BC%8F%E7%BC%96%E7%A8%8B/)

## 简单认识如何实现链式编程

- [ReactiveCocoa](https://link.jianshu.com?t=http://nshipster.cn/reactivecocoa/)

来自Mattt Thompson发布在 [NShipster](https://link.jianshu.com?t=nshipster.com)让你对引入RAC这类FRP(Functional Reactive Programming)框架对编程范式的改变有个直观的印象。

- [ReactiveCocoa与Functional Reactive Programming](https://link.jianshu.com?t=http://limboy.me/tech/2013/06/19/frp-reactivecocoa.html)

来自蘑菇街的[limboy](https://link.jianshu.com?t=http://limboy.me/)解释下RAC和FRP的关系。

- [深入浅出－iOS Reactive Cocoa的常见用法](https://www.jianshu.com/p/e63261712172)

## 着手RAC

- [最快让你上手ReactiveCocoa之基础篇](https://www.jianshu.com/p/87ef6720a096)
- [最快让你上手ReactiveCocoa之进阶篇](https://www.jianshu.com/p/e10e5ca413b7)

在这里直接推荐了两篇使用的文章。貌似会比较突然，但是作者觉得，Talk  is cheap ，show me the code.(别装逼了，亮代码吧)   思想总归是要用代码来实现的，这部份内容偏实用，预计需要一周的时间才能掌握的差不多，可能你在学习的过程中，会遗忘，没关系，思想的建立是一步一步的，学习这些代码还是为了更好的建立思想(我也没指望你一遍掌握RAC)，至于代码这篇文章，反正你是要看好几遍的，第一次忘了就忘了。

- [Reactive Programming入门](https://link.jianshu.com?t=https://github.com/benjycui/introrx-chinese-edition)

之前的文章都是 functional Programming，和reactive programming，这里偶然看到一篇响应式编程思想入门，强烈推荐。

- [iOS Reactive Cocoa使用浅析](https://www.jianshu.com/p/25922584bc43)
- [ReactiveCocoa 讨论会](https://link.jianshu.com?t=http://blog.devtang.com/2016/01/03/reactive-cocoa-discussion/index.html)

这篇文章中讲到了RAC自带的debug插件，在学习RAC过程中的实践，以及一些技术博文链接。

------

在学习过程中我们可能经常会听见一些比较函数式风格的名词，比如monad，functor等，学到这里我找到了另外比较好的资料。

1. [函数式 Swift](https://link.jianshu.com?t=https://www.objccn.io/products/functional-swift/)
2. [Functor、Applicative 和 Monad](https://link.jianshu.com?t=http://leichunfeng.github.io/blog/2015/11/08/functor-applicative-and-monad)
3. [Swift Functors, Applicatives, and Monads in Pictures](https://link.jianshu.com?t=http://www.mokacoding.com/)英文版
4. [Functors, Applicatives, And Monads In Pictures](https://link.jianshu.com?t=http://adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html)英文版

第一本书籍可能花费的时间很长，不过这本书也是最有深度的，可以从中学到更多函数式的思想。

## ReactiveCocoa2.x

非常不错的RAC入门教程

1. [ReactiveCocoa入门教程——第一部分](https://link.jianshu.com?t=http://benbeng.leanote.com/post/ReactiveCocoaTutorial-part1)对应的[英文版](https://link.jianshu.com?t=https://www.raywenderlich.com/62699/reactivecocoa-tutorial-pt1) 
2. [ReactiveCocoa入门教程——第二部分
   ](https://link.jianshu.com?t=http://benbeng.leanote.com/post/ReactiveCocoaTutorial-part2)对应的[英文版](https://link.jianshu.com?t=http://www.raywenderlich.com/62796/reactivecocoa-tutorial-pt2) 

------

来自sunnyxx的博文。

1. [Reactive Cocoa Tutorial [1\] = 神奇的Macros](https://link.jianshu.com?t=http://blog.sunnyxx.com/2014/03/06/rac_1_macros/)
2. [Reactive Cocoa Tutorial [2\] = 百变RACStream](https://link.jianshu.com?t=http://blog.sunnyxx.com/2014/03/06/rac_2_racstream/)
3. [Reactive Cocoa Tutorial [3\] = RACSignal的巧克力工厂](https://link.jianshu.com?t=http://blog.sunnyxx.com/2014/03/06/rac_3_racsignal/)
4. [Reactive Cocoa Tutorial [4\] = 只取所需的Filters](https://link.jianshu.com?t=http://blog.sunnyxx.com/2014/04/19/rac_4_filters/)

------

学了这么多来一篇RAC结构分享的文章

- [ReactiveCocoa v2.5 源码解析之架构总览](https://link.jianshu.com?t=http://leichunfeng.github.io/blog/2015/12/25/reactivecocoa-v2-dot-5-yuan-ma-jie-xi-zhi-jia-gou-zong-lan)

------

用了这么久的RAC，你可能不止一次听到冷热信号，也可能没有意识到有些什么是不对的，这里给出来自美团的对冷热信号的分析。

1. [RACSignal的Subscription深入分析 - 美团点评技术团队](https://link.jianshu.com?t=http://tech.meituan.com/RACSignalSubscription.html)
2. [细说ReactiveCocoa的冷信号与热信号（一）](https://link.jianshu.com?t=http://tech.meituan.com/talk-about-reactivecocoas-cold-signal-and-hot-signal-part-1.html)
3. [细说ReactiveCocoa的冷信号与热信号（二）：为什么要区分冷热信号](https://link.jianshu.com?t=http://tech.meituan.com/talk-about-reactivecocoas-cold-signal-and-hot-signal-part-2.html)
4. [细说ReactiveCocoa的冷信号与热信号（三）：怎么处理冷信号与热信号](https://link.jianshu.com?t=http://tech.meituan.com/talk-about-reactivecocoas-cold-signal-and-hot-signal-part-3.html)

------

美团博文最后给出了一个冷热信号可以转换的方法，但是没有讲清楚，这里有篇外国博文作为补充。

- [Comparing replay, replayLast, and replayLazily](https://link.jianshu.com?t=https://spin.atomicobject.com/2014/06/29/replay-replaylast-replaylazily/)

------

这里补充一篇对RAC的概述

- [说说ReactiveCocoa 2](https://link.jianshu.com?t=http://limboy.me/tech/2013/12/27/reactivecocoa-2.html)

------

RAC项目实战

1. [ReactiveCocoa2实战](https://link.jianshu.com?t=http://limboy.me/tech/2014/06/06/deep-into-reactivecocoa2.html)
2. [这样好用的ReactiveCocoa，根本停不下来](https://link.jianshu.com?t=http://ios.jobbole.com/82356/)
3. [iOS开发下的函数响应式编程](https://link.jianshu.com?t=http://williamzang.com/blog/2016/06/27/ios-kai-fa-xia-de-han-shu-xiang-ying-shi-bian-cheng/)

------

如果你认认真真的学习到了这里，想必以及有了不错的进步，接下来我们可以看下RAC的源码实现了，看下这个庞然大物是如何实现这些神奇的功能的。

1. [RAC核心元素与信号流](https://www.jianshu.com/p/d262f2c55fbe)
2. [剖析@weakify 和 @strongify](https://link.jianshu.com?t=http://ios.jobbole.com/85019/)
3. [ReactiveCocoa源码阅读之前序](https://www.jianshu.com/p/baeebca1f6f4)
4. [ReactiveCocoa源码阅读之RACSignal(一)](https://www.jianshu.com/p/d5e4dc7e592e)
5. [ReactiveCocoa源码阅读之RACSignal(二)](https://www.jianshu.com/p/bcdea71ba824)
6. [ReactiveCocoa源码阅读之bind函数](https://www.jianshu.com/p/7c1ddba2b3a4)
7. [ReactiveCocoa源码阅读之攻略flatten](https://www.jianshu.com/p/f939bf6afc93)
8. [ReactiveCocoa源码阅读之switchToLatest/combineLatestWith](https://www.jianshu.com/p/f3b00e90035d)
9. [ReactiveCocoa源码阅读之RACScheduler](https://www.jianshu.com/p/a151e5cb0aae)

## MVVM With ReactiveCocoa

这部份主要讲了RAC在MVVM中的表现，以及如何利用RAC在MVVM中做数据绑定这项核心操作。

1. [MVVM与ReactiveCocoa的运用(Part1)](https://www.jianshu.com/p/b2fe0920e3aa)
2. [MVVM Tutorial with ReactiveCocoa: Part 1/2](https://link.jianshu.com?t=https://www.raywenderlich.com/74106/mvvm-tutorial-with-reactivecocoa-part-1)
3. [MVVM与ReactiveCocoa的运用(Part2)](https://www.jianshu.com/p/b51344f4f3a3)
4. [MVVM Tutorial with ReactiveCocoa: Part 2/2](https://link.jianshu.com?t=https://www.raywenderlich.com/74131/mvvm-tutorial-with-reactivecocoa-part-2)
5. [MVVM With ReactiveCocoa](https://link.jianshu.com?t=http://leichunfeng.github.io/blog/2016/02/27/mvvm-with-reactivecocoa)

## ReactiveCocoa4.x

在学习这部份的时候发现没有合适的入门教程，所以就自己摸索着翻译了部分。可以参看

1. [ReactiveCocoa-Swift部分入门指南-Signal](https://link.jianshu.com?t=http://valiantcat.com/2016/07/21/ReactiveCocoa-Swift%E9%83%A8%E5%88%86%E5%85%A5%E9%97%A8%E6%8C%87%E5%8D%97-Signal/)
2. [ReactiveCocoa-Swift部分入门指南-SignalProducer](https://link.jianshu.com?t=http://valiantcat.com/2016/07/20/ReactiveCocoa-Swift%E9%83%A8%E5%88%86%E5%85%A5%E9%97%A8%E6%8C%87%E5%8D%97-SignalProducer/)

------

一份Reactive4文档翻译

1. [ReactiveCocoa 4 文档翻译目录](https://www.jianshu.com/p/fccba7be1ca1)

------

ReactiveCocoa4的详细讲解

1. [ReactiveCocoa 4 图解之一——事件（Event）
   ](https://www.jianshu.com/p/0ea216239efb)
2. [ReactiveCocoa 4 图解之二——监听器（Observer）
   ](https://www.jianshu.com/p/ba5247d713a9)
3. [ReactiveCocoa 4 图解之三——存根（Disposable)](https://www.jianshu.com/p/7a4a1d005aee)
4. [至于四作者并没给出，估计是挖的坑忘记填]()
5. [ReactiveCocoa 4 图解之五——信号（Signal)](https://www.jianshu.com/p/f0c945e5b2fe)
6. [ReactiveCocoa 4 图解之六——信号发生器（SignalProducer）](https://www.jianshu.com/p/617063a81136)

## RXSwift

使用自带教程入门

1. [RxSwift 入坑手册 Part0 - 基础概念](https://link.jianshu.com?t=http://blog.callmewhy.com/2015/09/21/rxswift-getting-started-0/)
2. [RxSwift 入坑手册 Part1 - 示例实战](https://link.jianshu.com?t=http://blog.callmewhy.com/2015/09/23/rxswift-getting-started-1/)

快速指南系列

1. [RxSwift快速指南(一)](https://www.jianshu.com/p/86df22e912e9)
2. [RxSwift快速指南(二)](https://www.jianshu.com/p/78309ae003c4)
3. [RxSwift快速指南(三)](https://www.jianshu.com/p/3bdb246881d4)
4. [RxSwift快速指南(四)](https://www.jianshu.com/p/401847dddfc5)

## 速查表

文末给出了我自己整理的RAC和RXSwift速查表，毕竟谁也不可能记得住那么多方法和小技巧的。

- [ReactiveCocoa和RXSwift速查表](https://link.jianshu.com?t=http://valiantcat.com/2016/07/22/ReactiveCocoa%E5%92%8CRXSwift%E9%80%9F%E6%9F%A5%E8%A1%A8/)

 

 

 



------

[<返回目录](https://weadar.github.io/index)

 

 