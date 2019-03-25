# html5

## 兼容性问题

​	支持Html5的浏览器包括Firefox（火狐浏览器），IE9及其更高版本，Chrome（谷歌浏览器），Safari，Opera等；国内的 遨游浏览器（Maxthon），以及基于IE或Chromium（Chrome的工程版或称实验版）所推出的360浏览器、搜狗浏览器、QQ浏览器、猎豹 浏览器等国产浏览器同样具备支持HTML5的能力。 

## 语法

### 内容类型（ContentType） 

HTML5的文件扩展符与内容类型保持不变，仍然为".html"或".htm"。 

### DOCTYPE声明 

不区分大小写 

### 指定字符集编码 

meta charset="UTF-8" 

### 可省略标记的元素 

不允许写结束标记的元素：br、col、embed、hr、img、input、、link、meta	

 可以省略结束标记的元素：li、dt、dd、p、option、colgroup、thead、tbody、tfoot、tr、td、th  

可以省略全部标记的元素：html、head、body、colgroup、tbody 

### 省略引号 

属性值可以使用双引号，也可以使用单引号。 

## HTML5 新增语义化标签

section元素 表示页面中的一个内容区块 

article元素 表示一块与上下文无关的独立的内容 

aside元素 在article之外的，与article内容相关的辅助信息 

 header元素 表示页面中一个内容区块或整个页面的标题 

footer元素 表示页面中一个内容区块或整个页面的脚注 

nav元素 表示页面中导航链接部分 

figure元素 表示一段独立的流内容，使用figcaption元素为其添加标题(第一个或最后一个子元素的位置) 

main元素 表示页面中的主要的内容 (ie不兼容) 兼容低版本浏览器： 

~~~html
<script src=“html5.js”></script> 
~~~

# Video和audio的应用

## video元素 定义视频

~~~html
<video src="movie.ogg" controls="controls"></video>
    
~~~

## audio元素 定义音频

~~~html
<audio src="someaduio.wav">Audio元素</audio>  
~~~

 controls属性：如果出现该属性，则向用户显示控件，比如播放按钮。 

autoplay属性：如果出现该属性，则视频在就绪后马上播放。 

loop属性：重复播放属性。 

muted属性：静音属性。 

poster属性：规定视频正在下载时显示的图像，直到用户点击播放按钮。 

