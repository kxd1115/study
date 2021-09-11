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

#### 字符串

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>字符串</title>
</head>
<body>
<script>

    // 类数组
    var str = "this is string"

    // 获取字符串中第一个字符
    str[0]
    str.charAt(0)

    // 查询第1-3个字符，如果起始字符＜终止字符，不影响查询
    // 不支持负数索引，负数索引表示为0
    alert(str.substring(0,3))

    // 切片
    // 支持负数索引，但必须按顺序索引
    alert(str.slice(0, 5))

    // 查找字符索引
    alert(str.indexOf('is', 3))

    // 分隔文本，并会返回一个数组
    alert(str.split('is'))

    str.toUpperCase() // 变为大写
    str.toLowerCase() // 变为小写

</script>
</body>
</html>
```

#### 布尔值

1. 布尔值：True / False
2. undefined / null / 0 / -0 / NaN / ""  这5种都会返回False

#### null和undefined

1. null是一个关键字
2. undefined是一个预先设置好的全局变量

* null == undefined
* 1+ null = 1
* 1 + undefined = NaN

#### 数组和onload事件

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>数组和onload事件</title>
    <script>
        window.onload = function () {
            var box = document.getElementById("box")
            alert(box)
        }
    </script>
</head>
<body>
    <div id="box"></div>
    <script>

        // 数组
        var arr = [1,2,3,4,5123,5123,12,666,10]

        // onload事件
        // 会等所有标签，图片，js，CSS，文字等内容全部加载完毕，再显示花括号中的代码
        // window.onload = function() {
        //
        // }


    </script>
</body>
</html>
```

#### 运算符

##### 1. 运算符

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>运算符</title>
</head>
<body>

<script>
    /* 求余数 */
    alert(6%4);

    /* 赋值操作符 */
    var a = 6;
    // 给a变量赋值为6

    // - * / % 会强制将参数转换为数字进行计算（+不会）

    a++; // a = a + 1
    a--; // a = a - 1

    var b = a++; // 先将a的值赋值给b，再自增
    var c = ++a; // 先自增，再赋值给c

</script>

</body>
</html>
```



##### 2. 逻辑运算符

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>逻辑运算符（与或非）</title>
</head>
<body>
<script>
        // 判断条件
        /* == > < >= <= != === */

        //逻辑运算符
        /*
        * && 和/与：遇到假条件就自动停止，并返回false；
        * || 或：只要满足其中一个条件,就会返回；
        * !  取反：取相反的结果；
        *  */
        var a = 6>3 && 7<9;
        alert(a);

        var b = !false;
        alert(b);

</script>
</body>
</html>
```

#### 循环

##### 1. do、while循环

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>do,while循环</title>
</head>
<body>
<script>

    var i = 0;

    // 版本1
    while(i<5) {
        console.log(i); //控制台日志输出当前i的结果
        i++; //当i<5时，循环自增
    }

    // 版本2
    do {
        console.log(i);
        i++;
    } while(i<5)

</script>
</body>
</html>
```

##### 2. for循环

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>for循环</title>
</head>
<body>
    <ul class="list">
        <li>123</li>
        <li>234</li>
        <li>345</li>
        <li>456</li>
        <li>567</li>
    </ul>
<script>

    //示例：
    // for(var i = 0; i<10; i++) {
    //     console.log(i);
    // }
    // alert("finish!")
    // 当i小于10的时候，就会执行大括号中的内容，然后执行i++
    // i++表示变量i自动+1
	
    // for循环的常规用法
    var uls = document.getElementsByClassName("list")[0];
    var lis = uls.getElementsByTagName("li");

    // 弹出相应标签中的值
    for (var i=0; i<lis.length; i++) {
        lis[i].onclick = function() {
            alert(this.innerHTML);
        };
    };

    // 弹出相应标签对应的索引值
    for (var i=0; i<lis.length; i++) {
        lis[i].index = i;
        lis[i].onclick = function() {
            alert(this.index);
        };
    };



</script>
</body>
</html>
```

#### if语句

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>流程控制语句</title>
</head>
<body>
<script>

    // 示例
    if (6<3) {
        alert(1);
    } else if (3<1) {
        alert(2);
    } else if (0>1) {
        alert(3);
    } else {
        alert("No!!!!");
    }

    // 一个条件的简写版本
    if(6>3) alert(1);

    // 三目运算符（当只有一个真条件和一个假条件时的简写版本）
    3<2 ? alert("3小于2") : alert("3不小于2");
    /* 判断问号前的内容，为真时执行冒号左侧的内容，为假时执行冒号右侧的内容 */

    //if语句在for循环中的使用
    for(var i=0; i<5; i++) {
        if(i==2) {
            continue; //跳过本次循环
            // break：终止循环
        }
        console.log(i);
    };


</script>
</body>
</html>
```

#### 函数

##### 1. 函数定义，匿名函数及执行

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>function函数定义，匿名函数及执行</title>
</head>
<body>
<script>

    // 匿名函数 —— 函数表达式
    function fn1() {
        alert(1);
    };

    // 及时函数 —— 定义完就执行
    (function() {alert(1)}());
    (function() {alert(1)})();

    -function() {alert(2)}();
    ~function() {alert(3)}();
    +function() {alert(4)}();
    !function() {alert(5)}();

    // 函数执行

</script>
</body>
</html>
```

##### 2. 给函数传递参数

	1. 给函数传递形参
 	2. 不定参数arguments

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>函数传参</title>
</head>
<body>
<script>

    // 给函数传递参数，其中a和b是函数add的形参
    function add(a, b) {
        c = a + b;
        return c;
    };

    // 10和20是函数的实参
    alert(add(10,20));

    // 不定参数（可变参数）：arguments
    function sum() {
        var result = 0;
        for (i=0; i<arguments.length; i++) {
            result += arguments[i];
        };
        return result;
    };

    alert(sum(1,2,3,4,5,6))

</script>
</body>
</html>
```

###### 说明：

- 匿名函数不能单独出现，需要名字，或者设定为及时函数直接执行
- 如果函数没有设置返回值，则默认返回`undefind`
- 用括号`()`包裹起来的函数就是及时函数(立即执行函数)，this指向windows对象
- 事件驱动函数执行，this指向触发事件的对象

```html
function fn1() {
        alert(1);
    }

    alert(fn1); // 会直接展示函数本身
    
    var fn1 = 0; // 函数会被该变量覆盖
```

##### 3. 局部变量和全局变量

- 定义在函数内部的变量只能被函数本身调用，被称为`局部变量`
- 定义在函数外的变量，可以被多个函数调用，被称为`全局变量`

```html
var a = 0;
    function fn() {
        alert(a);
        var b = 3;
        alert(b);
    };
    fn();
    alert(b)
```

##### 4. 闭包

- 函数内的变量是静态方式存储，创建之后不会被销毁（即“闭包”）
- 让程序可以在函数外访问函数内的变量

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>闭包</title>
</head>
<body>
<script>

    function fn1() {
        var a = 0;
        function fn2() {
            a++;
            alert(a);
        }
        return fn2; // 将下级函数fn2作为上级函数fn1的返回值返回
    }

    var f = fn1();

    f();

</script>
</body>
</html>
```

