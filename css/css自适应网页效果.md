# 高度塌陷

含义：若父元素没有设置高度，全凭借子元素来撑起来，那么当子元素浮动时，父元素就失去了高度。

# 自适应网页效果

含义：元素的大小能够根据窗口或子元素自动调整，这就是自适应。

自适应的优点：
能够使网页显示更灵活，可以适应在不同设备、不同窗口和不同分辨率下显示。

## 宽度自适应

   元素宽度设置为100%。（块元素宽度默认为100%）或者不设置宽度（width）;（宽度是父元素的宽度）

## 高度自适应

        ### 自适应元素高度

1. height:auto;或者不设置;（是子元素撑开父元素的高度） (父元素高度跟随子元素的变化而变化)
2. 元素高度自适应窗口高度(子元素的高度跟随父元素的变化而变化)-- 开发app页面使用次数较多

```html
设置方法：html,body{height:100%;}       
	<style>
		html,body{height:100%;}
		div {background:red;height:100%;}
	</style>
	<body>
		<div></div>
	</body>
    注：全屏页面才推荐使用高度100%的方式去开发。 如果设置子元素的高度跟随父元素的高度变化而变化，那么父元素必须有高度
```
3. 元素具备最小高度的自适应


```css
min-height属性：最小高度；(IE6浏览器不识别该属性)
hack1:min-height:value;_height:value;
hack2:min-height:value;  height:auto!important;height:value;  
```


```css
max-width: 最大宽度
max-height: 最大高度
```

4. 浮动元素父元素高度自适应（高度塌陷）

```css
 	当子元素有浮动并且父元素没有高度或者加最小高度（min-height:）的情况下父元素会出现高度塌陷hack1：给父元素添加声明
 	overflow:hidden;
    弊端：会隐藏一些定位在内容区域外侧的元素
    
hack2:在浮动元素下方添加空div,并给该元素添加声明：
	div{clear:both; height:0; overflow:hidden;}
这种声明方式在写网页的时候，可以有效的兼容ie6，ie6即是高度没有，也会保留大概6px的高度，只有height:0;和overflow:hidden;搭配使用才可以解决这样的问题。
    弊端：增加代码的冗余，大量存在一些不必要的元素。
hack3:万能清除浮动法
选择符:after{content:"";clear:both;display:block;height:0;
			overflow:hidden;visibility:hidden;}
也可以加上 .clearfix{*zoom:1;} 解决ie的问题
```
## 隐藏visibility:hidden

```css
visibility:hidden;属性会使对象不可见，但该对象在网页所占的空间没有改变，等于留出了一块空白区域
display:none;属性会使这个对象彻底消失不显示，也不再占用位置。
```

## 伪类选择符(伪元素/伪对象)

通常用在块级元素上面
:after 与content属性一起使用，定义在对象后的内容
:before 与content属性一起使用，定义在对象前的内容
:first-line  定义对象内第一行的样式
:first-letter 定义对象内第一个字符的样式