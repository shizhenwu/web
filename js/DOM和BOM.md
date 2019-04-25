# BOM

## BOM是browser object model的缩写，简称浏览器对象模型。 

## Window对象：  

window 对象表示浏览器中打开的窗口 

## Window对象属性

### 1.Document对象

​	每个载入浏览器的 HTML 文档都会成为 Document 对象。 

​	Document 对象使我们可以从脚本中对 HTML 页面中的所有元素进行访问 

​	Document 对象是 Window 对象的一部分，可通过 window.document 属性对其进行访问 

#### 	属性

​		1.all[] 提供对文档中所有 HTML 元素的访问。是数组类型 

​		2.forms[] 返回对文档中所有 Form 对象引用。是数组类型 body 提供对元素的直接访问。 

​		3.URL 返回当前文档的 URL。 bgColor属性：可以改变文档的颜色；（ document.bgColor="gray";） 

#### 	方法

​		1.getElementById() 返回对拥有指定 id 的第一个对象的引用。 

​		2.getElementsByName() 返回带有指定名称的对象集合。 

​		3.getElementsByTagName() 返回带有指定标签名的对象集合。 

​		4.write() 向文档写 HTML 表达式 或 JavaScript 代码。 

 ### 2.history对象

包含用户(在浏览器窗口中)访问过的 URL 

#### 	属性

​		1.length 返回浏览器窗口历史列表中的 URL 数量。 

#### 	方法 

​		1.back() 加载 history 列表中的前一个 URL。 

​		2.forward() 加载 history 列表中的下一个 URL。 

​		3.go() 加载 history 列表中的某个具体页面，或者要求浏览器移动到指定的页面数量（负数为后退，正 数为前进） 

​		go(0)表示刷新页面

###3.Location对象 

Location 对象包含有关当前 URL 的信息。 

#### 	location对象的属性

 		1.href属性 控制浏览器地址栏的内容 

​		2.hostname 设置或返回当前 URL 的主机名。 

#### 	location对象的方法

​		1.reload()方法 刷新页面 

​		2.reload(true) 刷新页面，不使用缓存 

###4.Screen对象 

###5.name 浏览器窗口的名字 

###6.defaultStatus 设置或返回窗口状态栏中的默认文本 

###7.status 设置窗口状态栏的文本 

## navigator对象 

包含有关浏览器的信息 

#### 属性

userAgent 用户代理信息，通过该属性可以获取浏览器及操作系统信息 

## Window对象的方法 

1.alert(“”) 显示带有一段消息和一个确认按钮的警告框。 

2.confirm(“”) 显示带有一段消息以及确认按钮和取消按钮的对话框。一般在删除时，会使用 

3.prompt(“”) 显示可提示用户输入的对话框。

4.open(“url”,”name”) 打开一个新的浏览器窗口或查找一个已命名的窗口。 

5.showModalDialog (“打开窗口的url”,”窗口名”,”窗口特征”)(chrome不支持) 

6.close() 关闭浏览器窗口。 （ FF不支持） 

7.focus () 窗口失去焦点 

8.setInterval() 按照指定的周期（以毫秒计）来调用函数或计算表达式。 

9.clearInterval() 取消由 setInterval() 设置的 timeout。 

10.setTimeout() 在指定的毫秒数后调用函数或计算表达式。 

11.clearTimeout() 取消由 setTimeout() 方法设置的 timeout。 

12.moveBy() 可相对窗口的当前坐标把它移动指定的像素。 

13.moveTo() 把窗口的左上角移动到一个指定的坐标。 

14.resizeBy() 按照指定的像素调整窗口的大小。 

15.resizeTo() 把窗口的大小调整到指定的宽度和高度。 

16.scrollBy() 按照指定的像素值来滚动内容。 

17.scrollTo() 把内容滚动到指定的坐标。 

## 打开窗口 

#### **window.open(“url”,”name”,”窗口特征”)** 

打开一个新的浏览器窗口或查找一个已命名的窗口。 

例如：

~~~js
window.open("sub.html","窗口名","Width=300px,Height=250px,left=100px,top=100px");
//子窗口操作父窗口：opener（代表父窗口的window对象）
document.onclick = function() {
opener.document.title='子窗口让我输出的！';
}
~~~

**窗口特征：**

1.width=pixels 窗口的文档显示区的宽度。以像素计。

2.height=pixels 窗口文档显示区的高度。以像素计。 

3.left=pixels 窗口的 x 坐标。以像素计。

4.top=pixels 窗口的 y 坐标。 

5.location=yes|no|1|0 是否显示地址字段。默认是 yes。 

6.menubar=yes|no|1|0 是否显示菜单栏。默认是 yes。 (需要父窗口菜单栏处于显示状态) 

7.resizable=yes|no|1|0 窗口是否可调节尺寸。默认是 yes。 

8.scrollbars=yes|no|1|0 是否显示滚动条。默认是 yes。 

9.status=yes|no|1|0 是否添加状态栏。默认是 yes。 

10.titlebar=yes|no|1|0 是否显示标题栏。默认是 yes。 

11.toolbar=yes|no|1|0 是否显示浏览器的工具栏。默认是 yes。 

## onload事件与匿名函数 

onload 事件会在页面或图像加载完成后立即发生。 

支持的标签：, , , , &lt;img&gt;, &lt;link&gt;, &lt;script&gt; 

支持的对象：image, layer, window 

例：

 1，&lt;body onload=“alert(‘页面加载完毕。');"&gt; 

2，&lt;body onload=“jiazaiwanbi()"&gt; function jiazaiwanbi(){ alert(“页面加载完毕。”); } 

3，window.onload=jiazaiwanbi; 

4，window.onload=function(){alert(“页面加载完毕。”);};

# DOM

## DOM（Document Object Model），文档对象模型。 

DOM定义了表示和修改文档所需的对象、这些对象的行为和属性以及这些对象之间的关系。 

### 1、节点 

这些对象又称为节点(在DOM的世界里，一切皆节点)： 

​	1.整个文档是一个**文档节点**（document）(document.documentElement:根节点HTML标签) 

​	2.每个 HTML 标签是一个**元素节点** 

​	3.包含在 HTML 元素中的文本是**文本节点** 

​	4.每一个 HTML 属性是一个**属性节点** 

​	5.注释属于**注释节点** 

### 2、DOM树 

对象之间的关系叫做Node (节点)**层次**： 

节点彼此都有等级关系。 

HTML 文档中的所有节点组成了一个文档树（或节点树）。

HTML 文档中的每个元素、属性、文本等都代表着 树中的一个节点。 

HTML标签是根（root）节点。

节点之间都存在着父子（parent \child）、同胞（sibling）的关系。 

### 3.查询元素节点 

~~~js
getElementById() //获取特定 ID 元素的节点

getElementsByTagName() //获取相同标签名的元素节点，返回数组，使用[0]来获取

getElementsByName() //获取相同name属性的元素节点，不是所有标签都有name属性，某些低版本浏览器会有兼容性问题

getElementsByClassName() //获取相同class属性的节点列表   IE8及以下不支持
~~~

###4.通过层级关系访问节点（包括文本和元素）

~~~js
parentNode //父节点。 

childNodes //当前节点包含的所有子节点(文本和元素节点都有)。 

firstChild //当前节点的第一个子节点。 

lastChild //当前节点的最后一个子节点。 
~~~

注：childNodes中的所有节点都具有相同的父节点，因此它们的 parentNode 属性都指向同一个节点。包含在 childNodes 列表中的每个节点相互之间都是同胞节点。 

~~~js
previousSibling //访问前一个同胞节点。

nextSibling //访问后一个同胞节点。
~~~

注：列表中第一个节点的 previousSibling 属性值为 null ，而列表中最后一个节点的 nextSibling 属性的值同样 也为 null。 

###5.通过层级关系访问元素节点 

~~~js
parentNode //父节点。

children //当前节点的所有子节点(只有元素节点)，即所有的元素类型的子节点

firstElementChild //当前节点的第一个元素类型的子节点。

lastElementChild //当前节点的最后一个元素类型的子节点。

previousElementSibling //访问前一个同胞元素类型的节点。

nextElementSibling //访问后一个同胞元素类型的节点。
~~~

注：列表中第一个节点的 previousElementSibling 属性值为 null ，而列表中最后一个节点的 nextElementSibling 属性的值同样也为 null。 

### 6.节点的增删改 

~~~js
document.createElement(HTML标签名) //创建一个元素节点

document.createTextNode(文字) //创建一个文本节点

node.appendChild(newChild) //newChild 被添加到孩子列表中的末端。

node.insertBefore(newChild, referenceNode) // 将 newChild 节点插入到 referenceNode 之前。

node.removeChild(oldChild) //删除 oldChild子节点。

node.replaceChild(newChild, oldChild) //用newChild节点替换oldChild节点
~~~

注：子节点中包含文本节点、属性节点和元素节点。 

### 7.通过nodeType属性来判断节点类型，

####1代表元素节点，

####2代表属性节点，

#### 3代表文本节点 

### 8.表格的增删改 

~~~js
//表上的行、列集合
tab.rows[index]; //取得表中的某一行
row.cells[index]; //取得行中某一列

//插入
tab.insertRow(index); //插入新行并返回新行，index为插入位置不写插入到表末
row.insertCell(index); //插入新列并返回新列，index为插入位置不写插入到行末

//删除
tab.deleteRow(index);
row.deleteCell(index);
~~~

###9.window.onscrolll页面滚动事件

~~~js
//取得滚动条位置
document.body.scrollTop //谷歌(设为0页面回到顶部)
document.documentElement.scrollTop //标准

//兼容写法
document.documentElement.scrollTop || document.body.scrollTop

//页面可见区域高度
document.body.clientHeight（如果出现问题用document.documentElement.clientHeight）

//取得某元素距离外层元素的距离，外层元素必须定位，否则就会找外外层，直到body
obj.offsetTop （不能设置，仅能获取）

//设置元素高度使用
obj.style.top
~~~

 



