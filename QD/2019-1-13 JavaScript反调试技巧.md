---
title: 2019-1-13 JavaScript反调试技巧
tags: js
grammar_cjkRuby: true
---
[引用](https://www.freebuf.com/articles/system/163579.html)
<font color='red'>目的：</font>给代码主动调试增加困难

<font color='green'>思路：</font>
1.   检测未知的执行环境（我们的代码只想在浏览器中被执行）；
2.   检测调试工具（例如DevTools）；
3.   代码完整性控制；
4.   流完整性控制；
5.   反模拟；
即程序运行时进行检测，当运行状态**不正常**，运行流程发生改变，跳转到伪造的代码块，并**隐藏**正在的代码块
<font color='yellow'>方法：</font>
## 函数重定义
*这是一种最基本也是最常用的代码反调试技术了。在JavaScript中，我们可以对用于收集信息的函数进行重定义。比如说，console.log()函数可以用来收集函数和变量等信息，并将其显示在控制台中。如果我们重新定义了这个函数，我们就可以修改它的行为，并隐藏特定信息或显示伪造的信息。*

### <font color='green'>更改调试函数console.log()的作用</font> ###
![重新构建console.log()函数1](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1547314125279.png)

![重新构建console.log()函数2](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1547314228299.png)

![重新构建console.log()函数3](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1547314219438.png)

### <font color='green'>控制代码的执行方式</font> ###

```
console.log("Normalfunction");
//First we save a reference to the original console.log function
var original = window['console']['log'];
//Next we create our fake function
//Basicly we check the argument and if match we call original function with otherparam.
// If there is no match pass the argument to the original function
var fake = function(argument) {
    if (argument === "Ka0labs") {
        original("Spoofed!");
    } else {
        original(argument);
    }
}
// We redefine now console.log as our fake function
window['console']['log']= fake;
//Then we call console.log with any argument
console.log("Thisis unaltered");
//Now we should see other text in console different to "Ka0labs"
console.log("Ka0labs");
//Aaaand everything still OK
console.log("Byebye!");
```

![伪造信息](https://www.github.com/Merlynr/Markdown/raw/noteImg/小书匠/1547314608948.png)

## 断点
### <font color='green'>重复调用debugger命令来终止脚本运行</font> ###
<font color='red'>目的：</font>就是让那些想要调试你代码的人感到厌烦，当运行某些调试的方式的时候，脚本弹出窗口询问是否debugger

```
setTimeout(function(){while (true) {eval("debugger")})
```
## 时间差异

### <font color='green'>脚本在调试工具(DevTools)中运行的时间比在正常程序中明显长</font> ###
<font color='red'>目的：</font>可以通过测量代码中两个设置点之间的运行时间，然后用这个值作为参考，如果运行时间超过这个值，说明脚本当前在调试器中运行。

==模拟函数==
```
set Interval(function(){
//获取脚本运行开始时时间
var startTime = performance.now(), check,diff;
  for (check = 0; check < 1000; check++){
    console.log(check);
    console.clear();
  }
  diff = performance.now() - startTime;
  if (diff > 200){
    alert("Debugger detected!");
  }
},500);
```

## DevTools(调试工具)检测
### <font color='green'>通过检查dome元素是否被调用来判断是否调试</font> ###

```
let div = document.createElement('div');
let loop = setInterval(() => {
    console.log(div);
    console.clear();
});
Object.defineProperty(div,"id", {get: () => {
    clearInterval(loop);
    alert("Dev Tools detected!");
}});
```
***理解：***dome元素渲染到浏览器的时候，浏览器获得元素的id！当浏览器通过控制台进行调试的时候，这个该demo的getter（）方法会被调用!所以通过检查该方法是否被调用来判断是否被调试！【类似很多可以检测很多函数】

## 隐式流完整性控制

1. containter页面获取文件信息，不用route来传值
2. 重新构建service，将select写入
2. 将评论内容直接保存到state中
2. 修改页面样式控制器，不需要刷新，直接将获取到的值push上去
3. 咨询后端对于文件状态审核是否支持批量操作
4. 咨询后端对于评论内容字数的控制
5. 控制头像
