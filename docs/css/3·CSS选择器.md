# 3·CSS选择器
如何选择选择到想要设置样式的标签？

## 目录
<!-- TOC -->
* [3·CSS选择器](#3css选择器)
  * [目录](#目录)
  * [标签选择器](#标签选择器)
  * [类选择器](#类选择器)
  * [id选择器](#id选择器)
  * [通配符选择器](#通配符选择器)
  * [后代选择器](#后代选择器)
  * [子代选择器](#子代选择器)
  * [并集选择器](#并集选择器)
  * [交集选择器](#交集选择器)
  * [伪类选择器](#伪类选择器)
  * [结构伪类选择器](#结构伪类选择器)
  * [伪元素](#伪元素)
  * [作用域](#作用域)
<!-- TOC -->

## 标签选择器
通过标签名找到页面中所有此类标签设置样式。
> 标签名 {css属性: 属性值;}
```css
/* 选中所有的p标签设置字体大小 */
p {
	font-size: 30px;
}
```

## 类选择器
通过类名，找到页面中所有带有这个类目的标签设置样式。 所有标签都有class属性，属性值为类名。  
类名由字母、数字、下划线和中划线组成，不能以数字和中划线开头。**一个标签可以同时有多个类名，类名之间用空格隔开。**
类名允许重复，所以类选择器可以同时选中多个标签。


> .类名 {css属性: 属性值;}
```css
/* 选中类名为one的标签, 颜色设置为蓝色 */
.one {
    color:blue;
}
```

## id选择器
通过id属性值，找到带有这个id的标签。所有标签都有id属性，id在一个页面中唯一不可重复。所以一个id选择器只能选择一个标签。  

规范的编码中id选择器最好只使用一次设置所有样式。

> #id属性值 {css属性名: 属性值; }

```css
#skyblue {
    color: skyblue;
}
```

## 通配符选择器
找到页面中所有的标签。极少情况下使用。
```css
/*设置所有标签颜色为蓝色*/
* {
    color: blue;
}
```

## 后代选择器
作用：根据HTML标签的嵌套关系，选择父元素后代中满足条件的元素。  
选择器可以是任何选择器（标签选择器、类选择器、id选择器）。  
后代包括所有后代（子代，孙子代、重孙子代）。  
> 选择器语法： 选择器1 选择器2 {css}
```css
/*选中div标签下的所有p标签*/
div p {
    
}
```

## 子代选择器
作用：根据标签嵌套关系，选择父元素子代中满足条件的元素。
> 选择器语法： 选择器1 > 选择器2 {css}
```css
/* 选中仅在一个div标签下的所有p标签 */
div>p {
    
}
```

## 并集选择器
作用：同时选择多组标签，设置相同的样式。并集选择器中的每组选择器之间用逗号分隔。每组选择器可以是基础选择器或复合选择器。
> 选择器语法： 选择器1 , 选择器2 {css}
```css
/* 选中center类 和 goods类的标签 和 p标签 */
.center ,
.goods , 
p {
    
}
```

## 交集选择器
选择同时满足所有选择器的标签。
> 选择器1选择器2 {css}
```css
/*选择 类名为goods 的 p标签 */
p.goods {
    
}
```

## 伪类选择器
hover伪类选择器，选中鼠标悬停在元素上的状态设置样式。伪类选择器选中的是元素的某种状态。任何标签都可以添加伪类。
> 选择器:hover {css}
```css
/*选中鼠标悬停在a标签上时的样式*/
a:hover {
    color: red;
    background-color: green;
}

div:hover {
    color: green;
}
```

## 结构伪类选择器
根据元素在HTML中的结构关系查找元素，可以减少对于HTML中类的依赖，常用于查找某父级选择器中的子元素。  

选择器：
- E:first-child {}：匹配父元素中第一个子元素，并且是E元素。
- E:last-child {}：匹配父元素中最后一个子元素，并且是E元素。
- E:nth-child(n) {}：匹配父元素中第n个子元素，并且是E元素。
- E:nth-last-child(n) {}：匹配父元素中倒数第n个子元素，并且是E元素。

n的取值方式：  
n可以为数值（0、1、2、3、4、...）  
n可以组成常见公式：
- 偶数：（2n、even）
- 奇数：（2n+1、2n-1、odd）
- 找到前5个：（-n+5）
- 找到从第5个往后：（n+5）

```css
li:first-child {}
li:last-child {}
li:nth-child(4n) {}
li:nth-last-child(-n+3) {}
```

## 伪元素
页面中的非主体内容可以使用伪元素。

区别：
- 元素：HTML标签。
- 伪元素：由CSS模拟出的标签效果。

种类：
- ::before：在父元素内容的最前添加一个伪元素。
- ::after：在父元素内容的最后添加一个伪元素。

使用注意：
1. 必须设置content属性才能生效。
2. 伪元素默认是行内元素。

```css
span::before {
  content: 'span:';
  color: pink;
}
span::after {
  content: 'span标签结束';
}
```

## 作用域
::placeholder：控制input标签的placeholder属性。
```css
input::placeholder {
  
}
```

