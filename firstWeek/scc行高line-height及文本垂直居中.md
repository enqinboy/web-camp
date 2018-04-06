 #####
 在CSS中，line-height 属性设置两段段文本之间的距离，也就是行高，如果我们把一段文本的line-height设置为父容器的高度就可以实现文本垂直居中了，比如下面的例子：

```
<!DOCTYPE html>
    <html lang="en">
    <head>
       <meta charset="UTF-8">
       <title>Document</title>
       <style>
       div {
           width: 300px;
           height: 200px;
           border: 1px solid red;
       }
       span {
           line-height: 200px;
       }
      </style>
</head>
<body>
   <div>
       <span>文本垂直居中原理</span>
   </div>
</body>
</html>
```
这样，span标签中的文字就相对于div垂直方向居中了，想要文本水平居中设置text-align：center即可。
那么，它怎么就垂直居中了？为了弄清楚它，下面我们先来看几个概念。
###### 行宽
![image](E:/有道云/line-height.png)
默认情况下一行文本的行高分为：上间距，文本的高度，下间距，并且上间距是等于下间距的，所以文字默认在这一行中是垂直居中的。
![image](E:/有道云/1.png)
几条线与行高的关系图解：
![image](E:/有道云/2.png)
文本的行高也可以看成是基线到基线的距离。
![image](E:/有道云/3.png)
如果一段文本的高度为16px，如果给他设置line-height的高度为200，那么相当于，文本的上下间距的高度增加了，但是文本本身的高度依然是16是不变的，并且一直默认在行框中垂直居中，而上间距和下间距平分了200px的高度并且减去文本本身的高度。所以，容器被这一行文本占满，而本身文字在自己的一行中是垂直居中的，所以看起来就像是在容器中垂直居中。
###### 行高也可以被继承
我们知道，CSS的三大特性是继承、层叠、优先级。line-height也是可以被继承的，如下面的示例

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Document</title>
<style>
span {
    display: inline-block;
}
</style>
</head>
<body>
<div>
    <span>中国人</span>
</div>
</body>
</html>

在不给div设置行高的情况下，span标签的文字行高默认为18


接着我们给div设置一个行高等于20px

div {
line-height: 20px;
}
span {
display: inline-block;
}
```

