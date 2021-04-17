# js-study-notes

### JS代码规范

- 区分大小写
- 每句代码之后使用分号`;`结尾
- 命名规范


### 引用方式
- 使用`script`标签中的`src=""`引用js文件
- 在`script`标签中写内容
- `javascript: void(0); onclick="alert('message')`

### 注释方式
- `//单行注释`
- `/*多行注释*/`


### 引用标签
```
<!DOCTYPE html>
<html>
<head>
	<title>初识js</title>
</head>
<body>
	<div class="box">4</div>
	<div class="box">2</div>
	<div class="box">3</div>
	<span id="boxes">1</span>
	<ul class="list">
		<li>1</li>
		<li>2</li>
		<li>3</li>
	</ul>
	<input type="text" name="user" id="ip1"/>
	<script>
		
		/*
			获取节点元素：
			alert(document.getElementById("boxes")); 通过id名字获取

			alert(document.getElementsByClassName("box"));通过class名字获取

			alert(document.getElementsByClassName("list")[0]); 索引第一个 

			alert(document.getElementsByTagName("li")); 通过标签名字获取
		*/ 

		alert(document.getElementsByName("user").length );

		var box = document.getElementById("boxes"); // 创建变量box

		box.innerHTML = "This is js!<a href='https://www.baidu.com'>跳转到百度</a>" // 修改内容
		box.innerText = "This is js!<a href='https://www.baidu.com'>跳转到百度</a>" // 显示文本

		var ip1 = document.getElementById("ip1");
		ip1.value = "This is a input!" // 输入框显示内容

	</script>
</body>
</html>
```

### 变量
#### 申明要求
1. 可以使用字母、数字、下划线，但是数字不能作为开头
2. 所有的变量都必须使用`var`声明之后才能使用

#### 六大数据类型

- Number ==> 数字
- String ==> 字符串
- Boolean ==> 布尔值
- function ==> 函数
- undefined ==> 未定义，值就是undefined
- Object ==> 对象

#### 事件
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>事件</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        #box {
            width: 300px;
            height: 300px;
            background-color: skyblue;
        }

    </style>
</head>
<body>
    <div id="box">
    </div>
    <script>
        // 单击事件
        var box = document.getElementById("box");
        box.onclick = function() {
            alert("我被单击啦！");
        }

        // 鼠标划入事件
        // onmouseenter / onmouseover 都是鼠标划入事件
        box.onmouseover = function () {
            console.log("鼠标划入！");
        }

        // 鼠标划出事件
        // onmouseleave / onmouseout 都是鼠标划出事件
        box.onmouseout = function () {
            console.log("鼠标划出！");
        }

        // 鼠标移动 ==> onmousemove
        // 左键双击 ==> ondblclick

        // 键盘事件(按下某个按键) ==> onkeydown
        // 键盘事件(抬起某个按键) ==> onkeyup

        // 失去焦点 ==> onblur
        // 得到焦点 ==> onfocus

        // 窗口大小被改变 ==> onresize
        window.onresize = function () {
            console.log("窗口大小给改变啦！！！");
        }

    </script>
</body>
</html>
```

#### 样式控制
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>样式控制</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        #box1 {
            width: 200px;
            height: 200px;
            background-color: pink;
        }

        #box {
            width: 100px;
            height: 100px;
            background-color: skyblue;
        }

    </style>
</head>
<body>
    <div id="box1"></div>
    <input id="btn" type="botton" value="点击改变盒子样式" />
    <script>

        var box1 = document.getElementById("box1");
        var btn = document.getElementById("btn");

        // 点击后调整样式
        btn.onclick = function() {
            // box1.id = "box";
            if (box1.id == "box1") {
                box1.id = "box";
            }
            else {
                box1.id = "box1";
            }
        }

        // 点击后调整内联样式
        btn.onclick = function () {
            box1.style.width = "400px";
            box1.style.height = "200px";
            box1.style.background = "skyblue";
            box1.style.marginLeft = "20px"; //方式一

            box1.style["margin-left"] = "30px"; //方式二

            box1.style.cssText = "margin-top: 30px; margin-left: 50px;" // 方式三
            box1.style.cssFloat = "right"; // Chrome、Firebox、Opera、IE9+
            box1.style.styleFloat = "right"; // IE5+
        }

    </script>
</body>
</html>
```

#### 数字数据类型

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>数字数据类型</title>
</head>
<body>
    <script>
        NaN：数据类型也是数字
        alert(Number(123))
        alert(Math.pow(16,2))  // 16的平方
        alert(Math.round(16.123)) // 四舍五入
        alert(Math.ceil(16.123)) // 向上取整
        alert(Math.floor(16.123)) // 向下取整
        alert(Math.max(16,11,10,7,8,9,22)) // 取最大值
        alert(Math.min(16,11,10,7,8,9,22)) // 取最小值
        alert(Math.random()) // 生成随机数（0-1），不需要添加参数
        alert(Math.random()*100) // 生成随机数（0-100）

        alert(parseInt("123asf")) //将参数解析成数字（当遇到第一个非数字的值时停止）
        alert(parseFloat("123.123asf")) //将参数解析成浮点数（当小数点后面的内容遇到第一个非数字的值时停止）

        var n = 4.56336363634
        alert(n.toFixed(2)) //保留小数点后2位
        alert(Math.random()*20 + 60)  // 生成60-80的随机数
        alert("hello! world!".length)  // 字符串长度
        // 数字没有长度属性


    </script>
</body>
</html>
```

