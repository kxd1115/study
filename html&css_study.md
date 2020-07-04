# HTML介绍 

1. **简介**
- `HTML`是一种超文本语言，是用于创建网页的语言，是一种标记语言。
- 具有标记标签的集合。标签是一种用尖括号括起来的词，所有的标签都成对出现。例如：==开始标签==`<body>`和==结束标签==`</body>`。又可以称之为：`起始标签`和`闭合标签`。

2. **`HTML`元素**
- 标签之间既是元素（web）
    
- `I like <code> web </code> and css`
    
- 如果不需要再标签之间放置内容，则可以创建一个==空元素==
    
- `I like <code> </code> HTML and css`
    
- 自闭和标签
    
- `I like <code/> HTML and css`，用来更加简洁的表达空元素，且同上具有相同意义。
    
- 空元素
    - 有些标签必须使用单个标签表示，这些被称之为空元素（void元素）。
    - 例如`hr`，它是一个分组元素，用来表示一个段落级别的内容.
    ```html
    <!-- 创建方式一 -->
    I like HTML
    <hr>
    I like css
    <!-- 浏览器能够识别出hr是一个void元素 -->
    
    <!-- 创建方式二 -->
    I like HTML
    <hr/>
    I like css
    <!-- 如同空元素一样去使用 -->
    
    ```

3. **`HTML`注释**
    
- 注释标签以`<!--`开始，`-->`结束，浏览器将会忽略在注释标签中的内容。
    
4. **`HTML`属性**
    - 以下代码显示了a元素的属性
    ```
    I like <a href="/index.html"> CSS </a> and HTML
    ```
    `a`元素允许创建一个超链接，当它被点击时，加载不同的`HTML`文档。
    - `href`是`a`元素的局部属性，用来配置超链接的`URL`。
    
    **全局属性**
    ```
    I like <a class="myClass" href="/index.html" id="myID"> CSS </a> and HTML
    ```
    `class`和`id`是全局属性，可以和局部属性同时混用。
    
    **布尔属性**
    ```
    Enter what you like: <input disabled>
    ```
    `disabled`就是一个布尔属性，用来阻止用户输入数据。
    
    可以通过分配空字符串（""）来定义相的布尔属性或将该值设置为属性的名称。
    ```
    <input disabled="">
    <input disabled="disabled">
    ```

5. `HTML`结构
    - 元素和属性用于标记`HTML`文档中的内容。    
    - `HTML`文档是具有`.html`扩展名的文件。
    - 对于大多数`HTML`文件，都可以直接拖放到浏览器中运行。
    
    **结构体**
    - 两个元素提供了`HTML`文档的外部结构。
    - `DOCTYPE element`
    - `html element`
    - 以下代码显示了`HTML`文档的基本结构
    ```html
    <! DOCTYPE HTML>
    <html>
    <!-- elements go here -->
    </html>
    ```
    `DOCTYPE`元素告诉浏览器，它正在处理一个`HTML`文档，这通过`HTML`布尔属性表示：
    ```
    <! DOCTYPE HTML>
    ```
    - `html`的开始标记位于`DOCTYPE`元素之后。
    - `HTML`文档是包含`html`标签的文本文件，`HTML`文档中的`HTML`标记用来标记网页。
    ```html
    <! DOCTYPE HTML>
    <html>
    	<body>
    		<h1>Hy Heading</h1>
    		<p>My paragraph</p>
    	</body>
    </html>>
    ```
    `<html>`和`</html>`之间的类容用来标记网页，`<body>`和`</body>`用来标记网页可见的内容。`<h1>`和`</h1>`用来定义标题，`<p>`和`</p>`创建段落。
    
    **`HTML`元数据**
    - `HTML`文档中的元数据提供了有关文档信息。
    - 元数据包含在`head`元素中。
    ```html
    <! DOCTYPE HTML>
    <html>
    	<head>
    		<!-- define your metadata here -->
    		<title>web document title</title>
    	</head>
    </html>
    ```
    代码中的`title`元素就是元数据。
    
    ```html
    <! DOCTYPE HTML>
    <html>
    	<head>
    		<!-- define your metadata here -->
    		<title>web document title</title>
    	</head>
    	<body>
    		This is the <code>content</code>
    	</body>
    </html>
    ```
    通过`body`元素来添加`html`文档内容。
    
    **父元素与子元素**
    - 包含另一个元素的元素是第二个元素的父级。
    ```html
    <! DOCTYPE HTML>
    <html>
    	<head>
    		<!-- define your metadata here -->
    		<title>web document title</title>
    	</head>
    	<body>
    		<h1>Hy Heading</h1>
    		<p>My paragraph</p>
    		This is the <code>content</code>
    	</body>
    </html>
    ```

6. **`HTML`实体**
    - 有些字符在`HTML`中具有特殊意义，例如`<`和`>`。
    - 如果需要使用这些特殊字符而不被解释为`HTML`，可以使用实体。
    - 实体是浏览器转换特殊字符的代码。
    
    **例子**
    - 常用实体
    
    | 显示结果 | 描述            | 实体名称  | 实体编号  |
    | -------- | --------------- | --------- | --------- |
    | ` `      | 空格            | `&nbsp;`  | `&#160;`  |
    | <        | 小于号          | `&lt;`    | `&#60;`   |
    | >        | 大于号          | `&gt;`    | `&#62;`   |
    | &        | 和号            | `&amp;`   | `&#38;`   |
    | ￠       | 分(cent)        | `&cent;`  | `&#162;`  |
    | £        | 镑(pound)       | `&pound;` | `&#163;`  |
    | ¥        | 元yen()         | `&yen;`   | `&#165;`  |
    | €        | 欧元(euro)      | `&euro;`  | `&#8364;` |
    | ©        | 版权(copyright) | `&copy;`  | `&#169;`  |
    | ®        | 注册商标        | `&reg;`   | `&#174;`  |

7. **`HTML`文档**
    - 需要使用`doctype`来开始每一个`HTML`文档，来告诉浏览器它将处理`HTML`，如下所示：
    ```
    <!DOCTYPE HTML>
    <!-- 该元素没有结束标记，只需要在每次开始时放置即可。 -->
    ```
    
    **`html`元素**
    - `html`元素或根元素表示`HTML`文档的开始。
    - `html`元素有一个`head`子元素和一个`body`子元素。
    
    **`head`元素**
    - `head`元素包含文档的元数据。
    - 在`HTML`文档中，元数据存有关于文档中的内容和标记信息。它还包括脚本和对外部资源的引用，例如`CSS`样式表。
    ```html
    <!DOCTYPE HTML>
    <html>
        <head>
           <title>Hello</title>
        </head>
    </html>
    ```
    `head`元素中除`title`元素无法被选择，其他的元素都是可以被选择的。
    
    **元数据元素**
    - 元数据元素本身不是内容，但是它们提供有关后续内容的信息。
    
    **`body`元素**
    - `body`元素封装了`HTML`文档的内容，而`head`元素封装了元数据和文档信息。
    - `body`元素总是位于`head`元素之后。
    ```html
    <!DOCTYPE HTML>
    <html>
        <head>
           <title>Example</title>
        </head>
    <body>
        <p>This is a test</p>
        <a href="http://www.w3cschool.cn">Visit  www.w3cschool.cn</a>
    </body>
    </html>
    ```
    
8. **`HTML`元数据**
    - `title`元素，用来设置文档的标题。
    - 浏览器通常会在浏览器窗口或者选项卡的顶部显示此元素的内容。
    - 每个文档应该只有一个标题元素，且必须是有意义的。
    
    **`HTML base`**
    - `base`元素为相对链接设置基本`URL`。
    - 相对链接是省略`URL`协议，主机和端口部分的链接，并且针对一些其他`URL`(基本元素或者由基本元素指定的`URL`)进行评估用于加载当前文档的`URL`。
    - `base`元素也用于指定如何在用户点击链接时打开链接，以及在表单提交后浏览器的行为。
    - `base`元素有两个属性。
        - `href`
        - `target`
    - `HTML`最多只能包含一个基本元素。

    **`href`属性**
    - `href`属性指定基本`URL`和解析文档中的相对`URL`。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<title>Example</title>
    	<base href="//www.w3cschool.cn/listings/"/>
    </head>
    <body>
    	<p>This is a test</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    	<a href="page2.html">Page 2</a>
    </body>
    </html>
    ```
    - 以上代码将基本`url`设置为`//www.w3cschool.cn/listings/`。
    - `www.w3cschool.cn`是服务器的名称，`listings`是服务器上的目录。
    - 稍后在文档中，它将使用相对`URL`创建一个超链接`page2.html`。
    - 当用户点击超链接时，浏览器将组合基本`URL`和相对`URL`来创建组合网址`//www.w3cschool.cn/listing/page2.html`。
    
    **`target`属性**
    - 指示浏览器如何打开网址。
    
    **`HTML`元数据**
    - `meta`元素定义文档的元数据，一个`HTML`文档可以包含多个`meta`元素。
        1. 使用`meta`定义名称/值元数据对
        ```html
        <!DOCTYPE html>
        <html>
        <head>
        	<meta name="author" content="www.w3cschool.cn"/>
        	<meta name="description" content="A simple example">
        </head>
        <body>
        	<a href="http://www.w3school.cn">Visit www.w3cschool.cn</a>
        </body>
        </html>
        ```
        - 使用`name`和`content`属性。
        - `name`属性用来指定元素引用的元数据类型，`content`属性用来提供一个值。
        - `meta`元素可以定义的元数据类型如下：
        
        | 元数据名称       | 描述                                 |
        | ---------------- | ------------------------------------ |
        | application name | 当前页面所属web应用程序的名称        |
        | author           | 当前页的作者的名称                   |
        | description      | 当前页的描述                         |
        | generator        | 生成`HTML`软件的名称                 |
        | keywords         | 一组用逗号分隔的字符串，用于描述内容 |
        
        - `robots`元数据类型被广泛应用。它允许`HTML`文档的作者指定文档应被如何使用。
        ```
        <meta name="robots" content="noindex">
        ```
        - 大多数搜索引擎识别的三个值是：
            - `noindex` 不要索引此页面
            - `noarchive` 不要创建此页面的存档或缓存版本
            - `nofollow` 不要追踪（即抓取）此页面的链接
    
    **`HTML`字符集**
    - 正确的显示页面需要设定字符集（字符编码）
    - `meta`元素的另一个用途就是用来声明字符编码
    - 通常都设置为`UTF-8`格式
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta name="author" content="www.w3cschool.cn"/>
    	<meta name="description" content="A simple example">
    	<meta charset="utf-8">
    </head>
    <body>
    	<a href="http://www.w3school.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    
    **`HTML http-equiv`**
    - 元素的最终用途是覆盖`HTTP`（超文本传输协议）头之一的值
    - `HTTP`通常用于在服务器和浏览器之间传输`HTML`数据
    - 来自服务器的每一个`HTTP`响应都包含一系列描述的内容，可以使用`meta`来模拟或替换其中的三个头。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta http-equiv="refresh" content="5"/>
    </head>
    <body>
    	<p>This is a test</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    以上代码中，`refresh`头被设置为5，它要求浏览器每5秒重新加载一次页面。
    
    **`Jump`**
    - 如果使用分号和`URL`跟随刷新间隔，浏览器将在间隔过去之后加载指定的`URL`
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta http-equiv="refresh" content="3; http://www.w3cschool.cn"/>
    </head>
    <body>
    	<p>This is a test</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    - 以下列出了`http-equiv`属性允许的三个值：
        - `refresh`
            - 设置一个周期（以秒为单位），之后将从服务器重新加载页面，也可以指定需要重新加载的`URL`，如上代码示例。
        - `default-style`
            - 设置应该用于此页面的首选样式表，`content`属性的值必须与同一文档中的脚本或链接元素上的`title`匹配。
        - `content-type`
            - 这是一种指定`HTML`页面字符编码的替代方法。
            - `<meta http-equiv="content-type" content="text/html charset=UTF-8"/>`
    
9. **`HTML`样式**
    - `style`元素允许在`HTML`文档中内联定义`CSS`文件样式。
    - `style`元素的局部属性：`type`、`media`、`scoped`。
    ```html
    <!DOCTYPE html>
    <html>
    <head> 
    <style type="text/css">
    a {
    	background-color: grey;
    	color: white;
    	padding: 0.5em;
    }
    </style>
    	<title>Test</title>
    </head>
    <body>
    	<p>This is a test</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    用a元素创建了一个新样式。
        
    - `type`
    -  因为浏览器唯一支持的样式机制是`CSS`，因此，该属性将始终是`text/css`
    
    - `media`
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <style  media="screen" type="text/css">
    a  {
        background-color: grey;
        color: white;
        padding:  0.5em
    }
    </style>
    <style  media="print">
    a   {
        color:Red;
        font-weight:bold;
        font-style:italic
    }
    </style>
    </head>
    <body>
        <p>This is a test.</p>
        <a href="http://www.w3cschool.cn">Visit  www.w3cschool.cn</a>
    </body>
    </html>
    ```
    
    **`HTML`资源链接**
    - `link`元素在`HTML`文档之间创建关系，用来链接外部资源，`CSS`样式和`JavaSprict`文件。
    - `link`元素局部属性：`href`、`rel`、`hreflang`、`media`、`type`、`sizes`。
        - `href`：指定链接元素引用的资源的`URL`。
        - `hreflang`：指定链接资源的语言。
        - `media`：指定链接内容用于的设备。
        - `rel`：指定文档和链接资源之间的关系类型。
        - `sizes`：指定图标的大小。
        - `type`：指定链接资源的`MIME`类型，例如`text/css`或`image/x-icon`。
    
    - `rel`属性值决定浏览器如何处理link元素，以下显示`rel`属性的常见值：
        - `alternate`：指向文档的替代版本的链接，例如翻译成另一种语言的链接。
        - `author`：链接到文档的作者。
        - `help`：与当前文档相关的帮助的链接。
        - `icon`：指定图标资源。
        - `license`：指向与当前文档相关联的许可证的链接。
        - `pingback`：指定`pingback`服务器，允许其他网站链接到博客时自动通知博客。
        - `prefetch`: 预加载资源。
        - `stylesheet`：加载`CSS`样式表。
    
    **例子**
    - 先创建一个`CSS`文件，制作一个样式表。
    ```css
    a {
    	background: grey;
    	color: red;
    	padding: 0.5em;
    }   
    ```
    - 要响应这个样式表，我们可以使用`link`样式表。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<link rel="stylesheet" type="text/css" href="styles.css" />
    </head>
    <body>
    	<p>This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    可以使用`link`元素来链接多个外部资源，外部样式表可以在多个文档中使用。
    
    **预加载资源**
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<link rel="prefetch" href="/page2.html" />
    	<base href="//www.w3cschool.cn/listings/" />
    </head>
    <body>
    	<p>This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    	<a href="page2.html">Page 2</a>
    </body>
    </html>
    ```
    上面的代码将`rel`属性设置为`prefetch`，并指定`HTML`页面`page2.html`被加载，期望用户将使用此页面。
    
10. **`HTML`图标**
    - `script`元素可以包括您的页面中的脚本，在文档中内联定义或引用外部文件。
    - 最长用的脚本是`JavaScript`脚本文件。
    - `script`元素局部属性：`type`、`src`、`defer`、`async`、`charset`。
    - `script`元素必须有结束标记，不得使用自关闭标记。
        - `type`：指定引用或定义脚本文件的类型，针对`JavaScript`脚本可以忽略此属性。
        - `src`：指定外部脚本文件的`URL`。
        - `defer`：指定如何执行脚本，只能与`src`属性一同使用。
        - `async`：指定如何执行脚本，只能与`src`属性一同使用。
        - `charset`：指定外部脚本文件的字符编码。此属性只能与`src`属性一同使用。
    
    **内联脚本**
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<script>
    		document.write("This is from the script");
    	</script>
    </head>
    <body>
    	<p>This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    `script`元素可以在`HTML`文档中的任何部位使用。
    
    **外部脚本**
    - 假设有一个外部脚本文件`simple.js`。
    ```
    document.write("This is from the external script");
    ```
    - 以下代码使用上面的脚本文件`simple.js`。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<script src="simple.js"></script>
    </head>
    <body>
    	<p>This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    
    **延迟脚本**
    - 创建脚本`simple2.js`
    ```
    document.getElementById("myId").innerText = "myValue";
    ```
    该脚本会在代码中查询`id=myId`，将其文本文件替换为`myValue`。
    
    - 代码示例：
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<p id="myId">This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    	<script src="simple2.js"></script>
    </body>
    </html>
    ```
    - 如果放在开头，则`script`元素则查询不到`Id=myId`的元素。
    - 必须将`script`元素放在文档的末尾，才能够找到`p`元素。
    
    **`defer`属性**
    - 使用`defer`属性可以起到相同的效果，且不需要必须将`script`元素放到文档最后。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<script defer src="simple2.js"></script>
    </head>
    <body>
    	<p id="myId">This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
    只能仅对外联脚本使用`defer`属性。
    
    **异步脚本**
    - `aysnc`属性可以用来提高性能。
    - 使用`aysnc`属性可以让浏览器异步加载和执行脚本，同时继续执行解析`HTML`中的其他元素，包括其他脚本元素。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<script async src="simple2.js"></script>
    </head>
    <body>
    	<p id="myId">This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```
        **注意**
        - 因具有`aysnc`属性的脚本的不会按顺序运行。
        - 因此`aysnc`属性不适用于依赖于由其他脚本定义的函数或者值的脚本。
    
    **`noscript`元素**
    - `noscript`元素允许当浏览器禁用`JavaScript`脚本时，显示`noscript`元素的内容。
    - 如果浏览器支持`JavaScript`，则不会显示`noscript`元素内的内容。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<script defer src="simple2.js"></script>
    	<noscript>
    		<h1>JavaScript is required!</h1>
    		<p>You cannot use this page without JavaScript</p>
    		<meta http-equiv="refresh" content="0; http://www.w3cschool.cn" />
    	</noscript>
    </head>
    <body>
    	<p id="myId">This is a test.</p>
    	<a href="http://www.w3cschool.cn">Visit www.w3cschool.cn</a>
    </body>
    </html>
    ```

11. `HTML`基本标签

    **`H1-H6`**
    - 标题元素，从1到6依次变小。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<h1>This is h1.</h1>
    	<p>I like XML.</p>
    	<h2>Additional h2</h2>
    	<p>I like XML.</p>
    	<h3>More information</h3>
    	<p>I like XML.</p>
    		<h1>Heading 1</h1>
    		<h2>Heading 2</h2>
    		<h3>Heading 3</h3>
    		<h4>Heading 4</h4>
    		<h5>Heading 5</h5>
    		<h6>Heading 6</h6>
    		<h1>Basic Text Formatting</h1>
    		<p>The purpose of a web browser is
    		    to read HTML documents and compose them into visible
    		    or audible web pages. The browser does not display
    		    the HTML tags, but uses the tags to interpret the
    		    content of the page. HTML describes the structure
    		    of a website semantically along with cues for
    		    presentation, making it a markup language rather
    		    than a programming language.
    		</p>
    
    		<h2>White Space and Flow</h2>
    		<p>
    			HTML elements form the building blocks of all
    		    websites. HTML allows images and objects to be
    		    embedded and can be used to create interactive
    		    forms. It provides a means to create structured
    		    documents by denoting structural semantics for
    		    text such as headings, paragraphs, lists, links,
    		    quotes and other items. It can embed scripts
    		    written in languages such as JavaScript
    		    which affect the behavior of HTML web pages.
    		</p>
    
    		<h2>Creating Headings</h2>
    		<p>
    			Web browsers can also refer to Cascading Style
    		    Sheets (CSS) to define the look and layout of text
    		    and other material. The W3C, maintainer of both
    		    the HTML and the CSS standards, encourages the
    		    use of CSS over explicit presentational HTML.
    		</p>
    </body>
    </html>
    ```
    
    - `hgroup`元素，允许将多个`标题元素`作为单个项目进行处理。
    ```html
    <!DOCTYPE HRML>
    <html>
    	<head>
    	</head>
    	<body>
    	    <hgroup>
    			<h1>H1</h1>
    			<h2>H2</h2>
    		</hgroup>
    		<h2>Additional</h2>
    		<h3>More information</h3>
    			<h1>H1</h1>
    			<p>This is a test.</p>
    			<h2>H2</h2>
    			This is a test.
    			<h3></h3>
    	</body>
    </html>
    ```
    **`HTML`线-已废弃**
    - `hr`元素表示水平规则，是一条横跨页面的直线。
    ```
    <!DOCTYPE HTML>
    <html>
    <head>
    </head>
    <body>
    	<p>
    		This is a test.
    	</p>
    	<hr/>
    	<p>This is another test.</p>
    </body>
    </html>
    ```
    
    **`div`元素**
    - 该元素不具有特殊含义，负责创建结构。是一个块元素。
    - `div`元素是`span`元素的`block`，行内元素始终保持在同一行。
    - `span`标签是用来组合行内元素，通过样式格式化它们。
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    	<style>
    	.favorites {
    		backgound: grey;
    		color: black;
    		border: thin solid black;
    		padding: 0.2em
    	}
    	</style>
    </head>
    <body>
    	<div class="favorites">
    		<p>This is a test.</p>
    		<p>This is another test.</p>
    	</div>
    	<p>This is a test.</p>
    </body>
    </html>
    ```
    - `span`元素
    - 利用该元素将全局属性应用到内容区域。
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    <style>
    	.myclass {
    		border: thin solid black;
    		padding:1px
    	}
    </style>
    </head>
    <body>
    	I like <span class="myclass">CSS</span> and
    	<span class="myclass">HTML</span>.
    </body>
    </html>
    ```
    - `HTML`段落
    - `p`元素表示一个段落
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      <p>
        I code in CSS.
      </p>
    
      <p>
        HTML is good.
      </p>
    
      <p>
        This is the third paragraph.
      </p>
    
    </body>
    </html>
    ```
    - `pre` - 预格式化内容
    - 在该元素中，空格不会被折叠，且保留文本原有样式。当需要显示编码模块时，非常有用。
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    </head>
    <body>
    	<pre>
    		<code>
    			var fruits=["XML", "HTML", "CSS", "Java"];
    			for (var i = 0; i < fruits.length; i++)	{
    			       document.writeln("I like    " + fruits[i])
    			}
    		</code>
    	</pre>
    </body>
    </html>
    ```
    - `HTML`引用
    - `blockquote`元素表示从另外一个来源引用的内容
    - 通常适合较大数量的引用内容。
    - `cite`属性表明引用的外部`URL`
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    </head>
    <body>
    	<blockquote cite="http://en.wikipedia.org/wiki/Cascading_Style_Sheets">
    	Cascading Style Sheets (CSS) is a style sheet language used for
      	describing the look and formatting of a document written in a markup language.
    	</blockquote>
    </body>
    </html>
    ```
    - `q`元素，当引用数量内容较少时使用。
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    </head>
    <body>
    	<p>
    		<q cite="http://en.wikipedia.org/wiki/Cascading_Style_Sheets">
    			The <dfn title="Cascading Style Sheets">CSS</dfn>
    			is a style sheet language used for describing the
              			look and formatting of a document written in a markup language.
    		</q>
    	</p>
    </body>
    </html>
    ```
    
    - `HTML`页面内容
    
    ```
    1. 作为语义化标签，section 应用的典型场景有文章的章节、标签对话框中的标签页、或者论文中有编号的部分。一般来说，当元素内容明确地出现在文档大纲中时，section 就是适用的。
    2. 对于article标签来说，无论从结构上还是内容上来说，article 本身就是独立的、完整的。有个最简单的判断方法是看这段内容脱离了所在的语境，是否还是完整的、独立的，如果是，则应该用article标签。
    3. div section article ，语义是从无到有，逐渐增强的。div 无任何语义，仅仅用作样式化或者脚本化，对于一段主题性的内容，则就适用 section，而假如这段内容可以脱离上下文，作为完整的独立存在的一段内容，则就适用 article。原则上来说，能使用 article 的时候，也是可以使用 section 的，但是实际上，假如使用 article 更合适，那么就不要使用 section 。
    ```
    
    **`article`标签**
    - 包含独立的文档，主要用来定义外部内容。
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    </head>
    <body>
      <article>
      	<header>
      	  <hgroup>
      		  <h1 id="fruitsilike">H1Like</h1>
      		  <h2>H2</h2>
      	  </hgroup>
      	</header>
      	This is a test.
      	<section>
      	  <h1 id="morefruit">XML</h1>
      	  This is a test.
      	    <section>
      	      <h1>HTML</h1>
      	      This is a test.
      	    </section>
      	</section>
      	<footer>
      	  <nav>
      	  	Nav
      	  </nav>
      	</footer>
      </article>
    </body>
    </html>
    ```
    
    **`section`元素**
    - `section`元素应该包含文档中的大纲或者目录。`cite`属性表示引用的`URL`，`section`元素适用于一段主题性的内容。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<section>
    		<hgroup>
    			<h1>H1</h1>
    			<h2>H2</h2>
    		</hgroup>
    		This is a test.
    		<section>
    			<h1>H1</h1>
    			This is a test.
    			<section>
    				<h1>More information</h1>
    				This is a test.
    			</section>
    		</section>
    	</section>
    </body>
    </html>
    ```
    
    **`nav`元素**
    - 导航栏标签
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      <header>
        <hgroup>
          <h1>H1</h1>
          <h2>by www.w3cschool.cn</h2>
        </hgroup>
        <nav>
          <h1>Contents</h1>
          <ul>
            <li><a href="#fruitsilike">XML</a></li>
            <ul>
              <li><a href="#morefruit">HTML</a></li>
            </ul>
            <li><a href="#activitiesilike">CSS</a></li>
            <ul>
              <li><a href="#tritypes">Java</a></li>
              <li><a href="#mytri">Javascript</a></li>
            </ul>
          </ul>
        </nav>
      </header>
      <section>
        <header>
          <hgroup>
            <h1 id="fruitsilike">Section h1</h1>
            <h2>Section h2</h2>
          </hgroup>
        </header>
        This is a test.
        <section>
          <h1 id="morefruit">Inner H1</h1>
          This is a test.
          <section>
            <h1>More information</h1>
            This is a test.
          </section>
        </section>
      </section>
      <section>
        <header>
          <h1 id="activitiesilike">Activities</h1>
        </header>
        <section>
          <p>This is a test.</p>
          <h1 id="tritypes">Java</h1>
          This is a test.
          <section>
            <h1 id="mytri">Javascript</h1>
          </section>
        </section>
      </section>
      <nav>
        More Information: <a href="http://www.w3cschool.cn">Learn More About</a>
        <a href="http://www.w3cschool.cn">Learn More About</a>
      </nav>
      <footer id="mainFooter">
        &#169;2011, www.w3cschool.cn. <a href="http://www.w3cschool.cn">Visit</a>
      </footer>
    </body>
    </html>
    ```
    
    **`Details`元素**
    - 创建一个节，用户可以展开该节获取更多有关主题的详细信息。
    - 通常包含一个摘要元素，用于为详细部分创建标签或标题。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<style>
    		details {
    			border: solid thin black;
    			padding: 5px;
    		}
    		details>summary {
    			font-weight: bold
    		}
    	</style>
    </head>
    <body>
    	<article>
    		<h1>这是一级标题</h1>
    		<section>
    			<p>这是第一个测试段落</p>
    			<details>
    				<summary>Summary</summary>
    				<ol>
    					<li>XML</li>
    					<li>HTML</li>
    					<li>CSS</li>
    				</ol>
    			</details>
    		</section>
    	</article>
    </body>
    </html>
    ```
    
    **`HTML Headers Footers`**
    - `header`元素表示节的标题，主要用来将头部内容包含在内。
    - 头部内容通常包含`h1?h6`元素或者一个`hgroup`元素，还可以包含节的导航元素。
    - `footer`元素是页眉的补充，也可以表示部分页脚。
    - 页脚通常包含关于版块的摘要信息，并且可以包括作者的详细信息，权限信息等。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<header>
    		<hgroup>
    			<h1>这是一级标题</h1>
    			<h2>这是二级标题，来自于KXD</h2>
    		</hgroup>
    	</header>
    	<section>
    		<header>
    			<hgroup>
    				<h1>第一部分</h1>
    				<h2>第二部分</h2>
    			</hgroup>
    		</header>
    		这是一个测试。
    		<section>
    			<h1>Inner Section h1</h1>
    			这是一个测试。
    		</section>
    	</section>
    	<footer id="mainFooter">
    		&169;2018, www.w3cschool.cn. <a href="http://www.w3cschool.cn">访问</a>
    	</footer>
    </body>
    </html>
    ```
    
    **`aside`元素**
    - 仅表示与周围元素相关的内容，类似于杂志或者报纸的侧边栏。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
     <style>
      
      article {
      	border: thin black solid;
      	padding: 10px;
      	margin-bottom: 5px
      }
      aside {
      	width: 40%;
      	background: white;
      	float: right;
      	border: thick solid black;
      	margin-left: 5px
      }
    
      aside>section {
      	padding: 5px
      }
    
      aside>h1 {
      	background: white;
      	color: black;
      	text-align: center
      }
     </style>
    </head>
    <body>
    	<article>
    		<header>
    			<hgroup>
    				<h1 id="fruitsilike">H1</h1>
    				<h2>H2</h2>
    			</hgroup>
    		</header>
    		<aside>
    			<h1>Why</h1>
    			 <section>
    				This is a test:
    				<ol>
    					<li>HTML</li>
    					<li>CSS</li>
    					<li>JavaScript</li>
    				</ol>
    			</section>
    		</aside>	
    	</article>
    </body>
    </html>
    ```

12. **`HTML`超链接**
    - 为`HTML`提供了基础，让用户可以通过`HTML`在同一文档和跨界面进行浏览内容。
    - 可以使用`a`元素创建超链接。
    
    **`a`元素属性**
    - 具有局部属性：`href` `hreflang` `media` `rel` `target` `type`
        - `href`：指定引用资源的`URL`
        - `hreflang`：指定链接资源的语言
        - `media`：指定链接内容用于的设备，此属性与头元素使用 相同的设备和特征值
        - `rel`：指定文档和链接资源之间的关系类型，此属性使用与链接元素的`rel`属性相同的值。
        - `target`：指定链接的页面在浏览器窗口中的打开方式。
        - `type`：所链接资源的`MIME`类型，例如text/html。
        
    
    **外部超链接**
    - 通过`href`属性设置以`http://`开头的`URL`来指向一个其他`HTML`文档的超链接
    ```html
    <!DOCTYPE html>
    <html>
     <head>
     </head>
     <body>
    	I like <a href="http:www.w3cschool.cn">W3Cschool</a>
     </body>
    </html>
    ```
    
    **相对网址**
    - 如果`href`属性的值不是以`start`开头识别的协议，则浏览器将超链接视为相对引用。
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      I like <a href="index.html">w3cschool</a>.
    </body>
    </html> 
    ```
    当用户点击相对网址时，浏览器将确定如何加载当前文档。
    
    **`target`属性** 浏览上下文
    - 该属性告诉浏览器要显示链接资源的位置。
        - `_blank`：在新窗口打开文档。
        - `_parent`：打开父框架集中的文档。
        - `_self`：在当前窗口中打开文档（这是默认行为）。
        - `_top`：在窗口的整个主体中打开文档。
        - `<frame>`：在指定的框架中打开文档。
    
12. **`HTML`格式化**
    
    **`abbr`元素**
    - 该元素表示缩写，使用`title`属性提供缩写的扩展文本。
    ```html
    <!DOCTYPE HTML>
    <html>   
    </head>
    <body>
     The <abbr title="Cascading Style Sheets">CSS</abbr>
     is a style sheet language used for describing the
     look and formatting of a document written in a markup language.
    </body>
    </html>
    ```
    
    **`address`元素**
    - 该元素定义文档或文章的联系信息。
    - 当`address`元素是`article`元素的后代时，提供该文章的联系信息。
    - 当`address`元素是`body`元素的后代时，提供该文档的联系信息。
    ```html
    <!DOCTYPE HTML>
    <html>   
    </head>
    <body>
     <header>
     	<h1>Things I like</h1>
     	<h2>by www.w3cschool.cn</h2>
     	<address>
     		Questions and comments ? <a href="mailto:info@example.com">Email me</a>
     	</address>
     </header>
    </body>
    </html>
    ```
    
    **`b`元素-已废弃**
    - 定义粗体文本。被`strong`标签所替代。
    ```html
    <!DOCTYPE HTML>
    <html>   
    </head>
    <body>
     <header>
     	I like <b>HTML</b> and <b>CSS</b>
    </body>
    </html>
    ```
    
    **`bdo`元素**
    - 指定一个明确的文本方向
    - 需要使用`dir`属性
        - `dir="ltr"` 文本从左到右
        - `dir="rtl"` 文本从右到左
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      <p>
      	This is left-to-right:
      	<bdo dir="ltr">This is a test</bdo>
      </p>
      <p>
      	This is right-to-left:
      	<bdo dir="rtl">This is a test</bdo>
      </p>
    </body>
    </html>
    ```
    
    **`br`元素-已废弃**
    - `br`元素引入换行符，将后续内容移动到新行上。
    - 只能在换行符是内容的一部分时使用。
    - 不能用于创建段落或其他内容分组。
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      I like<br/>HTML,
      <br/>CSS,
      <br/>JavaScript.
    </body>
    </html>
    ```
    
    **`cite`元素**
    - 通常表示它所包含的文本对某个参考文献的引用，例如杂事或者文章的标题。
    - 按照惯例，引用的文本将以斜体表示。
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      My favorite is <cite>CSS</cite> by http://en.wikipedia.org.
    </body>
    </html>
    ```
    
    ** `code`元素**
    - 一般包含一段计算机代码，且保留原有文本样式。
    
    **`del`元素**
    - 使用该元素来标记被删除的文本。
    - 有两个局部属性：`cite`、`datetime`
        - `cite`：指定文档的`URL`，解释为什么删除该文本。
        - `datetime`：指定进行修改的时间。
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      <P><ins>I like <del>HTML</del>.</ins></P>
    </body>
    </html>
    ```
    
    **`dfn`元素**
    - 定义一个术语，解释了词或短语的意义。
    ```html
    <!DOCTYPE HTML>
    <html>
    <body>
      <P>
      	The <dfn title="Cascading Style Sheets">CSS</dfn>
      	is a style sheet language used for describing the
      	look and formating of a document written in a markup language.
      </P>
    </body>
    </html>
    ```
    
    **`em`元素，`i`元素-已废弃**
    - `em`元素定义着重文字，一般使用斜体。用来替代`i`标签。
    - `i`元素一般定义与周围文本有不用意义的文本，使用斜体，一般是表示他国语言，技术或者科学术语。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<em>I</em> like <b>HTML</b> and <b>CSS</b>
    	My favorite is <i>JavaScript</i>.
    </body>
    </html>
    ```
    
    **`ins`元素**
    - 用来标记部分文本（增加下划线）。
    - 局部属性：
        - `cite`：指定文档的`URL`，解释为什么添加该文本。
        - `datetime`：指定进行修改的时间。
    
    **`kbd`元素**
    - 表示键盘文本，是从计算机中输入的文本。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	This is an <kbd>input</kbd>.
    </body>
    </html>
    ```
    
    **`mark`元素**
    - 表示突出显示的文本，一般用其他颜色显示。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	I like <mark>CSS</mark>.
    </body>
    </html>
    ```
    
    **`ruby` `rt` `rp` 元素**
    - `Ruby`元素是表示放置在某段文本上方或者右侧的符号，比如中文或者日语的发音字符和拼音。
        - `rt`元素标记`ruby`元素，而`rp`元素中的内容则在不支持`ruby`的浏览器中显示。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<p>I like
    	<ruby>
    		CSS
    		<rp>(</rp>
    		<rt>Cascading Style Sheets</rt>
    		<rp>)</rp>
    	</ruby>
    
    	
    	</p>
    </body>
    </html>
    ```
    
    **`s`元素-已废弃**，用来标记不正确的文本。现在已经被`del`标签替代。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	HTML is now <s>HTML4</s> HTML5.
    </body>
    </html>
    ```
    
    **`samp`元素**
    - 定义样式文本.
    
    **`small`元素**
    - 呈现小号字体的效果，且可以嵌套，知道呈现最小字体的效果。
    - 经常用于精细打印和免责声明等。
    
    **`strong`元素** 
    - 强调内容的重要性，显示为粗体。替代`b`标签
    
    **`sub`和`sup`元素**
    - `sub` 表示下标
    - `sub` 表示上标
    
    **`time`元素**
    - 用来表示时间或者日期。
        - 有`pubdate`和`datetime`两个局部属性。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	I thought a book at
    	<time datetime="15:00">3 o"clock</time>
    	on
    	<time datetime="2012-12-7">Decmber 7th</time>
    	.
    	<p>我们在每天早上9:00开始营业</p>.
    </body>
    </html>
    ```
    
    **`u`元素-已废弃**
    - 为超链接添加下划线。现在已经被`ins`标签替代
    
    **`var`元素**
    - 用来定义变量，表示变量的名称。
    
    **`wbr`元素**
    
    - 如果单词太长，担心浏览器会在错误的位置换行，则可以使用该标签。
    
13. **`HTML`列表**
    
    **无序列表**
    - `ul`表示无序列表
    - 列表中的项目使用`li`来表示
    ```
    <!DOCTYPE HTML>
    <html>
    <body>
      I like:
      <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>Javascript</li>
      </ul>
    </body>
    </html>
    ```
    
    - 关于嵌套列表
    ```
    <!DOCTYPE HTML>
    <html>
    <body>
        <ul>
            <li>HTML</li>
            <li>CSS
                <ul>
                    <li>Introdunction</li>
                    <li>CSS attributes</li>
                </ul>
            </li>
            <li>Javascript</li>
        </ul>
    </body>
    </html>
    ```
    
    **有序列表**
    - `ol`表示有序列表，列表中的项目仍然使用`li`表示。
    ```
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<ol>
    		<li>HTML</li>
    		<li>CSS
    			<ol>
    				<li>Introdunction</li>
    				<li>CSS attributes</li>
    			</ol>
    		</li>
    		<li>JavaScript</li>
    	</ol>
    </body>
    </html>
    ```
    
    - `satrt`属性 定义第一个项目的序列，未定义时，默认从第一个开始。
    - `type`属性 定义使用哪一种标记作为序列，类型如下：

    | 值   | 描述         | 例子                 |
    | ---- | ------------ | -------------------- |
    | 1    | 数字         | 1.，2.，3.           |
    | a    | 小写拉丁字母 | a.，b.，c.           |
    | A    | 大写拉丁字母 | A.，B.，C.           |
    | i    | 小写罗马数字 | i.，ii.，iii.，iv.   |
    | I    | 大写罗马数字 | I.， II.， III.， IV |
    
    
    
    **自定义列表**
    
    - 使用`dl` `dt` `dd` 来描述列表
        - `dl` 定义列表
        - `dt` 定义列表中的术语
        - `dd` 定义术语的解释和说明
    - 单个`dt`可以使用多个`dd`，允许为单个术语定义多个说明。
    
    ```html
    <!DOCTYPE html>
    <html>  
    <head>
    </head>
    <body>
    	L like:
    	<dl>
    		<dt>CSS</dt>
    		<dd>Cascading Style Sheets</dd>
    		<dd><i>a style sheet language used for 
    			   describing the look and formating
    			   of a document written in a markup language</i></dd>
    		<dt>HTML</dt>
    		<dd>The mark language</dd>
    
    		<dt>JavaScript</dt>
    		<dd>The coding logic</dd>
    	</dl>
    </body>
    </html>
    ```
    
14. **`HTML` `figure`**
    
    **`fig`和`figcaption`元素**
    - `figure`标签规定独立的流内容（图像、图表、照片、代码等等）。
    - `figure`元素的内容应该与主要内容有关，同时是相对独立的，如果被删除，不会被文档流产生影响。
    - `figcaption`元素被用来为`figure`元素定义标题。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	I like XML and CSS.
    	<figure>
    		<figcaption>Listing 01. Using the code element</figcaption>
    		<code>
    			var fruits = ["CSS", "HTML", "CSS", "JavaScript"];<br>
    			document.writeln("I like " + fruits.length + "fruits");
    		</code>
    	</figure>
    </body>
    </html>
    ```
15. **`HTML`图像**
    
    - `img`元素允许您将图像嵌入到`HTML`文档中。
    - 局部属性：
        - `src` `alt` `height` `width` `usemap` `ismap`
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<img src="http://www.w3cschool.cn/style/download.png" /
    		 alt="Triathlon Image"
    		 width="200"
    		 height="67">
    </body>
    </html>
    ```
    - `src`指定图像的`URL`
    - 当无法显示图像时，则`alt`属性定义内容。
    - `width`和`height`属性设置图像大小（以像素为单位）。
    
    **图像链接**
    
    - `img`元素通常用来结合`a`元素创建基于图像的超链接。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<p>
    		<a href="//www.w3cschool.cn/page.html">
    			<img ismap src="C://Users//kxd18//Desktop//pictures//90平简中式二居装潢大全.jpg" />
    			
    		</a>
    	</p>
    </body>
    </html>
    ```
    如果使用了`ismap`属性，浏览器则会吧鼠标的x，y的位置发送到服务器端，并响应。
    
    **客户端图像映射**
    - 创建客户端图像映射，单击图像中的不同区域会导致浏览器导航到不同的`URL`。
    - 关键元素是`map`和`name`。
    - `map`元素可以有多个`area`元素。
    - `alt` `href` `target` `rel` `media` `hreflang` `type` `shape` `coords`
        - `href` 点击区域时浏览器加载相应的网址
        - `alt` 替代内容，同`img`元素上的属性相同。
        - `target` 显示网址的浏览内容。
        - `rel` 描述当前文档和目标文档之间的关系。
        - `media` 区域有效的介质。
        - `hreflang` 目前文档的语言。
        - `type` 目前文档`MIME`类型。
        `shape`和`coords`属性一起工作，`coords`属性取决于`shape`属性的值。
            - `rect`
                - 表示矩形区域
                - `coords`属性必须由四个值组成，用逗号隔开
                    - 矩形左边缘到图像左边的距离
                    - 矩形右边缘到图像右边的距离
                    - 矩形上边缘到图像上边的距离
                    - 矩形下边缘到图像下边的距离
            
            - `circle`
                - 表示圆形区域
                - `coords`属性由三个值组成
                    - 左边缘到圆心的距离
                    - 顶部到圆心的距离
                    - 圆的半径
            
            - `poly`
                - 表示多边形
                - `coords`属性由6个值，每对表示多边形的一个点。
                
            - `default`
                - 默认区域，覆盖图像的其余部分。
                - 用此值时，不需要使用`shape`属性。
                
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<p>
    		<img src="C://Users//kxd18//Desktop//pictures//90平简中式二居装潢大全.jpg" usemap="#mymap" />
    	</p>
    	<map name="mymap">
    		<area href="a.html" shape="rect" coords="3,5,68,62" alt="test a">
    		<area href="b.html" shape="rect" coords="70,5,130,62" alt="test b">
    		<area href="c.html" shape="default" alt="test c">
    	</map>
    </body>
    </html>
    ```
    
16. ** `HTML iframe`**

- `iframe`标签可以在现有元素中嵌入另外一个`HTML`文档，内联框架。
- 局部属性：`src` `srcdoc` `name` `width` `height` `sandbox` `seamless`。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>ifrname标签</title>
    </head>
    <body>
    	<a href="http://www.w3cschool.cn" target="myframe">Tutorial</a>
    		<a href="http://www.w3cschool.cn" target="myframe">Tutorial</a>
    	<iframe name="myframe" width="1300" height="600"></iframe>
    </body>
    </html>
    ```
    - 创建一个名称为`myframe`的`iframe`，之后该属性在其他元素的目标属性中使用：主要是`a` `form` `bottom` `input` `base`
    
    - `a`标签会创建一堆超链接，超链接会将其`href`属性指定的网址加载到`iframe`中。
    - `width`和`height`属性指定大小（以像素为单位）。
    - `src`指定在`iframe`中显示的文档的`URL`
    - `srcdoc` 规定和在`iframe`中显示的页面的`HTML`内容
    - `seamless`设置浏览器线束`iframe`，并将其当做主`HTML`文档的一部分。
    
    **`irame sandbox`**
    - 启用一系列对`iframe`中文档的限制
    ```
    <iframe sandbox="allow-forms" name="myframe" width="300" height="100"></iframe>
    ```
        - `allow-forms` 启用表单
        - `allow-scripts` 启用脚本
        - `allow-top-navigation` 
        - `allow-same-origin`
    
17. **`HTML`表格**
    
    - 每个表必须包含三个元素：`table`，`tr`，`td`。
    - `table`
        - 具有局部属性：`border`
        - `table`元素可以包含`caption` `colgroup` `thead` `tbody` `tfoot` `tr` `th` `td`标签。
        - `border`属性的值必须为1。边框的厚度必须使用`CSS`设置。
        
    - `tr`
        - `tr`元素表示表行
        - `tr`可以在`table` `thead` `tfoot`和`tbody`元素内使用。
        - `tr`元素可以包含一个或者多个`td`/`th`元素。
    
    - `td`
        - `td`与`colspan` `rowspan` `headers`等局部属性表示表单元格。
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表格练习</title>
    </head>
    <body>
    	<table>
    		<tr>
    			<td>A</td>
    			<td>B</td>
    			<td>C</td>
    		</tr>
    		<tr>
    			<td>D</td>
    			<td>E</td>
    			<td>F</td>
    		</tr>
    	</table>
    </body>
    </html>
    ```
    - 可以通过局部属性`weight`和`height`来控制表格或者单元格的大小。
    - 可以通过`align`属性来控制`table`的水平位置，表格只能改变水平位置。同时，`cellspacing`属性可以控制表格的外边距，默认是`2px`。外边距是边框之间的距离。
    - 可以通过`align`和`valign`属性来控制单元格内的内容的水平位置和垂直位置。
    - 内边距是单元格内容距离边框的距离，通过属性`cellpadding`属性改变。
    - 以上内容只做了解，企业开发中，所有样式都通过`CSS`来进行变更。
    
    **`thead`表头包装器**
    
    - `thead`定义一行或多行，是表格的列标签。
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表头包装器</title>
    	<style type="text/css">
    		thead th {
    			text-align: left;
    			background: grey;
    			color: white
    		}
    
    		thead th {
    			text-align: right;
    			background: lightgrey;
    			color: grey
    		}
    	</style>
    </head>
    <body>
    	<table>
    		<thead>
    			<th>第一列</th>
    			<th>第二列</th>
    			<th>第三列</th>
    			<th>第四列</th>
    		</thead>
    		<tbody>
    			<tr>
    				<th>1st Favorite:</th>
    				<td>XML</td>
    				<td>HTML</td>
    				<td>CSS</td>
    			</tr>
    			<tr>
    				<th>2nd Favorite:</th>
    				<td>Java</td>
    				<td>JavaScript</td>
    				<td>Oracle</td>
    			</tr>
    			<tr>
    				<th>3rd Favorite:</th>
    				<td>C#</td>
    				<td>MySQL</td>
    				<td>Python</td>
    			</tr>
    		</tbody>
    	</table>
    </body>
    </html>
    ```
    
    **`th` 表头单元格**
    
    - 标记标题单元格，是我们能够区分及其描述。
    - 是`tr`的子元素。
    
    **`tbody`  表主体**
    
    - `tbody`元素标记表体的行，表示除标题行和页脚行之外的表主体内容。
    
    **`tfoot` 表页脚**
    
    - 表示标记表页脚
    - 可以出现在`tbody`或者`tr`标签之前或者之后。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表头包装器</title>
    	<style type="text/css">
    		thead th, tfoot th {
    			text-align: left;
    			background: grey;
    			color: white
    		}
    
    		tbody th {
    			text-align: right;
    			background: lightgrey;
    			color: grey
    		}
    	</style>
    </head>
    <body>
    	<table>
    		<thead>
    			<th>第一列</th>
    			<th>第二列</th>
    			<th>第三列</th>
    			<th>第四列</th>
    		</thead>
    		<tfoot>
    			<tr>
    				<th>一列页脚</th>
    				<th>二列页脚</th>
    				<th>三列页脚</th>
    				<th>四列页脚</th>
    			</tr>
    		</tfoot>
    		<tbody>
    			<tr>
    				<th>1st Favorite:</th>
    				<td>XML</td>
    				<td>HTML</td>
    				<td>CSS</td>
    			</tr>
    			<tr>
    				<th>2nd Favorite:</th>
    				<td>Java</td>
    				<td>JavaScript</td>
    				<td>Oracle</td>
    			</tr>
    			<tr>
    				<th>3rd Favorite:</th>
    				<td>C#</td>
    				<td>MySQL</td>
    				<td>Python</td>
    			</tr>
    		</tbody>
    	</table>
    </body>
    </html>
    ```
    
    **`HTML`表头**
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表头</title>
    	<style type="text/css">
    		thead th, tfoot th {
    			text-align: left;
    			background: grey;
    			color: white
    		}
    
    		tbody th {
    			text-align: right;
    			background: lightgrey;
    			color: grey
    		}
    	thead [colspan], tfoot [colspan] {
    		text-align: center
    	}
    	</style>
    </head>
    <body>
    	<table>
    		<thead>
    			<tr>
    				<th id="rank">Rank</th>
    				<th id="name">Name</th>
    				<th id="color">Color</th>
    				<th id="sizeAndVotes" colspan="2">Size & Votes</th>
    			</tr>
    		</thead>
    		<tbody>
    			<tr>
    				<th id="first" headers="rank">1st Favorites:</th>
    				<td headers="name first">XML</td>
    				<td headers="color first">HTML</td>
    				<td headers="sizeAndVote first">CSS</td>
    				<td headers="sizeAndVote first">ABC</td>
    			</tr>
    			<tr>
    				<th id="second" headers="rank">2nd Favorites:</th>
    				<td headers="name second">Empty</td>
    				<td headers="color second">XYZ</td>
    				<td headers="sizeAndVote second">ABC</td>
    				<td headers="sizeAndVote second">A</td>
    			</tr>
    		</tbody>
    		<tfoot>
    			<tr>
    				<th colspan="5">&copy; 2011 www.w3cschool.cn Fruit Data Enterpries></th>
    			</tr>
    		</tfoot>
    	</table>
    </body>
    </html>
    ```
    
    **`HTML`表列**
    
    - `HTML`表是面向行的，将单元格`td`定义在`tr`中。
    - 如果想将样式应用于列，则需要使用`colgroup`和`col`元素。
    - 具有局部属性`span`的`colgroup`元素表示列，根据`span`属性确定将`colgroup`应用于多少列。
    - `colgroup`元素可以包含0个或者多个`col`元素。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表列练习</title>
    	<style type="text/css">
    	#colgroup1 {
    		background: red
    	}
    
    	#colgroup2 {
    		background-color: green;
    		font-size: small 
    	}
    	</style>
    </head>
    <body>
    	<table>
    		<colgroup id="colgroup1" span="3" />
    		<colgroup id="colgroup2" span="2" />
    		<thead>
    			<tr>
    				<th>Rank</th>
    				<th>Name</th>
    				<th>Color</th>
    				<th colspan="2">Size & Votes</th>
    			</tr>
    		</thead>
    		<tbody>
    			<tr>
    				<th>1st Favorite:</th>
    				<td>XML</td>
    				<td>HTML</td>
    				<td>CSS</td>
    				<td>500</td>
    			</tr>
    			<tr>
    				<th>2ed Favorite:</th>
    				<td>CSS</td>
    				<td>Java</td>
    				<td>JavaScript</td>
    				<td>450</td>
    			</tr>
    		</tbody>
    	</table>
    </body>
    </html>
    ```
    - 全局属性`id`是为每个`colgroup`定义的，`CSS`样式通过`id`来为目标元素定义样式。
    
    **`col` 表示单个列**
    
    - 具有局部属性`span`
    - `col`元素放置在`colgroup`元素内部
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表列练习</title>
    	<style type="text/css">
    	#colgroup1 {
    		background: red
    	}
    
    	#col3 {
    		background-color: green;
    		font-size: small 
    	}
    	</style>
    </head>
    <body>
    	<table>
    		<colgroup id="colgroup1">
    			<col id="col1And2" span="2" />
    			<col id="col3" />
    		</colgroup>
    		<colgroup id="colgroup2" />
    		<thead>
    			<tr>
    				<th>Rand</th>
    				<th>Name</th>
    				<th>Color</th>
    				<th colspan="2">Size & Votes</th>
    			</tr>
    		</thead>
    		<tbody>
    			<tr>
    				<th>1st Favorite:</th>
    				<td>1234</td>
    				<td>1234</td>
    				<td>1234</td>
    				<td>500</td>
    			</tr>
    			<tr>
    				<th>2nd Favorite:</th>
    				<td>1234</td>
    				<td>1234</td>
    				<td>1234</td>
    				<td>450</td>
    			</tr>
    		</tbody>
    	</table>
    </body>
    </html>
    ```
    
    **`HTML`表跨度**
    
    - `colspan` 列跨度
    - 若需要将单元格合并，则使用`colspan`属性。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    </head>
    <body>
    	<table>
    
    		<thead>
    			<tr>
    				<th>Rand</th>
    				<th>Name</th>
    				<th>Color</th>
    				<th colspan="2">Size & Votes</th>
    			</tr>
    		</thead>
    		<tbody>
    			<tr>
    				<th>1st Favorite:</th>
    				<td>HTML</td>
    				<td>HTML</td>
    				<td>Oracle</td>
    				<td>MySQL</td>
    			</tr>
    			<tr>
    				<th>2nd Favorite:</th>
    				<td>HTML</td>
    				<td>HTML</td>
    				<td>Oracle</td>
    				<td>MySQL</td>
    			</tr>
    			<tr>
    				<th>3rd Favorite:</th>
    				<td>XML</td>
    				<td colspan="2" rowspan="2">Thsi is a test.</td>
    				<td>203</td>
    			</tr>
    			<tr>
    				<td>A</td>
    				<td>B</td>
    				<td>C</td>
    			</tr>
    		</tbody>
    		<tfoot>
    			<tr>
    				<th colspan="5>&copy; 2011 www.w3cschool.cn Enterprises"></th>
    			</tr>
    		</tfoot>
    	</table>
    </body>
    </html>
    ```
    
    - `rowspan` 行跨度
    - 将单元格跨多行，可以使用该属性。
    
    **`HTML`表标题**
    
    - `caption`元素允许您定义一个标题并将其与`table`元素相关联。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表格练习</title>
    </head>
    <body>
    	<table>
    		<caption>Result of the Survey</caption>
    		<tbody>
    			<tr>
    				<th>Favorite:</th>
    				<td>500</td>
    			</tr>
    		</tbody>
    	</table>
    </body>
    </html>
    ```
    一个表只能包含一个`caption`元素，但是可以不放在第一个。
    
    **`HTML`边框**
    
    - `table`标签的局部属性`border`定义表格的边框。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表格练习</title>
    </head>
    <body>
    	<table border="1">
    		<thead>
    			<th>第一列</th>
    			<th>第二列</th>
    			<th>第三列</th>
    			<th>第四列</th>
    			<th>第五列</th>
    		</thead>
    		<tbody>
    			<tr>
    				<th>1st Favorite:</th>
    				<td>XML</td>
    				<td>HTML</td>
    				<td>SQL</td>
    				<td>500</td>
    			</tr>
    			<tr>
    				<th>2nd Favorite:</th>
    				<td>Python</td>
    				<td>JavaScript</td>
    				<td>Java</td>
    				<td>450</td>
    			</tr>
    		</tbody>
    		
    	</table>
    </body>
    </html>
    ```
    - `border`属性的值必须为1或者空字符串（""），此属性不会控制边框样式。
    
18. **`HTML`表单**
    
    - 要创建基本表单，需要使用三个元素：`form` `input` `button`
    
    - 明文输入和暗文输入
    - 当局部属性`type`是`text`的时候，则表示明文输入，等于`password`的时候，则是暗文输入。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form>
    		账号：<input type="text" />
    		<br>
    		密码：<input type="password" />
    	</form>
    </body>
    </html>
    ```
    
    **单选按钮**
    - `type`属性为`radio`，且需要多个单选按钮`input`的`name`属性都一致。
    - 当局部属性`checked`为`checked`的时候，则默认选择该项。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form>
    		账号：<input type="text" />
    		<br>
    		密码：<input type="password" />
    		<br>
    		性别：
    		<input type="radio" name="n">男
    		<input type="radio" name="n">女
    		<input type="radio" name="n">保密
    		<br>
    	</form>
    </body>
    </html>
    ```
    
    **多选按钮**
    - `type`属性为`checkbox`时，可以进行多项勾选。
    - 当局部属性`checked`为`checked`的时候，则默认选择该项。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form>
    		爱好：
    		<input type="checkbox">篮球
    		<input type="checkbox">足球
    		<input type="checkbox">羽毛球
    		<input type="checkbox">乒乓球
    		<input type="checkbox">网球
    	</form>
    </body>
    </html>
    ```
    
    **`button`属性**
    - 定义一个普通按钮
    - 协助js脚本完成操作
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form>
    		<input type="button" value="我是按钮">
    </html>
    ```
    - 通过`value`属性来定义按钮上的标题。
    
    **定义重置按钮**
    - 当`type`属性为`reset`时，默认为清空表单中填写的数据。
    
    **定义提交按钮**
    - 当`type`属性为`submit`时，将表单中的数据提交到远程服务器。
    - 注意：
        - 要想把表单中的数据提交到远程服务器，需要明确告诉表单提交的服务器的地址，以及需要提交的数据。
        - 可以通过`form`标签的`action`属性告诉表单需要提交的服务器地址。
        - 可以通过`input`标签的`name`属性控制哪些数据需要提交。数据将会通过键值对的方式上传到远程服务器。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form action="http://www.baidu.com">
    		账号：<input type="text" name="x">
    		<br>
    		密码：<input type="password">
    		<br>
    		<hr>
    		性别：
    		<input type="radio" name="n">男
    		<input type="radio" name="n">女
    		<input type="radio" name="n" checked="checked">保密
    		<br>
    		<hr>
    		爱好：
    		<input type="checkbox">篮球
    		<input type="checkbox">足球
    		<input type="checkbox">羽毛球
    		<input type="checkbox" checked="checked">乒乓球
    		<input type="checkbox">网球
    		<br>
    		<hr>
    		<input type="reset">
    		<input type="submit">
    	</form>
    </body>
    </html>
    ```
    
    **Label标签**
    - 通过`label`标签将文字和输入框关联。
    - 需要使用该标签的`for`属性与`input`的`id`属性的值相同。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form action="http://www.baidu.com">
    		<label for="id_x">账号：</label><input type="text" id="id_x">
    		<br>
    		<label for="pwd">密码：</label><input type="password" id="pwd">
    		<br>
    	</form>
    </body>
    </html>
    ```
    
    **利用`datalist`标签添加待选列表**
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form>
    		请输入你的车型：<input list="cars" type="text">
    		<datalist id="cars">
    			<option>奔驰</option>
    			<option>宝马</option>
    			<option>奥迪</option>
    			<option>保时捷</option>
    		</datalist>

    	</form>
    </body>
    </html>
    ```
    
    **下拉列表**
    - 通过`select`标签进行下拉列表的制作。
    - 下拉列表不需要使用输入标签`inout`。
    - 通过`selected="selected"`让下拉列表显示默认选项。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单</title>
    </head>
    <body>
    	<form>
    		请选择地区：
    		<select>
    			<option>北京</option>
    			<option selected="selected">上海</option>
    			<option>深圳</option>
    			<option>武汉</option>
    			<option>广东</option>
    			<option>成都</option>
    		</select>
    	</form>
    </body>
    </html>
    ```
    
    **多行文本输入框**
    - 利用`textarea`标签来进行多行输入。
    - 默认情况下可以无限换行，且有默认高度和宽度。
    - 默认情况下输入框可以手动拉伸，进行放大和缩小。
    
    **注意：**
    - 表单进行提交时，除了`button`之外的所有数据都可以通过value属性来选择需要提交的数据。
    
    - 练习
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<meta charset="utf-8">
    	<title>表单练习</title>
    </head>
    <body>
    	<form action="http://www.baidu.com">
    		<fieldset>
    			<legend>注册界面</legend>
	    		<p>
	    			<label for="i">账号:</label><input type="text" id="i" name="accoument">	
	    		</p>
	    		<p>
	    			<label for="j">密码:</label><input type="password" id="j" name="pwd">
	    		</p>
	    		<p>
		    		性别:   		
		    		<input type="radio" name="gender" value="male">男
		    		<input type="radio" name="gender" value="female">女
		    		<input type="radio" name="gender" checked="checked" value="secret">保密
	    		</p>
	    		<p>
		    		爱好:
		    		<input type="checkbox" name="love" value="basketball">篮球
		    		<input type="checkbox" name="love" value="football">足球
		    		<input type="checkbox" name="love" checked="checked" value="creazy">足浴
	    		</p>
	    		<p>
		    		个人简介:
		    		<textarea cols="16" rows="1" name="message"></textarea>
	    		</p>
	    		<p>
		    		生日:
		    		<input type="date" name="birthday">
	    		</p>
	    		<p>
		    		邮箱:
		    		<input type="email" name="email">
	    		</p>
	    		<p>
		    		电话:
		    		<input type="number" name="Tel">
	    		</p>
	    		<p>
		    		&nbsp;<input type="submit" value="注册">
		    		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		    		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		    		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		    		<input type="reset" value="清空">
	    		</p>
    		</fieldset>
    	</form>
    </body>
    </html>
    ```
    
19. **多媒体标签**
    
    **`video`标签**
    - 局部属性：
        - `src:` 用于提供视频地址。
        - `autoplay:` 用来告诉是否需要自动播放视频。
        - `controls:` 用来显示视频的控制条等播放控件。
        - `poster:` 设置视频没有播放之前显示的占位图片。
        - `loop:` 用于设置广告视频。
        - `preload:` 预加载视频，和`autoplay`属性只能使用其一。
        - `muted:` 让视频静音
        - `width`和`height`设置视频的宽度和高度。
    - 视频格式：
        - `Ogg` `MPEG4` `WebM` 三种格式
        - 每种视频格式都不支持所有浏览器。因此需要使用`source`标签来指定视频格式。
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<title></title>
    </head>
    <body>
    	<video>
    		<source src="images/sb1.webm" type="video/webm"></video>
    		<source src="images/sb1.ogg" type="video/ogg"></video>
    		<source src="images/sb1.mp4" type="video/mp4"></video>
    	</video>
    </body>
    </html>
    ```
    
    **`audio`属性**
    - `video`中能够使用的属性大部分在`audio`中都能够使用，并且功能都差不多。
    - 且每种浏览器支持的音频格式也都不尽一样。
    - 因此和`viedo`一样，需要使用`source`标签。
    - 三种音频格式：`ogg` `mp3` `wav`
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    	<title></title>
    </head>
    <body>
    	<video>
    		<source src="images/yinyue.webm" type="video/webm"></video>
    		<source src="images/yinyue.ogg" type="video/ogg"></video>
    		<source src="images/yinyue.mp4" type="video/mp4"></video>
    	</video>
    </body>
    </html>
    ```
    - `height`/`width`/`poster`属性不能再`audio`中使用
    
    
    **`marquee`标签**
    - 设置跑马灯效果，让文字或图片自行滚动。
    - 通过局部属性`direction`控制滚动方向。
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    	<meta charset="utf-8" />
    	<title></title>
    </head>
    <body>
    	<marquee direction="right">
    		随便写点内容
    	</marquee>
    	<marquee direction="left">
    		随便写点内容
    	</marquee>
    	<marquee direction="up">
    		随便写点内容
    	</marquee>
    	<marquee direction="down">
    		随便写点内容
    	</marquee>
    </body>
    </html>
    ```
    
    ```html
    <!DOCTYPE HTML>
    <html>
    <head>
    	<meta charset="utf-8" />
    	<title></title>
    </head>
    <body>
    	<!-- direction局部属性控制滚动方向 -->
    	<marquee direction="right">
    		随便写点内容
    	</marquee>
    	<marquee direction="left">
    		随便写点内容
    	</marquee>
    	<marquee direction="up">
    		随便写点内容
    	</marquee>
    	<marquee direction="down">
    		随便写点内容
    	</marquee>
    	<hr/>
    	<!-- scrollamount局部属性控制滚动速度 -->
    	<marquee scrollamount="1">
    		随便写点内容
    	</marquee>
    	<hr/>
    	<!-- loop局部属性控制重复滚动次数，不设置则会无限重复 -->
    	<marquee loop="1">
    		随便写点内容
    	</marquee>
    	<hr/>
    	<!-- behavior局部属性设置滚动类型，为slide时，滚动到边界就停止，为alternate时，滚动到边界就会弹回 -->
    	<marquee behavior="slide">
    		随便写点内容
    	</marquee>
    	<marquee behavior="alternate">
    		随便写点内容
    	</marquee>
    </body>
    </html>
    ```
    

---
## CSS学习
> 属性和值用冒号分隔，每条样式后需要加分号
#### 使用class选择器设置标签样式
```
<!DOCTYPE html>
<html>
<head>
	<title>css学习第一次</title>
	<style type="text/css" media="screen">
		.title{
			color: red;
		}
	</style>
</head>
<body>
	<h2 class="title">This is H2!</h2>
	普通文本！
</body>
</html>
```
#### 使用id选择器调整标签样式
> id的值一个页面中不能有重复的，必须都是唯一的
```html
<!DOCTYPE html>
<html>
<head>
	<title>css学习第一次</title>
	<style type="text/css" media="screen">
		#title{
			color: green;
		}
	</style>
</head>
<body>
	<h2 class="title">This is H2!</h2>
	普通文本！
	<p id="title">这是一个段落标签，调整样式</p>
</body>
</html>
```
#### 元素选择器
> 直接使用元素命名的选择器，调整当前页面的所有同名标签的样式
```
<!DOCTYPE html>
<html>
<head>
	<title>css学习第一次</title>
	<style type="text/css" media="screen">

		h1{
			color:white;
			background-color: orange; 
		}
	</style>
</head>
<body>
	<h2 class="title">This is H2!</h2>
	普通文本！
	<p id="title">这是一个段落标签，调整样式</p>
	<h1>This is H1!</h1>
</body>
</html>
```
#### CSS选择器权重值：

    ID选择器>class选择器>元素选择器
 ```
 <!DOCTYPE html>
<html>
<head>
	<title>css学习第一次</title>
	<style type="text/css" media="screen">
		.title {
			color: red;
		}

		#title{
			color: green;
		}

		p {

		}
	</style>
</head>
<body>
	<p id="title" class="title">这是一个段落标签，调整样式</p>
	<h1>This is H1!</h1>
</body>
</html>
 ```

####  子代选择器/后代选择器/派生选择器
```
<!DOCTYPE html>
<html>
<head>
	<title>css学习第一次</title>
	<style type="text/css" media="screen">

		.list li {
			color: blue;
		}
		/*选中class=list下面的子标签<li>，这种选择器叫做：子代选择器/后代选择器/派生选择器*/

		.list .seconds {
			color: red;
		}

		li {
			color: #740BC4 !important;
		}
		/*如果有!important标注，则说明该选择器优先于id选择器*/

	</style>
</head>
<body>
	<p id="title" class="title">这是一个段落标签，调整样式</p>
	<h1>This is H1!</h1>

	<ul class="list">
		<li>111</li>
		<li class="seconds">222</li>
		<li>333</li>
	</ul>

</body>
</html>
```
> 说明：如果有!important标注，则说明该选择器优先于id选择器
#### 行内样式
- 标签里的style样式

#### 使用link标签引用样式 
- 通过`href`属性指定css文件
```
<!DOCTYPE html>
<html>
<head>
	<title>css学习第二次</title>

	<link rel="stylesheet" type="text/css" href="css_study_2.css">
</head>
<body>
	<ul class="seconds">
		<li>444</li>
		<li>555</li>
		<li>666</li>
	</ul>

</body>
</html>
```

---

### 文字样式

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>css学习 第二次</title>
	<style type="text/css" media="screen">
		#letter {
			/*字符间距*/
			letter-spacing: 10px;

			/*行间距*/
			line-height: 100px;

			/**/

		}

		.spacing {
			/*代表一个空格表示的间距长度，主要用于英语等其他语言*/
			word-spacing: 10px;
		}

		.align {
			/*文本对齐方式：左对齐，右对齐，居中*/
			/*left/right/center*/
			text-align: right;
		}

		.indent {
			/*文本首行缩进：一个汉字=16px*/
			/*文字最小不能小于12px*/
			/*
				单位：
				px：像素
				%：相对于body根文字的大小的%
				em：相对单位，1em = 当前文字的大小
				rem：body文字的大小
			*/
			text-indent: 32px;
		}
	</style>
	<!-- <link rel="stylesheet" type="text/css" href="css_study_2.css"> -->
	<!-- 一般样式都使用link标签引用css文件 -->
</head>
<body>
	<p>
		this is p!
	</p>
	<p id="letter">
		美媒指出，疫情反而凸显了中国产业链完整和劳动力人才储备的重要性。由于后疫情时代必然出现的经济衰退，更多企业出于成本和市场考量，很可能会扩大在华产业链，而不是相反。
	</p>
	<p class="spacing">
		The us media pointed out that the epidemic has highlighted the importance of China's industrial chain integrity and labor and talent reserve. Due to the inevitable economic recession in the post-epidemic era, more companies are likely to expand their industrial chain in China for cost and market reasons, rather than the other way around.
	</p>
	<p class="align">
		美媒指出，疫情反而凸显了中国产业链完整和劳动力人才储备的重要性。由于后疫情时代必然出现的经济衰退，更多企业出于成本和市场考量，很可能会扩大在华产业链，而不是相反。
	</p>
	<p class="indent">
		美媒指出，疫情反而凸显了中国产业链完整和劳动力人才储备的重要性。由于后疫情时代必然出现的经济衰退，更多企业出于成本和市场考量，很可能会扩大在华产业链，而不是相反。
	</p>
</body>
</html>
```
#### 文本装饰
```
<!DOCTYPE html>
<html>
<head>
	<title>css_study_4</title>
	<style type="text/css" media="screen">
		.underline {
			/*下划线*/
			text-decoration: underline;

			/*上划线*/
			text-decoration: overline;

			/*中划线*/
			text-decoration: line-through;
		}

		#a {
			/*消除下划线*/
			text-decoration: none;
		}

		.none1 li{
			list-style: none;
		}
	</style>
</head>
<body>
	<p class="underline">
		绝对零度 [1]  （absolute zero），是热力学的最低温度，但只是理论上的下限值。热力学温标的单位是开尔文（K），绝对零度就是开尔文温度标（简称开氏温度标，记为K）定义的零点。0K约等于摄氏温标零下273.15摄氏度，也就是0开氏度，在此温度下，物体分子没有动能和势能，动势能为0，故此时物体内能为0。物质的温度取决于其内原子、分子等粒子的动能。根据麦克斯韦-玻尔兹曼分布，粒子平均动能越大，物质温度就越高。理论上，若粒子平均动能低到量子力学的最低点时，物质即达到绝对零度，不能再低。然而，绝对零度是不可能达到的最低温度，自然界的温度只能无限逼近。如果到达，那么一切事物都将达到运动的最低形式。因为任何空间必然存有能量和热量，也不断进行相互转换而不消失。所以绝对零度是不存在的，除非该空间自始即无任何能量热量。在绝对零度下，原子和分子拥有量子理论允许的最小能量。
	</p>


	<!-- 消除下列标签自带的内容：下划线和圆点 -->
	<a id="a" href="mailto:joe@example.com?subject=feedback" "email me">email me</a>

	<ul class="none1">
		<li>111</li>
		<li>222</li>
		<li>333</li>
	</ul>
</body>
</html>
```
#### 字体风格
```
<!DOCTYPE html>
<html>
<head>
	<title>css_study_5</title>
	<style type="text/css">
		.zero {
			/*字体大小：使用偶数，不要使用奇数*/
			font-size: 12px;
			font-family: "思源黑体";

			/*字体风格：倾斜*/
			font-style: italic;

			/*文字加粗：
			100-900
			默认值：normal = 400
					bold = 700
				*/
			font-weight: bold;

		}
	</style>
</head>
<body>
	<p class="zero">
		开尔文（Kelvins），为热力学温标或称绝对温标，是国际单位制中的温度单位。 [1]  开尔文温度常用符号K表示，其单位为开。
每变化1K相当于变化1℃，计算起点不同。摄氏度以冰水混合物的温度为起点，而开尔文是以绝对零度作为计算起点，即-273.15℃=0K。开尔文过去也曾称为绝对温度。水的三相点温度为0.0076℃，也可以说开尔文是将水三相点的温度定义为273.16K后所得到的温度。2019年5月20日起，1开尔文被定义为“对应玻尔兹曼常数 [2]  为1.380649×10^-23J·K^-1的热力学温度”。
	</p>
</body>
</html>
```
#### 背景样式
```
<!DOCTYPE html>
<html>
<head>
	<title>背景样式</title>
	<style type="text/css" media="screen">
		
		.box1 {
			background-color: skyblue;
			width: 500px;
			height: 500px;

			/*背景图片*/
			background-image: url(https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1590683421616&di=0cabfb387c8023a832fa6f15e0cae49c&imgtype=0&src=http%3A%2F%2Fpic.baike.soso.com%2Fp%2F20120912%2Fbki-20120912223936-1706712065.jpg);

			/*背景图片是否重复*/
			background-repeat: no-repeat;

			/*图片位移*/
			background-position: 0 0; 

			/*图片占背景中的大小*/
			background-size: cover;
			/*cover代表平铺在背景*/
		}
	</style>
</head>
<body>
	789
	<div class="box1">
		123
	</div>
	456
	
</body>
</html>
```
#### DIV概述
- 块级元素：前后元素会被换行的元素。
> `h` `p` `div` `li` `ol` `ul` `form` `body` `html`
- 内联元素：不会被换行。
> `a` `b` `u` `i` `strong` `input`……
> 只有左右方向的外边距
##### 外边距：元素与元素之间的距离(上下左右四个方向距离边界的距离)
```
<!DOCTYPE html>
<html>
<head>
	<title>DIV</title>
	<style type="text/css" media="screen">
		.box1 {
			background: skyblue;
			height: 250px;
			/*width: 150px;*/
			margin-top: 20px; /* 上外边距 */
			margin-right: 20px; /* 右侧外边距只有在div没有设置宽度的时候才会起作用 */
			margin-left: 20px; /* 左外边距 */
			margin-bottom: 20px; /* 下外边距 */
		}

		.box2 {
			background: red;
			height: 100px;
			width: 80px;
		}

		.icon {
			margin-top:20px;
			margin-left: 20px;
			/*margin的简写方式：margin: 0 0 0 0 方向顺序：上右下左，参数为auto时，代表自适应，可以用来居中*/
		}
	</style>
</head>
<body>
	<!--  -->
	<div class="box1">
		<!-- 
		1. 会根据div中的内容自动缩进，自动将盒子宽度拉伸到最大
		2. 默认高度为0，可以有子元素将父元素高度撑起来
		3. 和h标签类似，前后元素会被换行
		p元素中不能容纳块级元素（前后元素会被换行的元素）
		 -->
		<b>This is B</b><br>
		this is other text

	</div>
	<div class="box2">
		
	</div>
	<i class="icon">123456</i>
</body>
</html>
```
#### 内边距
```
<!DOCTYPE html>
<html>
<head>
	<title>内边距</title>
	<style type="text/css" media="screen">
		.box1 {
			background: skyblue;
			height: 150px;
			width: 150px;

			/*内边距*/
			padding-left: 10px;
			padding-top: 10px;
			padding-bottom: 10px;
			padding-right: 10px;

			/*边框*/
			border-width: 5px;
			border-color: red;
			border-style: solid;

			border-left-width: 20px;
			/*点状边框*/
			border-right-style: dotted;
			/*虚线边框*/
			border-bottom-style: dashed;
			/*双线边框*/
			border-top-style: double;

		}
	</style>
</head>
<body>

	<div class="box1">
		12345678
	</div>

</body>
</html>
```

#### 边距重合
- 1. 主要是2个div的上下边距重合
- 2. 父元素和子元素的边距重合
> 主要使用添加属性`overflow: hidden`
```
<!DOCTYPE html>
<html>
<head>
	<title>边距重合</title>
	<style type="text/css" media="screen">
		.box1 {
			height: 150px;
			width: 150px;
			background: skyblue;
			margin-bottom: 30px;
		}
		.box2 {
			height: 150px;
			width: 150px;
			background: green;
			margin-top: 40px;
		}
		.box3 {
			height: 200px;
			width: 200px;
			background: green;
			margin-top: 40px;
			border: 1px solid transparent;
		}
		.box4 {
			height: 120px;
			width: 120px;
			background: orange;
			margin-top: 40px;
			border: 1px solid transparent;
		}
		.parent {
			/*border: 1px solid transparent; 解决边距重合的方式1*/
			overflow:hidden;
			/*解决边距重合的方式2*/
		}
	</style>
</head>
<body>
	<div class="box1">
		
	</div>
	<div class="parent">
		<div class="box2"></div>
	</div>
	<div class="box3">
		<div class="box4"></div>
	</div>
</body>
</html>
```
#### 浮动
- 浮动
> 主要作用于将盒子div横向排列
```
<!DOCTYPE html>
<html>
<head>
	<title>浮动2</title>
	<style type="text/css" media="screen">

		.box1 {
			background-color: skyblue;
			height: 300px;
			width: 100px;
			float: left;
		}

		.box2 {
			background-color: orange;
			height: 300px;
			width: 300px;
			float: left;
			margin: auto;
		}

		.wrap {
			/*background-color: green; */
			height: 900px;
			margin: auto;
			/*border-color: 5px solid red;*/
		}
/*		.clear {
			clear: both;
		}*/
	</style>
</head>
<body>
	<div class="wrap">

		<div class="box1"></div>
		<div class="box2"></div>
		<!-- <div class="clear"></div> -->
	</div>
</body>
</html>
```
> 清理浮动
- 1. 在同级中新增一个盒子，并添加属性`clear: both`
- 2. 在父级元素中添加属性`overflow: hidden`
```
<!DOCTYPE html>
<html>
<head>
	<title>浮动2</title>
	<style type="text/css" media="screen">

		.box1 {
			background-color: skyblue;
			height: 300px;
			width: 100px;
			float: left;
		}

		.box2 {
			background-color: orange;
			height: 300px;
			width: 300px;
			float: left;	
			margin: auto;
		}

		.wrap {
			/*background-color: green; */
			height: 900px;
			margin: auto;
			/*border-color: 5px solid red;*/
		}
/*		.clear {
			clear: both;
		}*/
	</style>
</head>
<body>
	<div class="wrap">

		<div class="box1"></div>
		<div class="box2"></div>
		<!-- <div class="clear"></div> -->
	</div>
</body>
</html>
```
#### CSS重置布局
- `reset css`
> 不同浏览器的默认样式有所不同，所以需要初始化布局，好统一不同的浏览器的初始样式。

#### 定位
> 将元素摆放在任意位置，且不影响其他元素的排列
##### 相对定位
- `position: relative`
- 所有可以相对定位的属性都有属性`top`,`bottom`, `left`,`right`，但是四个方向只能同时有2个方式可以使用，例如：上和左，下和右。
- 盒子移动之后，原来的位置依然会被占据
- 从原始位置开始移动
##### 绝对定位
- `position: absolute`
> 不占据任何空间，“比任何元素漂浮的都要高”

> 相对于定位父级（除了static以外的父级元素）进行移动节点进行移动
##### 固定定位
- `position: fixed`
> 不占据任何空间

> 以浏览器作为参考进行移动

> 始终固定在浏览器窗口中的某个位置，移动滚动条时，不会随着移动。
- 常用案例：论坛右侧，返回顶部，插播广告
```
<!DOCTYPE html>
<html>
<head>
	<title>固定定位</title>
	<style type="text/css" media="screen">
		
		.box1 {
			width: 400px;
			height: 300px;
			background: red;
			float: left;
		}

		.box2 {
			width: 200px;
			height: 300px;
			background: pink;
			float: right;
		}

		.wrap {
			width: 620px;
			height: 300px;
			margin-left: auto;
			margin-right: auto;
			border: 1px solid blue; 

		}

		.f-box {
			width: 40px;
			height: 40px;
			background-color: skyblue;
			float: right;
			left: 50%;
			bottom: 10px;
			margin-left: 400px;
			margin-right: 10px;
			position: fixed;
		}

		body {
			height: 2000px;
		}
	</style>
</head>
<body>
	<div class="wrap">

	<div class="box1"></div>
	<div class="box2"></div>
	<div class="box3"></div>
		
	</div>

	<div class="f-box">
		<a href="javascript: scroll(0,0)">
			<img src="C:\Users\kxd18\Desktop\箭头.png" alt="" height="40px" width="40px">
		</a>
	</div>
</body>
</html>
```
#### `z-index`层级关系
- `z-index：整数`
> 只针对于`static`以外的定位元素

> 值越高，显示越靠上，如果相同，则按顺序覆盖

#### banner轮播图
```
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>banner轮播图</title>
	<style type="text/css">
		
		* {
			margin: 0;
			padding: 0;
		}
		.banner-wrap {
			width: 616px;
			height: 232.2px;
			position: relative;
			margin: auto;
			margin-top: 50px;
		}

		li {
			list-style: none;
		}

		a {
			text-decoration: none; 
		}

		.img-box {
			width: 616px;
			height: 232.2px;
		}

		.img-box img {
			position: absolute;
		}

		.previous, .next {
			/*width: 30px;
			height: 30px;
			background-color: #909090;*/
			/*line-height: 30px;*/
			position: absolute;
			color: weight;
			top: 50%;
			z-index: 5;
			margin-top: -20px;
		}

		.previous {
			left: 5px;
		}

		.next {
			right: 5px;
		}

		.btn {
			position: absolute;
			bottom: 8px;
			z-index: 9;
			left: 50%;
			margin-left: -44px;
		}

		.btn li {
			width: 16px;
			height: 16px;
			background-color: #fff;
			float: left;
			margin-left: 8px;
			color: #bfbfbf;
			border-radius: 50%;
			cursor: pointer;
		}

		.btn .on {
			background-color: orange;
		}
	</style>
</head>
<body>
	<div class="banner-wrap">
		
		<div class="img-box">
			<!-- 图 -->
			<img src="C:\Users\kxd18\Desktop\banner\1.jpg" alt="" height="232.2" width="616" style="z-index: 1">
			<img src="C:\Users\kxd18\Desktop\banner\2.jpg" alt="" height="232.2" width="616">
			<img src="C:\Users\kxd18\Desktop\banner\3.jpg" alt="" height="232.2" width="616" >
			
		</div>

		<div class="paging">
			<!-- 左右两侧的耳朵 -->
			<div class="previous">
				<a href="javascript: void(0)">
					<img src="C:\Users\kxd18\Desktop\左箭头.png" alt="" width="40" height="40">
				</a>
			</div>
			<div class="next">
				<a href="javascript: void(0)">
					<img src="C:\Users\kxd18\Desktop\右箭头.png" alt="" width="40" height="40">
				</a>
			</div>
		</div>

		<ul class="btn">
			<!-- 下方圆点 -->
			<li class="on"></li>
			<li></li>
			<li></li>
		</ul>
		
	</div>
</body>
</html>
```
#### CSS元素类型，div回顾

##### `div`盒子
1. 默认占据一行
2. 高度默认为0，

##### CSS元素类型
1. 块级元素
    > 前后元素会被换行
    
    > 使用了脱离正常文档流的样式
2. 内联元素
    
    > 在一行的元素，前后元素不会被换行，且无法设置宽高和上下外边距
3. 内联块
    > 在一行的元素，除了占据一行，没有任何特质
    
#### `text-align` 
- 可以居中块级元素中的内联元素，内联块，文本

#### 文本线框
> 基线是文本下侧靠着的那条线
- 通过参数vertical-algin调整基线的位置
```
<!DOCTYPE html>
<html>
<head>
	<title>文本线框</title>
	<style type="text/css" media="screen">
		.box {
			background-color: red;
			vertical-align: bottom;
			/**/
		}
	</style>
</head>
<body>

	<div class="box">
		<img src="C:\Users\kxd18\Desktop\1.jpeg" alt="">
	</div>

</body>
</html>
```
#### `overflow`溢出
- `overflow:auto`，如果盒子里面有文本，且文本超出了盒子本身的高度，会自动添加一个纵向滚动条
> 其他参数还有：`hiden` `bottom`等
```
<!DOCTYPE html>
<html>
<head>
	<title>文本线框</title>
	<style type="text/css" media="screen">
		.box {
			background-color: red;
			width: 200px;
			height: 200px;
			overflow: auto; /*  文本超出后会自动添加纵向滚动条 */
		}
		.box1 {
			background-color: skyblue;
			width: 100px;
			height: 150px;
			margin-top: 10px;
		}
	</style>
</head>
<body>

	<div class="box">
		中新经纬客户端6月16日电 6月16日，最高人民法院发布《关于依法妥善审理涉新冠肺炎疫情民事案件若干问题的指导意见(三)》(以下简称《意见》)。最高人民法院民四庭庭长王淑梅称，最高法对国际海上货物运输的承运人可能遇到的问题作出了充分梳理，既要充分考虑防疫措施的合理性，又要考虑各方当事人之间的利益平衡，努力统筹好疫情防控和经济社会发展的需要。
		<div class="box1"></div>
	</div>

</body>
</html>
```
#### 透明及颜色转换
> opacity: 50%  调整透明度
- 会同时调整子元素的透明度

> background: rgba(r,g,b,a)
- a: 0-1 用来调整透明度
- 只等对于颜色本身，不会影响子元素
```
<!DOCTYPE html>
<html>
<head>
	<title>透明及颜色转换</title>
	<style type="text/css" media="screen">
		.box {
			background-color: pink;
			height: 300px;
			overflow: auto; /*  文本超出后会自动添加纵向滚动条 */
			opacity: 30%;
			/*R G B A*/
			background: rgb(1,2,3); /* 颜色转换 0-255 */
			
			/*16进制*/
			/*background: #21D24C;*/
		}
		.box1 {
			background-color: skyblue;
			width: 100px;
			height: 150px;
			margin-top: 10px;
		}
	</style>
</head>
<body>

	<div class="box">
		<img src="C:\Users\kxd18\Desktop\22.jpg" alt="">

	</div>

</body>
</html>
```
#### shadow阴影
```
<!DOCTYPE html>
<html>
<head>
	<title>透明及颜色转换</title>
	<style type="text/css" media="screen">
		.box {
			height: 300px;
			width: 300px;
			/*R G B A*/
			background: rgba(12,244,3,1); /* 颜色转换 0-255 */
			margin-top: 100px;
			margin-bottom: 10px;
			box-shadow: inset 5px 5px 5px #ff00cc
			/*inset:表示设置内阴影，参数1:横向方向，参数2：纵向方向，参数3：虚化程度，参数4：颜色，参数5：背景大小*/
		}
		.text {
			text-shadow: 5px 1px 5px #ff00cc;
		}
	</style>
</head>
<body>

	<div class="box">
		
	</div>
	<span class="text">同学们，你们好！this is span！</span>

</body>
</html>
```
#### selector 选择器
```
<!DOCTYPE html>
<html>
<head>
	<title>CSS selector选择器</title>

	<style type="text/css">
		
		.list li:first-child {
			font-size: 19px;
			background-color: orange;
		}
		/*first-child 第一个子元素，last-child 最后一个子元素*/

		.list li:nth-child(3) {
			background-color: red;
		}
		/*
		nth-child(3) 选择正数第三个子元素 nth-last-child(2) 选择倒数第二个子元素
		*/

		.box div:not(.box2) {
			width: 15px;
			height: 15px;
			background-color: pink;
			margin-bottom: 10px;
		}
		/*:not() 除了某个元素之外的其他元素*/
	</style>
</head>
<body>
	<div class="box">
		<div class="box1"></div>
		<div class="box1"></div>
		<div class="box1"></div>
		<div class="box2"></div>
	</div>
	<ul class="list">
		<li>2</li>
		<li>3</li>
		<li>4</li>
		<li>5</li>
		<li>6</li>
	</ul>

</body>
</html>
```
#### 锚伪类
- 样式必须按照顺序排序
> link > visited > hover > active

##### `hover`
```
<!DOCTYPE html>
<html>
<head>
	<title>锚伪类</title>
	<style type="text/css" media="screen">
		* {
			margin:0;
			padding: 0;
		}

		/*访问链接之前的样式*/
		.a1:link {
			color: blue;
		}

		/*访问链接过后的样式*/
		.a1:visited {
			color: green;

		}

		/*鼠标选中的样式*/
		.a1:hover {
			background-color: orange;
			color: white;
		}

		/*鼠标点击后的样式*/
		.al:active {
			background-color: pink;
			color: red;
		}

		.box {
			width: 300px;
			height: 300px;
			background-color: skyblue;
		}

		.box:hover {
			background-color: blue;
		}

		.nav {
			width: 300px;
			height: 600px;
			/*background-color: pink;*/
			border-color: red;
			border-width: 5px;
			border-style: solid;
			text-align: center;
			position: relative;
		}

		.list {
			display: none;
		}

		.item {
			background-color: pink;

		}

		/*hover 后面只能跟子元素*/
		.item:hover .list {
			background-color: skyblue;
			position: absolute;
			left: 300px;
			top: 0px;
			height: 40px;
			width: 100px;
			display: block;
			/*display: block 以块的形式显示子元素的内容*/
		}
	</style>
</head>
<body>
	<a href="https://www.qq.com" title="" class="a1">跳转到QQ</a>
	<div class="box"></div>
	<div class="nav">
		<div class="item">
			1
			<div class="list">2</div>
			
		</div>

		<div class="item">
			a
			<div class="list">b</div>
			
		</div>
		
	</div>

</body>
</html>
```
#### 显示隐藏元素
> `display: none`
- 完全隐藏，不占空间
> `visibility: hidden`
- 隐藏并且占空间

#### `border-radius`圆角
```
<!DOCTYPE html>
<html>
<head>
	<title>border-radius圆角</title>
	<style type="text/css" media="screen">
		
        .box {
        	width: 300px;
        	height: 300px;
        	background-color: pink;
        	margin: auto;
        	margin-top: 100px;

        	/*调整4个角，也可以用百分比：0%-100%*/
        	border-radius: 10px 10px 10px 10px;

        }

	</style>
</head>
<body>
	<div class="box">
		
	</div>
</body>
</html>
```
#### 伪类
```html
<!DOCTYPE html>
<html>
<head>
	<title>border-radius圆角</title>
	<style type="text/css" media="screen">
		
                * {
                        margin: 0;
                        padding: 0;
                }

                li {
                        list-style: none;
                        /*取消默认样式中的圆点*/
                }

                a {
                        text-decoration: none;
                        /*取消默认样式下划线*/
                }

                .list li {
                        float: left;
                        width: 125px;
                        background-color: orange;
                        text-align: center;
                        color: white;
                        margin-left: 20px;
                }

                .list li:after {
                        content: "asdadada"; 
                        /* 在每一个li标签的内容后面添加内容 */
                        /*center必须要写，即使其中不写内容*/
                }

                .list li:before {
                        /* 在每一个li标签的内容前面添加内容 */
                        /*center必须要写，即使其中不写内容*/
                        content: "";
                        position: absolute;
                        border-radius: 0px 50% 50% 0px;
                        width: 10px;
                        height: 10px;
                        background-color: red;
                }

	</style>
</head>
<body>
	<ul class="list">
                <li>1</li>
                <li>2</li>
                <li>3</li>
        </ul>
</body>
</html>
```