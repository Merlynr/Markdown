---
title: 2019-1-31不满意的半个小时post&post
tags: 新建,模板,小书匠
grammar_cjkRuby: true
---
### 题记
<font color="#f1403c">今日，无所事事，所以想起了一个感觉自己懂的概念，但是又不是能够给别人讲懂的。【别人 都不懂，那就是你不行】
</font>
<font color='green'>我以前没有很详细查过两个的区别，只是依稀的记得老师概述过，自己只是理解，post比get安全性更好，post传输的数据是被隐藏的，还有理解这两个语义，get是用来从服务器获取信息的，而post更为体现在交互性，当用户需要从服务器获取一些私人信息的时候，那么post的作用体现出来啦，密码啊，令牌这些你当然不希望别人一眼瞅出来哇！当然get也可以向服务器传输东西，但是给我感觉一般都是一些向服务器传一写过滤标准，然后在获取指定信息！</font>
<font color="#f1403c">赶紧google一下，发现了一个骇人听闻的文章，我还以为找到一个宝贝了！！！[jia宝贝](https://mp.weixin.qq.com/s?__biz=MzI3NzIzMzg3Mw==&mid=100000054&idx=1&sn=71f6c214f3833d9ca20b9f7dcd9d33e4#rd)，当然以我的智慧是无法来看出它是假的，不过我从中也学到了一些对于自己的有用的！</font>

![<font color='yellow'>假宝贝</font>](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548910435890.png)

![ 来自菜鸟的解读](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548911098029.png)
<font color="#f1403c">
蒽，还不错，模糊的概念分了个类，有道理！
</font>

### 解密
<font color='green'>首先感谢一下来自知乎[杨光](https://www.zhihu.com/question/28586791),他做了一个整合！！！</font>
<font color="#f1403c">
他的这篇文章，让我了解到我的TCP/IP，计算机网络，计算机组成原理，计算机操作系统白学了！阿里嘎多！
[99%的人都理解错了HTTP中GET与POST的区别=>jia宝贝](https://mp.weixin.qq.com/s?__biz=MzI3NzIzMzg3Mw==&mid=100000054&idx=1&sn=71f6c214f3833d9ca20b9f7dcd9d33e4#rd)这篇文章中提到的get和post都是tcp链接，我竟然当时没有读出异样。然后作者讲的get和post一样，什么区别get传一个TCP数据包，post传两个；还有直接将ajjax请求给引入进来讲了一通，我就被他折服啦，感觉自己好丢人。

![HTTP的底层是TCP/IP。所以GET和POST的底层也是TCP/IP，也就是说，GET/POST都是TCP链接](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548911785471.png)

![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548912438700.png)

![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548912417518.png)
</font>

多谢[知乎laike](https://zhuanlan.zhihu.com/p/25028045)帮我提出这个问题。
<font color='#f1403c'>回到杨光先生的文章中，他又讲到语义和语法，在最后扔了一个栗子出来，我当时只是一扫而过，觉得他的文章没有核心理解思路，当时当我写笔记的时候，又仔细看了一边他从[RFC7231](https://tools.ietf.org/html/rfc7231)中查到的区别，多谢！懂了！
</font>

![HTTP方法的几个性质](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548913144584.png)

![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1548913175609.png)
**我的理解**：get那些被菜鸟总结出来与post不一样的地方，正是由于它所具备了safe，idempotent，cacheable这些性质所决定的，而post没有这些性质也是它能够被用于做登陆验证，表单传输等一些安全系数较高的原因！这也是对于这两个方法适用于不同场合的原因！



