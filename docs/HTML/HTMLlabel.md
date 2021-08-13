---
title: HTML 标签
date: 2021-08-11 00:00:00
sidebar: auto
tags: 
  - HTML
categories: 
  - xxx
permalink: /pages/e88f82/
---

## 编辑器推荐
HTML推荐书籍[《网道HTML》](https://wangdoc.com/html/index.html)

推荐一个编辑器
![PMyAU.png](https://ss.im5i.com/2021/08/12/PMyAU.png)
## HTML起手式

!+Tab
![PMJqw.png](https://ss.im5i.com/2021/08/12/PMJqw.png)
`<!DOCTYPE html>`是文档类型，告诉浏览器我开始写`HTML`了。支持很多种类型。

然后是`html`标签，这是根标签，不写的话会帮忙你加上。

`lang="en"`的意思是语言是英文，告诉浏览器这个页面的语言是英文，一般我们会改成`zh-CN`  是中国的中文

一般来说head和body不缩进，head写的一般是看不见的内容。

<meta charset="UTF-8">意思是文件的编码是UTF-8。

一般先声明编码，下面的顺序无所谓
## 章节标签
表示文章或书的层级
标题h1 ~ h6
![PMcsZ.png](https://ss.im5i.com/2021/08/12/PMcsZ.png)
`<section>章节`
![PMsIJ.png](https://ss.im5i.com/2021/08/12/PMsIJ.png)
![PMU11.png](https://ss.im5i.com/2021/08/12/PMU11.png)
## 全局属性
![PMbln.png](https://ss.im5i.com/2021/08/12/PMbln.png)
`class`操作符使用   .操作符来匹配

`contenteditable`属性表示可以编辑

有没有可能让head里面的东西被看见呢？

比如style 标签

是可以的。
![PMt9l.png](https://ss.im5i.com/2021/08/12/PMt9l.png)
这样就做到了显示。

将可以编辑和看见style结合起来就可以让用户自己改自己的样式。

也可以算作是一个实时调试技巧

hidden就是让一个东西看不见，在标签页中加入hidden属性即可。比display : none 的优先级高。

id="xxx"      id选择器，请问他和class如何选择。

正确结论是，不到万不得已不要用id，因为id不报错，id在html中不是一定唯一的，就算有两个相同的id也不报错，id会给人误导。class够了。

id和css有关。在css讲解。其实就是加一个#来给元素加样式。

id和JS有股，JS可以直接获取id，比如：

```JavaScript
xxx.style.border = "1px solid red";     //比html中的style属性优先级高，因为JS会覆盖html中style属性
```

当有两个xxx时候，JS会找不到哪个xxx

上面这种写法不要这样用，打死也不要用。因为如果JS关键字或windows.***中有这个字母，无法识别。

如果我就想在JS中拿到id呢？那就只能这样写了。

```JavaScript
document.getElementById('top')
```

所以说这种方式只能在知道哪些是关键字之后才能用，老司机才敢用，新手不要这样写。

style也就是可以在标签中加样式。不是css。只是html的属性，优先级比head里面的样式高

可以使用JS调用它

`tabindex`是什么意思？
首先说明键盘上的Tab按键可以在浏览器中切换不同位置，会切换到页面上所有可交互的东西。
通过设置tabindex的值可以让用户使用Tab按键来切换相应的元素，数值是用来设置切换顺序的。
tabindex有一个特殊值是0，代表着最后一个tab顺序。
还有个特殊值-1，Tab永远找不到我。

![PMua7.png](https://ss.im5i.com/2021/08/12/PMua7.png)

最后一个全局属性，title。

![PMHG2.png](https://ss.im5i.com/2021/08/12/PMHG2.png)

white-space是不要换行
对于我们想要的题目来说，可以设置不允许换行，但是这样设置之后会出现后面的字顶出去了，很丑。
当单行文字溢出如何处理呢？css处理方法
下面是解法，首先是不要换行，第三句，溢出就省略，第二行，省略的部分用省略号表示，border边框不算第一句


![PMjHP.png](https://ss.im5i.com/2021/08/12/PMjHP.png)

所以title属性就是鼠标浮上去显示内容，就是下图“完整的内容”的显示形式，可以应用于查看完整内容的场景。

![PMTAD.png](https://ss.im5i.com/2021/08/12/PMTAD.png)
## 默认样式
默认样式就是HTML自己的样式，为什么html有默认样式？
因为css出现之前就有了html，文字也需要样式啊。
这是h1标签的默认样式

![PMXqj.png](https://ss.im5i.com/2021/08/12/PMXqj.png)

如何知道一个标签的默认样式呢？

通过浏览器的开发者工具，也就是上图的方式查看。右上角的灰色英文的意思是浏览器给h1加的默认样式。

这个写法不一定符合css的语法。

user agent 就是浏览器的意思。

可以通过html属性style来覆盖浏览器的默认样式。

由于html的默认样式很丑，现在的网页已经不适用默认样式了，所以需要把默认的样式干掉。

那么这种写法叫做**`CSS reset`**

常用的写法：
```CSS
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
*::before,
*::after {
  box-sizing: border-box;
}
a {
  color: inherit;
  text-decoration: none;
}
input,
button {
  font-family: inherit;
}
ol,
ul {
  list-style: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
```

也可以抄大厂的代码

1. 进入大厂首页

2. f12开发者工具

3. 复制到自己的项目

4. 命名为reset.css
## 内容标签
![PM2ES.png](https://ss.im5i.com/2021/08/12/PM2ES.png)
ol+li（有序的列表）

ol的意思是ordered list，也就是有序的列表。

li的意思是list item，列表中的一项。

所以ol只能含有li不能含有非li的东西，比如文字。

效果就是这样。

1. 发邮件

2. 跟产品经理撕逼

3. 写页面

4. 吃饭

5. 上厕所

6. 打游戏

当顺序不重要的时候

吧ol改成ul，ul是unordered list，就是无序列表。

也就是下面的样式：

- 发邮件

- 跟产品经理撕逼

- 写页面

- 吃饭

- 上厕所

- 打游戏
- dl+dt+dd，全称为description list+term + data,描述列表
![PM9IL.png](https://ss.im5i.com/2021/08/12/PM9IL.png)
- HTML有个特点，如果有多个空格或者回车，会缩成一个空格。

如果想保留空格，回车，Tab，就使用pre标签。

code标签一般放置代码，code里面的字体是等宽的。

hr：水平分割线

br：换行

a：超链接

```HTML
<a href="http://www.google.com" targeet="_blank">打开Google</a>
```

href用来写网址，_blank表示在新标签页中打开。

em：强调也就是斜体，语气的强调。

strong：加粗，本质的强调。

quote：表示引用，默认没有任何效果。行内元素，就是说在标签前面加字不会换行

blockquote：如果想要一个块级的引用，分行的话用这个标签。