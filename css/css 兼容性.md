 # 浏览器 兼容性

## 浏览器内核

五大浏览器内核代表作品

### Trident

  IE、Maxthon(遨游)、Theworld世界之窗、360浏览器

### Gecko

代表作品Mozilla Firefox 是开源的,它的最大优势是跨平台，能在Microsoft Windows、Linux和MacOS X等主要操作系统上运行。

### Webkit 

代表作品Safari、Chrome ， 是一个开源项目。

### Presto

 代表作品Opera ，Presto是由Opera Software开发的浏览器排版引擎。它也是世界上公认的渲染速度最快的引擎。

### Blink 

由Google和Opera Software开发的浏览器排版引擎，2013年4月发布

## 兼容性的由来

​	由于各大主流浏览器由不同的厂家开发，所用的核心架构和代码也很难重和，这就为各种莫名其妙的Bug(代码错误）提供了温床 

## CSS Bug、CSS Hack和Filter

### css bug

​	CSS样式在各浏览器中解析不一致的情况，或者说CSS样式在浏览器中不能正确显示的问题称为CSS bug. 

### css hack 

​	CSS中，Hack是指一种兼容CSS在不同浏览器中正确显示的技巧方法，因为它们都属于个人对CSS代码的非官方的修改，或非官方的补丁。也可使用patch(补丁)来描述这种行为

## filter

​	表示过滤器的意思，它是一种对特定的浏览器或浏览器组显示或隐藏规则或声明的方法。本质上讲，Filter是一种用来过滤不同浏览器的Hack类型

## IE6常见bug

### 1.图片间隙 

描述：在div中插入图片时，图片会将div下方撑大三像素

~~~css
hack1:将</div>与<img>写在一行上；
hack2:将<img>转为块状元素，给<img>添加声明：display:block;
~~~

### 2.双倍间距

描述：当Ie6及更低版本浏览器在解析浮动元素时，会错误地把浮向边界加倍显示。

~~~css
hack：给浮动元素添加声明：display:inline;
~~~

### 3.默认高度

描述：在IE6及以下版本中，部分块元素拥有默认高度（低于18px高度） 

~~~css
hack1：给元素添加声明：font-size:0;
hack2：给元素添加声明：overflow:hidden;
~~~

### 4.表单元素行高不一致

描述：表单元素行高对齐方式不一致

~~~css
hack:给表单元素添加声明：float:left;
~~~

### 5.按钮元素默认大小不一

描述：各浏览器中按钮元素大小不一致 

~~~css
hack1： 统一大小/（用a标记模拟）
hack2：在input上写按钮的样式，一定要把input的边框去掉。
hack3：如果这个按钮是一个图片，直接把图片作为按钮的背景图即可。
~~~

### 6.百分比bug

描述：在IE6及以下版本中在解析百分比时，会按四舍五入方式计算从而导致50%加50%大于100%的情况。

~~~css
hack:  给右面的浮动元素添加声明：clear:right;   
~~~

### 7.鼠标指针bug 

描述：cursor属性的hand属性值只有IE浏览器识别，其它浏览器不识别该声明，cursor属性的pointer属性值IE6.0以上版本及其它内核浏览器都识别该声明 

~~~css
hack：如统一某元素鼠标指针形状为手型，应添加声明：cursor:pointer;
~~~

### 8.透明属性 

IE浏览器写法：filter:alpha(opacity=value);取值范围 1-100

兼容其他浏览器写法：opacity:value;(value的取值范围0-1,0.1,0.2,0.3-----0.9)

# 表单表格高级

## 1.表格高级

~~~css
A.单元格间距：border-spacing:value; 
B.合并相邻单元格边框：border-collapse:separate/collapse;
C.无内容时单元格的设置：empty-cells:show/hide;
D.显示单元格行和列的算法(加快运行的速度)： table-layout:auto/fixed;
E.<caption>标题内容</caption>
F.rules="groups/rows/cols/all/none" 添加组分隔线
G.列分组<colgroup span="value"></colgroup> 
H.数据行分组
<thead></thead> 表头
<tbody></tbody> 表体
<tfoot></tfoot> 表尾
~~~

## 2.表单高级

~~~css
A、表单字段集：<fieldset disabled="disabled"></fieldset>
B、字段级标题：<legend ></legend>
C、提示信息标签：<label for="绑定控件id名"></label>
D、上传文件框：<input type="file" multiple="multiple" />
~~~

# 常见浏览器兼容情况

## 1.盒模型属性

```css
(全兼容)width、height、border、border-width、border-color、border-style、margin
```

~~~css
(IE6-不支持)：min-width、max-width、min-height、max-height
~~~

## 2.布局类属性

~~~css
(全兼容)display、float、clear、position、left、righttop、bottom、z-index、			   overflow、overflow-x、overflow-y、clip、visibility
~~~

~~~css 
IE6-不支持：固定定位position:fixed
IE7-浏览器不支持:table类属性值
(IE不支持)：resize
~~~

## 3.文本类属性

~~~css
(全兼容)：font、font-family、font-size、font-style、font-variant、font-weight、		  line-height、@font-face、text-indent、text-align、vertical-align、			 word-spacing、letter-spacing、text-transform、text-decoration、
		 white-space、text-overflow
~~~

~~~css
IE7-浏览器中vertical-align的百分比值不支持小数行高
~~~

## 4.修饰类属性

~~~css
(全兼容)：background、background-color、background-image、background-repeat、			 background-position、color、命名颜色、16进制、RGB、cursor
~~~

~~~css
(IE8-不支持)：background-attachment、background-clip、background-size、opacity、			RGBA、
~~~

## 5.其它类属性

~~~css
(全兼容)：通配选择器*、元素选择器div、类选择器.box、ID选择器#box、后代选择器div a、
		并集选择器 h1,p、 :link  :visited
		单位px in cm mm q pt pc em ex ch		
~~~

~~~css
(IE6-不支持)：属性选择器h1[class]、子元素选择器ul > li、相邻兄弟选择器div + p、
			(只有当选择器部分和左大括号之间有空格时，IE6-浏览器才支持):first-letter
			:first-line
			(IE6-不支持给<a>以外的其他元素设置伪类):hover  :active  
(IE7-不支持)：普通兄弟选择器div ~ p 、:before   :after  
(IE8-不支持)::selection rem
~~~

























 

