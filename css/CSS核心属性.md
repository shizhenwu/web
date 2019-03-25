# CSS核心属性

# 属性和属性值的定义

- 属性：属性是指定选择符所具有的属性，它是css的核心

- 属性值：属性值包括法定属性值及常见的数值加单位，如25px，或颜色值等。

- # 文本属性

- ## 文本大小：{font-size:12px;} 

- 单位还可以是em，是父级元素的font-size的倍数；系统默认的字号大小为16px ,即1em.默认情况下，1em=16px，  0.75em=12px

- ## 文本字体：{font-family:字体1，字体2，字体3；}

- ​	浏览器首先会寻找字体1、如存在就使用改字体来显示内容，如在字体1不存在的情况下，则会寻找字体2，如字体2也不存在，按字体3显示内容，如果字体3 也不存在；则按系统默认字体显示.

- 注：当字体是中文字体时，需加双引号；

-  	当英文字体由多个单词组成时，需加双引号如（“Times New Roman”） 

- ​	当英文字体只有一个单词组成是不加双引号；如：（Arial）； Windows中文版本操作系统下，中文默认字体为宋体或者新宋体，英文字体默认为Arial. 

- ## 文本颜色：{color:颜色值;}red/#f00/rgb(255,0,0) 

- 1. 用十六进制(是计算机中数据的一种表示方法)表示颜色值：

     0 1 2 3 4 5 6 7 8 9
     0 1 2 3 4 5 6 7 8 9 A B C D E F

  2. 颜色模式：光色模式

     R G B
     FF 00 00
     颜色值的缩写：
     当表示三原色的三组数字同时相同时，可以缩写为三位;
     当用十六进制表示颜色值时，需要在颜色值前加“#”
     \# fa 00 00

  3. RGB表示方式：color:rgb(255,0,0);

     ## 文字加粗font-weight 

     值：normal 正常

     ​	bold	   加粗

     ​	bolder  更粗的

     ​        100-900的整数数值，把字体的粗细分为9个等级，分别为100—900，其中100对应最轻的字体变形，而900对应最重的字体变形

     ## 文本倾斜：font-style  

     值：italic   倾斜字（字体本身就是斜的）

     ​	oblique  倾斜（让现有字体发生倾斜）

     ​	normal（取消倾斜，常规显示）

     ## 字体水平对齐方式text-align  

     值：left     左

     ​	right  右

     ​	center  居中

     ​	justify  两端对齐(在部分浏览器中，对于中文不起作用)

     注：只针对文本或图片 

     ## 垂直对齐方式vertical-align 

     值：top         上

     ​	bottom  下

     ​	middle   居中

     ​	baseline基线（默认值 ，某些特定的元素类型起作用）

     ## 文字行高 line-height 

     如： line-height:20px; 

     ​        line-height:2em; (当行高的单位省略时，默认为em) 

     注：当行高等于容器的高度时，可以实现单行文本垂直居中

     ​       当行高小于容器的高度时，单行文本偏上

     ​       当行高大于容器的高度时，单行文本偏下

     ## 文本修饰 text-decoration 

     值：none:   没有修饰 

     ​	underline: 添加下划线 

     ​	overline: 添加上划线 

     ​	line-through: 添加删除线 

     ## 首行缩进ext-indent 

     数值：

     ​	text-indent可以取负值；

     ​	text-indent属性只对第一行起作用

     ## 检索英文字母大小写text-transform 

     值：none 无转换

     ​	capitalize首字母大写

     ​	uppercase全都大写

     ​	lowercase全都小写

     ## 字间距letter-spacing 

     数值控制英文字母或汉字的字距，可以为负值，单位用px

     ## 词间距word-spacing 

     数值用来控制英文单词词距

     ## 文本流控制layout-flow  

     值：horizontal   自左向右

     ​	vertical-ideographic  自上而下

     ## 文字属性简写

     font：字号，行高，字体 

     注：font的属性值应按以下次序书写(各个属性之间用空格隔开) 顺序: font-style font-weight font-size / line-height font-family  字体和字号是必备 

     ## 列表属性

     1. 定义列表符号样式

        list-style-type：disc(实心圆)

     ​			circle(空心圆)

     ​			square(实心方块)

     ​			none(去掉列表符号)

     2. 使用图片作为列表符号

        list-style-image：url(所使用图片的路径及全称)；

     3. 定义列表符号的位置

        list-style-position: outside(外边ul里)

        ​			     inside(里边li里)

        list-style:none;去掉列表符号

     ## 边框

     border-width边框宽度 

     border-style边框风格   

     ​		     属性值：solid(实线)

     ​				    dashed(虚线)

     ​				    dotted(点划线)

     ​				    double(双线)

     ​				     none(去掉边框);

     border-color边框颜色

     连写：border:边框宽度 边框风格 边框颜色

     ​	如：border:5px solid #ff0000 ;

     可单独设置一方向边框：

     border-bottom:边框宽度 边框风格 边框颜色;      底边框

     border-left:边框宽度 边框风格 边框颜色;             左边框

     border-right:边框宽度 边框风格 边框颜色;          右边框

     border-top:边框宽度 边框风格 边框颜色;           上边框

     ## 背景属性background

     ### 1.背景颜色 background-color

     ###2.背景图片background-image

     ​	background-image：url(背景图片的路径及全称）

     ​	注：给一个标签设置背景图片时一定要设置宽高，否则图片出不来

     ### 3.背景图片是否平铺background-repeat

     ​	值：no-repeat   不平铺

     ​		repeat  平铺

     ​		repeat-x  X轴平铺

     ​		repeat-y   Y轴平铺 

     ###4.背景图片位置background-position

     ​	<1>方位值：left/center/right/数值      top/center/bottom/数值

     ​	<2>数值background-position:值1 值2; 两个值 ：第一个值表示水平位置的值，第二个值：表示垂直的位置.当两个值都是center的时候写一个值就可以代表的是水平位置和垂直位置.

     #### 雪碧图，CSS蓝精灵

     讲多张小图片放在一张大图片上，通过position属性的属性值进行位置的移动，只需要把需要的一小部分显示出来，从而减少向服务器发起请求的次数

     ### 背景图的固定background-attachment

     ​	值：fixed固定,不随内容一块滚动，根据可视窗口固定位置

     ​		scroll滚动,随内容一块滚动

     ### 背景样式连写background：color  url( )  no-repeat center top 

     ## 网页上常用的图片格式

     ​	1）jpg :有损压缩格式，靠损失图片本身的质量来减小图片的体积，适用于颜色丰富的图像(像素点组成的，像素点越多会越清晰 )
     	2）gif：无损压缩格式，支持透明，支持动画，适用于颜色数量较少的图像
     	3）png:无损压缩格式，支持透明，不支持动画，(是fireworks的 源文件格式)，适用于颜色数量较少的图像;

     ## CSS浮动属性

     ~~~html
     语法：float:none/left/right; 
     浮动的目的：就是让竖着的元素横着显示
     一个元素设置了float：left/right;元素会脱离文档流（半脱离），不占空间；
     有三个取值：
     left:元素向左浮动
     right:元素向右浮动
     none:默认值，不浮动
     ~~~

     ### 清除浮动（打破横向排列）

     ~~~html
     清除浮动的属性是clear，语法：
     clear : none | left | right | both
     none:默认值。允许两边都可以有浮动对象
     left:清除左浮动/不允许左边有浮动对象
     right:清除右浮动/不允许右边有浮动对象
     both:清除两端浮动/不允许有浮动对象
     注：对于CSS的清除浮动(clear)，一定要牢记：这个规则只能影响使用清除的元素本身，不能影响其他元素
     ~~~

     

     - 

     