# CSS的五种定位方式

position属性规定应用于元素的定位方法的类型（五种类型：static,relative,absolute,fixed,sticky）

### 1.position:static :

html元素的默认定位方式为static，其定位不受bottom,top,left,right属性的影响静态定位，表示没有定位，元素会按照正常的位置显示，此时 top、bottom、left 和 right 4 个定位属性也不会被应用。

示例代码如下：

```
<!DOCTYPE html>
<html>
<head>
    <style>
        div{
            height: 100px;
            border: 1px solid black;
        }
        div.static {
            width: 130px;
            height: 50px;
            background-color: #CCC;
            line-height: 50px;
            text-align: center;
            position: static;
            top: 50px;
            left: 20px;
        }
    </style>
</head>
<body>
    <div>
        <div class="static">postiont: static;</div>
    </div>
</body>
</html>
```

![静态定位](http://c.biancheng.net/uploads/allimg/210809/104U46022-0.gif)

### 2.position:relative：、

元素相对其正常位置进行定位,设置相对定位的元素的 top、right、bottom 和 left 属性将导致其偏离其正常位置进行调整。不会对其余内容进行调整来适应元素留下的任何空间。

```
<!DOCTYPE html>
<html>
<head>
    <style>
        div{
            border: 1px solid black;
        }
        div.static {
            width: 140px;
            height: 50px;
            background-color: #B3FF99;
            line-height: 50px;
            text-align: center;
            position: relative;
            top: 25px;
            left: 10px;
        }
        p {
            width: 100px;
            height: 100px;
            background-color: #CCC;
            margin: 0;
        }
    </style>
</head>
<body>
    <div>
        <div class="static">position: relative;</div>
        <p></p>
    </div>
</body>
</html>
```

![相对定位](http://c.biancheng.net/uploads/allimg/210809/104U43X5-2.gif)

![top、bottom、left、right 属性演示](http://c.biancheng.net/uploads/allimg/210809/104U424H-1.gif)

### 3.position:absolute:

元素相对于最近的祖先元素进行定位，如果绝对定位的元素没有祖先，它将使用文档主体（body），并随页面滚动一起移动。![top、bottom、left、right 属性在绝对定位中的使用](http://c.biancheng.net/uploads/allimg/210809/104U46010-3.gif)

使用绝对定位的元素会脱离原来的位置，不再占用网页上的空间。与相对定位相同，使用绝对定位的元素同样会与页面中的其它元素发声重叠，另外使用绝对定位的元素可以有外边距，并且外边距不会与其它元素的外边距发生重叠。

【示例】下面通过示例来演示绝对定位的使用：

```
<!DOCTYPE html><html><head>    <style>        div{            border: 1px solid black;            position: relative;        }        div.static {            width: 150px;            height: 50px;            background-color: #B3FF99;            line-height: 50px;            text-align: center;            position: absolute;            bottom: 10px;            right: 5px;        }        p {            width: 100px;            height: 100px;            background-color: #CCC;            margin: 0;            text-align: center;            line-height: 100px;        }    </style></head><body>    <div>        <div class="static">position: absolute;</div>        <p>&lt;p&gt;</p>    </div></body></html>
```

![绝对定位](http://c.biancheng.net/uploads/allimg/210809/104U42506-4.gif)

### 4.position:fixed:

元素相对于视图窗口进行定位，即使滚动页面，它也始终位于同一位置。 top、right、bottom 和 left 属性用于定位此元素。

```
<!DOCTYPE html><html><head>    <style>        div{            height: 500px;        }        p {            width: 150px;            height: 50px;            background-color: #CCC;            margin: 0;            text-align: center;            line-height: 50px;            position: fixed;            right: 20px;            bottom: 20px;        }    </style></head><body>    <div>        <p class="fixed">position: fixed;</p>    </div></body></html>
```

运行结果如下图所示：



![固定定位](http://c.biancheng.net/uploads/allimg/210809/104U45956-5.png)

### 5.position:sticky:

元素根据用户的滚动位置进行定位，粘性元素根据滚动位置在相对（relative）和固定（fixed）之间切换。起先它会被相对定位，直到在视口中遇到给定的偏移位置为止 - 然后将其“粘贴”在适当的位置（比如 position:fixed）。

```
<!DOCTYPE html><html><head>    <style>        div{            height: 500px;            position: relative;        }        p {            width: 100%;            height: 50px;            margin: 0;            text-align: center;            line-height: 50px;            background-color: #CCC;        }        p.sticky {            background-color: blue;            position: sticky;            top:0px;        }    </style></head><body>    <div>        <p>1</p>        <p>2</p>        <p class="sticky">position: sticky;</p>        <p>4</p>        <p>5</p>        <p>6</p>        <p>7</p>    </div></body></html>
```

运行结果如下图所示：



![粘性定位](http://c.biancheng.net/uploads/allimg/210809/104U4B28-6.png)
图：粘性定位


在使用粘性定位时，需要注意以下几点：

- 在设置`position:sticky;`时，必须再定义 top、bottom、right、left 四个属性之一，否则只会处于相对定位的状态；
- 使用粘性定位元素的父元素不能定义`overflow:hidden`或者`overflow:auto`属性；
- 父元素的高度不能低于粘性定位元素的高度；
- 粘性定位的元素仅在其父元素内有效。