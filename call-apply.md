### call和apply函数
1. es5以下this一直指向的是调用的函数
```
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>无标题文档</title>
</head>

<body>
<script>
var name = "father";

var fn = {
	name:"child"	,
	fn1:function(){
		console.log(this.name)	
	},
	fn2:function(){
		setTimeout(function(){this.fn1()},0)	//报错，因为setTimeout函数的调用对象时window，但是window没有fn1
	}
}

fn.fn2()
</script>
</body>
</html>

```
2. apply（）———— fun.apply(thisArg, [argsArray])
1）thisArg改变fun运行时候的this指向，如果值为null 或 undefined则指向window对象，如果是数字，字符串，布尔值会指向该原始值的自动包装对象
2）argsArray一个数组或者类数组对象，传递给fun作为参数
```
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>无标题文档</title>
</head>
<body>
<script>
function people(name,age){
	this.name = name;
	this.age = age	
}
function student(name,age,grade){
	people.apply(this,arguments);
	this.grade = grade	
}
var student1 = new student("xxx","19","二年级")
console.log(student1.age,student1.name,student1.grade)
</script>
</body>
</html>
```
