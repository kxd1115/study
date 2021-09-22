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

#### 节点属性操作

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>节点属性操作</title>
</head>
<body>
    <img class="img" id="img" src="https://img2.baidu.com/it/u=172397982,3095585162&fm=26&fmt=auto&gp=0.jpg" alt="">
    <a class="baidu" href="http://www.baidu.com">跳转到百度</a>
    <input class="in" type="text">

    <script>

        var imgs = document.getElementById("img");
        var bai = document.getElementsByClassName("baidu")[0];
        var ins = document.getElementsByClassName("in")[0];

        //修改名称
        imgs.className = "box";
        imgs.id = "box2";

        //更改尺寸
        imgs.width = "200";

        //更改链接
        bai.href = "http://pick.baidu.com/";

        //实时记录输入信息（监控用户输入内容）
        ins.onkeyup = function () {
            console.log(this.value);
        };

        // 标签属性的修改
        alert(ins.getAttribute("class"));    // 获取变量ins对应的标签中class属性的值
        ins.setAttribute("class", "wang");   // 将变量ins对应的input标签中class属性的值修改为wang
        ins.removeAttribute("class");        // 将class属性从ins对应的input标签中移除

    </script>
</body>
</html>
```

- 修改标签属性的三种方法除了对系统中存在的合法标签属性可以生效(例如`class`, `id`等)，也可以对用户自行设置的标签属性生效(例如`abc`, `xyz`等)

##### 最终呈现样式的获取方式

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>最终呈现出来的样式的获取方式</title>
    <style>

        * {
            width: 0;
            height: 0;
        }

        #box {
            width: 200px;
            height: 150px;
            background: skyblue;
        }


    </style>
</head>
<body>
<div style="width: 300px; height: 180px; background: #F0F8FF" id="box"></div>
<script>

    var box = document.getElementById("box");

    // alert(getComputedStyle(box).width);             // 显示宽度
    // alert(getComputedStyle(box).height);            // 显示高度
    // alert(getComputedStyle(box).backgroundColor);   // 显示背景颜色

    function getstlye(element, attr) {
        return element.currentStyle ? element.currentStyle[attr] : getComputedStyle(element)[attr];
    };

    alert(getstlye(box, "backgroundColor"));

</script>
</body>
</html>
```

#### 数组操作1

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>详解数组1</title>
</head>
<body>
<script>

    var a1 = [1,2,3,4,5,6,"2", function() {}]; // 数组可以包含任意数据类型
    var a2 = [,];
    var a3 = new Array(105); // 当只有一个整数元素时，会创建一个长度为105的数组；

    // ES6
    var a4 = Array.of(12);   // ES6语法下，创建一个长度为1，元素为12的数组；

    // 判断是否是数组
    Arrary.isArray(a1);  // 判断是否是数组
    a2 instanceof Array; // 判断阿是否是数组的实例

    a3.length; // 查询数组长度

    ar4[0];    // 索引

</script>
</body>
</html>
```

#### 数组操作2

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>详解数组2</title>
</head>
<body>
<script>

    var a1 = [1,2,3];

    a1.length = 0; // length可以被赋值，原数组的长度会被改变；

    a1.kang = "xiao"; // 数组对象可以被赋予新的属性
    alert(a1.kang);

    // 操作数组
    a1.push(1,2,3,"abc"); //从数组的末尾添加元素，参数可以是任意数据类型
    alert(a1);

    a1.unshift(111,333); // 从数组的开头添加元素，参数可以是任意数据类型
    alert(a1);

    a1.pop();   // 删除数组最后一个元素，并将其作为值返回  a1.pop() = "abc"
    alert(a1);

    a1.shift(); // 删除数组第一个元素，并将其作为值返回 a1.shift() = 111
    alert(a1);

    a1.splice(2, 0, "new");  // 替换或插入元素
    //参数1：替换或插入的起始索引位置
    //参数2：要替换或插入的元素数量
    //参数3：要替换或插入的元素
    alert(a1)

    // a1.toString(); //将数组转化为字符串，默认用逗号拼接
    alert(a1.join("")); //将数组用新的方式拼接起来(用join的参数替代原来的逗号)，并且会产生一个新的字符串
    alert(typeof a1.join(""));
    alert(typeof a1);

</script>
</body>
</html>
```

#### 定时器

##### 1. 延时定时器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>定时器</title>
</head>
<body>
<script>

    // 延时定时器
    //方式1
    setTimeout(fn1, 1000);  //1秒钟后执行函数fn1

    function fn1() {
        alert(1);
    }

    //方式2
    setTimeout(function fn2() {alert(2);}, 2000);

    //方式3
    setTimeout('fn1()', 3000)

    //清除延时定时器
    var time2 = setTimeout('alert(11231)', 5000);

    clearTimeout(time2);

</script>
</body>
</html>
```

##### 2. 循环定时器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>循环定时器</title>
</head>
<body>
<span class="timer"></span>
<script>

    //循环定时器
    var in1 = setInterval(fn1, 2000); //每2秒执行一次fn1参数

    function fn1() {
        alert(2);
    }

    //清除循环定时器
    clearInterval(in1);


    //自定义方式
    // var in2 = setInterval(function() {
    //     var i = 0;
    //
    //     if(i>=3) {
    //         clearInterval(in2);
    //     } else {
    //         alert(666);
    //     }
    //
    //     i++;
    // }, 5000)

    //自动刷新时间
    var span = document.getElementsByClassName("timer")[0];

    setInterval(
        function() {

            var date = new Date();
            var timer = date.getHours() + "时" + date.getMinutes() + "分" + date.getSeconds() + "秒"

            span.innerHTML = timer;

        }, 1000
    );

</script>
</body>
</html>
```

#### 时间日期

##### 1. 获取时间日期

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>时间日期</title>
</head>
<body>
<span class="timer"></span>
<script>

    var date = new Date(); //获取目前最新的时间

    // 快速生成时间戳
    alert(date*1)
    // date.getTime()

    date.getFullYear(); //获取年
    date.getMonth();    //获取月,注意：获取的值类似索引，是从0开始的（1月份会返回0）
    date.getDate();     //获取日
    date.getHours();    //获取时
    date.getMinutes();  //获取分
    date.getSeconds();  //获取秒
    date.getDay();      //获取星期

    var span = document.getElementsByClassName("timer")[0];
    setInterval(
        function() {
            var date = new Date();
            var timer = date.getFullYear() + "年" + (date.getMonth()+1) + "月" + date.getDate() + "日" + date.getHours()+"时"+date.getMinutes()+"分"+date.getSeconds()+"秒";
            span.innerHTML = timer;
        }, 1000
    )


</script>
</body>
</html>
```

##### 2. 倒计时

- 示例1

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>倒计时</title>
</head>
<body>
<span class="timer"></span>
<script>

    var span = document.getElementsByClassName("timer")[0]
    setInterval(
        function() {
            var date = new Date(2021, 8, 17, 21, 10, 0);  // 获取倒计时目标时间（特别注意月份）
            var targetTime = (date - new Date())/1000     // 获取时间gap
            var ss = parseInt(targetTime%60)              // 获取秒
            var mm = parseInt((targetTime/60)%60)         // 获取分
            var hh = parseInt(targetTime/3600)       // 获取时

            var timer = "倒计时："+hh+"小时"+mm+"分钟"+ss+"秒"

            span.innerHTML = timer
        },1000
    )

</script>
</body>
</html>
```

- 示例2

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>倒计时2</title>
</head>
<body>
<script>

    console.log(
        countDown({
        target: "2021-9-18 22:30:00",
    }));

    function countDown(json) {
        var arr = json.target.split(" ");
        var dateT = arr[0].split("-");
        var dateH = arr[1].split(":");

        // 年月日
        var yearT = dateT[0];
        var montT = dateT[1]-1;
        var dayT = dateT[2];

        // 时分秒
        var hourT = dateH[0] || 0;
        var minuT = dateH[1] || 0;
        var secoT = dateH[2] || 0;

        var targetTime = (new Date(yearT, montT, dayT, hourT, minuT, secoT) - new Date())/1000     // 获取时间gap
        var ss = parseInt(targetTime%60)              // 获取秒
        var mm = parseInt((targetTime/60)%60)         // 获取分
        var hh = parseInt(targetTime/3600)       // 获取时

        return "倒计时："+hh+"小时"+mm+"分钟"+ss+"秒"

    }

</script>
</body>
</html>
```

- 示例3

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>倒计时3_小作业</title>
</head>
<body>
<h2>请选择倒计时目标时间</h2>
<h3>
    日期: <input id="indate" type="date" value="2021-09-20"
               max="2021-12-31" min="2021-01-01"
               onchange="upperCase1(this.id)"/>
    时间: <input id="intime" type="time" value="23:30:30" onchange="upperCase2(this.id)"/>
</h3>
<h1 id="timer"></h1>

<script>

    // 获取日期
    function upperCase1() {
        // 获取日期，时间
        var onInput1 = document.getElementById("indate").value;
        var dateT = document.getElementById("indate").value = onInput1.toUpperCase();

        var onInput2 = document.getElementById("intime").value;
        var timeT = document.getElementById("intime").value = onInput2.toUpperCase();

        // 倒计时
        var dateTime = dateT + " " + timeT
        var h2Dom = document.getElementById("timer");

        setInterval(function() {
            countDown({
                target: dateTime,
                success: function(dd,hh,mm,ss) {
                    h2Dom.innerHTML = "距离目标时间还剩"+dd+"天"+hh+"小时"+mm+"分钟"+ss+"秒";
                }
            })
        }, 1000);

        function countDown(json) {
            var arr = json.target.split(" ");
            var dateT = arr[0].split("-");
            var dateH = arr[1].split(":");

            // 年月日
            var yearT = dateT[0];
            var montT = dateT[1]-1;
            var dayT = dateT[2];

            // 时分秒
            var hourT = dateH[0] || 0;
            var minuT = dateH[1] || 0;
            var secoT = dateH[2] || 0;

            var targetTime = (new Date(yearT, montT, dayT, hourT, minuT, secoT) - new Date())/1000     // 获取时间gap
            var ss = parseInt(targetTime%60)            // 获取秒
            var mm = parseInt((targetTime/60)%60)       // 获取分
            var hh = parseInt((targetTime/3600)%24)     // 获取时
            var dd = parseInt((targetTime/3600)/24)     // 获取时

            if(json.success && (typeof json.success).toLowerCase() === "function") {
                json.success(dd,hh,mm,ss);
            };

            return "倒计时："+dd+"天"+hh+"小时"+mm+"分钟"+ss+"秒"

        }

    };



</script>

</body>
</html>
```

> 1. 本来是准备做一个获取input时间后，实时显示倒计时的；但目前所学无法完成，后期学习更多内容后再完善
>
> 2. 进行了检查微调之后，发现可以运行了！

#### JSON

> JSON是一种数据交互格式，以字符串的形式呈现（是一种规范，基本上所有的语言都偶有字符串，可以交互）
>
> 和js对象的不同：js对象是js中的一种特殊数据类型，是JSON数据在js中的一种呈现形式

- 两种创建js对象的方法

```js
// 方式1
var obj = {
    "name": "Mr.Z",
    "age": 18,
}

// 方式2
var obj = new Object();
obj.name = "kang";
obj.age = 18;
```

- 将json字符串转换成js对象`JSON.parse()`

```js
var s = '{"name": "kang", "age": 18}';
var obj = JSON.parse(s);  // 将json字符串转换成js对象
```

- 将js对象转换成json字符串`JSON.stringify()`

```js
var json = JSON.stringify(obj);
```

#### 获取宽高度

##### 1. 获取元素宽高度

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>获取宽高度</title>
    <style>
        * {
            width: 0;
            height: 0;
        }

        #box {
            width: 150px;
            height: 50px;
            background: skyblue;     /*盒子颜色*/
            border: 20px solid red;  /*外边框，宽度和颜色*/
            padding: 80px 0;    /*内边距*/
            overflow: hidden;  /*隐藏超出部分*/
        }

        body {
            width: 1000px;
            height: 2000px;
        }

    </style>
</head>
<body>
    <div id="box">
        1<br/>
        1<br/>
        1<br/>
        1<br/>
        1<br/>
        1<br/>
        1<br/>
        1<br/>
        1<br/>
    </div>
    <div id="box1">
        <div id="box2">
            <div id="box3">

            </div>
        </div>
    </div>
<script>

    var box = document.getElementById("box");
    alert(box.clientHeight); //获取高度 padding + height
    alert(box.offsetHeight); //获取高度 padding + height + border
    alert(box.scrollHeight); //获取高度 元素总高度

    alert(document.body.scrollHeight); //获取网页的总高度
    alert(document.body.scrollTop); //获取该网页从上往下滚动的高度

    // 滚动事件：实时获取并在log中显示滚动的高度
    window.onscroll = function() {
        console.log(document.documentElement.scrollTop);
    }

    // 自定义：从某处自动滚动到高度0（原生Js写法，可以进一步封装）
    document.documentElement.scrollTop = 1500;
    var timer = setInterval(
        function () {
            if (document.documentElement.scrollTop <= 0) {
                document.documentElement.scrollTop = 0;
                clearInterval(timer);
                /*如果挡墙高度≤0，则停止循环定时器*/
            } else {
                var doc = document.documentElement.scrollTop;
                document.documentElement.scrollTop = (doc - 10);
                /*否则以每毫秒10px的速度向上移动滚动条*/
            }
        }, 1000/10
    )

</script>
</body>
</html>
```



##### 2. 获取元素到定位父级的宽高度

- 以`offsetLeft`举例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>获取宽高度2</title>
    <style>
        * {
            width: 0;
            height: 0;
        }

        #box1 {
            width: 200px;
            height: 200px;
            background: red;
            margin-left: 100px; /*距离左侧边缘100px*/
            margin-top: 100px;  /*距离顶部边缘100px*/
        }

        #box2 {
            width: 120px;
            height: 120px;
            background: orange;
            position: relative;
            margin-left: 20px;
        }

        #box3 {
            width: 40px;
            height: 40px;
            background: skyblue;
            position: relative; /*absolute 绝对定位*/
            left: 20px;
            top: 30px;
        }

    </style>
</head>
<body>
<div id="box1">
    <div id="box2">
        <div id="box3">

        </div>
    </div>
</div>
<script>
    // 获取当前元素到定位父级的距离（左侧或者顶部距离）
    var box3 = document.getElementById("box3");
    alert(box3.offsetLeft); // box3距离box2左侧边缘的距离（因为box2使用了相对定位，即使box3不适用定位，也可以定位到距离）
</script>
</body>
</html>
```

- 只要父级元素有进行定位，那么子级元素就能够使用`offsetLeft`等方法获取到距离该父级元素边框的距离（左侧或者顶部边框）

#### 用Js操作节点

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>节点操作</title>
</head>
<body>
    <div id="box2"></div>
    <div id="box">
        <p></p>
        <a href="javascript: void(0);"></a>
        <span>
            <b></b>
        </span>
    </div>
    <div id="box1"></div>
    <script>

        // 获取子元素 Element.children
        var box = document.getElementById("box");

        alert(box.children);
        box.children[0].innerHTML = "通过Js将内容添加到p标签";

        box.children[1].innerHTML = "跳转到百度"
        box.children[1].href = "https://baidu.com"

        box.children[2].children[0].innerHTML = "hello world!"

        // 获取下一个同级元素 nextElementSibling
        alert(box.nextElementSibling.id);

        // 封装成所有浏览器都支持
        function getNextElementSibling(element) {
            if (element.nextElementSibling === null) { return null; }
            return element.nextElementSibling ? element.nextElementSibling : element.nextSibling;
        }

        // 获取上一个同级元素
        alert(box.previousElementSibling.id);

        // 获取父级元素
        alert(box.parentNode);

        // 删除元素（必须通过父级元素去操作删除）
        var parent = box.parentNode;
        parent.removeChild(box); //删除掉Id名为box的子级元素

        // 创建元素 createElement
        var aDom = document.createElement("a"); //创建一个a标签
        aDom.href = "https://jd.com";
        aDom.innerHTML = "跳转到京东"

        parent.appendChild(aDom);  //添加新创建的a标签（只能添加到末尾）

        // 插入元素 将创建的a标签插入到script标签前面（可以将选中的标签添加到选中标签的上方）
        parent.insertBefore(aDom, document.getElementsByTagName("script")[0]);
    </script>
</body>
</html>
```

