## 一 JavaScript概述

编程语言有解释型和编译型两种：
- 解释型：源代码无需经过编译，一行一行解析执行，比如javascript、python
- 编译型：源码编译为可执行文件后，运行可执行文件，比如C、C++，这些语言往往拥有一个名为main的入口函数

JavaScript（以下简写为js）是一门解释型脚本编程语言，也是当前Web开发领域的核心语言，没有之一。  

该语言由网景(Netscape)公司(火狐的前身)的`Brendan Eich（布兰登·艾奇）`花费了10天时间创建，语言名称中虽然带了Java，但是和另一门编程语言Java没有任何关系，网景早期的意愿是设计一款和Java一样脚本语言。  

由于各家引擎对JS的支持有所不同，为了统一JS的发展反向，欧洲计算机制造商协会为JavaScript提出了语法规范：ECMAScript。即各家的JS脚本语言都要以ECMAScript语法规范来开发。  

提到JavaScript时，通常指的版本是ECMAScrip3和ECMAScript5，js的当前主要版本：
- ECMAScript3：1999年标准规范，火狐的js1.5和1.8都是基于3规范
- ECMAScript4：为了适应互联网发展出来的激进版本，由于存在大量分歧，该版本并未普及
- ECMAScript5：2009年发布，包含了4中的一些常见功能，当前的主流版本
- ECMAScript6：诞生于2015年，也称为ES2015，是js划时代意义的版本。引入了开发大型项目所需要的功能，JS终于不再是一门`玩具语言`。
- ES2016：诞生于2016年，即ES7，后续版本均以年为名称，如ES2017、ES2018。ES2016中引入`async await`异步解决方案。

任何编程语言都需要编程语言引擎来对代码进行解析，从而让代码转换为机器指令（因为计算机只能运行机器指令，不能直接运行代码）。常见的JS引擎有：
- v8引擎：js最著名的引擎，以高性能著称，被应用于Chrome浏览器与Node.js
- SpiderMonkey：火狐浏览器中的js引擎

在编程引擎基础上，第三方会为编程语言开发一些独立的库，对编程语言进行功能上的包装，这些最终包装出来的编程环境，我们称之为运行时！常见的js运行时有：
- Chrome浏览器：JS引擎为：V8，内置webkit排版引擎，提供了html文档操作API
- FireFox浏览器：JS引擎为：SpiderMonkey，内置Gecko排版引擎，也提供了html文档操作API
- Node.js：JS引擎为V8，内置了Node的API，即提供了网络、文件等计算机系统操作API

## 二 Hello World

`Hello World`程序是1974年`Brian Kernighan`撰写的`《Programming in C: A Tutorial》`中首次面向大众介绍C语言时使用的最简单程序示例。后来该习惯相继被大量编程语言沿用。   

本笔记中的JavaScript代码大多都依赖于Chrome运行时，故而我们需要一定的HTML文件来运行。

编写js版`Hello World`，创建helloworld.html文件，代码如下：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <script>
        // 这里开始书写js代码
        console.log("Hello World!");
    </script>
</body>
</html>
```

用浏览器打开该网页，按F12打开控制台，控制台将会输出：`Hello World!`。  

## 三 JavaScript书写位置

JavaScript的代码要被书写于脚本标签中，但是HTML5和HTML4的脚本标签规范不尽一致：
- HTML4脚本标签：`<script type="application/javascript"> </script>`
- HTML5脚本标签：`<script> </script>`

贴士：本章节均使用较新的HTML5规范。 

脚本标签有三种书写位置：
```html
<!-- 内嵌式：直接在html网页中书写代码，HelloWorld中使用了内嵌式 -->
    <script>
        console.log("Hello World!");
    </script>

<!-- 外联式：推荐方式。代码位于专门的js文件，由脚本标签引入 -->
    <script src="./hello.js"> 
    
    </script>

<!-- 3 内嵌式 极度不推荐。代码直接书写于html标签中 -->
    <button onclick="fn()">登录</button>
```

注意：推荐使用外联式，可以将js文件合并到一个文件中。如果使用内嵌式，建议JS代码写在body标签后，以确保JS执行的正确性。  

## 四 JavaScript一些常见使用

#### 4.1 注释

js中的注释：
```js
//  单行注释

/*
    多行注释
*/
```

#### 4.2 控制台

```js
console.log("打印日志");
console.warn("打印警告");
console.error("打印错误");
```

#### 4.3 分号

js语句末尾的分号可以写也可以不写，不写的时候要保证每行代码都具备完整的语义！  

**笔者推荐：书写代码时，尽量保证每行代码都有自己的独立意义，不能在一行代码中添加多个功能！**

#### 4.4 JS区分大小写

注意：JavaScript是区分大小写的！

#### 4.5 转义字符

常见转义字符：
```
\n  换行符
\v  垂直制表符
\f  换页符  
\r  回车符
```
