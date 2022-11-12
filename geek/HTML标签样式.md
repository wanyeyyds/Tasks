# HTML标签样式

优先级：内联样式 > 内部样式 > 外部样式

在<style>....</style>内设置样式

### 1、内联样式：写在标签里面

<body>
<!--内联样式 写在标签里面-->
2.<!--style=背景颜色;width:宽度像素-->

表示<div style="background-color: pink;width: 300px">人生苦短，我用python</div>

</body>

### 2.内部样式《标签[选择器](https://so.csdn.net/so/search?q=选择器&spm=1001.2101.3001.7020)》：：<style> 标签{   } </style>



功能：同步设置多个标签样式

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--    内部样式-->
    <style>
        div{background-color: pink;
            width: 470px;}

    </style>
</head>
<body>

    <div>人的一生为什么要努力？因为最痛苦的事，不是失败，是我本可以</div>
</body>
</html>

### 3、外部样式：

新建css样式表，html用Link方法引用
css样式表：

<style>
    div{background-color: pink;width: 200px;}
</style>
#### 4、html引用css

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--    外部样式-->
    <link rel="stylesheet" href="01_css基本使用.css">

    4、html引用css
1.<!DOCTYPE html>
2.<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--    外部样式-->
    <link rel="stylesheet" href="01_css基本使用.css">
5、《class选择器》：
    先定义类（. ABC）-标签内引用类<p class='ABC'>
功能：针对单个标签设置样式，可被多个标签引用


![1d14321985b04aa5bfb80b13bda7b059](https://img-blog.csdnimg.cn/1d14321985b04aa5bfb80b13bda7b059.png)
    

 输出：
![10a41591966e41a38db7923d1395ea88](https://img-blog.csdnimg.cn/10a41591966e41a38db7923d1395ea88.png)

###  6、《id选择器》：

定义id（#ABC） -标签内通过id属性引用（id='ABC'）
功能：具有唯一性（引用多个会语法报错）

![6c36aaf88322441eb157fd5e620f67aa](https://img-blog.csdnimg.cn/6c36aaf88322441eb157fd5e620f67aa.png)

###  7、《群组选择器/并集标签》：

标签1，.类名{background-color：背景颜色,  height：高度,width：宽度}
功能：多种标签、自定义类等同时设置样式

<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
<!--    三种写法ul li / .nav  / .nav li -->
        div,p,ul li{color: pink;}
    </style>
</head>
<body>
    <div>熊大</div>
    <p>熊二</p>
    <ul class="nav">
        <li>第一个li</li>
        <li>第二个li</li>
        <li>第三个li</li>
    </ul>
</body>
![6ab37b9cf6cf4c5aa3d75da09ffe97ea](https://img-blog.csdnimg.cn/6ab37b9cf6cf4c5aa3d75da09ffe97ea.png）

###  8、《兄弟选择器》：

（标签1~标签2）
功能：给标签1后面的所有同级标签2设置样式。

<!--    兄弟选择器-->
    <style>
        div~p{
            background-color: bisque;
            height: 40px;
        }
    </style>
</head>
<body>
    <div>我是第一个div盒子</div>
    <div>
        <p>我是第一个p盒子</p>
    </div>
    <p>第一个p标签</p>
    <p>第二个p标签</p>
    <p>第三个p标签</p>
</body>
兄弟选择器输出：

![ec7cf6c8b9614f149017c8793ba99145](C:\Users\86191\Pictures\Saved Pictures\ec7cf6c8b9614f149017c8793ba99145.png))

### 9、《相邻标签》 ：

（.类名）+标签（必须是相邻且从上往下找）
功能：给小李邻居老王设置样式

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*相邻选择器*/
        .div2+p{
            background-color: blueviolet;
            height: 30px;
        }
    </style>
</head>
<body>
    <div class="div1">我是第一个div盒子</div>
    <div class="div2">
        <span>我是第一个span盒子</span>
    </div>
    <p>第一个p标签</p>
    <p>第二个p标签</p>
    <p>第三个p标签</p>
</body>
</html>
相邻标签输出：
![1476c12e6bd640fd8d46fa785e57f5f5](https://img-blog.csdnimg.cn/1476c12e6bd640fd8d46fa785e57f5f5.png)


###  10、子代选择器：

标签1>标签2
功能：给dic标签内的p标签设置样式

![ba96675ecf3e48c08766a2a8dc3f115f](https://img-blog.csdnimg.cn/ba96675ecf3e48c08766a2a8dc3f115f.png)

子代选择器输出：
![bad2f1fda11f44dcaef0a184ed78dc0d](https://img-blog.csdnimg.cn/bad2f1fda11f44dcaef0a184ed78dc0d.png)
                                                            

### 11、《后代选择器》

功能：仅给内嵌标签设置样式，不限层数

    <style>
        /*后代选择器*/
        div p{background-color: bisque;height: 50px;}
    </style>
</head>
<body>
    <div>我是第一个div盒子</div>
    <div>
        <span>我是第一个span盒子</span>
        <div>
            <p>我是内嵌的p标签</p>
            <span>
                <p>我也是内嵌的p标签</p>
            </span>
        </div>
    </div>
    <p>第一个p标签</p>
    <p>第二个p标签</p>
    <p>第三个p标签</p>
</body>
后代选择器输出：
![b9583ee9182e4381b2ee7d8026e0ef12](https://img-blog.csdnimg.cn/b9583ee9182e4381b2ee7d8026e0ef12.png)

###  12、class相同：

需要加工的标签.类名{...样式....}
功能：当拥有相同类的不同标签，针对某个标签需加样式时

    <style>
        /*box类字体蓝色*/
        .box{color:blue}
        /*首先你必须是个div，其次class为box*/
        div.box{
            background-color: palegoldenrod;
            height: 40px;
        }
    </style>
</head>
<body>
    <div class="box">我是一个div盒子</div>
    <span class="box">我是一个span盒子</span>
    <p class="box">我是一个p标签</p>
</body>
class相同输出：
![a8014a3fad704576bc116522fdd5c1de](https://img-blog.csdnimg.cn/a8014a3fad704576bc116522fdd5c1de.png)

### 13、伪装选择器

：链接标签a：link{color:yellow}
link 超链接点击之前
visited 链接被访问过之后
功能：作用于链接标签当鼠标移动标签时触发...

设置未被点击的时字体颜色：a：link{color:yellow}
设置已被点击的链接字体颜色：a:visited{color: brown}
设置鼠标悬停的字体颜色：a:hover{color: yellow;}
设置鼠标点击未释放字体颜色:a:active{color: blue;}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*未被点击的时候*/
        a:link{color: coral;}

        /*已被点击的链接*/
        a:visited{color: brown;}
     
        /*鼠标悬停背景的样式*/
        a:hover{color: yellow;}
     
        /*鼠标点击未释放*/
        a:active{color: blue;}
        /*如果这四个选择器都要设置，必须要按照上面的顺序，lvha*/
    </style>
</head>
<body>
    <a href="#">百度一下</a>
</body>
</html>

### 14、focus伪类选择器：

表单标签：focus{样式}
功能：作用于表单标签，当鼠标悬停在表单时触发

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        input:focus{ background-color: pink;}
    </style>
</head>
<body>
    <input type="text">
    <input type="text">
    <input type="text">
</body>
</html>
focus伪类选择器输出：当鼠标悬停在表单时背景色为pink

    https://img-blog.csdnimg.cn/7f70978a9bd847dba48f923ed7a48491.png

### 15、字体样式

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*字体*/
        #box1{font-family: 'Arial','宋体';}

        /*字体大小*/
        /常用单位： *% rem em* px/
        #box2{font-size: 28px;}
     
        /*字体样式，斜体*/
        #box3{font-style: italic;
            /*font-style: oblique;斜体*/
            /*font-style: normal;  如果要把斜体字变为正常的，就用这个*/}
    </style>
</head>
<body>
    <div id="box1">这是第一个div盒子</div>
    <div id="box2">这是第一个div盒子</div>
    <div id="box3">这是第一个div盒子</div>

</body>
</html>
    我们可以使用font-family（字体），color（颜色），和font-size（字体大小）属性来定义字体的样式:

实例

1.<h1 style="font-family:verdana;">一个标题</h1>
2.<p style="font-family:arial;color:red;font-3.size:20px;">一个段落。</p>

现在通常使用font-family（字体），color（颜色），和font-size（字体大小）属性来定义文本样式，而不是使用<font>标签。

### 16、文本样式

​    <style>
​        /*对齐方式  left  right center*/
​        #p1{text-align: right;}

        /*文字缩进*/
        #p2{text-indent: 2em;}
     
        /*词间距,仅针对单词*/
        #p3{word-spacing: 40px;}
     
        /*字间距,中文和单词均可使用*/
        #p4{letter-spacing: 20px;}
     
        /*线条*/
        #p5{text-decoration: line-through; /*删除线*/
            /*text-decoration: underline;   下划线*/
            /*text-decoration: overline;   上划线*/}
    </style>
</head>
<body>
    <p id="p1">如果这世界上真有奇迹，那只是努力的另一个名字</p>
    <p id="p2">看似不起波澜的日复一日，会突然在某一天让人看到坚持的意义</p>
    <p id="p3">hello my name is mochuan</p>
    <p id="p4">nice to meet you我是糖醋人鱼</p>
    <div id="p5">因为足够努力，才会显得毫不费力</div>

</body>

### 17、文字内容超出省略

​    <style>
​        div{
​            width: 300px;
​            height: 30px;
​            background-color: bisque;
​            /*文本一行显示*/
​            white-space: nowrap;
​            /*超出部分隐藏*/
​            overflow: hidden;
​            /*省略号表示*/
​            text-overflow: ellipsis;
​        }
​    </style>
</head>
<body>
​    <div>上班累吧，总不能不上吧，感情再假，总不能不碰吧，家再远，总不能不回吧。
​        我的意思是：人生这道选择题怎么选都会有遗憾的，不妨大胆一点，反正我们都
​        不能活着离开这个世界，大胆一点，勇敢的去尝试。人生说到底，活的是一种心
​        态，生活的刁难，并不是要你变得气急败坏，而是要你变得更加从容，未来还长，
​        不必慌张，愿我们都能平心静气的面对生活中的每个选择，在稳稳的努力中收获
​        稳稳的幸福。
​    </div>
</body>

### 18、块级元素

块级元素：h1~h6 div p ol ul li 可以设置宽高，独占一行

### 19、行内元素

行内元素： span 、a、  em、 del、 ins，行可以有多个

1、宽高设置是无效的，默认宽度是本身内容的宽度
2、行内元素只能放文本或者其他行内元素
3、a标签里面可以放块级标签

### 20、行内块元素

img  input td 有块级元素特点，也有行内元素特点

### 21、显示形式转换

行内元素转换为块级元素....块级→行内...行内→行内块

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        a{width: 100px;
            height: 50px;
            /*转换成块级元素*/
            display: block;
            background-color: red;}

        div{width: 100px;
            height: 50px;
            background-color: gold;
            /*转换成行内元素*/
            display: inline;}
        span{width: 100px;
            height: 50px;
            background-color: pink;
            /*转换为行内块元素*/
            display: inline-block;}
    </style>
</head>
<body>
表示<a href="#">我是空链接</a>

<div>我是块级元素</div>
<span>我是行内元素</span>
</body>
</html>

### 22、背景

​    <style>
​        div{
​            width: 2560px;
​            height: 1440px;
​            /*默认铺满整个屏幕*/
​            background-image: url(../img/r2g7rm.jpg);

            /*    不平铺*/
            background-repeat: no-repeat;
        }
    </style>
### 23、背景图片位置

background-position(接收两个参数)：x轴位置 y轴位置

    <style>
        div{
            width: 1000px;
            height: 1000px;
            /*默认铺满整个屏幕*/
            background-image: url(../images/logo.png);
     
            background-color: yellowgreen;
        /*    不平铺*/
            background-repeat: no-repeat;
            /*精确单位：background-position(两个参数)：x轴位置 y轴位置 */
            /*background-position: 20px 50px;*/
            /*background-position: center top; 上居中*/
            /*background-position: left top;*/
            /*background-position: bottom;*/
        }
    </style>
### 24、固定背景

​    <style>
​        div{
​            width: 1000px;
​            height: 1000px;
​            /*默认铺满整个屏幕*/
​            background-image: url(../images/girl.png);

        /*    不平铺*/
            background-repeat: no-repeat;
     
        /*   背景固定  scroll*/
            background-attachment: fixed;
        }
    </style>
### 25、背景复合写法

/*背景，不平铺，固定  （无顺序）*/
div{
background: url(../images/girl.png) no-repeat fixed}
整体设置样式

    <style>
        body{
            height: 2500px;
        }
    </style>
来自[Bianca427](https://blog.csdn.net/Bianca427/article/details/124980762)


[普通网友。](https://blog.csdn.net/m0_68459853/article/details/126540549)