---
title: 适配大部分分辨率的网页编写注意事项
tags: QD, note
grammar_mindmap: true
---

## 流式布局

 1. 网页布局
避免使用使用固定布局，将网页设计为百分比布局
==目标元素宽度÷上下文元素宽度=百分比宽度 #ff5722==
**HTML**：横向使用块状元素【float】=》{*避免在网页变化过程中导致内容的不连贯*}，纵向使用行状元素=》{*页面整体瀑布式渲染，避免互相影响*}【保证功能模块的完整性】
*viewport是网页默认的宽度和高度，上面这行代码的意思是，网页宽度默认等于屏幕宽度（width=device-width），原始缩放比例（initial-scale=1）为1.0，即网页初始大小占屏幕面积的100%。*

``` <meta name="viewport" content="width=device-width, initial-scale=1" />
```

**CSS**：页面宽度谨遵方程式，小数部分尽量7位，基本单位才用em；max-width可以有效避免弹性图片在页面中放大过程中导致页面瘫痪
**JavaScript**：
通过获取当前显示器的分辨率进行调试`<script type="text/javascript">document.cookie='resolution='+Math.maxscreen.width,
screen.height)+'; path=/';</script>`（1）为不同的屏幕尺寸提供不同的图片【nope】（2）通过获取当前屏幕的初始值来限定网页的基本样式，再通过百分比来实现网页的自适应