# CSS伪类

### 1.CSS 伪类

是用来添加一些选择器的特殊效果。

伪类用于定义元素的特殊状态。

例如，它可以用于：

- 设置鼠标悬停在元素上时的样式
- 为已访问和未访问链接设置不同的样式
- 设置元素获得焦点时的样式

由于状态的变化是非静态的，所以元素达到一个特定状态时，它可能得到一个伪类的样式；当状态改变时，它又会失去这个样式。由此可以看出，它的功能和 class 有些类似，但它是基于文档之外的抽象，所以叫伪类。

### 2.伪类语法：

selector:pseudo-class {property:value;}

### 3.CSS也可以使用伪类：

selector.class:pseudo-class {property:value;}

### 4.Anchor伪类：

在支持CSS的浏览器中，链接的不同状态都可以以不同的方式显示

举例：

a:link {color:#FF0000;} 未访问的链接
a:visited {color:#00FF00;} 已访问的链接
a:hover {color:#FF00FF;}  鼠标划过链接
a:active {color:#0000FF;}  已选中的链接

注意： 在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。

注意： 在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。

注意：伪类的名称不区分大小写。

### 5.伪类和css类

伪类可以与CSS类配合：

当您将鼠标悬停在例子中的链接上时，它会改变颜色：

实例
a.highlight:hover {
  color: #ff0000;
}

![img](https://img-blog.csdnimg.cn/5c582d2454544aa8a54a11cdfae039c4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASDU2Nzgw,size_20,color_FFFFFF,t_70,g_se,x_16)

如果在上面的例子的链接已被访问，它会显示为红色

悬停在 <div> 上
在 <div> 元素上使用 :hover 伪类的实例：

实例
div:hover {
  background-color: blue;
}

简单的工具提示悬停
把鼠标悬停到 <div> 元素以显示 <p> 元素（类似工具提示的效果）：

悬停到我上面来显示 <p> 元素。

显示的：嘿嘿，我在这里！
p {
  display: none;
  background-color: yellow;
  padding: 20px;
}

div:hover p {
  display: block;
}



### 6.CSS：first-child伪类

可以使用：first-child伪类来选择元素的第一个子元素

注意：在IE8的之前版本必须声明<!DOCTYPE>,这样：first-child才能生效。

### 7.匹配一个<p>元素

在下面的例子中，选择器匹配作为任何元素的第一个子元素的 <p> 元素：

![img](https://img-blog.csdnimg.cn/c3c738f705964a54bc2c05b7f3e429be.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASDU2Nzgw,size_17,color_FFFFFF,t_70,g_se,x_16)

### 8.匹配所有<p>元素中的第一个<i>元素

在下面的例子中，选择相匹配的所有 <p> 元素的第一个 <i> 元素：

![img](https://img-blog.csdnimg.cn/6e18392fc78c4af1bc7d8aeb7f60c7ff.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASDU2Nzgw,size_20,color_FFFFFF,t_70,g_se,x_16)

### 9.匹配所有作为第一个元素的<p>元素中的所有<i>元素

在下面的例子中，选择器匹配所有作为元素的第一个子元素的<p>元素中的所有<i>元素：

例子：

 ![img](https://img-blog.csdnimg.cn/4e5bb1838e474b9e8182aa80b29200d4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASDU2Nzgw,size_20,color_FFFFFF,t_70,g_se,x_16)

### 10.CSS：lang伪类

lang伪类使你有能力为不同的语言定义特殊的规则

注意：IE8必须声明<!DOCTYPE>才能支持；lang伪类。

在下面的例子中，lang类为属性值为no的q元素定义引号的类型：

例子：

 ![img](https://img-blog.csdnimg.cn/1eaba33f411b4f5887064882f47d9c98.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBASDU2Nzgw,size_20,color_FFFFFF,t_70,g_se,x_16)

### 11.所有CSS伪类/元素

选择器

示例

示例说明

:link

a:link

选择所有未访问链接

:visited

a:visited

选择所有访问过的链接

:active

a:active

选择正在活动链接

:hover

a:hover

把鼠标放在链接上的状态

:focus

input:focus

选择元素输入后具有焦点

:first-letter

p:first-letter

选择每个<p> 元素的第一个字母

:first-line

p:first-line

选择每个<p> 元素的第一行

:first-child

p:first-child

选择器匹配属于任意元素的第一个子元素的 <]p> 元素

:before

p:before

在每个<p>元素之前插入内容

:after

p:after

在每个<p>元素之后插入内容

:lang(language)

p:lang(it)

为<p>元素的lang属性选择一个开始值

[来源](https://www.w3school.com.cn/css/css_pseudo_classes.asp)