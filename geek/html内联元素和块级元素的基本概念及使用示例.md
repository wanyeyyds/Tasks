# html内联元素和块级元素的基本概念及使用示例

### 一.定义

HTML可以将元素分类方式分为内联（行内）元素、块级（块状）元素和行内[块元素](https://so.csdn.net/so/search?q=块元素&spm=1001.2101.3001.7020)三种。行内元素与块级函数可以相互转换,这三种类型可以通过`display`属性进行相互转换。

根据块级元素的概念我们可以理解为块级元素前后带有换行符，也就相当于元素前后加了一个<br>标签。我们可以把块级元素想象成一个块或一个矩形，所以块级元素能设置高度宽度属性



根据内联元素的概念，我们可以理解为内联元素前后没有换行符。我们可以把内联元素想象成一条线，所以它不能设置height属性和width属性。

### 二、块级元素

1.设置元素为块级元素：display:inline

2.特点：

独处一行。
宽度默认为父级100%，高度为元素的高度。
可设置宽高。
可以容纳行内元素和其他块元素。特殊：文字类的块级元素不能放块元素，例如<p>、<h1>~<h6>、<dt>。

3.块级元素（block element）标签

address -地址
blockquote - 块引用
center – 居中对齐
dir -目录列表
div - 常用块级容易，也是CSS layout的主要标签
dl - 定义列表
fieldset - form控制组
form - 交互表单
h1 - 大标题
h2 - 副标题
h3 - 3级标题
h4 - 4级标题
h5 - 5级标题
h6 - 6级标题
hr - 水平分隔线
isindex - input prompt
menu - 菜单列表
noframes - frames可选内容，（对于不支持frame的浏览器显示此区块内容
noscript - 可选脚本内容（对于不支持script的浏览器显示此内容）
ol - 排序表单
p - 段落
pre - 格式化文本
table - 表格
ul - 非排序列表

### 三、行内元素

1.设置元素为块级元素：display:block

2.特点：

与其他元素共处一行。
宽高为内容的宽高，不可设置宽高。
不可设置上下的外边距。
行内元素只能容纳其他行内元素或者文本。特殊：a比较特殊，可以放块级元素，但是链接里面不能再放链接。
3.常见的行内元素有：img、a、span、i、lebel、input、button内联元素(inline element)

a - 锚点
abbr - 缩写
acronym - 首字
b - 粗体(不推荐)
bdo - bidi override
big - 大字体
br - 换行
cite - 引用
code - 计算机代码(在引用源码的时候需要)
dfn - 定义字段
em - 强调
font - 字体设定(不推荐)
i - 斜体
img - 图片
input - 输入框
kbd - 定义键盘文本
label - 表格标签
q - 短引用
s - 中划线
samp - 定义范例计算机代码
select - 项目选择
small - 小字体文本
span - 常用内联容器，定义文本内区块
strike - 中划线
strong - 粗体强调
sub - 下标
sup - 上标
textarea - 多行文本输入框
tt - 定义打字机文本
var - 定义变量

### 四、行内块级元素

1.设置元素为块级元素：display:inline-block

2.特点：

和相邻行内元素在同一行，但是之间会有空白缝隙。
默认宽度是他本身内容的宽度。
宽度、高度、行高、外边距以及内边距都可以手动设置。
3.常见的行内块级元素有：<img>、<input>、<td>
4.可以把行内块级元素当成文本来对待：
（1）行内块级元素间会有字间距，可以采用父级font-size：0px;自己font-size：想要的字号。进行消除间距。
（2）此时元素是不存在文档流中的，所以使用margin值并不能使其居中，而是应该在父级添加text-aling：center ==》水平居中。line-height ==>竖直居中

### 五。块级元素和内联元素深入理解

块元素又名块级 [元素](http://baike.baidu.com/view/19993.htm)(block element)，和其对应的是内联元素(inline element)，都是html规范中的概念。块元素和内联元素的基本差异是块元素一般都从新行开始。而当加入了css控制以后，块元素和内联元素的这种 [属性](http://baike.baidu.com/view/77730.htm)差异就不成为差异了。比如，我们完全可以把内联元素加上display:block这样的属性，让它也有每次都从新行开始的属性，即成为块元素同样我们可以把块元素加上display:inline这样的属性，让它也在一行上排列。

## 2block元素的特点 

①总是在新行上开始；

②高度，行高以及外边距和内边距都可控制；

③宽度缺省是它的容器的100%，除非设定一个宽度。

④它可以容纳内联元素和其他块元素

## 3inline元素的特点[编辑](http://baike.baidu.com/view/8864845.htm?fr=aladdin#)

①和其他元素都在一行上；

②高，行高及外 [边距](http://baike.baidu.com/view/1268350.htm)和内边距不可改变；

③宽度就是它的文字或图片的宽度，不可改变

④内联元素只能容纳文本或者其他内联元素————————————————

版权声明：本文为CSDN博主「WHOVENLY」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/huanan__/article/details/117431828



：本文为CSDN博主「前端学习线路」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/webxuexi168/article/details/104382660