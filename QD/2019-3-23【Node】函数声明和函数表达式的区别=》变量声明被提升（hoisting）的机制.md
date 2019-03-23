---
title: 2019-3-23【Node】函数声明和函数表达式的区别=》变量声明被提升（hoisting）的机制 
tags: js,node
grammar_cjkRuby: true
---

# 声明提前

[声明变量](https://blog.csdn.net/qq673318522/article/details/50810650)

function(){}与var fun=function(){}的区别

![书写顺序](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1553337634581.png)

![声明顺序](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1553337644511.png)

函数内【声明提前】：

![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1553341605258.png)

![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1553341616153.png)


所有全局变量都是window或Global的属性

函数声明会被提到范围作用域的顶端

变量声明会被提到范围作用域的顶端

变量声明比函数声明优先级高，变量声明优于函数声明，如果两者同时存在，后被提升的函数声明会覆盖被提升的变量声明

变量赋值不会被提升，到执行行代码才开始赋值