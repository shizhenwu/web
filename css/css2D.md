# 动画课程

## 过渡效果transition

注：1.兼容性

​		IE10以上、google、firefox、opera、safari都支持

​	2.谁要发生变化就给谁加此属性

## 相关属性

### transition-property

规定了参与css过度的具体属性

- transition-property 具体参数：
- none 没有过渡效果
- all 全部属性参与过渡
- property 具体属性值，每一个属性值之间使用逗号分隔。

​	1.若没有在本条属性中设置某个属性参与过渡，则没有参与的属性就不会有过渡效果。

​	2.若不设置，则标签中的所有属性默认都会参与到过渡效果中来。每个属性值之间用逗号分隔。

​	3.若想要所有的属性都参与过渡，可以将属性值设置为all。

​	4.若不想要所有属性参与到过渡中来，但还是必须设置这个属性，属性值设为none。

### transition-duration

过度时间，过渡所需要使用的具体时间。单位秒（s）、毫秒（ms）

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            transition-property: all;
            transition-duration: 1s;
        }
        p:hover {
            width: 3000px;
            height: 4000px;
            background-color: pink;
        }
    </style>
</head>
<body>
    <p>
    </p>
</body>
</html>
~~~



### transition-timing-function

规定过渡效果的时间曲线，默认值为ease。

​	常用贝塞尔曲线来模拟时间曲线。其网址为：http://cubic-bezier.com

属性值：

​	1.cubic-bezier后面设置的是具体的贝塞尔曲线的值。如cubic-bezier(.26，.84，.87，.11)

​	2.linear规定以相同的速度从开始到结束，等于cubic-bezier(0,0,1,1)

​	3.ease规定慢速开始，然后加速，最后慢速结束，等于cubic-bezier(0.25,0.1,0.25,1)

​	4.ease-in规定慢速开始和结束的过渡效果，等于cubic-bezier(0.42,0,1,1)

​	5.ease-out慢速结束的过渡效果，等于cubic-bezier(0,0,0.58,1)

​	6.ease-in-out  规定以慢速开始和结束的过渡效果，等于 cubic-bezier(0.42,0,0.58,1)

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            transition-property: all;
            transition-duration: 10s;
            /*transition-timing-function: cubic-bezier(.17,.67,.87,.11);*/
            /*transition-timing-function: linear;*/
            /*transition-timing-function: ease;*/
            transition-timing-function: ease-in;
        }
        p:hover {
            width: 300px;
            height: 400px;
            background-color: pink;
        }
    </style>
</head>
<body>
    <p>

    </p>
</body>
</html>
~~~

### transition-delay

​	（延迟）在指定的时间之后再来执行变化效果。单位秒（s）、毫秒（ms）在实际设置延迟的时候，也可以给具体的某个属性设置延迟。

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightpink;
            transition:1s/*1s为动画时间*/ width 2s/*2s为延迟时间*/,2s height ,3s background-color;
        }
        p:hover {
            width: 300px;
            height: 300px;
            background-color: red;
        }
    </style>
</head>
<body>
    <p>
    </p>
</body>
</html>
~~~

### transition简写

transition: property duration timing-function delay;

如果使用简写的话，不去设置的具体属性都会采用默认值的形式。

#### 过渡示例（手风琴）

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>手风琴</title>
    <style>
        body {
            margin:0;
            padding:0;
            background-color: #f7f7f7;
        }
        h3 {
            margin:0;
            padding:0;
        }
        .box {
            width: 500px;
            margin:0 auto;
        }

        .list h3 {
            height: 35px;
            line-height:35px;
            padding-left: 30px;
            border-bottom:2px solid #690;
            font-size:14px;
            color: #fff;
            background-color: #369;
            transition: all 0.3s ease 0s;
        }
        .list .pictxt {
            height: 0;
            background-color: lightblue;
            transition: all 0.3s ease 0s;
        }
        .list:hover  h3 {
            background-color: #036;
        }
        .list:hover .pictxt{
            height: 150px;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="list">
            <h3>今日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>昨日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>前日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>去年新闻</h3>
            <div class="pictxt"></div>
        </div>
    </div>
</body>
</html>
~~~

## css2D

### 相关属性

1.transform 2D和3D之间的转换，用于设置2D和3D效果属性的

2.transform-origin  更改元素的基点

### 相关属性值（位移 、缩放、旋转、倾斜）

1.translate(x,y)沿着x,y轴移动元素。

​	translateX(n)：沿着X轴位移的距离

​	translateY(n)：沿着Y轴位移的距离

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .box {
            width: 600px;
            height: 300px;
            border: 2px solid orange;
            margin: 0 auto;
        }
        .box .d1 {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            margin:0 auto;
            transition: 2s;
        }
        .box:hover .d1 {
            transform: translate(100px,100px);
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="d1"></div>
    </div>
</body>
</html>
~~~

2.scale（X,Y）缩放，更改元素的高度和宽度，将宽度改为原来的X倍，将高度改为原来的Y倍

​	scaleX(n):将宽度改为原来的X倍

​	scaleY(n):将宽度改为原来的Y倍

scale(0,0)将内容缩小到原来的0倍，也就是缩小至0，没有了

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>scale</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: lightpink;
            transition: 2s;
        }
        div:hover {
            transform: scale(0.5,0.5);
        }
    </style>
</head>
<body>
    <div>
    </div>
</body>
</html>
~~~

3.ratate（angle）旋转  angle为角度，单位为deg

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>rotate</title>
    <style>
        .d1 {
            width: 100px;
            height: 100px;
            background-color: deepskyblue;
            border-left: 2px solid lawngreen;
            border-right: 2px solid gold;
            border-top: 2px solid palevioletred;
            border-bottom: 2px solid royalblue;
            transition: 5s;
            border-radius: 50%;
        }
        .d1:hover {
            transform: rotate(1080deg);
        }
    </style>
</head>
<body>
    <div class="d1">指向谁谁乌龟-></div>
</body>
</html>
~~~

4.skew(X-angle,Y-angle)定义2D倾斜转换，沿着X轴和Y轴

​	skewX(angle)沿着X轴转换

​	skewY(angle)沿着Y轴转换

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>skew</title>
    <style>
        .playhappy {
            width: 100px;
            height: 100px;
            background-color: aquamarine;
            margin:100px auto;
            /*transition: 2s;*/

        }
        .playhappy:hover {
            transform: skew(0deg,10deg);
        }
    </style>
</head>
<body>
    <div class="playhappy"></div>
</body>
</html>
~~~

5.transform-origin更改元素的基点

transform-origin:(x轴值,y轴值)

- x轴: left | center | right | length | % 
- y轴: top | center | bottom | length | %

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>盘它</title>
    <style>
        img {
            width: 300px;
            height: 300px;
        }
        .anim_image {
            transition: all 1s ease-in-out;
            cursor: pointer;
        }
        .anim_image_top {
            position: absolute;
            transform: scale(0,0);
        }
        .anim_box:hover .anim_image_top {
            transform: scale(1,1);
            transform-origin: top right;
        }
        .anim_box:hover .anim_image_bottom {
            transform: scale(0,0);
            transform-origin: bottom left;
        }
    </style>
</head>
<body>
    <div class="anim_box">
        <img src="./images/photo3.jpg" class="anim_image anim_image_top">
        <img src="./images/photo4.jpg" class="anim_image anim_image_bottom">
    </div>
</body>
</html>
~~~

