### 闭包 ———— 可以访问另一个函数作用域内的函数。
1. 基础闭包,其中cc（）就是闭包函数
```
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<meta http-equiv="Cache-Control" content="max-age = 7200" />
<title>无标题文档</title>
</head>
<body>
<script>
var name = "aa";
function bb(){
	var name = "bb"
	function cc(){
		console.log(name)	
	}
	cc();
}

bb()
</script>
</body>
</html>
```
2. 闭包的缺点，
