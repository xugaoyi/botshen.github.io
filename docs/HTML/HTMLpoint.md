---
title: HTML重难点
date: 2021-08-12 00:00:00
sidebar: auto
tags: 
  - HTML
permalink: /pages/fd4589/
categories: 
  - HTML
---
### meta-vp 适配手机的代码
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no">
```
### a标签详细介绍
![P7htw.png](https://ss.im5i.com/2021/08/12/P7htw.png)
href =hyper+ref

超级+引用/链接

所以`href`就叫做超链接，也叫做超级引用。

`target`作用就是在哪一个窗口打开这个超链接

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <a href="https://www.google.com">超链接</a>
</body>

</html>
```

不允许双击打开html，要使用vscode的live server插件打开，如果是webstorm直接右上角就有浏览器图标打开。
![P7wmZ.png](https://ss.im5i.com/2021/08/12/P7wmZ.png)
### 使用http-server
`yarn global add http-server`

`http-server -c -1`
### 使用 parcel
`yarn global add parcel`

`parcel index.html`

<hr/>
个人推荐live-server打开，方便。

`target="_blank"`就是在空白页打开超链接

`download`很多浏览器不支持，理论上是下载这个网页。

`rel=noopener`现在理解不了，以后再说
### a的href 的属性
![P7gV7.png](https://ss.im5i.com/2021/08/12/P7gV7.png)
![P7GW2.png](https://ss.im5i.com/2021/08/12/P7GW2.png)
//google.com叫做无协议的网址
### 查看开发者工具
![P7K0P.png](https://ss.im5i.com/2021/08/12/P7K0P.png)
![P7VND.png](https://ss.im5i.com/2021/08/12/P7VND.png)
无协议到http到https，两层跳转。

所以我们再写网址的时候只写//打头的，会自动跳转，写错协议会产生bug。

跳转路径/a/b/c,为什么写绝对路径实际是相对路径。

当我们使用http之后，不是文件路径，所以不是相对于电脑，

所以此时的根目录就是在哪里开启的服务，哪里就是根目录。

伪协议：

```HTML
<a href="javascript:alert(1);">Javascript伪协议</a>
```

在视图中点击可以运行JavaScript代码。

只是为了在这里可以执行JavaScript代码，早起有用，现在已经不用了。

现在的用途是写 一个a标签，但是什么都不做。如下

```HTML
<a href="javascript:;">空的协议</a>
```

除了这种写法，没有别的写法可以做到。

href还可以等于一个id

比如：

```HTML
<a href="#xxx">查看xxx</a> 
```

点击后会跳转到id为xxx的标签上。

href可以添加mailto值：

```HTML
<a href="mailto:363088847@qq.com">给沈鑫发邮件</a> 
```

tel 属性可以添加打电话的效果：

```XML
<a href="tel:18840102768">打电话给我</a>
```
### a的target 属性
![P7dtj.png](https://ss.im5i.com/2021/08/12/P7dtj.png)
_blank就是在新的页面打开网页

_self是默认值，就是在当前页面打开网页

_top是在最顶层页面打开网页，直接看不出来，需要有两个窗口

iframe可以引入另一个页面

![P7fxS.png](https://ss.im5i.com/2021/08/12/P7fxS.png)

就像这样，在红色区域，也就是内层点击a标签会在顶层打开Google，因为属性设置了_top。

Google不允许别人使用iframe指向他。

_parent是在父级窗口打开。

target还可以设置为xxx

效果就是当两个a标签都设置为xxx时候，会在第一个窗口打开。

就是说两个a标签，一个是Google，一个是百度，先点击Google，再点击百度，百度的页面会覆盖掉Google的网页的意思。

当没有xxx窗口的时候就创建一个xxx窗口，当有xxx的时候，打开第二个xxx会覆盖。

target还可以写iframe的名字。
![P7rhL.png](https://ss.im5i.com/2021/08/12/P7rhL.png)
### iframe标签

用来内嵌一个网页，很少使用了，不好用。参考上面。
### table标签
![P7yJt.png](https://ss.im5i.com/2021/08/12/P7yJt.png)
表格。

table标签里面只能有这三个标签。

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <table>
        <thead>
            <tr>
                <th>英语</th> //表头
                <th>翻译</th>

            </tr> //table row 英文，表示一行
        </thead>
        <tbody>
            <tr>
                <td>hyper</td> //table data 表示数据
                <td>超级</td>
            </tr>
            <tr>
                <td>target</td> //table data 表示数据
                <td>目标</td>
            </tr>
            <tr>
                <td>reference</td> //table data 表示数据
                <td>引用</td>
            </tr>
            <tr>
                <td>frame</td> //table data 表示数据
                <td>边框、框架</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td>空</td>
                <td>空</td>
            </tr>
        </tfoot>

    </table>
</body>

</html>
```
![P7Boq.png](https://ss.im5i.com/2021/08/12/P7Boq.png)
两个表头怎么做呢？

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>

    <body>
        <table>
            <thead>
                <tr>
                    <th></th>
                    <th>小红</th>
                    <th>小明</th>
                    <th>小颖</th>

                </tr>
            </thead>
            <tbody>
                <tr>
                    <th>数学</th>
                    <td>98</td>
                    <td>35</td>
                    <td>78</td>
                </tr>

            </tbody>
            <tbody>
                <tr>
                    <th>语文</th>
                    <td>98</td>
                    <td>35</td>
                    <td>78</td>
                </tr>

            </tbody>
            <tbody>
                <tr>
                    <th>英语</th>
                    <td>98</td>
                    <td>35</td>
                    <td>78</td>
                </tr>

            </tbody>


        </table>
    </body>
</body>

</html>
```
![P7JMm.png](https://ss.im5i.com/2021/08/12/P7JMm.png)

这样就可以了。

相关的样式：

auto 为默认样式，会自动计算宽高,根据内容，fixed会尽量平均。

```HTML
<style>
        table{
            table-layout: auto;
        }
    </style>
```

> [`auto`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/auto)

> 大多数浏览器采用自动表格布局算法对表格布局。表格及单元格的宽度取决于其包含的内容。

> `fixed`

> 表格和列的宽度通过表格的宽度来设置，某一列的宽度仅由该列首行的单元格决定。在当前列中，该单元格所在行之后的行并不会影响整个列宽。

> 使用 “fixed” 布局方式时，整个表格可以在其首行被下载后就被解析和渲染。这样对于 “automatic” 自动布局方式来说可以加速渲染，但是其后的单元格内容并不会自适应当前列宽。任何一个包含溢出内容的单元格可以使用 [`overflow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow)  属性控制是否允许内容溢出。

border-collapse：collapse

让单元格合并:

![P7sds.png](https://ss.im5i.com/2021/08/12/P7sds.png)

border-spacing是border之间的距离。

一般会在css reset里面写,表示表格的边框合并，距离为0。

```CSS
table{
border-spacing: 0;
border-collapse: collapse;
} 
```
### image标签
![P7EXQ.png](https://ss.im5i.com/2021/08/12/P7EXQ.png)
```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<img src="dog.png" alt="不加载显示我">
</body>
</html>
```

img 是image的缩写，src是source的缩写，代表资源，可以是一个网址，可以是相对绝对路径。

img可以发出get请求，通过开发者工具。
![P7U03.png](https://ss.im5i.com/2021/08/12/P7U03.png)
alt属性是当图片加载失败的时候显示的内容。

使用height和width设置图片的高和宽，注意这不是css而是html的属性，只写高度或者宽度，图片会自适应，如果同时写高度和宽度，会让图片变形。

前段工程师的底线，永远不能让图片变形。

在js中有两个事件，用来监听图片是否加载成功。onerror和onload。
![P7tSy.png](https://ss.im5i.com/2021/08/12/P7tSy.png)

可以来挽救，让加载失败的时候显示404
![P7utO.png](https://ss.im5i.com/2021/08/12/P7utO.png)

max-width=100%，用来做响应式布局，在手机上也能很好的呈现。
![P75xR.png](https://ss.im5i.com/2021/08/12/P75xR.png)

可替换元素（面试问），看下面链接：

https://developer.mozilla.org/zh-CN/docs/Web/CSS/Replaced_element
### form标签（表单）
![P7jwd.png](https://ss.im5i.com/2021/08/12/P7jwd.png)
```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
</head>
<body>
<form action="/xxx">
  <input type="text">
  <input type="submit">
</form>
</body>
</html>
```

action相当于img中的src，填写后台的路径。

上面就是一个最简单的form。
![P7TJ4.png](https://ss.im5i.com/2021/08/12/P7TJ4.png)

method="POST"表示使用post请求，默认是get。

```HTML
<form action="/xxx" autocomplete="on">
        <input name="username" type="text">
        <input type="submit">
    </form>
```

当autocomplete="on"时，输入会给出建议。

target和a标签的差不多，_blank的意思就是在新开的页面打开xxx。也就是告诉浏览器我要提交到哪个页面 。

最后是onsubmit事件，意思就是当用户点击的时候会触发onsubmit事件。

有一个细节就是我在代码里面没有写提交两个字，提交哪来的？

这是一个本地化的过程。当写type="submit"的时候，浏览器会根据你的语言写上提交字样。

也可以自己修改`<input type="submit" value="搞起" />`，这样提交字样就会变成搞起。
![P7WoW.png](https://ss.im5i.com/2021/08/12/P7WoW.png)

那么按钮和input标签有什么区别呢？

- input里面不能再有任何内容。因为是写在value里面的，用双引号包起来的，怎么加标签呢？

- button里面随便加内容，比如给搞起两个字加一个强调标签`<strong>`，button里面是可以加其他的标签的。

form标签里面必须要用一个含有submit的按钮或者按钮。如果不写，默认就是submit。如果换成了其他值，表单的按钮就没有提交功能。也就没了意义这个form。
### input标签
![P7XOG.png](https://ss.im5i.com/2021/08/12/P7XOG.png)

默认的type是text。文本

type还可以是color。颜色

type还可以是password。密码

type还可以是radio。单选，这里有一个问题，比如男女选项。

如果正常写两个input会出现两个选项都可以选择，这时候需要给input标签加一个name。、

下面是示例代码：

![P79dz.png](https://ss.im5i.com/2021/08/12/P79dz.png)

type还可以是checkbox。多选，怎么知道哪几个多选框是一组的呢？

答案还是一样的。加相同的name。

下面是多选：
![P7RX5.png](https://ss.im5i.com/2021/08/12/P7RX5.png)
效果图：

![P7YD6.png](https://ss.im5i.com/2021/08/12/P7YD6.png)

type还可以是file。文件，且为单个文件。如果想选择多个文件。加上multiple即可。

```HTML
<input type="file" multiple /> 
```
![P7oS8.png](https://ss.im5i.com/2021/08/12/P7oS8.png)

type还可以是hidden。表示看不见的。

一般来说这种input不是给人类输入的，是给机器输入的。

比如给js填写一些id、字符串等。

onchange事件，当用户输入改变的时候就会触发这个事件。

onfocus事件，当用户把鼠标放在上面的时候就会触发事件。

onblur事件，当用户把鼠标移出去标签的时候会触发事件。

html5自带验证器。

意思就是如果加了required，提交时不写会提示。
![P73uU.png](https://ss.im5i.com/2021/08/12/P73uU.png)

### textarea标签
表示一个输入框。可以输入文字。

有个特点，右下角可以拖动，如果想去掉，需要加style="resize:none;"
![P7I8w.png](https://ss.im5i.com/2021/08/12/P7I8w.png)
### select标签
```HTML
  <select>
        <option value="1">星期一</option>
        <option value="2">星期二</option>
        <option value="3">星期三</option>
        <option value="4">星期四</option>
        <option value="5">星期五</option>
        <option value="6">星期六</option>
        <option value="7">星期日</option>
    </select>
```
![P7iwZ.png](https://ss.im5i.com/2021/08/12/P7iwZ.png)

### 其他标签
![P7mcJ.png](https://ss.im5i.com/2021/08/12/P7mcJ.png)
![P7x31.png](https://ss.im5i.com/2021/08/12/P7x31.png)

