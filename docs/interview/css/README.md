# css面试题

## 水平垂直居中

> 父元素：display:flex;子元素：margin:aoto;

<div style="display:flex;width:100px;height:100px;background-color:red">
  <div style="margin:auto;width:50px;height:50px;background-color:blue"></div>
</div>

```html
<div style="display:flex;width:100px;height:100px;background-color:red">
  <div style="margin:auto;width:50px;height:50px;background-color:blue"></div>
</div>
```

> 父元素flex布局，主轴和交叉轴居中：display:flex;align-items:center;justify-content:center;

<div style="display:flex;align-items:center;justify-content:center;width:100px;height:100px;background-color:red">
  <div style="width:50px;height:50px;background-color:blue"></div>
</div>

```html
<div style="display:flex;align-items:center;justify-content:center;width:100px;height:100px;background-color:red">
  <div style="width:50px;height:50px;background-color:blue"></div>
</div>
```

> 子元素定位：position:absolute;top:50%;left:50%;transform: translate(-50%, -50%);

<div style="position:relative;width:100px;height:100px;background-color:red">
  <div style="position:absolute;top:50%;left:50%;transform: translate(-50%, -50%);width:50px;height:50px;background-color:blue"></div>
</div>

```html
<div style="position:relative;width:100px;height:100px;background-color:red">
  <div style="position:absolute;top:50%;left:50%;transform: translate(-50%, -50%);width:50px;height:50px;background-color:blue"></div>
</div>
```

---

## 左中右布局

> 使用浮动布局**先加载中间部分**
<div class="float-container">
  <div class="float-m"></div>
  <div class="float-l"></div>
  <div class="float-r"></div>
</div>

```html
<div class="float-container">
  <div class="float-m"></div>
  <div class="float-l"></div>
  <div class="float-r"></div>
</div>
```

```css
  .float-container {
    width: 100%;
  }

  .float-container::after {
    content: '';
    display: block;
    clear: both;
  }

  .float-container>div {
    float: left;
    width: 100px;
    height: 50px;
    background-color: #ccc;
  }

  .float-container .float-l {
    margin-left: -100%;
  }

  .float-container .float-m {
    background-color: red;
    width: 100%;
  }

  .float-container .float-r {
    margin-left: -100px;
  }

```

> 使用flex布局**先加载中间部分**
<div class="flex-container">
  <div class="flex-m"></div>
  <div class="flex-l"></div>
  <div class="flex-r"></div>
</div>

```html
<div class="flex-container">
  <div class="flex-m"></div>
  <div class="flex-l"></div>
  <div class="flex-r"></div>
</div>
```

```css
 /* 左中右布局：flex布局 */

  .flex-container {
    display: flex;
    height: 50px;
  }

  .flex-container .flex-l,
  .flex-container .flex-r
  {
    width: 100px;
    background-color: #ccc;
  }
  .flex-container .flex-r{
    order: 3;
  }
  .flex-container .flex-m{
    flex: 1;
    order: 2;
    background-color: red;
  }

```

---

## css盒模型

| 名称 |组成部分| 性质 |
| ----------- | -- |---|
| 标准盒模型 |4| 包含margin border padding content |
| IE盒模型|2| 包含margin content(border+padding+content)|
>盒子模型转换

```css

/* 标准盒模型 */
box-sizing:content-box;
/*  IE盒模型 */
box-sizing:border-box;

```

---

## css选择器、css属性继承

|选择器|语法|列子|说明
|---|---|---|---|
|通配 |*|
|id选择器|#|#app|
|类选择器|.|.classname|
|标签|html标签|div、span|
|后代选择器|中间空格|ul li|
|子元素选择器|>|ul >li|
|相邻选择器|+|ul li +li|ul下面li的相邻li,第一个li被排除
|属性选择器|html标签[href]||不常用

### **css哪些属性可以继承**

- 文字系列：font-size color line-height text-align

### **css哪些属性不可以继承**

- border padding margin

### **css优先级**

- !important>内联样式>id>class>标签>通配
- 优先级算法：相加
|名称|权重|
|---|---|
!important|无穷大|
|内联样式style|1000|
|id|100|
|class|10|
|标签&伪元素|1|
|通配&>&+|0|

---

## css画三角形

### **用边框border画**

<div style="display:flex;align-items:center;width:100px;justify-content:space-between;">
  <div style="border:10px solid transparent;border-bottom-color:#ccc;"></div>
  <div style="border:10px solid transparent;border-top-color:#ccc;"></div>
  <div style="border:10px solid transparent;border-right-color:#ccc;"></div>
  <div style="border:10px solid transparent;border-left-color:#ccc;"></div>
</div>

```html

<div style="display:flex;align-items:center;width:100px;justify-content:space-between;">
  <div style="border:10px solid transparent;border-bottom-color:#ccc;"></div>
  <div style="border:10px solid transparent;border-top-color:#ccc;"></div>
  <div style="border:10px solid transparent;border-right-color:#ccc;"></div>
  <div style="border:10px solid transparent;border-left-color:#ccc;"></div>
</div>
```

---

## BFC

> [!NOTE]
>
> - BFC : **块级格式化上下文** block formatting context
> - BFC原则 : 如果一个元素具有了BFC，那么其**子元素无论如何变化**都不会影响其他元素
> - 如何触发BFC
>   - float为**none**
>   - overflow的值非**visible**
>   - display的值为**inline-block table-cell...**
>   - position的值为**absolute、fixed**

### **清除浮动的方法**

- 触发BFC
- 多创建一个盒子，添加样式 clear:both;
- after方式

```css
ul:after,ul:before{
    content:'';
    display:block;
    clear:both;
}
```

---

## display:none;和visibility:hidden的区别

||display:none|visibility:hidden|
|--|--|--|
|dom节点从文档中移除|是|否|
|是否产生回流|是|否|
|是否产生重绘|是|是|

> [!NOTE]
>
> - 回流是dom节点树（包括位置）产生变化、重绘是根据dom节点和样式渲染图像
> - 产生回流一定会产生重绘
> - 产生回流的场景： 定位发生变化、display显示隐藏
> - 产生重绘的场景： 样式变化、换皮肤
>
---

## 定位

|定位|参照物|文档流|说明|注意事项|
|---|---|---|---|---|
|static|不定位||默认||
|fixed|浏览器窗口|脱离|固定定位||
|relative|自身|不脱离|定位后以前的位置还在|有left则right不起效，有top则bottom不起效|
|absolute|父元素|脱离|定位后以前的位置不在|top left bottom right 都能生效|
---

## css重置

> normalize **让不同浏览器样式一样**

```html
<link href="https://cdn.bootcdn.net/ajax/libs/normalize/8.0.1/normalize.css" rel="stylesheet">
```

> reset.css **重置样式**

```css
/*! minireset.css v0.0.6 | MIT License | github.com/jgthms/minireset.css */html,body,p,ol,ul,li,dl,dt,dd,blockquote,figure,fieldset,legend,textarea,pre,iframe,hr,h1,h2,h3,h4,h5,h6{margin:0;padding:0}h1,h2,h3,h4,h5,h6{font-size:100%;font-weight:normal}ul{list-style:none}button,input,select{margin:0}html{box-sizing:border-box}*,*::before,*::after{box-sizing:inherit}img,video{height:auto;max-width:100%}iframe{border:0}table{border-collapse:collapse;border-spacing:0}td,th{padding:0}

```

## 常见问题

> height 和line-height的区别

- **height是元素的高度、line-height是行高**
- **line-height是行高,如果换行盒子的高度会增大**

> padding 和margin的区别

### **padding作用于元素内部，会增加宽和高；margin作用于元素外部，不会增加元素的宽和高**

> 百分比和vw vh的区别

### **百分比会继承父元素的宽高，vw vh只和设备的宽高有关**

> 实现小字体

<div>
  <div style="font-size:12px">12px字体</div>
  <div style="display: inline-block;font-size:12px;transform:scale(0.8);-webkit-transform:scale(0.8)">小字体</div>
</div>

```html
<div>
  <div style="font-size:12px">12px字体</div>
  <div style="display: inline-block;font-size:12px;transform:scale(0.8);-webkit-transform:scale(0.8)">小字体</div>
</div>
```

---

> opacity和rgba的区别

- 相同点：都能实现透明 取值0-1
- opacity子元素会继承、rgba不会
