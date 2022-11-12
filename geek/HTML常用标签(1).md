# HTML常用标签

HTML概述

1.1 什么是HTML
HTML是做网站的、Web开发、互联网生态开发(PC端+移动端+微应用) 目前我们使用的都是HTML5,支持传统的PC端开发，还支持移动端开发还支持微应用开发,从而替换了部分传统的移动端开发技术


1.2 HTML概念
HTML:Hyper Text Markup Language，超文本标记语言。是用来帮助我们构建网页的。

【超文本】：网页本身是一个文本文件，而超文本指的是这种文件中既可以包含文本信息，又可以包含图片，音频，视频和链接等非文字的信息。

【标记语言】：标记，也叫做标签。也就是说HTML这门语言是由标签组成的。

HTML的标签包含以下两种:

(1) 带有标签体的标签< a>标签体< /a >

(2) 不带标签体的标签(自结束标签)< br/>,< hr/>

HTML通过提前约定好的标签来构建我们的网页内容，通过浏览器来进行解释执行

浏览器是一个HTML的解释器，在浏览器中内置了一个解释器，该解释器中包含了所有HTML标签的展示风格HTML常用基础标签

## 3、创建.html文件

使用【!+tab】，一键生成html模板。（注意：是**英文**的感叹号!）

![image-20221109113125385](https://img-blog.csdnimg.cn/bcaa4f65452142ed94c641814fb2d771.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_20,color_FFFFFF,t_70,g_se,x_16)

**分析：**

### （1）模板组成：

A、声明为HTML5文档：

```html
<!DOCTYPE html>
```

B、完整的HTML页面部份：

```html
<html>



 



</html>
```

a、头部元素：

<html>

</html>

该标签为标题，显示在浏览器标签页处。

<title>Document</title>
b、可见的页面内容：

<body>
    
</body>
在此处写的内容，可以显示到浏览器页面上。

c、标签分为：

        开始标签：<head>
    
        结束标签：</head>

d、标签内部有属性，如：charset，用来进一步描述标签的内容。


##### HTML文件的骨架:

![骨架:](C:\Users\86191\Pictures\Saved Pictures\bb3b966444869bd2d4a9fb6982fac640.png)

Head标签：其中可以对网页进行整体设置

Body标签：是HTML的正文标签,我们在网页上能看到的内容都写在该标签中

HTML的IDE工具

(1) DW(Dreamweaver)

(2) HBuilder

(3) Subline

(4) VSCode

(5) WebStorm

(6) 记事本

(7) 其他编程语言的IDE工具


标签的分类:
1.带有标签体的标签，这种标签成对出现;有开始标签也有单独的结束标签,:<html></html>,<head></head>,<body></body>
2.没有标签体的标签（空标签，自结束标签）,开始在结束在同一个标签中<br />,<hr />

常用基本标签
1.标题标签hn(h1——h6)

表示<h1>-级标题</h1>

表示<h2>二级标题</h2>

表示<h3>三级标题</h3>
表示<h4>四级标题</h4>
表示<h5>五级标题</h5>
表示<h6>六级标题</h6>

效果如下

![image-20221109112003824](https://img-blog.csdnimg.cn/114f1e27a806484b80dbfc7d6112fdad.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_11,color_FFFFFF,t_70,g_se,x_16)

2.字体标签(font)

![image-20221109105545469](https://img-blog.csdnimg.cn/img_convert/d10759888d363c667662e7a53110172e.png)

3.段落标签（p）

主要用于将一段内容包裹起来，便于后期的统一设置，p标签本身没有效果,标签内的内容与标签外的内容空一行（自动换行）

1.<p>这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落</p>

2. <p>这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落</p>

3. <p>这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落</p>

   效果如下

   ![image-20221109112212009](https://img-blog.csdnimg.cn/54cc8806e9044539809021d22e5c29fd.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_20,color_FFFFFF,t_70,g_se,x_16)

4.换行标签(br)

`< br/ >`换行标签，中间不空行

5.水平线标签(hr)

```
< hr/ >
```

![image-20221109105906112](https://img-blog.csdnimg.cn/img_convert/51b33fada1a55f185c943169c59a8da2.png)

6.图片标签(img)

```
< img src=”图片地址” width=”宽度” height=”高度” / >
   
   <img src="head.jpg" alt="图片加载失败">
alt：图片显示异常时，显示的文字。
```

![image-20221109105940453](https://img-blog.csdnimg.cn/img_convert/e9323f2be618435d749928ffc695f113.png)

7.背景音乐(audio)

```
< audio src=”音乐” autoplay=“autoplay” loop=”loop”/ >
```

![img](https://img-blog.csdnimg.cn/img_convert/3cf343b2f589de233a937804245fe36a.png)

8.视频(video)

在H5之前大多数视频使用flash插件实现的，但flash插件加载速度较慢，在H5之后专门提供了一个视频的标签</p>

9.超链接标签(a)

用法1：超链接:主要用于将多个页面关联到一起，使用超链接可以直接访问另一个页面;

![image-20221109110043496](https://img-blog.csdnimg.cn/img_convert/e1e8679c22c42aca8e53dc292f54cd72.png)

通过base标签统一设置页面超链接的显示目标< base target="_blank" / > 用法2：用于锚记页面中的某个![image-20221109110118459](https://img-blog.csdnimg.cn/img_convert/1c34b4b2cfba1af8e4fc91dcbd296ebc.png)位置或其他页面中的某个位置

![image-20221109110136521](https://img-blog.csdnimg.cn/img_convert/8e84493823fff55805a63feded1d6359.png)

  显示效果如下

哪吒出世



10.列表标签

(1)有序列表

```
< ol >
< li >列表项< /li >
< /ol >
```

![image-20221109110802735](https://img-blog.csdnimg.cn/img_convert/ff9be974350ebc6fe36f85d36b8de776.png)

显示效果如下

1.注册

2.登录

....

(2)无序列表

![image-20221109110837480](https://img-blog.csdnimg.cn/img_convert/9e5bfd25ff50a362b88002b389fb96c1.png)

1. <ul>

2. ​        <li>语文</li>

3. ​        <li>数学</li>

4. ​        <li>英语</li>

5. ​    </ul>

   ![image-20221109112434311](https://img-blog.csdnimg.cn/a204627297ab42178e66bb543b0f656a.png)

块级标签-----<div>

    <div>
        
    </div>

### 行内标签——<span>

```html
    <span></span>
```

### 8、换行——<br>

```xml
<br>
```

###  9、分割线——<hr>

```xml
<hr>
```



(1) 自定义列表

dl：外围标签

dt：列表的标题标签

dd：设置列表的具体列表项

![image-20221109110932030](https://img-blog.csdnimg.cn/img_convert/1ffebe263c689f9648a618aca7c63d10.png)



1![image-20221109111019368](https://img-blog.csdnimg.cn/img_convert/89b2ccee59811ed5dde5feaa8965fbef.png)

![image-20221109111051875](https://img-blog.csdnimg.cn/img_convert/9614702fd19f14a280ee0d7c0d6acf25.png)

2.文本设置标签

< b >< /b >字体加粗

< i >< /i >设置斜体

< u >< /u >设置文本下划线

< s >< /s >在文本上设置一个删除线

13.其他基本标签

2< sup >n< /sup >：设置上标

log< sub>10< /sub>10:设置下标

————————————————
版权声明：本文为CSDN博主「shengyin714959」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/shengyin714959/article/details/125009120

