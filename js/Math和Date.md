# Math算术

## 常用函数

### 1.Math.round(x) 

把一个数字舍入为最接近的整数 

无论正负数，小数位小于5就舍去，大于5，整数就加1(不考虑负号问题)

 ~~~js
<script type="text/javascript">
    document.write(Math.round(0.60) + "<br />")//1
    document.write(Math.round(0.50) + "<br />")//1
    document.write(Math.round(0.49) + "<br />")//0
    document.write(Math.round(-4.40) + "<br />")//-4 而不是-5
    document.write(Math.round(-4.60))//-5 而不是-4
</script>
 ~~~

###2.Math.random()

返回0-1之间的随机数(包扣0不包扣1)

~~~js
<script type="text/javascript">
	document.write(Math.random())//0.7156723238903799(随机)
</script>
~~~

任意两个整数之间的随机数=取整（小数+随机数*（大数-小数）） 

如：想要12-20之间的随机数

~~~js
var x=Math.random()*8+12；
~~~

###3.Math.max(num1, num2)

返回两个指定的数中带有较大的值的那个数 ,只有两个参数

​	参数中最大的值。如果没有参数，则返回 -Infinity(负无穷)。如果有某个参数为 NaN，或是不能转换成数字的非数字值，则返回 NaN。 

~~~js
<script type="text/javascript">
    document.write(Math.max(5,7) + "<br />")//7
    document.write(Math.max(-3,5) + "<br />")//5
    document.write(Math.max(-3,-5) + "<br />")//-3
    document.write(Math.max(7.25,7.30))//7.3
</script>
~~~

###4.Math.min(num1, num2)

可返回指定的数字中带有最低值的数字 ，只有两个参数

​	参数中最小的值。如果没有参数，则返回 Infinity(正无穷)。如果有某个参数为 NaN，或是不能转换成数字的非数字值，则返回 NaN。 

~~~js
<script type="text/javascript">
    document.write(Math.min(5,7) + "<br />")//5
    document.write(Math.min(-3,5) + "<br />")//-3
    document.write(Math.min(-3,-5) + "<br />")//-5
    document.write(Math.min(7.25,7.30))//7.25
</script>
~~~

###5.Math.abs(num)

可返回数的绝对值 

~~~js
<script type="text/javascript">
    document.write(Math.abs(7.25) + "<br />")//7.25
    document.write(Math.abs(-7.25) + "<br />")//7.25
    document.write(Math.abs(7.25-10))//2.75
</script>
~~~

###6.Math.ceil(num)

对一个数进行上舍入 

~~~js
<script type="text/javascript">
    document.write(Math.ceil(0.60) + "<br />")//1
    document.write(Math.ceil(0.40) + "<br />")//1
    document.write(Math.ceil(5) + "<br />")//5
    document.write(Math.ceil(5.1) + "<br />")//6
    document.write(Math.ceil(-5.1) + "<br />")//-5
    document.write(Math.ceil(-5.9))//-5
</script>
~~~

###7.Math.floor(num) 

对一个数进行下舍入 

~~~js
<script type="text/javascript">
    document.write(Math.floor(0.60) + "<br />")//0
    document.write(Math.floor(0.40) + "<br />")//0
    document.write(Math.floor(5) + "<br />")//5
    document.write(Math.floor(5.1) + "<br />")//5
    document.write(Math.floor(-5.1) + "<br />")//-6
    document.write(Math.floor(-5.9))//-6
</script>
~~~

###8.Math.pow(x,y)

返回 x 的 y 次幂的值 

如果结果是虚数或负数，则该方法将返回 NaN。如果由于指数过大而引起浮点溢出，则该方法将返回 Infinity。 

~~~js
<script type="text/javascript">
    document.write(Math.pow(0,0) + "<br />")//1
    document.write(Math.pow(0,1) + "<br />")//0
    document.write(Math.pow(1,1) + "<br />")//1
    document.write(Math.pow(1,10) + "<br />")//1
    document.write(Math.pow(2,3) + "<br />")//8
    document.write(Math.pow(-2,3) + "<br />")//-8
    document.write(Math.pow(2,4) + "<br />")//16
    document.write(Math.pow(-2,4) + "<br />")//-16
</script>
~~~

###9.Math.sqrt(num) 

参数 *x* 的平方根。如果 *x* 小于 0，则返回 NaN。 

~~~js
<script type="text/javascript">
    document.write(Math.sqrt(0) + "<br />")//0
    document.write(Math.sqrt(1) + "<br />")//1
    document.write(Math.sqrt(9) + "<br />")//3
    document.write(Math.sqrt(0.64) + "<br />")//0.8
    document.write(Math.sqrt(-9) + "<br />")//NaN
</script>
~~~

# 十进制转其他进制

~~~js
var x=110; 
alert(x); 
alert(x.toString(8));//十进制转8进制
alert(x.toString(32));//十进制转32进制
alert(x.toString(16));  //十进制转16进制
~~~

# Date日期

Date对象用于处理日期和时间，Date对象记录着从**1970年1月1日**00:00:00开始以来的**毫秒数**。 

### Date对象的定义

~~~js
var myDate=new Date(); //获取当前时间
//Date对象自动使用当前的日期和时间作为其初始值。
~~~

### 1.创建Date对象同时指定日期和时间

 ~~~js
new Date("month dd,yyyy hh:mm:ss"); 
//new Date("6 15,1994 12:25:36");
new Date("month dd,yyyy");
//new Date("6 15,1994");
new Date(yyyy,mth,dd,hh,mm,ss); 
//new Date("1994,6,15,12,25,36");
new Date(yyyy,mth,dd); 
//new Date("1994,6,15");
new Date(ms); 
 ~~~

### 2.获取时间 

~~~js
 getDate() //返回天
 getDay() //返回星期几 ，从0开始
 getHours() //返回小时数
 getMinutes() //返回分钟数
 getMonth() //返回月份值 ，从0开始
 getSeconds() //返回秒数
 getTime() //返回完整的时间 ，毫秒数
 getFullYear() //返回年份
~~~

### 3.设置时间 

~~~js
 setDate() //改变Date对象的日期
 setHours() //改变小时数
 setMinutes() //改变分钟数
 setMonth() //改变月份，从0开始
 setSeconds() //改变秒数
 setTime() //改变完整的时间，毫秒数
 setYear() //改变年份
~~~

### 4.字符串转换时间戳 

Date.parse(日期字符串或日期对象)

 //返回自1970年1月1日起至参数日期止的毫秒数 

### 5.Date转换为字符串 

  ~~~js
toTimeString() // 把 Date 对象的时间部分转换为字符串。
toDateString() //把 Date 对象的日期部分转换为字符串。
toUTCString() //根据世界时，把 Date 对象转换为字符串。
toLocaleString() //根据本地时间格式，把 Date 对象转换为字符串。
toLocaleTimeString() //根据本地时间格式，把 Date 对象的时间部分转换为字符串。
toLocaleDateString() //根据本地时间格式，把 Date 对象的日期部分转换为字符串。
  ~~~

# 定时器

###1.setInterval    

（回调函数，毫秒数）设置每隔指定的毫秒数执行一次回调函数，返回定时器编号。

###2.clearInterval 

（定时器编号）清除定时器设置。 

~~~js
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
	div{
		width: 300px;
		height: 300px;
		border:2px solid #000;
	}
	</style>
</head>
<body>
	<div id="acolor" ></div>
	<button onclick="get()">点击</button>
</body>
</html>
<script>
	
	function charColor(){
		// 编写函数获得随机的颜色字符串（#20cd4f）
			var str="#";
		for(var i=0;i<6;i++){
			
			str +=parseInt(Math.random()*16).toString(16);
		}
		// console.log(str);
		return str;
	}
	function borColor(){
		// 编写函数获得随机的颜色字符串（#20cd4f）
			var str="#";
		for(var i=0;i<6;i++){
			
			str +=parseInt(Math.random()*16).toString(16);
		}
		// console.log(str);
		return str;
	}
	function getColor(){
		document.getElementById("acolor").style.backgroundColor=charColor();
		document.getElementById("acolor").style.borderColor=borColor();
	}
	function get(){
		setInterval(getColor,1000);
	}
</script>
~~~

###3.setTimeout    

（回调函数，毫秒数） 设置在指定的毫秒数后执行一次回调函数，返回定时器编号。 

###4.clearTimeout  

（定时器编号）清除定时器设置

 注：因为只执行一次回调函数，所以为达到不停执行回调函数的效果必须在回调函数中再次设置。

~~~js
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
	div{
		width: 300px;
		height: 300px;
		border:2px solid #000;
	}
	</style>
</head>
<body>
	<div id="acolor" ></div>
	<button onclick="get()">点击</button>
</body>
</html>
<script>
	
	function charColor(){
		// 编写函数获得随机的颜色字符串（#20cd4f）
			var str="#";
		for(var i=0;i<6;i++){
			
			str +=parseInt(Math.random()*16).toString(16);
		}
		// console.log(str);
		return str;
	}
	function borColor(){
		// 编写函数获得随机的颜色字符串（#20cd4f）
			var str="#";
		for(var i=0;i<6;i++){
			
			str +=parseInt(Math.random()*16).toString(16);
		}
		// console.log(str);
		return str;
	}
	function getColor(){
		document.getElementById("acolor").style.backgroundColor=charColor();
		document.getElementById("acolor").style.borderColor=borColor();
		setTimeout(getColor,1000);
	}
	function get(){
		setTimeout(getColor,1000);
	}
</script>
~~~

 







 
