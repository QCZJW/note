# js疑难全解

### 关于for循环应当注意的作用域辨别

``` html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style>
			img {
				height: 100px;
				width: 150px;
				border: solid 5px white;
			}

			.side {
				display: inline-block;
			}

			#main {
				position: relative;
				height: 800px;
				width: 900px;
				top: 100px;
				margin: 0 auto;
			}

			body {
				background-image: url("images/1.webp");
			}

			.side_ {
				display: inline-block;
				border: solid 2px rebeccapurple;
			}
		</style>
	</head>
	<body id="temp">
		<div id="main">
			<div class="side"><img src="images/1.webp" alt=""></div>
			<div class="side"><img src="images/2.webp" alt=""></div>
			<div class="side"><img src="images/3.webp" alt=""></div>
			<div class="side"><img src="images/4.webp" alt=""></div>
			<div class="side"><img src="images/5.webp" alt=""></div>
		</div>
	</body>
	<script>
		var side = document.getElementsByClassName("side");
		for (var i = 0; i < side.length; i++) {
			side[i].onclick = function() {
				remove();
				this.className="side_"
				document.getElementById("temp").style.backgroundImage = "url(\"images/" + (i+1) + ".webp\")";
			}
		}
	</script>
</html>

```

以上代码会出现什么结果？答案是这个！

![image-20230508124740523](C:\Users\JW\AppData\Roaming\Typora\typora-user-images\image-20230508124740523.png)

原因是

> ​            当 onclick 函数被调用时，循环已经执行完毕，此时 i 的值是 side.length。
> ​			因此，当尝试访问 side[i] 时，会得到 undefined。
> ​			解决这个问题的方法是使用一个自执行函数或闭包来创建一个新的作用域，以便在每个迭代中保存 i 的值。

``` html
(function(index) {
				side[index].onclick = function() {
					remove();
					console.log(side[index])
					side[index].className = "side_";
					document.getElementById("temp").style.backgroundImage = "url(\"images/" + (index+1) + ".webp\")";
				};
			})(i);
```

# js小疑难案列

``` js
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>Document</title>
		<style>
			* {
				margin: 0;
				padding: 0;
			}

			body {
				padding: 100px;
			}

			textarea {
				width: 300px;
				height: 100px;
				border: 1px solid #ccc;
				outline: none;
				resize: none;
			}

			ul {
				margin-left: 70px;
				list-style: none;
			}

			li {
				width: 300px;
				padding: 5px;
				border-bottom: 1px dotted #ccc;
				font-size: 14px;
				/*将元素隐藏,方便等会使用特效显示出来*/
				display: none;
			}

			li a {
				margin-left: 10px;
			}
		</style>
	</head>
	<body>
		<div class="box">
			<span>发表留言</span>
			<textarea name="" class="txt" cols="30" rows="10"></textarea>
			<button class="btn">发布</button>
		</div>
		<ul></ul>

	</body>
	<script src="jquery-3.3.1.min.js"></script>
	<script>
		$("button").click(function() {
			var li = $("<li></li>")
			li.html($("textarea").val() + "  " + "<a href='javascript:void(0);'>删除</a>")
			/*
			必须增加JavaScript：void（0）；不增加那么a标签将先跳转再执行删除操作
			
			也可以用以下代码来阻止浏览器跳转
			event.preventDefault();
			*/

			$("ul").prepend(li)
			li.slideDown()
			$("textarea").val("")
		})
		/*注意下行的格式
		
		    使用 jQuery 的 .on() 函数为 <ul> 元素添加了一个事件委托监听器。当有 click 事件触发时，将检查要响应的事件目标元素是否是 a 标签（这里没有指定类名或 ID）。
		    如果源元素是 <a> 标签，就会执行函数。
		    在函数中，调用 $ (this) 选择当前被点击的链接元素，并使用 .parent() 方法找到该链接元素的父元素（即父级 <li> 元素）。然后使用 .slideUp() 方法向上收缩（逐渐隐藏）该父级元素，最后通过一个回调函数来解除该元素与 DOM 树之间的联系。
		
		*/
		$("ul").on("click", "a", function() {
			/*为了实现动画效果所以匹配的是a标签，可以直接匹配li标签来删除*/
			$(this).parent().slideUp(function() {
				$(this).remove()
			})
		})
	</script>
</html>

```

