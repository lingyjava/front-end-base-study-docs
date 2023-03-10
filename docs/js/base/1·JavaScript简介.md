# 1·JavaScript简介

<!-- TOC -->
* [1·JavaScript简介](#1javascript简介)
  * [介绍](#介绍)
  * [浏览器如何执行JS](#浏览器如何执行js)
  * [JS的组成](#js的组成)
  * [JS编写位置](#js编写位置)
  * [注释](#注释)
  * [输入输出](#输入输出)
  * [命名规范](#命名规范)
<!-- TOC -->

## 介绍
JavaScript是一种运行在客户端的脚本语言。脚本语言是不需要编译，运行过程中由js引擎逐行进行解释并执行。
现在也可以基于Node.js技术进行服务器端编程。  

JavaScript作用：
- 表单动态验证（密码强度检测等，js最初的目的）。
- 网页特效。
- 服务端开发(Node.js).
- 桌面程序(Electron).
- App(Cordova).
- 控制硬件-物联网(Ruff).
- 游戏开发(cocos2d-js).

## 浏览器如何执行JS
浏览器有 渲染引擎 和JS引擎。  
浏览器本身并不执行JS代码，通过内置JS引擎执行JS代码。JS引擎逐行解析每一行源码转换为机器语言后由计算机执行。

- 渲染引擎也叫浏览器内核，用来解析HTML和CSS.
- JS引擎用来读取处理运行网页中的JS代码。

## JS的组成
JS由三部分组成：
- ECMAScript：ECMAScript规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。
- DOM(Document Object Model)：页面文档对象模型，是W3C组织推荐的处理可扩展标记语言的标准编程接口。通过DOM提供的接口可以对页面上的各种元素进行操作。
- BOM(Browser Object Model)：浏览器对象模型，提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过BOM可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等。

## JS编写位置
JS的三种编写位置：

- HTML行内式。
  - 可以将单行或少量的JS代码写在HTML标签的事件属性(以on开头)中。
  - 在HTML中推荐使用双引号，JS中推荐使用单引号。
  - 可读性差，引号易混淆，特殊情况下使用。
```html
<input type="text" onclick="alert('弹出一个框')">
```

- HTML内嵌式。
  - 可以编写多行代码。
```html
<script >
  alert('弹出一个框');
</script>
```

- 外部js文件。
  - 适用于JS代码量比较大的情况。
  - 利于HTML页面代码结构化，把大段JS代码独立到HTML页面之外，美观且利于复用。
  - 引用外部JS文件的script标签中可以不编写代码。
```js
alert('弹出一个框');
```

- 引入外部JS文件
```html
<script src="#"></script>
```
## 注释

```js
// 这是单行注释

/*
* 这是
* 多行注释
* */
```

## 输入输出
JS中提供了一些输入输出方法，方便信息的输入输出。

方法：
- alert(msg)：浏览器弹出警示框。
- console.log(msg)：浏览器控制台打印输出信息。
- prompt(info)：浏览器弹出输入框，用户可以输入。

## 命名规范
标识符命名规范：
- 变量、函数的命名必须有意义。
- 变量的名称用名词。
- 函数的名词用动词。
