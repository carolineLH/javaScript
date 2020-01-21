# String类型

字符串可以由双引号(")或单引号(')表示，而且这两种语法形式没有什么区别。


#### 字符字面量

String数据类型包含一些特殊字符字面量，也叫转义序列，用于表示非打印字符，或者具有其他用途的字符
```js
字面量 | 含义
-|-
\n | 换行 |
\t | 制表 |
\b | 空格 |
\r | 回车 |
\f | 进纸 |
\\ | 斜杠 |
\' | 单引号（'），在用单引号表示的字符串中使用。例如：'He said, \'hey.\'' |
\" | 双引号（"），在用双引号表示的字符串中使用。例如："He said, \"hey.\"" |
\xnn | 以十六进制代码nn表示的一个字符（其中n为0～F）。例如，\x41表示"A" |
\unnnn | 以十六进制代码nnnn表示的一个Unicode字符（其中n为0～F）。例如，\u03a3表示希腊字符Σ |
```
这些字符字面量可以出现在字符串中的任意位置，而且也将被作为一个字符来解析。例如：
```js
var text = "This is the letter sigma: \u03a3."
alert(text.length); // 输出28
```
这个例子中的变量text有28个字符，其中6个字符长的转义序列表示1个字符。


#### 转换为字符串

要把一个值转换为一个字符串有两种方式。第一种是使用几乎每个值都有的toString()方法。

数值、布尔值、对象、和字符串值都有toString()方法。但null和undefined值没有这个方法。

toString()方法可以传递一个参数：输出数值的基数，只有数值才有。例如：
```js
var num = 10;
alert(num.toString()); // "10"
alert(num.toString(2)); // "1010"
alert(num.toString(8)); // "12"
alert(num.toString(10)); // "10"
alert(num.toString(16)); // "a"
```


在不知道要转换的值是不是null或undefined的情况下，还可以使用转型函数String(),这个函数能够将任何类型的值转换为字符串。
* 如果值有toString()方法，则调用该方法（没有参数）并返回相应的结果
* 如果值是null，则返回"null"
* 如果值是undefined，则返回"undefined"

```js
var value1 = 10;
var value2 = true;
var value3 = null;
var value4;

alert(String(value1));   // "10"
alert(String(value2));   // "true"
alert(String(value3));   // "null"
alert(String(value4));   // "undefined"
```

###### 要把某个值转换成字符串，可以使用加号操作符把它与一个字符串("")加在一起。