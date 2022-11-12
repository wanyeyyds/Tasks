# CSS选择器

# 基本选择器

| 选择器名称 | 举例                  | 描述                              |
| ---------- | --------------------- | --------------------------------- |
| 元素选择器 | p {color:red;}        | 选择所有<p>元素。                 |
| 类选择器   | .mystyle {color:red;} | 选择所有class='mystyle’的标签元素 |
| id选择器   | #myid {color:red;}    | 选择所有id="myid"的标签元素       |

### 1.通用选择器

使用符号：（*）来选择页面上的所有的 HTML 元素。

*{
   color:red;
   font-size:40px;
}

1.<h1>标题1</h1>
2.<p>段落1</p>
3.<p>我们将看到通用选择器的修饰结果</p>
观察运行结果，我们可以看到两个段落和一个标题都被修饰了红色，字体大小为40像素

![image-20221112143904738](https://img-blog.csdnimg.cn/793e452658bb41a98113fbbb71cf6b57.png)

### 2.元素选择器

根据元素名称来选择 HTML 元素。

```css
p {
  text-align: center;
  color: green;
}
```

### 3.类选择器（class选择器）

    (1)语法格式：.class名{属性:属性值; 属性:属性值;}
    
    例如：html中有四张图片，第一张图片宽高为50px*50px,其他图片尺寸为30px*35px。我们就可以给第一张图片加class名。
           加类名： <img class="item" src="路径">
           设置样式：.item{width:50px;height:50px;}
    
    注意：类名可以由英文、中文（不推荐）、数字（不能放在第一位）、_组成。
    (2)使用场景
    1.当我们需要把某个元素单独设置样式时
    2.当html里有不同元素需要统一样式时使用
    
    特点：一个元素可以有多个类名，类名之间需要用空格隔开

   代码演示      

![image-20221112142133910](https://img-blog.csdnimg.cn/0429fdcbf83f4647909e526f0a1866c9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAbTBfNjU3OTA1NDk=,size_20,color_FFFFFF,t_70,g_se,x_16)              

运行结果

![image-20221112142216318](https://img-blog.csdnimg.cn/070161311b55409596a8d1b3abbc364c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAbTBfNjU3OTA1NDk=,size_11,color_FFFFFF,t_70,g_se,x_16)

选择有特定 class 属性的 HTML 元素。

.mystyle1 {
  background:rgb(200,200,0);
  color:blue;
}
.mystyle2{
  font-size: 14px;
  font-weight: 500;
  display: block;
  margin-top: 25px;	
}

运行结果

1.<p>这个段落没有引用</p>
2.<p class="mystyle1 mystyle2">这个段落引用两个类。</p>

### ![image-20221112142913862](https://img-blog.csdnimg.cn/16e01ed1207e4439b8b909dffdacdbcc.png)4.ID选择器

ID是HTML元素的一种属性，由于元素的 id 在页面中是唯一的，因此 id 选择器用于选择一个唯一的元素！
在样式定义时，id选择器前面要添加’#'符号

（1)语法格式: #id名{属性:属性值;属性:属性值;}

 例如：html中有四张图片，第一张图片宽高为50px*50px,其他图片尺寸为30px*35px。我们就可以给第一张图片加id。

    添加ID：<img id="banner" src="路径">
    
     调用id：#banner{width:50px;height:50px;
     (2)使用场景
    
     1.当我们需要把几个相同元素做区分设置样式时使用
    
     2.当html里有不同元素需要统一样式时使用

注意：每个元素只能有一个id名，id命名规则参考class。

#div1{
	background:rgb(200,200,0);
	color:blue;
	font-size:20px;}

运行结果

1.<p>这是一个段落</p>
2.<p id="div1">这是一个段落</p>

![image-20221112143348166](https://img-blog.csdnimg.cn/a56154a7a78746848357d1a74d6a76cb.png)

注意：由于id属性的唯一性，一般使用css做样式不使用该选择器，而该选择器的主要用途是用来做js特效
————————————————
版权声明：本文为CSDN博主「夺笋123」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/m0_54510474/article/details/124859028

    （1)语法格式: #id名{属性:属性值;属性:属性值;}

 例如：html中有四张图片，第一张图片宽高为50px*50px,其他图片尺寸为30px*35px。我们就可以给第一张图片加id。

    添加ID：<img id="banner" src="路径">
    
    调用id：#banner{width:50px;height:50px;}
    (2)使用场景
     1.当我们需要把几个相同元素做区分设置样式时使用
    
     2.当html里有不同元素需要统一样式时使用

注意：每个元素只能有一个id名，id命名规则参考class。
————————————————

来源：[一点也不酷哼](https://blog.csdn.net/m0_65790549/article/details/122897055)

[夺笋123](https://blog.csdn.net/m0_54510474/article/details/124859028)