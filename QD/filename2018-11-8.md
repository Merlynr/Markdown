---
title: 未完成【事件循环机制】【js作用域】2018-11-8Js [定义变量区别](https://www.jianshu.com/p/4e9cd99ecbf5)
tags: js,QD
grammar_cjkRuby: true
---

## var的使用注意事项
1. 在JS函数中的var声明，作用域为函数体的全部
	当在for循环语句借宿运行后，for语句内定义的变量在语句外也可以进行使用
2. 循环内变量过度共享
i的数值遍历可以通过let定义来处理，但是无法多次单次多步调用setTimeout()
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541644962786.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541644928893.png)
*==尝试解决！！！失败 #f44336==*
- [ ] 猜想：认为与事件循环机制有关系，待处理
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541645056479.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541645070574.png)

## let的使用注意事项
	1.let声明的变量拥有块级作用域。
即变量作业范围在声明函数内部起作用，函数外部则无效。
- [ ] *==外层块和外层函数不理解 #f44336==*
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541646733123.png)
2. let声明的全局变量不是全局对象的属性。
不知道有啥用、、、、、、！
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541650156173.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541650136160.png)
3. 在同一个作用域内，let不能重复定义同一个变量
4. 形如for (let x...)的循环在每次迭代时都为x创建新的绑定。
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541659075539.png)

## const 的使用注意事项
[引用](https://www.jianshu.com/p/bbbe7ab62e36)
1. 必须给定义变量初始化
2. 无法给定义好的变量重新赋值【var，let，const】
3. 只在块级作用域起作用和let一样
4. 不可重复定义相同名称的变量
5. ==传址赋值 #ff9800==
用const声明对象的常量的时候，就是传址赋值。
==传址 #ff9800==：在赋值过程中，变量实际上存储的是数据的地址（对数据的引用），而不是原始数据或者数据的拷贝。

[loading](https://www.jianshu.com/p/4e9cd99ecbf5)

### for语句使用var和let定义i的区别
[链接](https://segmentfault.com/a/1190000010913782)

### let和var的解构特性

### use strict
