---
title: 2018-12-23logistic regression
tags: mfunction
grammar_cjkRuby: true
---

[sigmoid函数](https://www.zhihu.com/question/24259872)（s型函数）：
神经网络的激活函数，用途引入<font color='green'>非线性</font>。
优点:输出范围有限（0,1），数据在传递过程中不容易发散。易于求导。求导y=sigmoid(x), y'=y(1-y)；容易对结果进行匹配
缺点：饱和的时候梯度太小。

cost function 代价函数：
任何能够衡量模型预测出来的值 h(\theta)  与真实值 y 之间的差异的函数都可以叫做代价函数 C(\theta)