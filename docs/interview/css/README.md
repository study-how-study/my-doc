
## 水平垂直居中

> 父元素：display:flex;子元素：margin:aoto;

<div style="display:flex;width:100px;height:100px;background-color:red">
  <div style="margin:auto;width:50px;height:50px;background-color:blue"></div>
</div>

```
<div style="display:flex;width:100px;height:100px;background-color:red">
  <div style="margin:auto;width:50px;height:50px;background-color:blue"></div>
</div>
```

> 父元素flex布局，主轴和交叉轴居中：display:flex;align-items:center;justify-content:center;

<div style="display:flex;align-items:center;justify-content:center;width:100px;height:100px;background-color:red">
  <div style="width:50px;height:50px;background-color:blue"></div>
</div>

```
<div style="display:flex;align-items:center;justify-content:center;width:100px;height:100px;background-color:red">
  <div style="width:50px;height:50px;background-color:blue"></div>
</div>
```

> 子元素定位：position:absolute;top:50%;left:50%;transform: translate(-50%, -50%);

<div style="position:relative;width:100px;height:100px;background-color:red">
  <div style="position:absolute;top:50%;left:50%;transform: translate(-50%, -50%);width:50px;height:50px;background-color:blue"></div>
</div>

```
<div style="position:relative;width:100px;height:100px;background-color:red">
  <div style="position:absolute;top:50%;left:50%;transform: translate(-50%, -50%);width:50px;height:50px;background-color:blue"></div>
</div>
```

## 常见问题

> padding 和margin的区别

**padding作用于元素内部，会增加宽和高；margin作用于元素外部，不会增加元素的宽和高**

> 百分比和vw vh的区别

**百分比会继承父元素的宽高，vw vh只和设备的宽高有关**

> 小字体

<div>
  <div style="font-size:12px">12px字体</div>
  <div style="display: inline-block;font-size:12px;transform:scale(0.8);-webkit-transform:scale(0.8)">小字体</div>
</div>

```
<div>
  <div style="font-size:12px">12px字体</div>
  <div style="display: inline-block;font-size:12px;transform:scale(0.8);-webkit-transform:scale(0.8)">小字体</div>
</div>
```
---