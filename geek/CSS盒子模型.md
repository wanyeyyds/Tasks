# CSS盒子模型

盒子模型是html+css中最核心的基础知识，理解了这个重要的概念才能更好的排版，进行页面布局。下面是自己积累和总结的关于css盒子模型的知识^_^，希望对初学者有用。

### **一、css盒子模型概念**

CSS css盒子模型 又称框模型 (Box Model) ，包含了元素内容（content）、内边距（padding）、边框（border）、外边距（margin）几个要素。如图：

![img](https://images2015.cnblogs.com/blog/993105/201607/993105-20160722121801872-494280136.gif)

图中最内部的框是元素的实际内容，也就是元素框，紧挨着元素框外部的是内边距padding，其次是边框（border），然后最外层是外边距（margin），整个构成了框模型。通常我们设置的背景显示区域，就是内容、内边距、边框这一块范围。而外边距margin是透明的，不会遮挡周边的其他元素。

那么，元素框的总宽度 = 元素（element）的width + padding的左边距和右边距的值 + margin的左边距和右边距的值 + border的左右宽度；

元素框的总高度 = 元素（element）的height + padding的上下边距的值 + margin的上下边距的值 ＋ border的上下宽度。

### **二、css 外边距合并（叠加）**

两个上下方向相邻的元素框垂直相遇时，外边距会合并，合并后的外边距的高度等于两个发生合并的外边距中较高的那个边距值，如图：

![img](https://images2015.cnblogs.com/blog/993105/201607/993105-20160722171008560-1813889758.png)![img](https://images2015.cnblogs.com/blog/993105/201607/993105-20160722171015419-1530764673.png)

比较容易理解，所以在页面中有时候遇到实际情况是需要考虑这个因素的。当然外边距合并其实也有存在的意义，如下图：

![img](https://images2015.cnblogs.com/blog/993105/201607/993105-20160722171428919-1743116155.png)

需要注意的是：只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。

css reset 中也会经常用到

```
* {
  margin : 0;
  padding : 0;
}
```

 

### **三、box-sizing属性介绍**

box-sizing属性是用户界面属性里的一种，之所以介绍它，是因为这个属性跟盒子模型有关，而且在css reset中有可能会用到它。

box-sizing : content-box|border-box|inherit;

(1) content-box ,默认值，可以使设置的宽度和高度值应用到元素的内容框。盒子的width只包含内容。

　　即总宽度=margin+border+padding+width

(2) border-box , 设置的width值其实是除margin外的border+padding+element的总宽度。盒子的width包含border+padding+内容

　　　　即总宽度=margin+width

很多CSS框架，都会对盒子模型的计算方法进行简化。

(3) inherit , 规定应从父元素继承 box-sizing 属性的值

关于border-box的使用：

1 一个box宽度为100%，又想要两边有内间距，这时候用就比较好
2 全局设置 border-box 很好，首先它符合直觉，其次它可以省去一次又一次的加加减减，它还有一个关键作用——让有边框的盒子正常使用百分比宽度。

 

### **四、实际开发中遇到的和框模型相关的应用及小问题。**

#### 1 margin越界（第一个子元素的margin-top和最后一个子元素的margin-bottom的越界问题）

以第一个子元素的margin-top 为例：

当父元素没有边框border时，设置第一个子元素的margin-top值的时候，会出现margin-top值加在父元素上的现象，解决方法有四个：

（1）给父元素加边框border （副作用）

（2）给父元素设置padding值  （副作用）

（3）父元素添加 overflow：hidden （副作用）

（4）父元素加前置内容生成。（推荐）

以第四种方法为例：

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
.parent {
     width : 500px;
     height : 500px;
     background-color : red;       
}
.parent : before {
     content : " ";
     display : table;
}

.child {
     width : 200px;
     height : 200px;
     background-color : green;
     margin-top : 50px;
}
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
<div class="parent">
    <div class="child"></div> 
</div>
```

#### 2 浏览器间的盒子模型。

（1）ul标签在Mozilla中默认是有padding值的，而在IE中只有margin有值。

（2）标准盒子模型与IE模型之间的差异：

　　标准的盒子模型就是上述介绍的那种，而IE模型更像是 box-sizing : border-box; 其内容宽度还包含了border和padding。解决办法就是：在html模板中加doctype声明。

#### 3 用盒子模型画三角形

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
<!DOCTYPE html>
<html>
  <head>
    <style>
        .triangle {
            width : 0;
            height: 0;
            border : 100px solid transparent;
            border-top : 100px solid blue; /*这里可以设置border的top、bottom、left、right四个方向的三角*/
        }
    </style>
  </head>
  <body>
    <div class="triangle"></div>
  </body>
</html>    
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

页面显示结果为：

![img](https://images2015.cnblogs.com/blog/993105/201607/993105-20160722183120076-268805707.png)