# 01/11/2020 前端作业
## **1.	HTML 的标签都有哪些？语义化什么意思？**
```
<!--...--><!DOCTYPE><a><abbr><acronym><address><applet><area><article><aside><audio><b><base><basefont><bdi><bdo><big><blockquote><body><br><button><canvas><caption><center><cite><code><col><colgroup><command><datalist><dd><del><details><dfn><dialog><dir><div><dl><dt><em><embed><fieldset><figcaption><figure><font><footer><form><frame><frameset><h1>to<h6><head><header><hr><html><i><iframe><img><input><ins><kbd><keygen><label><legend><li><link><main><map><mark><menu><meta><meter><nav><noframes><noscript><object><ol><optgroup><option><output><p><param><pre><progress><q><rp><rt><ruby><s><samp><script><section><select><small><source><span><strike><strong><style><sub><summary><sup><table><tbody><td><textarea><tfoot><th><thead><time><title><tr><track><tt><u><ul><var><video> <wbr> 
```
语义化是指根据内容的结构化，选择合适的标签，便于开发者阅读和写出更优雅的代码的同时，让浏览器爬虫和机器更好的解析。语义化常用标签：```<header><nav><article><section><aside><footer>```

---
## **2.	引入CSS的方法都有哪些？link和import有哪些区别？(5个左右的大区别）**
1. 内联样式 ```<div style=”display:none;”>``` 直接在标签中设置style
2. 嵌入样式 ```<style> div{display:inline-block} </style>``` 在html的head里写入style，只对当前网页生效
3. 链接样式 ```<link rel=”stylesheet” type=”text/css” href=”style.css”>``` 外部创建css文件并链接至html文件中，可维护性高，最常用方式
4. 导入样式 @import url(style.css); 使用CSS规则引入外部CSS文件
---
### Link和import的区别：
1.	Link是XHTML标签，除了加载CSS外，还可以定义RSS等其他事务；@import只能加载CSS。
2.	Link引用CSS时在页面加载同时加载；@import需要等网页完全载入后加载。
3.	Link是XHTML标签，无兼容问题；@import是CSS2.1提出的，低版本浏览器不支持。
4.	Link支持使用JS控制DOM改变样式；@import不支持。
5.	@import可以在CSS文件中引入其他CSS文件。
---
## **3.	CSS 选择器都有哪些？ 优先级的规则是什么？**
### 基本选择器：
1.	*（通用选择器，适配任何元素）
2.	E（标签选择器，适配任何E元素）
3.	.myClass（class选择器，适配所有class名为myClass的元素）
4.	#myId（id选择器，适配唯一id等于myId的元素）
优先级规则为 #>.>E>* ，选择器叠加可以增加优先级，例如.myClass #myId 比 #myId 优先级高。
---
## **4.	伪类？都有哪些？怎么用？应用场景？**
1.	E:link 匹配所有未被点击的链接
2.	E:visited 匹配所有已被点击的链接
3.	E:active 匹配鼠标已经按下，还未释放的E元素
4.	E:hover 匹配鼠标悬停的E元素
5.	E:focus 匹配当前聚焦的E元素
6.	E:lang(c) 匹配lang属性等于c的E元素
7.	E:not(s) 匹配不符合s的元素
8.	E:enabled 匹配表单中激活的元素
9.	E:disabled 匹配表单中禁用的元素
10.	E:checked 匹配表单中被选中的radio或checkbox元素
11.	E::selection 匹配用户当前选中的元素
12.	E:root 匹配根元素（html）
13.	E:first-child E:last-child匹配E元素中第一个/最后一个子元素
14.	E:nth-child(n)；E:nth-last-child(n) 匹配E元素中第n个/倒数第n个子元素
15.	E:nth-of-type(n)；nth-last-of-type(n) 匹配E元素中第n个/倒数第n个同种元素标签的元素
16.	E:first-of-type；E:last-of-type 等于E:nth-of-type(1)；nth-last-of-type(1)
17.	E:only-child 匹配E元素中仅有的一个子元素
18.	E:only-of-type 匹配E元素中同种标签的仅有子元素
19.	E:empty 匹配一个不包含任何子元素的元素
20.	E:target 匹配文档中特定”id”点击后效果
---
## **5.	伪元素？都有哪些？怎么用？应用场景？**
 
1.	E:first-line匹配E元素的第一行
2.	E:first-letter 匹配E元素的第一个字母
3.	E:before 在E元素之前插入生成的内容
4.	E:after 在E元素之后插入生成的内容
---
## **6.	把竖着排列的元素变横有哪些方法**
1. 将块元素变为内联元素 display:inline/display:inline-block
2. 使用float设置元素
3. 使用display:flex并设置flex-direction:row
---
## **7.	让一堆元素左对齐、右对齐有哪些方法**
1. 使用text-align设置为left/right
2. 使用display:flex并设置justify-content:flex-start/flex-end
---
## **8.	让一堆元素水平居中、垂直居中有哪些方法**
### 水平居中：
1.	行内元素：设置父级元素的text-align:center
2.	块状元素：设置margin:0 auto
3.	多个内联块状元素：

    a.	先设置父级元素的text-align:center，再设置每个子元素display:inline-block

    b.	设置父级元素display:flex并设置justify-content:center
### 垂直居中
1.	已知高度宽度元素：

    a.	设置父级元素position:relative，然后设置子元素position:absolute并设置top与left为50%，再设置margin为子元素高宽的一半，取负数。
    
    b.	设置父级元素position:relative，然后设置子元素position:absolute，并设置margin:auto，再设置top/bottom/left/right为0

2.	未知高度宽度元素：

    a.	子元素时inline/inline-block时，将父元素设置为display:table-cell，配合vertical-align:middle设置

    b.	设置父级元素position:relative，然后设置子元素position:absolute，并设置top/left为50%，再用transform:translate(-50%, -50%)

    c.	使用display:flex配合justify-content:center与align-items:center
---
## **9.	哪些CSS属性会继承？那些不会？**
## 有继承性的属性：
1.	字体系列属性
Font, font-family, font-weight, font-size, font-style, font-variant, font-stretch, font-size-adjust
2.	文本系列属性
text-indent, text-align, text-shadow, line-height, word-spacing, letter-spacing, text-transform, direction, color
3.	元素可见性：visibility
4.	表格布局属性：caption-side, border-collapse, empty-cells
5.	列表属性：list-style-type, list-style-image, list-style-position、list-style
6.	设置嵌套引用的引号类型：quotes
7.	光标属性：cursor
### 无继承的属性
1.	display
2.	文本属性：vertical-align, text-decoration
3.	盒子模型的属性:宽度、高度、内外边距、边框等
4.	背景属性：背景图片、颜色、位置等
5.	定位属性：浮动、清除浮动、定位position等
6.	生成内容属性:content、counter-reset、counter-increment
7.	轮廓样式属性:outline-style、outline-width、outline-color、outline
8.	页面样式属性:size、page-break-before、page-break-after
---
## **10.	请用background属性，实现Google导航栏的more-icon**
---
## **11.	vw，vh，rem， em都是干嘛的？怎么用？应用场景？**
1. vw, vh：依据视窗大小设置宽高，视窗宽为100vw，视窗高为100vh。在需要根据用户屏幕大小进行自适应设置时使用。
2. em：大小不是固定的，会继承父级元素的大小。
3. rem：大小不是固定的，始终基于根元素```<html>```的大小
---
## **12.	如何做一个底栏能够一直在底部的(sticky-footer)?有几种方法？那种比较好？（负margin, flex)**
1. 负margin方法：给main content块设置padding-bottom为footer的高度，然后将footer的margin-top设置为负自身高度

    优势：兼容性最佳

    劣势：结构复杂，需提前明确footer高度
2. Flex方法：父级元素设置display:flex，main-content子元素设置flex:1

    优势：结构简单，方便使用

    劣势：兼容性较差
---
## **13.	屏幕适配（媒体查询media-query）**
- 表达式 @media (condition){} 如果condition为true则运行内部CSS。应用于不同屏幕情况下的CSS变更。
---
## **14.	veritcal-align这个属性为什么没有用？他什么时候有用？**
- Vertical-align只对于inline和table-cell元素起作用。
---
## **15.	float如何使用？如何清除float？都有哪些方法？为什么要清除Float，不清除会怎么样**
- float使块状元素向左或向右浮动，脱离普通文档流，让block元素无视float元素，但inline元素围绕着float元素实现浮动布局。多应用于文字环绕图片，或导航栏横向菜单。
- 清除float方法：

    1.	在父元素内添加一个div至最后，并给予clear:both

    2.	父元素定义overflow:auto/hidden

    3.	使用伪类:after方法，向需要清除的父元素后添加:after{clear:both,content:’.’,display:block;
- 清除浮动可以使后续元素块正常排列到浮动元素下排，而且可以使父级元素正常显示高度与margin。如果不清楚浮动会使父级元素高度塌陷，并无法正常显示margin。
---
## **16.	line-height属性是做啥的？有什么用？跟height有什么区别？**
- Line-height设置了上一行baseline到下一行baseline中间的行高。Line-height决定了文本内容的高度，而height定义了元素自身的高度。两者值设置相等可以达到垂直居中的效果。
---
## **17.	display/position都有哪些属性？里面每个属性的用法+使用场景？**
- Display:

    1.	None：元素不会占用空间也不会显示，常用在动态显示某一元素时使用。

    2.	Block: 设置为块状元素，会独占一行，不指定宽高的情况下，宽会继承父元素，高会被内容撑开。常用div元素默认为block。

    3.	Inline: 设置为行内元素，宽高设置无效，text-align设置也无效。多用于将元素排列在一行。

    4.	Inline-block: 既具有block的宽高属性，又具有inline的同行元素特性。

    5.	Flex：弹性布局属性，子元素的float，clear，vertical-align全部失效。可应用与各种场景。
- Position:

    1. absolute：绝对定位，相对于static定位以外的第一个父元素进行定位。元素的位置通过left/top/right/bottom属性进行规定。

    2. fixed：绝对定位，相对于浏览器窗口进行定位。元素的位置通过left/top/right/bottom属性进行规定。
    
    3. relative：相对定位，相对于其正常位置进行定位。

    4. static：默认值，没有定位。元素出现在正常流中。left/top/right/bottom/z-index会被忽略。
---
## **18.	box-shadow怎么用**
- 参数设置：

    1.	Inset阴影类型：可选值，默认外阴影，可用inset设置为内阴影。

    2.	X-offset：阴影水平偏移量，正右负左。

    3.	Y-offset：阴影垂直偏移量，正下负上。

    4.	阴影模糊半径：可选，只能正值，值越大阴影越模糊。

    5.	阴影扩展半径：可选，正扩大负缩小。

    6.	阴影颜色：可选。
- 可用逗号分隔，设置多个阴影。
---
## **19.	css中，百分比的使用，有哪些需要注意的？他是谁的百分比？**
- 常用百分比：

    1.	Width&height：百分比基于父元素的宽高计算。如果父元素宽高没有明确设置，并且子元素定位是绝对定位时，百分比基于root

    2.	Margin&padding：百分比基于父元素的宽度，适用于margin和padding的四个方向。

    3.	Border-radius：百分比基于自身的尺寸。

    4.	Background-position：百分比计算值为（父元素-背景图片）*百分比。

    5.	Font-size：百分比参考值是父元素的font-size。

    6.	Line-height：百分比参考值是自身font-size大小。

    7.	Vertical-align：百分比参考值是自身line-height。

    8.	Bottom, left, right, top：百分比基于父元素的尺寸。与margin&padding不同，top/bottom基于高，left/right基于宽。

    9.	Transform:translate: 百分比基于自身元素的宽度或高度。参考为border-box的尺寸。
---
## **```20.	<meta name="viewport" content="width=device-width, initial-scale=1.0">？？```**
- Viewport主要针对手机端网页，创建虚拟窗口，并使开发者设置窗口大小和缩放，使手机用户体验更加。
- 参数设置：

    1.	Width；控制viewport宽度，可设置数字值，也可设置device-width，为用户设备的宽度。

    2.	Height：控制viewport高度。

    3.	Initial-scale：初始缩放比例。

    4.	Maximum-scale：允许用户缩放到的最大比例。

    5.	Minimum-scale：允许用户缩放到的最小比例。

    6.	User-scalable：用户是否可以手动缩放。
---
## **```21.	<meta http-equiv="X-UA-Compatible" content="ie=edge">？？```**
- eta http-equiv会向浏览器传回一些有用的信息，让网页显示正确的信息。
- 语法：```<meta http-equiv=“参数” content=“参数变量值”>```
- 此参数允许开发者选择IE浏览器的版本。
- 实用参数：

    1)	Expires(期限)  使用GMT的时间格式。 网页过期，到服务器上重新传输。
```＜meta http-equiv="expires"content="Wed, 20 Jun 2007 22:33:00 GMT"＞```

    2)	Pragma(cache模式) 禁止浏览器从本地机的缓存中调阅页面内容
```＜metahttp```-equiv="Pragma"content="no-cache"＞```

    3)	Refresh(刷新) 2秒后自动刷新到URL地址
```＜meta http-equiv="Refresh" content="2；URL=http://www.net.cn/"＞```

    4)	Set-Cookie(cookie设定)  网页过期，那么存盘的cookie将被删除
```＜meta http-equiv="Set-Cookie"content="cookievalue=xxx;expires=Wednesday, 20-Jun-2007 22:33:00 GMT； path=/"＞```

    5)	Window-target(显示窗口的设定 强制页面在当前窗口以独立页面显示 用来防止别人在框架里调用自己的页面)
```＜meta http-equiv="Window-target"content="_top" /＞```
---
## **22.	Js 有哪些引入方法？放在head里面跟body里面有啥区别？放在body的开头跟结尾有啥区别？**
- 引入方法：

    1.	外部引入：```<script type=”text/javascript” src=”name.js”></script>```

    2.	内部标签：```<script>填写代码</script>```

    3.	直接在HTML标签中插入代码：```<a href=”#” onclick=”javascript:alert(‘hello’);”>```
- 放在head里会让js比网页body更早被解析，如果js定义了全局变量并调用了body中某一元素，这时因为body还未被解析，所以会报错undefined。
- 因为js脚本会阻塞其他资源下载（图片等）和页面渲染，出于js对页面下载性能方面考虑，会尽量把script标签放在body最后运行，这样前面的资源和渲染完成后才会运行脚本。
---
## **23.	Role的作用**
- Role的作用是增强语义性，当现有HTML标签无法充分表达语义性时，可以使用role来说明。
- 例如：将div当做button使用时，可以设置div的role=”button”来表明作用为按钮。
- 另一个作用是提供无障碍阅读，为阅读障碍人士设置的属性，类似于img的alt，可被读屏软件解析。
---
## **24.	White-space？**
- 属性设置

    1.	Normal：所有空格、回车、tab都合并成一个空格，文本自动换行。

    2.	Nowrap：所有空格、回车、tab都合并成一个空格，文本不换行。

    3.	Pre：所有东西原样输出，文本不换行。

    4.	Pre-wrap：所有东西原样输出，文本换行。

    5.	Pre-line：所有空格、tab合并成一个空格，回车不变，文本换行。
- 经常搭配overflow:hidden; text-overflow:ellipsis使超出文本省略。
---
## **25.	flex-order?**
- 属性定义flex里项目的排列顺序，数值越小，排列越靠前，可设定为负数，默认为0。
---
## **26.	linear-gradient函数**
- 线性渐变：以直线的渐变方式。表达式linear-gradient（角度，颜色）。
- 角度可设为：to 正角度（top/bottom/right/left），to 四角（例bottom left）角度值（0~360deg）。
- 颜色最少两个，可无限增加。可在颜色后添加出现位置（例70%），或像素值（例20px）。
- 径向渐变（radial-gradient）为以圆心的渐变方式。
---
## **27.	document.querySelector和document.getElementById**
- 都是元素选择器。
- querySelector取得结果为静态，对元素的操作并不会影响结果。
- getElementById取得结果为动态，对元素进行操作会影响最终结果
