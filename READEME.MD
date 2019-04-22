# Java​Script 第一步
目录
* [什么是JavaScript](#什么是JavaScript)
* [JavaScript疑难解答](#JavaScript疑难解答)
* [变量](#变量)
* [数字和操作符](#数字和操作符)
* [文字处理](#文字处理)
* [实用字符串方法](#实用字符串方法)
* [数组](#数组)

## 什么是JavaScript
广义的定义：JavaScript 是一种脚本，一门编程语言。<br>
它可以做什么：
1. 在变量中储存有用的值。
2. 操作一段文本（在编程中称为“字符串”（string））。
3. 运行代码以响应网页中发生的特定事件。
4. 应用程序接口（Application Programming Interfaces（API））API 是已经建立好的一套代码组件，可以让开发者实现原本很难甚至无法实现的程序。
## JavaScript疑难解答
错误类型<br> 
1. 语法错误：
2. 逻辑错误：

## 变量
1. 变量是用于存放数值的容器<br>
2. 声明变量:
`var myName;`
`var myAge;`
3. 初始化变量
`html myName = 'Chris';`
`myAge = 37;` 
`var myName = 'Chris';`

4. 变量命名的规则
* 变量名不要以下划线开头
* 变量名不要以数字开头
* 小写整个命名的第一个字母然后大写剩下单词的首字符
* 让变量名直观，它们描述了所包含的数据。
* 变量名大小写敏感
* 避免使用JavaScript的保留字给变量命名
<br>

5.变量类型: 
`Number` `String` `Boolean` `Array` `Object`


## 数字和操作符

数字类型<br>
1. 整数 就是整数,例如 10, 400, 或者 -5.
2. 浮点数 (浮点) 有小数点或小数位，例如 12.5，和 56.7786543。
3. 双精度双精度是一种特定类型的浮点数，它们具有比标准浮点数更高的精度（这意味着它们精确到更大的小数位数）。
4. 二进制 — 计算机的最基础语言; 0s and 1s
5. 八进制 - 基数8，每列使用0-7
6. 十六进制 - 基数16，每列使用0-9，然后使用a-f。 在CSS中设置颜色时，可能会遇到这些数字。

算数运算符
```
运算符	名称	作用	
+	    加法	两个数相加。	
-	    减法	从左边减去右边的数。	
*	    乘法	两个数相乘。	
/	    除法	用右边的数除左边的数	
%	    求余(有时候也叫取模)	在你将左边的数分成同右边数字相同的若干整数部分后，返回剩下的余数
```

递增和递减运算符<br>
* 反复添加或从数字变量值中减去一个。 使用增量`++`和递减`--`运算符来完成。

操作运算符
```
运算符	      名称	       作用	                         示例	              等价于
+=	递增赋值	右边的数值加上左边的变量，然后再返回新的变量。	x = 3;   x += 4;	x = 3;  x = x + 4;
-=	递减赋值	左边的变量减去右边的数值，然后再返回新的变量。	x = 6;   x -= 3;	x = 6;  x = x - 3;
*=	乘法赋值	左边的变量乘以右边的数值，然后再返回新的变量。	x = 2;   x *= 3;	x = 2;  x = x * 3;
/=	除法赋值	左边的变量除以右边的数值，然后再返回新的变量。	x = 10;  x /= 5;	x = 10;  x = x / 5;
```

比较运算符
```
运算符	名称	作用	示例
===	   严格等于	        测试左右值是否相同	            5 === 2 + 4
!==  	 严格不等于	     测试左右值是否相同	            5 !== 2 + 3
<	     小于	            测试左值是否小于右值。     	  10 < 6
>	     大于	            测试左值是否大于右值	         10 > 20
<=	   小于或等于	      测试左值是否小于或等于右值。	  3 <= 2
>=	   大于或等于	     测试左值是否大于或等于正确值。	  5 >= 4
```

## 文字处理
创建一个字符串
```
var string = 'The revolution will not be televised.';
string;
```
单引号和双引号`' '`  `" "` 同义，选择一种<br>
[转义字符串中的字符](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Escape_notation)<br>
连接字符串
```
var one = 'Hello, ';
var two = 'how are you?';
var joined = one + two;
joined;
```
上下文中的串联
``` html
<button>Press me</button>
```
```javascript
var button = document.querySelector('button');

button.onclick = function() {
  var name = prompt('What is your name?');
  alert('Hello ' + name + ', nice to see you!');
}
```


## 实用字符串方法
把字符串当作对象:在javascript中，一切东西都可以被当作对象。
获得字符串的长度 
```javascript
var browserType = 'mozilla';
browserType.length;  
// 7
```
检索特定字符串字符
```javascript
browserType[0];
browserType[browserType.length-1];
```
在字符串中查找子字符串并提取它 
- indexOf()方法
```javascript
browserType.indexOf('zilla');  // 2

browserType.indexOf('vanilla'); // -1 主字符串中找不到子字符串
```
- 您可以使用它来查找不包含子串“mozilla”的所有字符串实例，或者如果使用否定运算符，请执行以下操作。
```javascript
if(browserType.indexOf('mozilla') !== -1) {
  // do stuff with the string
}
```
- 当你知道字符串中的子字符串开始的位置，以及想要结束的字符时，slice()可以用来提取 它。 尝试以下：
```javascript
browserType.slice(0,3); // moz
```
- 此外，如果您知道要在某个字符之后提取字符串中的所有剩余字符，则不必包含第二个参数，而只需要包含要从中提取的字符位置 字符串中的其余字符。
```javascript
browserType.slice(2);  ///返回“zilla”
```
转换大小写
```javascript
var radData = 'My NaMe Is MuD';
radData.toLowerCase();        
//  "my name is mud"
radData.toUpperCase();
//"MY NAME IS MUD"
```
替换字符串的某部分
```javascript
var browserType = 'mozilla';
browserType.replace('moz','van');
//"vanilla"
```

## 数组
数组是一个包含了多个值的对象。
```javascript
//创建数组
var shopping = ['bread', 'milk', 'cheese', 'hummus', 'noodles'];
shopping;
var random = ['tree', 795, [0, 1, 2]];
//访问和修改数组元素
shopping[0];
// returns "bread"
shopping[0] = 'tahini';
shopping;
// shopping will now return [ "tahini", "milk", "cheese", "hummus", "noodles" ]
random[2][2];
//获取数组长度
sequence.length;
// should return 7
//虽然 length 属性也有其他用途，但最常用于循环（循环遍历数组中的所有项）。 例如：

var sequence = [1, 1, 2, 3, 5, 8, 13];
for (var i = 0; i < sequence.length; i++) {
  console.log(sequence[i]);
}
```
一些有用的数组方法
字符串和数组之间的转换
```javascript
var myData = 'Manchester,London,Liverpool,Birmingham,Leeds,Carlisle';
var myArray = myData.split(',');
myArray;

myArray.length;
myArray[0]; // the first item in the array
myArray[1]; // the second item in the array
myArray[myArray.length-1]; // the last item in the array

使用 join() 方法进行相反的操作。 尝试以下：
var myNewString = myArray.join(',');
myNewString;

数组转换为字符串的另一种方法是使用 toString() 方法。
var dogNames = ["Rocket","Flash","Bella","Slugger"];
dogNames.toString(); //Rocket,Flash,Bella,Slugger
```
添加和删除数组项
```javascript
var myArray = ['Manchester', 'London', 'Liverpool', 'Birmingham', 'Leeds', 'Carlisle'];
 push() 
 myArray.push('Cardiff');  //7
myArray;   // (7) ["Manchester", "London", "Liverpool", "Birmingham", "Leeds", "Carlisle", "Cardiff"]
myArray.push('Bradford', 'Brighton');
myArray;  //["Manchester", "London", "Liverpool", "Birmingham", "Leeds", "Carlisle", "Cardiff", "Bradford", "Brighton"]
var newLength = myArray.push('Bristol');
myArray; //["Manchester", "London", "Liverpool", "Birmingham", "Leeds", "Carlisle", "Cardiff", "Bradford", "Brighton", "Bristol"]
newLength;  //10
 pop()
 myArray.pop();
 var removedItem = myArray.pop();
myArray;
removedItem;

unshift() 和 shift() 从功能上与 push() 和 pop() 完全相同，只是它们分别作用于数组的开始，而不是结尾。

//首先 unshift()。尝试一下命令
myArray.unshift('Edinburgh');
myArray;
//现在 shift()。 尝试这些！
var removedItem = myArray.shift();
myArray;
removedItem;
```



