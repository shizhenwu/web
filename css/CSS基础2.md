# CSS基础2

## 盒子模型

所有的标签都可以看成是一个盒子，一个盒子包含了五个关键词：

width 内容的宽度

height 内容的高度

border 边框

padding 内边距（盒子与内容之间的距离）

margin 外边距（盒子与盒子之间的距离）

### border边框

~~~html
写法一：
	如border：1px solid red; 表示边框的宽度为1px, 颜色为红色的实线边框 
写法二：
	如border-width:1px; 表示边框的宽度为1px
	  border-style:solid; 表示边框的线型为实线
	  border-color:red; 表示边框的颜色为红色
写法三：border-top:1px solid red; 表示上边框的宽度为1px, 颜色为红色的实线边框
	   border-right:1px solid red; 表示右边框的宽度为1px, 颜色为红色的实线边框
	   border-bottom:1px solid red; 表示下边框的宽度为1px, 颜色为红色的实线边框
	   border-left:1px solid red; 表示左边框的宽度为1px, 颜色为红色的实线边框
写法四：border-top-width:1px; 表示上边框的宽度为1px
	   border-top-style:solid; 表示上边框的线型为实线
	   border-top-color:red; 表示上边框的颜色为红色
	   同理还有右、下、左边框的宽度，线型，颜色
注：border使用后会增加盒子实际所占的宽度和高度，如果不想改变原有盒子的宽度和高度，就需要减少盒子的宽度和高度
~~~

### padding内边距

~~~html
写法一：
	如padding：10px; 表示上右下左的内边距都为10px
	  padding:10px 20px; 表示上下内边距10px,左右内边距20px
	  padding:10px 20px 30px; 表示上内边距px,左右内边距px,下内边距30px
      padding:10px 20px 30px 40px; 表示上内边距10px,右边距20px,下内边距30px，左内边距40px
写法二：
	如padding-top:10px; 表示上内边距10px
	  padding-right:10px; 表示右内边距10px
	  padding-bottom:10px; 表示下内边距10px
	  padding-left:10px; 表示左内边距10px
注：padding使用后会增加盒子实际所占的宽度和高度，如果不想改变原有盒子的宽度和高度，就需要减少盒子的宽度和高度
~~~

### margin外边框

~~~html
写法及含义同padding
通过margin:0 auto;的设置可以让元素居中对齐,但需要注意以下几点：
	必须有明确的宽度设置
	只有在标准文档流中才有效果，一旦元素设置了浮动，相对定位，固定定位就不能使用了
	只是让盒子居中，若要让文字居中用text-align:center;
~~~

## 行内元素和块级元素

出现原因：文档流

### 标准文档流

#### 内容

元素（标签）在排版（浏览器解析）的时候，顺序是从上往下，从左往右的

#### 微观现象

1. 空白折叠
2. 高矮不齐，底边对齐
3. 自动换行，一行写不满就换行写

#### 等级问题

行内元素和块级元素

### 行内元素的特性

1.  无法设置宽度和高度，只能凭借内容撑起来，若没有内容则会缩成一小条
2. 多个行内元素可以并排显示

### 块级元素的特性

1. 可以设置宽度和高度
2. 若没有设置宽度，则默认占满当前屏幕宽度的百分百
3. 若没有设置高度，则会缩成一条横线，也可靠内容来撑

### 常用举例

行内元素：b	span    em	i   u  s   a 等

块级元素：div   p   h1~h6   ul~li   ol~li	dl~dt~dd等 

### 二者的相互转换

行内元素→→块级元素	display:block;

块级元素→→行内元素	display:inline;

行内元素、块级元素→→行内块元素	display:inline-block;

注：行内块元素既可以设置宽高，又可以并排显示

## 浮动float

html网页中对于元素的种种限制，其实都来自标准文档流，例如行内元素不能设置宽高等，那么想要摆脱这种限制，则需要脱离标准文档流

### 脱离标准文档流的方法

1. 浮动
2. 绝对定位
3. 固定定位
4. 相对定位（半脱离文档流）

### 浮动的属性及属性值

float:left; 左浮动

float:right; 右浮动

float:none; 默认不浮动

### 浮动的特性

1. 让元素脱离标准文档流（行内元素也可设置宽高）
2. 浮动会让元素相互紧贴（高矮不齐顶对齐）
3. 会存在字围现象（浮动脱离了标准文档流，但没有脱离标准文字流）
4. 收缩现象

### 浮动元素带来影响的解决办法

浮动会使网络布局的结构不稳定，解决办法如下：

~~~html
1. 给父元素（必须是子元素发生了浮动）设置一个具体的高度
2. 使用clear属性
   .clear {
   	clear:both;
   }		给受影响的元素设置属性去掉浮动带来的影响
   	内墙法：两个元素之间插入：
   			<div class="clear"></div>
   	外墙法：浮动的第一个标签后面插入：
   			<div class="clear"></div>
3. 使用:after   :before 属性
   .one:before {
   	content:" ";
   }
   .one:after {
   	content:" ";
   }
4. overflow:hidden;  溢出隐藏
5. 出现浮动的标签：
   .clearfix {
		*zoom:1;
   }
   .clearfix:before , .clearfix:after{
   		content:" ";
		display:table;
   }
   .clearfix:after {
   	clear:both;
   }
~~~

## margin塌陷

margin塌陷只发生在标准文档流中，一旦元素脱离了标准文档流，塌陷也就不存在了

### 第一种

​	对于两个垂直并排的盒子，上面盒子设置margin-bottom:50px;下面盒子设置margin-top:20px;则两个盒子的外边距不是所谓的简单相加70px，而是由于发生了margin高度塌陷，他们的外边距为两者数值中较大的那个，也及外边距为50px

​	上述情况如果给两个盒子都设置了浮动等，让其脱离标准文档流后，两个盒子的外边距就是70px

### 第二种

​	对于同为块级元素的父元素和子元素中若父元素没有设置边框，默认状态子元素紧贴着父元素，若想让父元素与子元素之间有一定距离，使用了margin-top结果并不能实现，因为此时父元素会盒子元素一起移动。

解决办法：可以使用padding来解决，及把子元素看成是一个文本。

## 行高

### line-height=height

此时可以让单行文本垂直居中

### line-height=font-size

此时可以让文本上下间距为零

### 多行文本垂直居中

首先计算padding-top=（盒子高度-总行高）/2，然后盒子的高度修改为减去padding-top之后的高度















