# HTML基础

## 浏览器发展史

1. 网景浏览器，网景公司开发的浏览器，称为领航者。
2. IE浏览器，盖茨开发的。
3. firefox火狐浏览器。
4. google浏览器。
5. 升级IE的浏览器。

## HTML概念

(Hyper Text Markup Language)超文本标记语言，是用来描述网页的一种语言

  1. 超文本(Hyper Text):不只包括文本，也可以包括图片、链接、音乐、视频等非文本元素
  2. 标记语言(Markup Language):标记语言是一套标记标签，HTML使用标记标签来描述网页
## 访问网站要经历的流程

1. 输入网址
2. 发起请求
3. DNS解析（将网址转换成IP地址）
4. 分析请求
5. 正常则返回数据

##一个网站从前端的角度来看包含的内容

1. HTML（结构）负责网页的结构搭建

2. CSS（表现）负责网页的修饰和美化

3. JS（行为）javascript 负责网页的交互

   拓展内容 ：组织解析：
        （1）W3C( World Wide Web Consortium )万维网联盟，创建于1994年是Web技术领域最具权威和影响力的国际中立性技术标准机构。W3C (制定了结构(xhtml、xml)和表现(css)的标准，非赢利性的。)
        （2）ECMA(European Computer Manufactures Association) 欧洲电脑场商联合会。ECMA制定了行为(DOM(文档对象模型)，ECMAScript)标准

   ​     （3）WHATWG网页超文本应用技术工作小组是：一个以推动网络HTML 5 标准为目的而成立的组织。在2004年，由Opera、Mozilla基金会和苹果这些浏览器厂商组成。

## 如何创建一个网页

1. 新建一个文本文档
2. 改后缀名为  .html
3. 选择编辑器打开编辑内容
4. 完成后选择用浏览器打开

## html的主体结构

~~~html
<!DOCTYPE HTML>	文档声明头，说明用的是html5的代码
<html>	根标签
<head>	网页的设置信息，给浏览器看的
    <meta charset="utf-8">	设置当前的编码格式，让中文不再乱码
    <title></title>	网页的标题
</head>	
<body>	网页的主题内容，给用户看的
</body>
</html>
~~~

## html标签分类

#### 核心：语义化（从标签代表的意义上选择标签，而不是根据标签的样式来决定）

1. 文本标签

   <h1>LOGO</h1> 
   <h2>二级标题</h2> 
   <h3>三级标题</h3> 
   <h4>四级标题</h4> 
   <h5>五级标题</h5>
   <h6>六级标题</h6>

   注：文本标题标签自带加粗，有自己的文本大小，并且独占一行，有默认间距

2. 段落标签

   <p>段落文本内容</p> 标识一个段落(段落与段落之间有段间距) 

3. 换行

   <br >换行是一个空标记(强制换行) ，在网页中无论是中文还是英文，浏览器都会自动甄别当前的词汇是否已经结束，若没有，并且后面空间不足以显示下一个词汇，那么浏览器就会自动换行。如果写的英文没有使用空格，则浏览器就不能识别出来，也就不会换行。

4. 水平线

   <hr >单标签

5. 空格（实体字符）

   ~~~html
   &nbsp;
   表示一个空格，如果需要几个空格，就写几个&nbsp;
   ~~~

   空白折叠现象：在代码中使用的多个空格最终在网页中合并成一个空格显示出来

6. 加粗

   <b>加粗内容</b>只是显示加粗

   <strong>强调的内容</strong>突出的文本 

7. 倾斜

   <em>强调文本</em>

   <i>倾斜文本</i>

8. 扩展了解

   <u></u>下划线

   <del></del>删除线

   <s></s>删除线

   <sub></sub>下标

   <sup></sup>上标

9. **列表(ul,ol,dl)** 

   ~~~html
   无序列表组成：
   
   <ul>(unordered list)
   
   <li></li>
   
   <li></li>
   
   ．．．．．．
   
   </ul>
   
   
   *有序列表
   
   有序列表组成：
   
   <ol>(ordered list)
   
   <li></li>
   
   <li></li>
   
   ．．．．．．
   
   </ol>
   
   *自定义列表
   <dl>(definition list)
   	<dt>名词</dt>
   		<dd>解释</dd>
   		(definition description)
   		．．．．．．
       <dt>名词</dt>
   		<dd>解释</dd>
   		．．．．．．
   </dl>
   ~~~

   拓展知识：

   1)、type:规定列表中的列表项目的项目符号的类型 语法：<ol type="a"></ol>

   ​               1 数字顺序的有序列表（默认值）（1, 2, 3, 4）。

   ​               a 字母顺序的有序列表，小写（a, b, c, d）。 

   ​               A 字母顺序的有序列表，大写（A,B,C,D) 

   ​               i 罗马数字，小写（i, ii, iii, iv）。 

   ​               I 罗马数字，大写（I, ii, iii, iv）。 

   2)、start 属性规定有序列表的开始点。 语法：<ol start="5"></ol> 

10. 插入图片

   ~~~html
   <img src="目标文件路径及全称" alt="图片替换文本" title="图片标题" width="宽度" height="高度"/>
   ~~~

   **title的作用:图片的标题；** 当鼠标悬停在该图片上时显示一个小提示，鼠标离开就没有了，HTML的绝大多数标签都支持title属性，title属性就是专门做提示信息的
   **alt的作用:**提示文本 必写；alt属性是在你的图片因为某种原因不能加载时在页面显示的提示信息，它会直接输出在原本加载图片的地方。（优化图片的）

   ***相对路径的写法：**
   	1)当当前文件与目标文件在同一目录下，直接书写目标文件文件名+扩展名；<img src=”q12.jpg”/>
   	2)当当前文件与目标文件所处的文件夹在同一目录下，写法如下：
   文件夹名/目标文件全称+扩展名；<img src=”images/q12.jpg”/>
   	3)当当前文件所处的文件夹和目标文件所处的文件夹在同一目录下，写法如下：
   ../目标文件所处文件夹名/目标文件文件名+扩展名；<img src=”../images/q12.jpg”/>

11. 超链接

    ~~~html
    <a href="目标文件路径及全称/连接地址" title="提示文本">链接文本/图片</a>
    <a href="#"></a>空链接
    属性：target:页面打开方式，默认属性值_self(当前窗口打开)
    属性值：_blank 新窗口打开
    <a href="#" target="_blank">新页面打开</a>
    ~~~

12. 表格

    ~~~html
    作用：显示数据
    表格组成
    <table width="value" height="value" border="value">
        <caption>表格的标题</caption>
          <tr>
                <td>内容</td>
                <td>内容</td>
         </tr>
    </table>
    注：一个tr表示一行;一个td表示一个单元格
    <th></th>表格的列标题
    *数据表格的相关属性
    1）width：表格的宽度
    2）height：表格的高度
    3）border：表格的边框
    4）bgcolor：表格的背景色
    5）bordercolor：表格的边框颜色
    6）cellspacing：单元格与单元格之间的间距
    7）cellpadding：单元格与内容之间的空隙
    8）align：水平对齐方式   属性值：left左对齐  center居中  right右对齐
    9) valign：垂直对齐方式  属性值：top顶对齐   middle居中  bottom底对齐  baseline(基线)
    10)合并单元格属性：
    colspan：合并列，属性值：“所要合并的单元格的列数”
    rowspan：合并行，属性值：“所要合并的单元格的行数”
    ~~~

13. 表单

    ~~~html
    作用：登录、注册、搜索、收集用户的信息
    表单组成：表单框（表单域form）
             提示信息
             表单控件/表单元素
    1)、表单框
    <form name="表单名称（英文字母开头的）" method（提交方式）="post/get" action="表单提交的地址"></form>
    	Form中的获取数据的两个方式get和post的区别？
    	1. get是从服务器上获取数据，post是向服务器传送数据。
    	2. get是把参数数据队列加到提交表单的ACTION属性所指的URL中，值和表单内各个字段一一对应，在URL中可以看到。post是通过HTTP post机制，将表单内各个字段与其内容放置在HTML HEADER内一起传送到ACTION属性所指的URL地址。用户看不到这个过程。
    	3. 对于get方式，服务器端用Request. QueryString获取变量的值，对于post方式，服务器端用Request.Form获取提交的数据。
    	4. get传送的数据量较小，不能大于2KB。post传送的数据量较大，一般被默认为不受限制。
    	5. get安全性非常低，post安全性较高。但是执行效率却比Post方法好。
    	建议：
    	1、get方式的安全性较Post方式要差些，包含机密信息的话，建议用Post数据提交方式；
    	2、在做数据查询时，建议用Get方式；而在做数据添加、修改或删除时，建议用Post方式；
    2）文本框
    <input type="text" value="默认值" placeholder="提示文本" />
    3)密码框
    <input type="password" placeholder="密码"/>
    4)提交按钮
    <input type="submit" value="按钮内容" />提交按钮
    <input type="reset" value="按钮内容"/>重置按钮 
    5）单选框/单选按钮
    <input type="radio" name="ral" value="radiovalue"/>
    <input type="radio" name="ral" checked="checked" />
    注：单选按钮里的name属性必须写，同一组单选按钮的name属性值必须一样
    6）复选框
    <input type="checkbox" name="like" value="checkboxvalue" />
    注：复选按钮里的name属性必须写，同一组复选按钮的name属性值必须一样。
    checked="checked"表示默认被选中，可简写成checked
    disabled="disabled"表示禁用，可简写成disabled
    enabled:可用状态
    7)下拉菜单
    <select name="">
    	<option name="" value="表单被提交时被发送到服务器的值">菜单内容</option>
        <option name="" value="">菜单内容</option>
        ....
    </select>
    8）多行文本框（文本域）
    <textarea name="textareal" cols="字符宽度" rows="行数">
    </textarea>
    9)跳转按钮
    <input name="'" type="button" value=“按钮内容” />
    <button></button>
    button和submit的区别是：
    <button type="submit"></button>
    	submit是提交按钮起到提交信息的作用，type类型是button只起到跳转的作用，不进行提交。只有type类型是submit才会有跳转提交的作用。
    	注释：<input type="checkbox"> 和 <input type="radio"> 中必须设置 value和name属性。
    ~~~

14. label标签（提示信息标签）

    ~~~html
    作用：获得焦点，将提示信息及相应的表单控件进行关联
    方法一：<label   for="user">提示信息</label>
    	   <input type="text" id="user">
    方法二：<label>提示信息
        		 <input type="text">
    		</label>
    ~~~

15. div和span的用法 

    ~~~html
     <div ></div>
       没有具体含义， 除了独占一行之外没有任何其它的默认属性，是页面布局中常用的标签.
     <span> </span>
       文本结点标签
       可以是某一小段文本，或是某一个字。 它除了不换行外，没有任何其它的默认属性.
    ~~~

    

    

      

      

      













