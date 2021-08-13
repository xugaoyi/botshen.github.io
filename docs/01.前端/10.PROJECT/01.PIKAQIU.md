---
title: 制作一个皮卡丘
date: 2020-12-28 00:00:00
categories: 
  - frontEnd
tags: 
  - HTML
permalink: /pages/0f4249/
---
## 制作一个皮卡丘
设计稿：![VCXOO.png](https://ss.im5i.com/2021/08/12/VCXOO.png)
## 项目搭建
新建一个目录，比如：pikaqiu-3

创建src目录，里面创建`index.html`,`style.css`,`main.js`
因为项目要适配手机端，需要添加meta-vp
这里我我们直接复制淘宝的即可，打开淘宝网，开发者工具切换到手机，复制即可。
也可以直接抄我的代码：
```html
src/index.html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no,viewport-fit=cover">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>皮卡丘</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<script src="main.js"></script>
</body>
</html>
```
我们使用`parcel`打包和预览

首先运行
`yarn global add parcel`

在根目录运行
`parcel src/index.html`即可实时预览
## HTML编写
首先搭建框架，把最外层的元素先用div框起来
```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no,viewport-fit=cover">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>皮卡丘</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
<div class="skin">
    <div class="eye"></div>
    <div class="eye"></div>
    <div class="nose"></div>
    <div class="face"></div>
    <div class="face"></div>
    <div class="mouth"></div>
</div>
<script src="main.js"></script>
</body>
</html>
```
### 鼻子
鼻子是居中的，所以先做鼻子，鼻子可以转换成一个三角形和一个半圆形
![VC9fR.png](https://ss.im5i.com/2021/08/12/VC9fR.png)
#### 三角形
通过定位和边框来制作三角形：
```html
<div class="skin">
    <div class="eye"></div>
    <div class="eye"></div>
    <div class="nose">
        <div class="san"></div>
    </div>
    <div class="face"></div>
    <div class="face"></div>
    <div class="mouth"></div>
</div>
```
```css
.skin {
    position: relative;
}

.san {
    border: 10px solid red;
    border-color: red transparent navy transparent;
    width: 0px;
    height: 0px;
    border-bottom: none;
    position: absolute;
    left: 50%;
    top: 200px;
    margin-left: -5px;
}
```
#### 圆头
如果再次重新定位会很麻烦，所以这里把鼻头放在三角形里相对三角形定位
代码：
```html
<div class="skin">
    <div class="eye"></div>
    <div class="eye"></div>
    <div class="nose">
        <div class="san">
            <div class="yuan"></div>
        </div>
    </div>
    <div class="face"></div>
    <div class="face"></div>
    <div class="mouth"></div>
</div>
```
```css
* {box-sizing: border-box}
*::before {box-sizing: border-box}
*::after {box-sizing: border-box}
.skin {position: relative;}
.san {
    border: 10px solid red;
    border-color: red transparent navy transparent;
    width: 0px;
    height: 0px;
    border-bottom: none;
    position: absolute;
    left: 50%;
    top: 200px;
    margin-left: -5px;
}
.yuan {
    position: absolute;
    width: 20px;
    height: 6px;
    top: -16px;
    left: -10px;
    border-radius: 10px 10px 0 0;
    background: red;
}
```
这样一个差不多的鼻子就做出来了，下面是眼睛
### 眼睛