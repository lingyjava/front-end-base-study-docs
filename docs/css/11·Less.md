# 11·Less

> 给CSS加点料。  
> 使用Less语法快速编译生成CSS代码。  

<!-- TOC -->
* [11·Less](#11less)
  * [Less 简介](#less-简介)
  * [vscode插件](#vscode插件)
  * [注释](#注释)
  * [计算](#计算)
  * [嵌套](#嵌套)
  * [变量](#变量)
  * [导入](#导入)
  * [导出](#导出)
<!-- TOC -->

- [Less中文文档](https://less.bootcss.com/)

## Less 简介
Less是一个CSS预处理器，Less文件后缀是.less  
Less扩充了CSS语言，使CSS具备一定的逻辑性、计算能力。  
浏览器不识别Less代码，网页要引入对应的CSS文件。  

## vscode插件
- Easy Less：less文件保存自动生成CSS文件。

## 注释
语法：
```less
// 单行注释内容

/*
  多行注释
  注释内容
*/
```

## 计算
允许使用 加、减、乘、除 的计算表达式。除法需要添加小括号或使用./  

```less
.box {
  width: 6 + 5 rem;
  height: 6 - 5 rem;
  padding: 6 * 5 rem;
  margin: (6 / 5rem);
  line-height: 6 ./ 5 rem;
}
```

## 嵌套
通过嵌套写法生成后代选择器。  
使用 & 符号表示当前选择器不生成为后代选择器，配合伪类选择器、伪元素使用。  

语法：
```text
.父级选择器 {
    // 父级样式
    .子级选择器 {
        // 子级样式
    }
}
```

```less
.box {
  width: 85px;
  .nav {
    display: flex;
    width: 20px;
    .left {
      flex: 1;
      &:hover {
        color: pink;
      }
    }
  }
}
```

## 变量
使用变量存储数据，方便使用和修改。  

定义变量语法：@变量名: 值;  
使用变量语法：CSS属性: @变量名;  

```less
@color: pink;

.box {
  color: @color;
}
```

## 导入
在Less中引入其他样式（公共样式等）的Less文件。  

```less
/*less文件后缀可以省略*/
@import "#url.less";
```

## 导出
将Less文件编译并导出一个CSS文件。文件位置默认与less文件同级。  

修改导出文件位置:Less文件的第一行添加如下代码, 注意文件夹名称后面务必要加 / ，如果没有css文件，会自动新建一个css文件，如果添加在了第二行，会当成注释解析。
```less
// out: ./url/file.css/
```

如果不想less文件导出为css文件，在第一行添加如下代码：
```less
// out: false
```
