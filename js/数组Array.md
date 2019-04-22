

# 数组

含义：数组也是一个对象，和普通对象功能类似，也是用来存储一些值的，不同的是普通对象是使用字符串作为属性名的，而数组是使用索引操作元素的。

索引：从零开始的整数

数组的存储性能比普通对象要好，在开发中经常用数组来存储一些数据。

## 1.创建数组

### (1).var arr=new Array();构造函数方式 

~~~js
var arr=new Array(10,20,30);//创建一个数组,里面有三个元素
console.log(arr[0]);//10
var arr=new Array(5);//创建一个数组,长度为5;
console.log(arr[0]);//undifined
console.log(arr.length);//5
var arr=new Array();//创建一个空数组;
~~~

### (2).var arr=[12,13,14];常量方式

~~~js
var arr=[10,11,12];
console.log(arr[0]);//10
console.log(arr.length);//3
~~~

**注：var arr=[5] 和var arr=new Array(5);**

var arr=[5]:创建一个数组，里面有一个元素，值为5

var arr=new Array(5):创建一个数组，元素值未定，数组长度为5

## 2.向数组中添加元素

**语法：数组[索引]=值**

~~~js
//如：
var arr=[];
arr[0]=12;
arr[1]=13;
arr[2]=14;
console.log(arr);//[12,13,14]
~~~

## 3.读取数组中的元素

**语法：数组[索引]**

### 下标（索引）

是从0开始的整数，下标可以是常量，也可以是变量，也可以是表达式

最大下标是length-1

~~~js
var arr=[10,12,13];
console.log(arr[0]);//10
console.log(arr[3]);//undifined 不存在的索引，不会报错，而是返回undifined
~~~

## 4.获取数组的长度

**语法：数组.length**

~~~js
var arr=[10,12,13];
console.log(arr.length);//3 下标连续的数组的长度就是元素的个数

var arr=[];
arr[0]=12;
arr[1]=13;
arr[2]=14;
arr[10]=20;
console.log(arr.length);//11  对于非连续的数组，使用length会获取到数组的最大下标+1
console.log(arr);//[12,13,14,,,,,,,,10]//对于非连续的数组,输出时会将位置空出来，比较占位置，一般不建议写不连续的数组
~~~

## 5.修改数组的length

~~~js
var arr=[];
arr[0]=12;
arr[1]=13;
arr[2]=14;
arr.length=5;
console.log(arr.length);//5
console.log(arr);//[12,13,14,,,]  若是修改的length大于原长度，则多出的部分会空出来
							 //若是修改的length小于原长度，则多出的部分会被删掉
~~~

## 6.像数组的最后一个位置添加元素

**语法：数组[数组.length]=值**

~~~js
var arr=[];
arr[0]=12;
arr[arr.length]=13;//相当于arr[1]=13
arr[arr.length]=14;//相当于arr[2]=14
console.log(arr);//[12,13,14]
~~~

## 7.数组中的元素

#### 数组中的元素可以是任意的数据类型，可以是对象，也可以是一个函数，也可以是数组

~~~js
var arr=[[],[],[]];//创建一个二维数组
var arr=[[1,2,3],[4,5,6],[7,8,9]];
console.log(arr);//[[1,2,3],[4,5,6],[7,8,9]]
console.log(arr[0]);//[1,2,3]
console.log(arr[1]);//[4,5,6]
console.log(arr[2]);//[7,8,9]
~~~

## 8.数组的遍历

### (1)for循环

~~~js
var arr=[1,2,3,4,5];
for(var i=0;i<arr.length-1;i++){
   console.log(arr[i]);
}
~~~

### (2)for in

~~~js
var arr=[1,2,3,4,5];
for(var i in arr){  //其中的i是数组的下标，注意这里的i是字符串类型的
   console.log(arr[i]);
}
~~~

## 9.数组的排序

将数组中的所有元素都取出来

### (1)冒泡排序

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title></title>
</head>
<body>
	<button onclick="test()">测试</button>
</body>
</html>
<script>
	function test(){
		var arr=[12,9,33,62,58,99,11];
		for(var i=0;i<arr.length-1;i++){
			for(var j=0;j<arr.length-1-i;j++){
				if(arr[j]>arr[j+1]){
					var temp=arr[j];
					arr[j]=arr[j+1];
					arr[j+1]=temp;
				}
			}
		}
		document.write(arr);
	}
</script>
~~~

### (2)选择排序

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title></title>
</head>
<body>
	<button onclick="test()">测试</button>
</body>
</html>
<script>
	function test(){
		var arr=[12,9,33,62,58,99,11];
		for(var i=0;i<arr.length-1;i++){
			var min=i;
			for(var j=i+1;j<arr.length;j++){
					if(arr[min]>arr[j]){
						min=j;
					}	
				}
				var temp=arr[min];
					arr[min]=arr[i];
					arr[i]=temp;
			}
		for(var i=0;i<arr.length;i++){
		document.write(arr[i]+",");
		}
}
</script>
~~~

## 10.数组中的常用方法

### (1)push()

向数组的末尾添加一个或多个元素，并返回数组的新的长度

~~~js
var arr=[1,2,3];
var x=arr.push(4);
console.log(arr);//[1,2,3,4]
console.log(x);//4

var y=arr.push(5,6,7);
console.log(arr);//[1,2,3,4,5,6,7]
console.log(y);//7 返回新的长度
~~~

### (2)pop()无参数

删除数组中的最后一个元素，并返回被删除的元素

~~~js
var arr=[1,2,3];
var x=arr.pop();
console.log(arr);//[1,2]
console.log(x);//"3"
~~~

### (3)unshift()

向数组的开头添加一个或多个元素，并返回数组的新的长度

会影响数组原元素的下标

```js
var arr=[1,2,3];
var x=arr.unshift(4);
console.log(arr);//[4,1,2,3]
console.log(x);//4

var y=arr.push(5,6,7);
console.log(arr);//[5,6,7,4,1,2,3]
console.log(y);//7 返回新的长度
```

### (4)shift()无参数

删除数组中的第一个元素，并返回被删除的元素

```js
var arr=[1,2,3];
var x=arr.shift();
console.log(arr);//[2,3]
console.log(x);//"1"
```

### (5)slice()不会改变原数组

从某个已有的数组返回选定的元素，返回一个新数组，

slice(start,end)包含start，不包含end

start：必须，若是负数，表示从尾部开始，-1指最后一个元素，-2指倒数第二个元素，以此类推

~~~js
var arr=[1,2,3,4,5];
var x=arr.slice(0,2);//两个参数，第一个参数：截取开始的位置的索引,第二个参数：截取结束的位置的索引
console.log(arr);//[1,2,3,4,5]
console.log(x);//[1,2]//包含开始，不包含结束
~~~

### (6)splice()

从某个已有的数组添加/删除元素，返回被删除的元素

slice(start,length,add)

start：必须，表示起始下标的位置

length：必须，表示删除的个数

add：可选，表示向数组中添加的元素，可以多个。这些元素会自动插入到开始位置索引的前面

~~~js
<script type="text/javascript">//不删除，只添加
    var arr = new Array(6)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    arr[3] = "James"
    arr[4] = "Adrew"
    arr[5] = "Martin"
document.write(arr + "<br />")//[George,John,Thomas,James,Adrew,Martin]
arr.splice(2,0,"William")
document.write(arr + "<br />")//[George,John,William,Thomas,James,Adrew,Martin]
</script>

<script type="text/javascript">//添加和删除
    var arr = new Array(6)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    arr[3] = "James"
    arr[4] = "Adrew"
    arr[5] = "Martin"
document.write(arr + "<br />")//[George,John,Thomas,James,Adrew,Martin]
arr.splice(2,1,"William")
document.write(arr)//George,John,William,James,Adrew,Martin
</script>

//arr.splice(2,0) 数组不增不减，没有改变
~~~

### (7)concat()不会改变原数组

用于连接两个或多个数组,

~~~js
<script type="text/javascript">
    var a = [1,2,3];
    document.write(a.concat(4,5));//[1,2,3,4,5]//连接具体的值

    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    var arr2 = new Array(3)
    arr2[0] = "James"
    arr2[1] = "Adrew"
    arr2[2] = "Martin"
    document.write(arr.concat(arr2))//[George,John,Thomas,James,Adrew,Martin] //连接2个数组

    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    var arr2 = new Array(3)
    arr2[0] = "James"
    arr2[1] = "Adrew"
    arr2[2] = "Martin"
    var arr3 = new Array(2)
    arr3[0] = "William"
    arr3[1] = "Franklin"
    document.write(arr.concat(arr2,arr3))//[George,John,Thomas,James,Adrew,Martin,William,Franklin] //连接3个数组
</script>
~~~

### (8)join()不会改变原数组

通过指定的分隔符进行分隔 ,用于把数组中的所有元素放入一个字符串。 

~~~js
<script type="text/javascript">
    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    document.write(arr.join())//[George,John,Thomas]

    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    document.write(arr.join("."))//[George.John.Thomas]
</script>
~~~

### (9)reverse()无参数

颠倒数组中元素的顺序 

~~~js
<script type="text/javascript">
    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    document.write(arr + "<br />")//[George,John,Thomas]
    document.write(arr.reverse())//[Thomas,John,George]
</script>
~~~

### (10)sort()

对数组的元素进行排序 

~~~js
<script type="text/javascript">
    var arr = new Array(6)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"
    arr[3] = "James"
    arr[4] = "Adrew"
    arr[5] = "Martin"
    document.write(arr + "<br />")//[George,John,Thomas,James,Adrew,Martin]
    document.write(arr.sort())//[Adrew,George,James,John,Martin,Thomas] 按字母顺序进行排序
</script>
~~~

~~~js
<script type="text/javascript">
    var arr = new Array(6)
    arr[0] = "10"
    arr[1] = "5"
    arr[2] = "40"
    arr[3] = "25"
    arr[4] = "1000"
    arr[5] = "1"
    document.write(arr + "<br />")//[10,5,40,25,1000,1]
    document.write(arr.sort())//[1,10,1000,25,40,5] 按字母顺序(unicode)进行排序,而不是按照数值的大小对数字进行排序
</script>
~~~

~~~js
<script type="text/javascript">
    function sortNumber(a,b)
    	{
    		return a - b //升序
   	 }
	
	//function sortNumber(a,b)
    	//{
    		//return b - a //降序
   	 //}
    var arr = new Array(6)
    arr[0] = "10"
    arr[1] = "5"
    arr[2] = "40"
    arr[3] = "25"
    arr[4] = "1000"
    arr[5] = "1"
    document.write(arr + "<br />")//[10,5,40,25,1000,1]
    document.write(arr.sort(sortNumber))//[1,5,10,25,40,1000]  升序
</script>
~~~

### ES5数组新增的方法

浏览器支持：Opera 11+ fireFox 3.6+ Chrome 8+ iE 9+ Safari 5+ 

### (1)indexOf()

在数组中查找一个数所在的位置(查下标)

~~~js
var arr1 = [12,23,34,45,56,67];
console.log(arr1.indexOf(23)); //1
~~~

### (2)forEach()

对数组的每个元素做某个处理（函数的方式） 

~~~js
var arr1 = [12,23,34,45,56,67];
arr1.forEach(alert);//依次弹出显示数组的每个元素
~~~

foEach()函数的参数是个回调函数，forEach对应的回调函数有三个参数（数组元素内容，元素索引，数组本身） 

~~~js
var arr1 = [12,23,34,45,56,67];
arr1.forEach(arrInc);
function arrInc(num,index,arr){
arr[index] = num+1; //每个元素都加1
}
~~~

### (3)map()不影响原数组

把原始数组的每个元素进行某种处理后，产生（映射）一个新的数组。回调函数参数是数组元素本身。 

~~~js
var arr1 = [12,23,34,45,56,67];
var arr2 = arr1.map(arrSqr);
function arrSqr(num){
return num*num
}
console.log(arr2);//返回的每个数都在arr1的基础上乘方
~~~

###(4)filter() 返回值为布尔类型

过滤的意思，根据条件过滤数组的元素，filter的回调函数需要返回的是boolean类型的值 

~~~js
var arr1 = [-12,23,-34,45,-56,67];
var arr2 = arr1.filter(eqZero); //过滤掉所有小于等于0的数，留下大于0的数
function eqZero(num){
return num>0;
}
console.log(arr2)
~~~

