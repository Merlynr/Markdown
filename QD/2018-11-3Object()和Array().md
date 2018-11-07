---
title: 2018-11-3Object()和Array()
tags: js,QD
grammar_cjkRuby: true
---

==数组就是特殊的对象，即有序的对象 #ffc107==
**粗劣的理解**
对象类似于人体由众多相关部分组成，数据结构｛key:value｝,在目前的数据处理中，对于对象的操作，大多体现在对数组的操作，类似于Java的相关数组；而数组，即由相同属性的元素，数组，对象。。，组成的集合。
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541238054549.png)



# 区别对象和数组
1. typeof ==不可用 #f44336==
图片供上：==typeof不能区分数组和对象的种类，都认为是object== 
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541305911435.png)

2. Array的自带function ==可用 #ffeb3b==
**判断数组**
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541306297056.png)

3. Object对象自定义类型 ==最方便进行判断数据类型 #ffc107==
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541324490016.png)

4. instanceof运算符进行判定 ==建议双重使用==
由于数组和对象的typeof分别是[object array][object object],所以不能识别是不是对象，只能识别是不是数组
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541569480332.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541569467617.png)

5. isPrototypeOf()
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541610694895.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541610198073.png)

6. 利用构造函数constructor
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541610629643.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541610644338.png)

### ==类型的了解 #f44336==
[object] Window 对象表示浏览器中打开的窗口。
[object Object]自定义对象
[object Array]自定义数组

![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541326655958.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541326708159.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541326727710.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541326751053.png)
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541326760679.png)

==直接定义一个字符串和new String的区别 #ff9800==：最基本就是新建一个string，另一个是新建一个object，可以使用typeof()测试出来，用对象的方法Object.prototype.toString.call().返回值都为[Object String]
使用__proto__检查构建函数一样
![使用__proto__检查构建函数一样](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541327517554.png)
 初步认为是使用new String来新建字符串，相当于调用一个方法来创建，即返回值为一个对象。
 
.==isPrototypeOf()检查机制在原型链中的延生#ff5722==
![enter description here](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1541610349622.png)