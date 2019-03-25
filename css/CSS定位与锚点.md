# 权重

## 继承

1. 可以继承的属性：color   text-开头的   line-开头的  font-开头的与文字相关的属性大都可以继承，但浮动和定位的属性完全不能被继承
2. 如果选择器没有直接选中目标元素，而是通过继承去影响的，则权重为零
3. 如果权重一样的，谁在后面听谁的
4. 如果选择器直接选中了目标元素，则比权重大小
5. 如果多个选择器都是通过继承去影响的，谁离目标元素近则听谁的
6. class里面的类名与顺序无关

## ！important

​	如：div {color:red !important;}则它的权重无限大

注：不能乱用，尽量少用

​	能够提升某个单独的属性的权重，不能提高选择器的权重

​	不影响就近原则

# CSS定位position

## 相对定位relative

### 定义

元素会相对于自己原来的位置进行移动（四个值left right top bottom），并且不会脱离标准文档流，即原来的位置还在

### 作用

1. 微调元素位置
2. 作为绝对定位的参考点

### 举例

~~~css
div {
	position:relative;
	top:12px;
	left:12px;
}
~~~

## 绝对定位absolute

### 说明

采用绝对定位的元素会脱离标准文档流

### 需要参考点

1. 没有父元素：top为首屏屏幕（页面而不是浏览器）的左上角作为参考

   ​		    bottom为浏览器窗口首屏窗口尺寸页面的左下角

2. 存在父元素：浏览器就会从当前使用绝对定位的元素开始一层一层的去找，父元素没有就找祖先元素，直到找到某个祖先元素的身上具有相对定位或绝对定位的属性，那么这个祖先元素就作为参考点进行位移，如果没有找到，就以网页作为参考点进行位移

### 举例

~~~css
div {
	position:absolute;
	top:12px;
	left:12px;
}
~~~

###说明

 	1. 子元素使用绝对定位，父元素最好使用相对定位。如果父元素和子元素都是用了绝对定位，哪么就会造成网页的不稳定
 	2. 绝对定位的子元素，如果作为参考元素的父元素设置了padding，除非子元素没有设置一些唯一参数。例如top ，left 等，那么就会被padding影响，可是一旦设置了位置参数，将不会受到影响

### 绝对定位元素如何居中

绝对定位的盒子居中，需要left=50%，margin-left= - 宽度的一般

## 固定定位fixed

### 含义

将某个元素固定在浏览器的某个确定（通过调整top bottom left right来改变位置）的位置，不随滚动条的移动而变化。（IE6不兼容）

### 用途

返回顶部，广告等

### 举例

~~~css
div {
	position:fixed;
	top:12px;
	left:12px;
}
~~~

## 粘性定位sticky

### 定义

是相对定位和固定定位的结合体，当元素处于屏幕范围之内，元素的定位就相当于相对定位，而元素一旦脱离了屏幕范围，那元素的定位属性就会类似于固定定位。

# Z-index 层级关系

## 3种情况

1. 若单纯的比较两个发生未知冲突的标签，谁的z-index值大，谁就在上面
2. 若两个子元素发生位置冲突，则看父元素的层级关系，谁的父元素z-index值大，谁的子元素就在上面，父元素的层级小，子元素的层级再高也没有办法。
3. 若两个父元素发生位置冲突，且一个父元素的层级没有设置，则子元素可以通过z-index盖过与之发生冲突的另外一个元素

# overflow溢出隐藏

五个属性值：

## visible默认值

​	当容器内容溢出了容器时，不采取任何行动，任由内容溢出。在ie7- 会存在另外一种情况，使用button 按钮或者input type=button 这两种类型的按钮，都会出现按钮当中字越多，按钮两边的padding越大。
	解决:overflow:visible;

## hidden

将溢出的内容隐藏，位置也隐藏，不占位置

overflow失效:
	当子元素处于绝对定位的状态，并且溢出了父元素。这个时候父元素的overflow:hidden或者其他属性都会失效。
	解决方案:给需要溢出隐藏的包含块设置position:relative;总结：overflow主要用来解决溢出的问题，溢出可以分两种，一种是文字溢出，一种是元素溢出。

## scroll

滚动，如果存在溢出的内容，将以滚动条的形式展示。、

注：在ie8+ 还有火狐浏览器 在解释overflow:scroll或者overflow:auto的时候会存在padding-bottom的缺失

## auto

自动，若存在溢出的内容则出滚动条，若不溢出，不出滚动条

## inherit

继承

~~~css
overflow-x:visible/hidden/auto/scroll  
overflow-y:visible/hidden/auto/scroll 
能够通过这两个属性单独的设置某一个方向的溢出。
~~~

# 空余空间white-space

6个属性值， 该属性用来设置如何处理元素内的空白

## normal

空白折叠

## nowrap

强制将文本放在一行显示，如果没有碰到br，就会一直在一行显示。除非遇到br 标签才换行

## pre

按照原内容显示，浏览器 会自动换行

## pre-wrap

类似于pre标签，会保留空白符，但内容会自动换行

## pre-line

空白折叠，合并空白字符，但会保留换行符

## inherit

继承

# 省略号text-overflow

## 属性值

1. clip（剪） 不显示省略号
2. ellipsis      显示省略号

## 运用条件

1. 要有明确的宽度
2. 内容必须在一行显示 ，即white-space:nowrap;
3. 溢出的元素要隐藏掉，即overflow:hidden;
4. 才是设置text-overflow:ellipsis; 溢出内容显示为省略号

# a标签锚点定位

## 概念

​	<a>元素 (或HTML锚元素, Anchor Element)通常用来表示一个锚点/链接。但严格来说，<a>元素不是一个链接，而是超文本锚点，可以链接到一个新文件、用id属性指向任何元素。如果没有<a>元素没有href属性的话，可以作为原本链接位置的占位符，常用于home链接

​	注：任何文档流内容都可以被嵌套，只要不是交互内容类别(如按钮、链接等)

## href属性（表示地址）

### 链接地址

~~~html
<a href="http://www.baidu.com">百度</a>
~~~

### 下载地址

~~~html
<a href="test.zip">下载测试</a>
~~~

### 锚点

#### href:#id名

~~~html
<a href="#test">目录</a>
<br>内容<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div id="test" style="height: 200px;width: 200px; border: 1px solid black;margin-bottom: 300px;">内容</div>
~~~

####href：页面地址#ID名

~~~html
<a href="http://baike.baidu.com/view/2202.htm#2">足球比赛规则</a>
~~~

### href与src的区别

​	href(hypertext reference)指超文本引用，表示当前页面引用了别处的内容

  src(source)表示来源地址，表示把别处的内容引入到当前页面

  所以<img>、<script>、<iframe>等应该使用src，而<a>和<map>应该使用href

  注意：href属性一定不要留空，若暂时不需要写地址，则写`#`或`javascript:;若href留空，会刷新页面

### 手机号码

​	在移动端，使用<a href="tel:15012345678>15012345678</a>可以唤出手机拨号盘

### target

target属性表示链接打开方式

  1、_self  当前窗口（默认）

  2、_blank  新窗口

# 圆角边框

border-radius:50%;元素宽高一样

# display转换元素

|       属性值       |                 描述                 |
| :----------------: | :----------------------------------: |
|        none        |          c此元素不会被显示           |
|       block        |            转换为块级元素            |
|       inline       |         默认，转换为行内元素         |
|    inline-block    |           转换为行内块元素           |
|     list-item      |            列表显示，如li            |
|       run-in       | 根据上下文作为块级元素或行内元素显示 |
|       table        |             块级表格显示             |
|  table-row-group   | 一个或多个行的分组显示，类似于tbody  |
| table-header-group | 一个或多个行的分组显示，类似于thead  |
| table-footer-group | 一个或多个行的分组显示，类似于tfoot  |
|     table-row      |       一个表格行显示，类似于tr       |
| table-column-group |   一个表格单元格列显示，类似于col    |
|     table-cell     |   一个表格单元格显示，类似于th td    |
|   table-caption    |   一个表格标题显示，类似于caption    |
|      inherit       |     从父元素继承display属性的值      |





