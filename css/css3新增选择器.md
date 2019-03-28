# 浏览器及前缀

## 主流浏览器

| 浏览器名称  |     内核     |
| :---------: | :----------: |
| 谷歌google  |    webkit    |
| 火狐firefox |    gecko     |
|   safari    |    webkit    |
|  欧朋opera  | blink presto |
|     IE      |   trident    |

## 浏览器前缀

​	使用一些css3的属性的时候应该考虑到不同浏览器的内核兼容情况，需要针对不同的内核使用不同的浏览器前缀。

| 浏览器名称 |   前缀   |
| :--------: | :------: |
|   google   | -webkit- |
|   safari   | -webkit- |
|     ie     |   -ms-   |
|  firefox   |  -moz-   |
|   opera    |   -o-    |

注：浏览器前缀自动补全的网址:http://autoprefixer.github.io

# 选择器

## 属性选择器

注：E（elements元素）、attr（属性）、value（值）

E[attr]

​	例：ul li[title] { color:red;}	选中的是具有title属性的li元素。		

E[attr=value]

​	例：ul li[title="b"] { color:red;}	选中的是具有title属性并且属性值为b的li元素。

E[attr^=value]

​	例：ul li[title^=a] { color:red;}	选中的是具有title属性并且属性值以a开头的li元素。

E[attr$=value]

​	例：ul li[title$=c] { color:red;}	选中的是具有title属性并且属性值以c结束的li元素。

E[attr*=value]

​	例：ul li[title*=d] { color:red;}	选中的是具有title属性并且属性值中包含d的li元素。

E[attr~=value]

​	例：ul li[title~=test] { color:red;}	选中的是具有title属性并且属性值中包含test单词的li元素。

E[attr|=value]

​	例：ul li[title|=test] { color:red;}	选中的是具有title属性并且属性值中以test开头的单词（test-old）的li元素。

http://static.wenku.bdimg.com/static/wkcommon/pkg/pkg_wkcommon_base_z_a372731.png

## 结构伪类选择器

E:nth-of-type()   / E:nth-child()
E:first-of-type  / E:first-child
E:last-of-type  / E:last-child
E:only-of-type / E:only-child 

:nth-child(x) 选择第x个元素
:nth-child(n) 全选
:nth-child(2n) 选择偶数
:nth-child(2n+1) 奇数

:first-child 第一个
:last-child 最后一个

:only-child 唯一的一个子元素

:nth-child(x) 选择的是指定位置的子元素
:nth-of-type(x) 选择的是指定位置的元素
Tip:  当我们使用:nth-of-type的时候，前面一定要加上元素名不然太猛了

E:first-of-type 同级的情况下，选择第一个元素
E:last-of-type 同级的情况下选择最后一个元素
E:only-of-type 同级的情况下选择唯一的元素