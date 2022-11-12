# css的基础样式

### 1.文本颜色的设置(可以继承）

color属性：设置文字颜色的比如color：red；（红色等等颜色）；

英文单词color：red;

大多数颜色都有对应的英文单词描述，但英文单词终究有其局限性:无法表示所有颜色

rgb  color：rgb(255,0,0)

什么是三原色？ red，green，blue 什么是像素px？ 对于光学显示器，一整个屏幕是有一个个点组成，每一个点称为一个像素 点，每个像素点都是由一个三元色的发光元件组成，该元件可以发出三种颜 色，red，green，blue。 发光元件协调三种颜色发光的明亮度可以调节出其他颜色 格式：rgb(255,0,0); 参数1控制红色显示的亮度 参数2控制绿色显示的亮度 参数3控制蓝色色显示的亮度数字的范围0-255，0代表不发光，255代表发光，值越大越亮红色：rgb(255,0,0) 绿色：rgb(0,255,0) 蓝色：rgb(0,0,255) 黑色：rgb(0,0,0) # 所有都不亮 白色：rgb(255,255,255) # 所有都最亮 灰色：只要让红色/绿色/蓝色的值都一样就是灰色，而且三个值越小，越偏 黑色，越大越偏白色

rgba  color：rgba(255,0,0,0.1);

rgba到css3中才推出，比起rgb多了一个a，a代表透明度 a取值0-1，取值越小，越透明

十六进制  color: #FF0000;!* 颜色编号 * !* /

#FFEE00 其中FF代表R，EE代表G，00代表B 只要十六进制的颜色每两位都是一样的，那么就可以简写为一个， 例如#F00 等同于#FF0000





### 2.设置字体：

### font-family（可以继承）

常见的字体有："Microsoft YaHei"、"SimHei"、"SimSun"

body {

1. /*font-family可以把多个字体名称作为一个“回退”系统来保存。如果浏览器不支持第一个字体，则会尝试下一个。浏览器会使用它可识别的第一个值。(第一个字体不生效会使用下一个字体。 依此类推)*/

   /* SimSun 宋体
       KaiTi  楷体
       SimHei 黑体*/
       font-family: "Microsoft Yahei", "微软雅黑", "Arial", sans-serif;}常见字体：
   serif 衬线字体
   sans-serif 非衬线字体
   中文：宋体，微软雅黑，黑体

注意：
    1、设置的字体必须是用户电脑里已经安装的字体，浏览器会使用它可识别的第一个值。
#####     2、如果取值为中文，需要用单或双引号扩起来
### 3.设置字体大小：

### font-size

字体常用单位是px，em，，可以设置小数，但是记住最好别设置奇数，浏览器自带默认字号（16px），最小支持12px

了解：Chrome浏览器上默认字体大小16px


p {
    font-size: 24px;}注意：
1、通过font-size设置文字大小一定要带单位，即一定要写px

2、如果设置成inherit表示继承父元素的字体大小值。

### 4.字体风格 ：

### font-style：（可以继承）

normal：正常多数元素的默认值对于默认倾斜或斜体的元素 i em 可以调整成正常非倾斜样式
italic 让元素呈现斜体 一般指的是一个字体在字体设计的过程中，会对一个文字设计 正常体 斜体 粗体 等状态而italic只是选择让使用斜体显示

### 5.文字粗细：

font-weight:(可以继承)

用来定义字体的粗细 其实目前浏览器只支持3个级别 细 正常 粗
normal：正常粗细 可以将默认加粗的字体进行改变为正常 比如 b strong
bold：加粗

border：更粗

lighter：更细

100-900 整除100的整数：因为浏览器只支持 细 粗 正常3个 所以100-300 是细，400-500 正常，600-900 加粗，设置具体粗细，400等同于normal，而700等同于bold，100为lighter，900为bolder

inherit：继承父元素字体的粗细值

### 6.文字属性简写：

/*font-weight: bolder;*//*font-style: italic;*//*font-size: 50px;*//*font-family: 'serif','微软雅黑';*/简写为font: bolder italic 50px 'serif','微软雅黑';

### 6.line-height：注意看清楚他的作用（可以继承）

值：(不支持负值)
数字：没有单位，比如1.5 就是当前元素文字大小的1.5倍
百分比：也是相对于当前元素的文字大小计算的，很少使用
长度：带单位，直接设置行高
使用line-height对单行文字（也可以是内联元素）做垂直居中

text-height：行高
注意: 文字像素不能大于行高

text-height:px或em, 文本行高

文本水平居中: line-height: 值 (值要等于居中元素的高度)

文本垂直居中: text-align:center

![CSSåºç¡æ ·å¼å±æ§è®¾ç½®_ç½é¡µå¸å±](https://s2.51cto.com/images/blog/202105/20/af2aa52c1b0b42db564e73ca7bd736ed.jpeg?x-oss-process=image/watermark,size_16,text_QDUxQ1RP5Y2a5a6i,color_FFFFFF,t_30,g_se,x_10,y_10,shadow_20,type_ZmFuZ3poZW5naGVpdGk=/format,webp/resize,m_fixed,w_1184)

<html lang="en"><head>

    1.<meta charset="UTF-8">
    2.<title>Titletitle>
    <style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
            text-align: center;
            line-height: 100px;
        }
    style>head><body><div>
    <p>文本p>div><br><br><br><div>
    <span>文本span>div><br><br><br><div>

<span style="inline-block">文本span>div>body>html>



### 7.首行文本缩进：

text-indent：单位是px

将段落的第一行缩进 32像素：

p {
  text-indent: 32px;}

### 8.控制行内容水平方向对齐：

text-align

left：默认 左对齐
center：居中
right：右对齐

justify：两端对齐

使用text-align注意:

在使用text-align时, 它只能争对文字(包括在块元素中的文字), 行内元素, 和行内块元素进行水平居中, 只争对没有包含文字的块元素是不起作用的.

### 9.设置背景：

background-color(和color一样，只是它设置的是背景）background-color: red;``background-color: rgb(0,255,0);``background-color: rgba(0,255,0,0.1);``background-color: #00ffff;

background-image

设置标签的背景图片

background-image: url(“images/2.jpg”);background-image: url(“图片网址”);注意：如果图片的大小没有标签的大小大，那么会自动在水平和锤子方向平铺和填充

background-size

设置标签的背景图片的宽、高

background-size: 300px 300px; background-size: 100% 100%;

background-repeat

设置标签的背景图片的平铺方式

background-repeat: repeat; #默认值，在垂直和水平方向都重复background-repeat: no-repeat; #不重复，背景图片将仅显示一次background-repeat: repeat-x; #背景图片将在水平方向平铺background-repeat: repeat-y; #背景图片将在垂直方向平铺应用：可以在服务端将一个大图片截成小图片，然后在客户端基于平铺属性将小图重复这样用户就以为是一张大图，如此，既节省了流量提升了速度，又不影响用户访问例如很多网站的导航条都是用这种手法制作的

background-attachment

设置标签的背景图片在标签中固定或随着页面滚动而滚动

background-attachment: scroll; #默认值，背景图片会随着滚动条的滚动而滚动background-attachment: fixed; #不会随着滚动条的滚动而滚动

background-position

前端的坐标系"：`` *-------------------->x轴 | | | | | | y轴 *图片默认都是在盒子的左上角，background-position：属性，就是专门用于控制背景图片的位置

background-position：水平方向的值，垂直方向的值1、具体的方位名词 *水平方向：left，center，right* *垂直方向：top，center，bottom*　　 *如果只设置了一个关键词，那么第二个值就是"center"。*2、百分比``　　***第一个值是水平位置，第二个值是垂直位置。\* 　　\*左上角是 0% 0%。右下角是 100% 100%。\* 　　\*如果只设置了一个值，另一个值就是50%。 ***``3、具体的像素（一定要加px单位）`` 例如：30px，50px等等　　第一个值是水平位置，第二个值是垂直位置。　　左上角是 0 0。单位是像素 (0px 0px) 或任何其他的 CSS 单位。　　如果只设置了一个值，另一个值就是50%。　　可以混合使用%和position值。

inherit

设置从父元素继承background属性值

以上背景属性的值均可以设置为inherit，代表从父元素继承background属性



### 10.文本修饰：

text-decoration:(不继承)

1. none：取消下划线 默认。定义标准的文本

2. underline:下划线

3. overline:上划线

4. line-through：删除线 定义穿过文本下的一条线。

5. inherit

  继承父元素的text-decoration属性的值。

  常用的为去掉a标签默认的下划线：

  a {
    text-decoration: none;}

  ### 11.设置一个元素的宽（width）和高（height）

  ### 12.让块级元素水平居中：

  margin:0 auto;

  ### 13.设置边框：

  border:5px dashed darkturquoise;（里面的值是边框线的大小）

  ### 14.border：

  是简写属性，设置所有的边框属性

  1.border-width
  2.border-style
  3.border-color

  

  6.字符间距（了解）
  注意: 只对中文起作用

  letter-spacing: px或em, 定义文字与文字之间的距离
  7.单词间距（了解）
  word-spacing: px或em, 定义英文单词之间的距离
  8.示例
  登录后复制 
  后代选择器 {
              width: 500px;
              height: 200px;
              background-color: yellow;

              text-align: center;
      
              text-decoration: underline;
      
              line-height: 200px;
          }
          a {
              text-decoration: none;
          }
      " _ue_custom_node_="true">hello英雄不问出处，流氓不论岁数<a href="#">
  -----------------------------------

  
  来源：[凝望1](https://blog.csdn.net/weixin_62127171/article/details/126491935)

  [51CTO博客作者淘小欣](https://blog.51cto.com/u_15073468/2792610)
