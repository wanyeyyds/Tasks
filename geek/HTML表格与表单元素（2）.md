# HTML

# 表格与表单元素

1.<table border="1">

2.        <thead>
            <th>序号</th>
            <th>名称</th>
            <th>单价</th>
          </thead>
          <tbody>
              <tr>
                  <td>1</td>
                  <td>苹果</td>
                  <td>￥1.00</td>
              </tr>
              <tr>
                  <td>2</td>
                  <td>香蕉</td>
                  <td>￥2.00</td>
              </tr>
              <tr>
                  <td>3</td>
                  <td>桃子</td>
                  <td>￥3.00</td>
              </tr>
          </tbody>
          </table>

效果如下：

—<table border="1">
        <thead>
            <th>序号</th>
            <th>名称</th>
            <th>单价</th>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>苹果</td>
                <td>￥1.00</td>
            </tr>
            <tr>
                <td>2</td>
                <td>香蕉</td>
                <td>￥2.00</td>
            </tr>
            <tr>
                <td>3</td>
                <td>桃子</td>
                <td>￥3.00</td>
            </tr>
        </tbody>
    </table>
效果如下：

![image-20221109113538257](https://img-blog.csdnimg.cn/45a115bfbd1a4cbfb24dddaef2de6eae.png)

分析： 

<table></table>：表格标签

        border="1"，设置边框厚度

<thead></thead>：表头（在表格的第一行，会加粗）

        <th></th>：表头的第一列中的每一个数据（即：序号、名称、单价）

<tbody></tbody>：表体（从第二行开始的数据）

        <tr></tr>：表体的每一行（即第一行；第二行；第三行）
    
                <td></td>：表体每一行中的每一列数据（即：1 苹果 ￥1.00）

2）进阶表格样式：
    1.<table border="1">
        <thead>
            <th></th>
            <th>周一</th>
            <th>周二</th>
            <th>周三</th>
            <th>周四</th>
            <th>周五</th>
        </thead>
        <tbody>
            <tr>
                <td rowspan="4">上午</td>
                <td>语文</td>
                <td>数学</td>
                <td>英语</td>
                <td>语文</td>
                <td>数学</td>
            </tr>
            <tr>
                <td>美术</td>
                <td>英语</td>
                <td>劳动</td>
                <td>体育</td>
                <td>科学</td>
            </tr>
            <tr>
                <td>科学</td>
                <td>语文</td>
                <td>音乐</td>
                <td>数学</td>
                <td>美术</td>
            </tr>
            <tr>
                <td>体育</td>
                <td>劳动</td>
                <td>数学</td>
                <td>美术</td>
                <td>英语</td>
            </tr>
            <tr>
                <td colspan="6" align="center">午休</td>
            </tr>
            <tr>
                <td rowspan="3">下午</td>
                <td>英语</td>
                <td>语文</td>
                <td>英语</td>
                <td>音乐</td>
                <td>体育</td>
            </tr>
            <tr>
                <td>劳动</td>
                <td>音乐</td>
                <td>美术</td>
                <td>英语</td>
                <td>语文</td>
            </tr>
            <tr>
                <td>自习</td>
                <td>自习</td>
                <td>自习</td>
                <td>自习</td>
                <td>自习</td>
            </tr>
            <tr>
                <td colspan="6" align="center">放学</td>
            </tr>
        </tbody>
    </table>
![image-20221109113715060](https://img-blog.csdnimg.cn/abb5d6752e2b4262ad582405f9b275c5.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_13,color_FFFFFF,t_70,g_se,x_16)

二、表单元素——<form> 
1、基本样式：
    <form action="">

    </form>

2、input标签1——用户名和密码
        <label for="username">用户名:</label>
        <input id="username" type="text" placeholder="用户名">
        <br><br>
        <label for="password">密码:</label>
        <input id="password" type="password" placeholder="密码">
效果如下：

![image-20221109114131097](https://img-blog.csdnimg.cn/49be71c2426347d9a243b663adfb02b9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_13,color_FFFFFF,t_70,g_se,x_16)

分析：

第一行：<label> + <input>

第二行：<label> + <input>

label：标签的意思。

<label>：

        for属性：意为将该标签，绑定到id为username的<input>上。
    
        绑定成功后，点击“用户名”，即可获取到输入框的焦点。

<input>：

        id属性：<input>的唯一标识，就像我们的身份证一样。
    
        type：
    
                text：文本框。
    
                password：密码框，输入时，自动隐藏密码（自动转换成小圆点）。
    
        placeholder：当输入框无内容时，显示的提示信息（灰色）。

3、select标签——下拉框
        <select name="" id="">
            <option value="">男</option>
            <option value="">女</option>
        </select>
效果如下： 

 ![image-20221109114003018](https://img-blog.csdnimg.cn/d00af3e06fd64c1dbcc3e2f5b3f8c632.png)

 分析：

        <option>：下拉框中的每一个值

4、input标签2——单选框（type="radio"）
        <label for="">苹果:</label>
        <input type="radio" name="fruit">
        <label for="">香蕉:</label>
        <input type="radio" name="fruit">
        <label for="">桃子:</label>
        <input type="radio" name="fruit">
效果如下：

![image-20221109113933904](https://img-blog.csdnimg.cn/41a9ec89a8c344ae875df33f5064b1b9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_11,color_FFFFFF,t_70,g_se,x_16)

分析： 

        type="radio"：将<input>转换为单选框。
    
        name="fruit"：将数据绑定到fruit组，同组元素，最多只能选择其中一项。 

5、input标签3——复选框（type="checkbox"）
        <label for="">苹果:</label>
        <input type="checkbox">
        <label for="">香蕉:</label>
        <input type="checkbox">
        <label for="">桃子:</label>
        <input type="checkbox">
效果如下：![image-20221109114033787](https://img-blog.csdnimg.cn/3f48dc948375476d875815283e82d256.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAcHJvMTgyMg==,size_11,color_FFFFFF,t_70,g_se,x_16)



分析：

        type="checkbox"：将<input>转换为复选框 

6、input标签2——提交按钮（type="submit"，type="button"）
        <input type="submit">
        <input type="submit" value="登录">
        <input type="button" value="按钮">
效果如下：

![image-20221109113911486](https://img-blog.csdnimg.cn/e8c5219650e247a4b65864d4ad18fa1d.png)

分析：

        value：设置<input>的显示值，没有设置的话，默认为“提交”。
    
        type：
    
                submit：点击时，可以将表单的数据提交到服务器。
    
                button：一个普通的按钮。

三、代码如下：

1.<!DOCTYPE html>
2.<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demo02</title>
</head>

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demo02</title>
</head>

<body>
    <table border="1">
        <thead>
            <th>序号</th>
            <th>名称</th>
            <th>单价</th>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>苹果</td>
                <td>￥1.00</td>
            </tr>
            <tr>
                <td>2</td>
                <td>香蕉</td>
                <td>￥2.00</td>
            </tr>
            <tr>
                <td>3</td>
                <td>桃子</td>
                <td>￥3.00</td>
            </tr>
        </tbody>
    </table>



<br><br>

<form action="">
    <label for="username">用户名:</label>
    <input id="username" type="text" placeholder="用户名">

    <br><br>
     
    <label for="password">密码:</label>
    <input id="password" type="password" placeholder="密码">
     
    <br><br>
     
    <select name="" id="">
        <option value="">男</option>
        <option value="">女</option>
    </select>
     
    <br><br>
     
    <label for="">苹果:</label>
    <input type="radio" name="fruit">
    <label for="">香蕉:</label>
    <input type="radio" name="fruit">
    <label for="">桃子:</label>
    <input type="radio" name="fruit">
     
    <br><br>
     
    <label for="">苹果:</label>
    <input type="checkbox">
    <label for="">香蕉:</label>
    <input type="checkbox">
    <label for="">桃子:</label>
    <input type="checkbox">
     
    <br><br>
     
    <input type="submit">
    <input type="submit" value="登录">
    <input type="button" value="按钮">
</form>

</body>
</html>