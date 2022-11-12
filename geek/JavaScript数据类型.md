# JavaScript数据类型

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111138.jpg)

### **数字型 Number**

- JavaScript 数字类型既可以用来保存整数值，也可以保存小数(浮点数）。

- 在JS中八进制前面加0，十六进制前面加 0x

- 数字型三个特殊值， Infinity ，代表无穷大，大于任何数值； -Infinity ，代表无穷小，小于任何数值； NaN ，Not a number，代表一个非数值

- isNaN() 用来判断一个变量是否为非数字的类型，不是数字返回 true ，是数字返回 false

- Number类型包含两种数值：整型和浮点型。
  浮点数值的取值范围：Number.MIN_VALUE和Number.MAX_VALUE之间。
  alert(Number.MIN_VALUE); //最小值
  alert(Number.MAX_VALUE); //最大值

  看下面的例子：

  ```
  <!DOCTYPE html>``<``html` `lang``=``"en"``>``<``head``>``  ``<``meta` `charset``=``"UTF-8"``>``  ``<``meta` `name``=``"viewport"` `content``=``"width=device-width, initial-scale=1.0"``>``  ``<``meta` `http-equiv``=``"X-UA-Compatible"` `content``=``"ie=edge"``>``  ``<``title``>JavaScript数据类型</``title``>``  ``<``script``>``    ``// 1、Undefined``    ``// 未定义``    ``//alert(a); // 页面会报错：``    ``// 定义未赋值``    ``//var box;``    ``//alert(box);// 弹出警告框：undefined` `    ``// 2、Null``    ``/* var box=null;``    ``a lert(typeof box); */` `    ``// 3、Boolean``   ``/*  var box=true;``    ``alert(box); */` `    ``// 4、Number``    ``var box=45; // 整型``    ``var box1=45.6;// 浮点型``    ``alert("box的值是:"+box+","+"box1的值是:"+box1);``  ``</``script``>``</``head``>``<``body``>  ``</``body``>``</``html``>
  ```

  效果：

  ![img](https://img.jbzj.com/file_images/article/202202/2022022611074930.jpg)

  注意：

  Number类型除了整型和浮点型，还有另外一种类型：NaN，即非数值（Not a Number）是一个特殊的值，这个数值用于表示一个本来要返回数值的操作数而未返回数值的情况（这样就不会抛出错误了）。比如，在其他语言中，任何数值除以0都会导致错误而终止程序执行。但在ECMAScript中，会返回特殊的值，因此不会影响程序执行。
  例如：

  ```
  <!DOCTYPE html>``<``html` `lang``=``"en"``>``<``head``>``  ``<``meta` `charset``=``"UTF-8"``>``  ``<``meta` `name``=``"viewport"` `content``=``"width=device-width, initial-scale=1.0"``>``  ``<``meta` `http-equiv``=``"X-UA-Compatible"` `content``=``"ie=edge"``>``  ``<``title``>JavaScript数据类型</``title``>``  ``<``script``>``    ``// 1、Undefined``    ``// 未定义``    ``//alert(a); // 页面会报错：``    ``// 定义未赋值``    ``//var box;``    ``//alert(box);// 弹出警告框：undefined` `    ``// 2、Null``    ``/* var box=null;``    ``a lert(typeof box); */` `    ``// 3、Boolean``   ``/*  var box=true;``    ``alert(box); */` `    ``// 4、Number``    ``/* var box=45; // 整型``    ``var box1=45.6;// 浮点型``    ``alert("box的值是:"+box+","+"box1的值是:"+box1); */``    ``// 特殊的Number类型:NaN``    ``var box=0/0; //NaN``    ``var box1=12/0; //Infinity 无穷大``    ``var box2=12/0*0; //NaN``    ``alert("box的值是:"+box+","+"box1的值是:"+box1+","+"box2的值是:"+box2);``  ``</``script``>``</``head``>``<``body``>  ``</``body``>``</``html``>
  ```

  结果：

  ![img](https://img.jbzj.com/file_images/article/202202/2022022611074931.jpg)

  可以通过Number.NaN得到NaN值，任何与NaN进行运算的结果均为NaN，NaN与自身不相等（NaN不与任何值相等）。

  ```
  alert(Number.NaN); ``//NaN``alert(NaN+1); ``//NaN``alert(NaN==NaN); ``//false
  ```

  ECMAScript提供了isNaN()函数，用来判断这个值到底是不是NaN。isNaN()函数在接收到一个值之后，会尝试将这个值转换为数值。

  ```
  alert(isNaN(NaN)); ``//true``alert(isNaN(25)); ``//false 25是一个数值
  ```

  isNaN()函数也适用于对象。在调用isNaN()函数过程中，首先会调用valueOf()方法，然后确定返回值是否能够转换成数值。如果不能，则基于这个返回值在调用toString()方法，在测试返回值。

  ```
  var` `box={``   ``toString:``function``(){``      ``return` `'123'``;    ``     ``}``};
  ```

  有3个函数可以把非数值转换为数值:Number()、parseInt()和parseFloat()。Number()函数是转型函数，可以用于任何数据类型，而另外两个则专门用于把字符串转换成数值。

  ```
  alert(Number(``true``));  ``//1，Boolean类型的true和false分别转换成1和0``alert(Number(25));   ``//25，数值型直接返回
  var` `box=250;``alert(``typeof` `box);``//box是Number类型，值是250，类型返回的字符串是number。
  ```

### **布尔型 Boolean**

- 布尔类型有两个值：true 和 false ，其中 true 表示真（对），而 false 表示假（错）。

- 布尔型和数字型相加的时候， true 的值为 1 ，false 的值为 0。

- ### Boolean类型

  Boolean类型有两个值：true和false。而true不一定等于1，false不一定等于0，JavaScript是严格区分大小写的，True和False或者其他都不是Boolean类型的值。
  看下面例子：

  ```
  <!DOCTYPE html>``<``html` `lang``=``"en"``>``<``head``>``  ``<``meta` `charset``=``"UTF-8"``>``  ``<``meta` `name``=``"viewport"` `content``=``"width=device-width, initial-scale=1.0"``>``  ``<``meta` `http-equiv``=``"X-UA-Compatible"` `content``=``"ie=edge"``>``  ``<``title``>JavaScript数据类型</``title``>``  ``<``script``>``    ``// 1、Undefined``    ``// 未定义``    ``//alert(a); // 页面会报错：``    ``// 定义未赋值``    ``var box;``    ``//alert(box);// 弹出警告框：undefined` `    ``// 2、Null``    ``/* var box=null;``    ``a lert(typeof box); */` `    ``// 3、Boolean``    ``var box=true;``    ``alert(box);``  ``</``script``>``</``head``>``<``body``>  ``</``body``>``</``html``>
  ```

  效果：

  ![img](https://img.jbzj.com/file_images/article/202202/2022022611074829.jpg)

  注意：

  虽然Boolean类型的字面量只有true和false两种，但ECMAScript中所有类型的值都有与这两个Boolean值等价的值。要将一个值转换为与其对应的Boolean值，可以使用转型函数Boolean()。

  ```
  var` `hello=``'Hello World'``;``var` `hello2=Boolean(hello);``alert(``typeof` `hello); 弹出``true
  ```

  上面是一种显示转换，属于强制性转换。而实际应用中，还有一种隐式转换。比如，在if条件语句里面的条件判断，就存在隐式转换。

  ```
  var` `hello =``'Hello World!'``;``if``(hello){``  ``alert(``'如果条件为true，就执行我这条！'``);``}``else``{``  ``alert(``'如果条件为false，就执行我这条！'``);``}
  var` `box=``true``;``alert(``typeof` `box);``//box是Boolean类型，值是true,类型返回的字符串是boolean
  ```

### 字符串型 String

字符串型可以是引号中的任意文本，其语法为 双引号 “” 和 单引号’’

因为 HTML 标签里面的属性使用的是双引号，JS 这里我们更推荐使用单引号

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111139.png)

- JS 可以用单引号嵌套双引号 ，或者用双引号嵌套单引号 (`外双内单，外单内双`)
- 字符串是由若干字符组成的，这些字符的数量就是字符串的长度。通过字符串的 `length` 属性可以获取整个字符串的长度。

```
var` `strMsg = ``"我是帅气多金的程序猿！"``;``alert(strMsg.length); ``// 显示 11
```

多个字符串之间可以使用 + 进行拼接，其拼接方式为 `字符串 + 任何类型 = 拼接之后的新字符串`(只要有字符串类型和其他类型相拼接，最终结果是字符串类型)

```
//1.1 字符串 "相加"alert('hello' + ' ' + 'world'); // hello world//1.2 数值字符串 "相加"alert('100' + '100'); //
```

JavaScript

String类型用于表示由零个或多个16为Unicode字符组成的字符序列，即字符串。字符串可以由双引号("")或单引号('')表示。
例如：

```
var` `box=``"我是字符串类型，我用双引号"``;``var` `box1=``'我也是字符串类型，我用单引号'``;
```

注：在某些其他语言中，单引号和双引号表示的字符串解析方式不同，而ECMAScript中，这两种表示方法没有任何区别。但要记住的是，必须成对出现，不能穿插使用，否则会出错。
例如：

```
// 会报错，单引号和双引号不能交叉使用``var` `box='我是字符串类型，我用双引号";
```

如果值有toString()方法，则调用该方法并返回相应的结果；如果是null或者undefined，则返回"null"或者"undefined"。

```
var` `box=``'字符串'``;``alert(``typeof` `box);``//box是String类型，值是字符串，类型返回的字符串是string。
```

### Object类型

ECMAScript中的对象其实就是一组数据和功能的集合。对象可以通过执行new操作符后跟要创建的对象类型的名称来创建。

```
var` `box=``new` `Object();
```

- Undefined类型只有一个值，即undefined。
- 表示未定义或者定义未赋值。

看下面的例子：

```
<!DOCTYPE html>``<``html` `lang``=``"en"``>``<``head``>``  ``<``meta` `charset``=``"UTF-8"``>``  ``<``meta` `name``=``"viewport"` `content``=``"width=device-width, initial-scale=1.0"``>``  ``<``meta` `http-equiv``=``"X-UA-Compatible"` `content``=``"ie=edge"``>``  ``<``title``>JavaScript数据类型</``title``>``  ``<``script``>``    ``// 1、Undefined``    ``// 未定义``    ``alert(a); // 页面会报错：``  ``</``script``>``</``head``>``<``body``>  ``</``body``>``</``html``>
```

效果：

![img](https://img.jbzj.com/file_images/article/202202/2022022611074826.jpg)

```
<!DOCTYPE html>``<``html` `lang``=``"en"``>``<``head``>``  ``<``meta` `charset``=``"UTF-8"``>``  ``<``meta` `name``=``"viewport"` `content``=``"width=device-width, initial-scale=1.0"``>``  ``<``meta` `http-equiv``=``"X-UA-Compatible"` `content``=``"ie=edge"``>``  ``<``title``>JavaScript数据类型</``title``>``  ``<``script``>``    ``// 1、Undefined``    ``// 未定义``    ``//alert(a); // 页面会报错：``    ``// 定义未赋值``    ``var box;``    ``alert(box);// 弹出警告框：undefined``  ``</``script``>``</``head``>``<``body``>  ``</``body``>``</``html``>
```

效果：

![img](https://img.jbzj.com/file_images/article/202202/2022022611074827.jpg)

我们没有必要显式的给一个变量赋值为undefined，因为没有赋值的变量会隐式的赋值为undefined；而undefined主要的目的是为了用于比较，ECMAScript第3版之前并没有引入这个值，引入之后为了正式区分空对象与未经初始化的变量。

注：未初始化的变量与根本不存在的变量（未声明的变量）也是不一样的。

```
var` `box;``alert(age); ``// age is not defined
```

如果typeof box，typeof age都返回的undefined。从逻辑上思考，他们的值，一个是undefined，一个报错；他们的类型，却都是undefined。所以，我们在定义变量的时候，尽可能的不要只声明，不赋值。

```
var` `box;``alert(``typeof` `box);``//box是Undefined类型，值是undefined，类型返回的字符串是"undefined"。
```

Null类型是一个只有一个值的数据类型，即特殊的值null。它表示一个空对象引用（指针），而typeof操作符检测null会返回Object。
看下面的例子：

```
<!DOCTYPE html>``<``html` `lang``=``"en"``>``<``head``>``  ``<``meta` `charset``=``"UTF-8"``>``  ``<``meta` `name``=``"viewport"` `content``=``"width=device-width, initial-scale=1.0"``>``  ``<``meta` `http-equiv``=``"X-UA-Compatible"` `content``=``"ie=edge"``>``  ``<``title``>JavaScript数据类型</``title``>``  ``<``script``>``    ``// 1、Undefined``    ``// 未定义``    ``//alert(a); // 页面会报错：``    ``// 定义未赋值``    ``var box;``    ``//alert(box);// 弹出警告框：undefined` `    ``// 2、Null``    ``var box=null;``    ``alert(typeof box);``  ``</``script``>``</``head``>``<``body``>  ``</``body``>``</``html``>
```

效果：

![img](https://img.jbzj.com/file_images/article/202202/2022022611074828.jpg)

如果定义的变量准备在将来用于保存对象，那么最好将该变量初始化为null。这样。当检查null值就知道该变量是否已经分配了对象。

```
var` `box=``null``;``if``(bod!=``null``){``  ``alert(``'box 对象已存在！'``);``}
```

#### 12.数组:

1.数组没有类型限制

2.数组可以读取任意的下标的值

3.长度可以任意变化

var as=[1,2,"3",true];

as[100]="a";//下标无限制

console.log(as);

as.length=2;//拿到数组的前两个

console.log(as);

### 3.2 获取变量数据类型

typeof 可用来获取检测变量的数据类型

```
var` `num = 18;``console.log(``typeof` `num) ``// 结果 number
```

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111140.jpg)



### 3.3 数据类型转换

转换为字符串

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111141.jpg)

转换为数字型（重点）

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111142.jpg)

转换为布尔型

![在这里插入图片描述](https://img.jbzj.com/file_images/article/202203/20220327165111143.jpg)





来源：[...](https://www.jb51.net/article/242384.htm)

[。。](https://www.jb51.net/article/238946.htm)