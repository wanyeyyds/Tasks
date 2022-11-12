# JavaScript的基本语法

### 什么是JavaScript？

JS是一门弱类型的语言，用于给我html页面上面添加动态效果与互相操作。

### JavaScript基本语法

#### 1.JavaScript编写代码必须在 script标签中

列如：<script>在这中间编写我们的代码</script>

#### 2.输入语句

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165110130.png)

#### 3.定义变量

在JavaScript里面无论是数字还是字符或者布尔类型都用var来定义。

列如：

  整数number

var a1=1;

console.log(a1);

小数

var a2=1.232;

console.log(a2);

 

 定义字符变量：

在我的js里面字符可以使用双引号"  "

单引号'  '

  还可以使用该反引号`  `

var a3='1234';

console.log(a3);

​    

var  a4='数字的值'+a1+"Hello";

console.log(a4);

 只有反引号可以使用$进行连接

var a5=`哈哈哈${a1}`

console.log(a5);

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165110132.png)

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165110133.png)

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165110134.png)

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165110134.png)

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111136.png)

### 变量命名规范

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111137.png)

#### 4.查看类型

  console.log(1234/”1234”); 求出来的值为1

因为在我们的js里面字符可以和数字相除相乘,系统会自动把字符转换成数字，前提是该字符是1223这类的如果是(abbch哈哈哈)无法转换。

   NaN 非数字 not a number

无穷大Infinity

console.log(1/0);

无穷小-Infinity

console.log(-Infinity);

#### 5.类型转换

   转换将"123"这类字符转成数字

parseInt转成整数

  console.log(parseInt("1.23"));值为1

parseFloat转成小数

console.log(parseFloat("1.23"))值为1.23

#### 6.小数

在所有的编程软件中,基本一些小数预算不靠谱

console.log(0.6-0.2);

 在我们的数学里面等于0.4,但是在我们的编程语句里为3.999999.......

小数取几位(????).tofixed

console.log((1.2345).toFixed(2));//值为1.2

boolean类型

var b1=true;

var b2=false;

#### 7.boolean 运算符：

  ||:或者  &&：并且
||:或者里面一个为真那个为真，

console.log(b1||b2); 真

&&：并且里面一个为假就为假

console.log(b1&&b2); 假

console.log(!b1);//值为假

console.log(!b2);//值为真

#### 8.什么情况下会得到false

1.当我们的字符串为""时为false

2.当我们的数字为0时为false

3.null:为false

4.undefined:为无定义 也为false

5.NaN:非数字 false

#### 9.什么情况下会得到true

1.当我们的字符为a,z和任意文字时为true.

2.当我们的数字不为0时为true.

3.当不为null时为true.

#### 10.短路:

在||里面如果前面的数有一个为真的那么就会在这个数停下

如果为假会一直往后走

console.log(""||0);//在0的时候停下所以拿到0

console.log(1||"1"||"");//在第一个数停下值为1,因为第一个数为真，所以不需要再进行判断了，因为或者里面一个为真就为真。

//&&当有该数为假那就在这里停下拿到该值

console.log(1&&"123"&&0&&"");//值为0在遇到第一个假时直接退出，因为并且里面一个为假就为假。

#### 11.js中的弹框

1.提示框

var c1=alert("请带好随身物品");

2.询问框

var c2=confirm("你确定要退出吗?");

点击确定时值为:true  点击取消时值为:false

console.log(c2);

3.输入框:输入框里的都是字符

var c3=prompt("请输入一个数字");

console.log(c3);

#### 12.数组:

1.数组没有类型限制

2.数组可以读取任意的下标的值

3.长度可以任意变化

var as=[1,2,"3",true];

as[100]="a";//下标无限制

console.log(as);

as.length=2;//拿到数组的前两个

console.log(as);

#### 13.定义对象

var stu={

"stu_no":1,

"stu_name":"小明",

"stu_sex":"男"

}

//可以增加动态属性

stu.stu_address="xx";

console.log(stu);

#### 14.=的不同意思

=     赋值

==    无视类型,作比较

=== 比较,先比较类型,在比较值console.log(1=="1");//true

console.log(1==="1");//false

#### 15.!!的作用

!!可以转成boolean类型

console.log(!!"a");//false

####  16.while循环

var d1=1;

while(d1<10){

d1++;

在我们的页面中进行HTML输出，里面可以放HTML代码

document.write("哈哈哈<br>");

}

#### 17.for循环

​    由用户在我们的输入框中输入一个数，因为输入框里面的数是字符，所以转换成整数。

var d2=prompt("请输入你要循环的次数");

for(var i=1;i<parseInt(d2);d2++){

document.write("哈哈哈哈<br>");

}
来源：[客行.](https://blog.csdn.net/m0_65725031/article/details/123148853)