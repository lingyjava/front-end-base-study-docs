# 2·Flex布局

<!-- TOC -->
* [2·Flex布局](#2flex布局)
  * [简介](#简介)
  * [模型构成](#模型构成)
  * [主轴对齐方式](#主轴对齐方式)
  * [侧轴对齐方式](#侧轴对齐方式)
  * [尺寸特点](#尺寸特点)
  * [弹性伸缩比](#弹性伸缩比)
  * [修改主轴方向](#修改主轴方向)
  * [弹性盒子换行](#弹性盒子换行)
  * [调整行对齐方式](#调整行对齐方式)
<!-- TOC -->

## 简介
Flex布局/弹性布局：
- 是一种浏览器提倡的布局模型。
- 布局网页更简单、灵活。
- 避免浮动脱标的问题。

## 模型构成
基于Flex精准灵活控制块级盒子的布局方式，避免浮动布局中脱离文档流现象发生。Flex布局非常适合结构话布局。  

设置方式：父元素添加属性display: flex ，子元素就可以自动的挤压或拉伸。

组成部分：
- 弹性容器
- 弹性盒子
- 主轴
- 侧轴 / 交叉轴

视觉效果：
- 子级一行排列 / 水平排列。
- 默认主轴在水平方向，弹性盒子都是沿着主轴排列。

```css
div {
    display: flex;
}
```

## 主轴对齐方式
在Flex布局模型中，通过调节主轴或侧轴的对齐方式来设置盒子之间的间距。

修改主轴对齐方式属性：justify-content  
属性值：
- flex-start：默认值，起点开始依次排列。
- flex-end：终点开始依次排列。
- center：沿主轴居中排列。
- space-around：弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子两侧。
- space-between：弹性盒子沿主轴均匀排列，空白间距均分在相邻盒子之间。
- space-evenly：弹性盒子沿主轴均匀排列，弹性盒子与容器之间间距相等。

## 侧轴对齐方式
修改侧轴(水平方向)对齐方式属性：
- align-items：（添加到弹性容器）。
- align-self：控制某个弹性盒子在侧轴的对齐方式（添加到弹性盒子）。

属性值：
- flex-start：默认值，起点开始依次排列。
- flex-end：终点开始依次排列。
- center：沿侧轴居中排列。
- stretch：默认值，弹性盒子沿着主轴线被拉伸至铺满容器。

## 尺寸特点
- 当align-items为默认值stretch时，此时盒子下的所有子盒子的高度为100%， 但如果子盒子指定了align-self属性与父盒子不同的值，这个子盒子高度将塌陷，高度由内容撑开。
- 当不给弹性盒子设置宽度时，宽度由内容撑开。

## 弹性伸缩比
修改弹性盒子的伸缩比。设置弹性盒子占用父级剩余尺寸的份数。份数计算时只占用父盒子剩余尺寸。

属性名：flex  
属性值：整数数值

```css
.box {
  display: flex;
}

.box div:nth-child(1){
  flex: 3;
}
```

## 修改主轴方向
Flex布局模型中，弹性盒子默认沿着水平方向排列。主轴默认是水平方向，侧轴默认是垂直方向。   
使用flex-direction属性修改主轴方向，改变元素排列方向。主轴方向修改后，侧轴方向也随着改变。  

属性名：flex-direction  

属性值：
- row：行，水平（默认值）。
- column：列，垂直。
- row-reverse：行，从右向左。
- column-reverse：列，从下向上。

```css
div {
  display: flex;
  flex-direction: column;
}
```

## 弹性盒子换行
弹性盒子的表现是宽高可以自由伸缩。想要弹性盒子分成多行排列，需要使用弹性盒子换行。  
使用flex-wrap属性设置允许弹性盒子根据宽高自动换行排列。  

属性名：flex-wrap  
属性值：
- nowrap：默认值，不换行。
- wrap：自动换行。

```css
div {
  display: flex;
  flex-wrap: wrap;
}
```

## 调整行对齐方式
弹性盒子换行后通过调整行对齐方式设置行之间的间距。  

属性名：align-content  
属性值：与justify-content属性大致相同。

```css
div {
  display: flex;
  flex-wrap: wrap;
  align-content: space-between;
}
```