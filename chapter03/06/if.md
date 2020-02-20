# if语句

大多数编程语言中最为常用的一个语句就是if语句。以下是if语句的语法：
```js
if (condition) statement1 else statement2
```
其中的condition（条件）可以是任意表达式，而且对这个表达式求值的结果不一定是布尔值。ECMAScript会自动调用Boolean()转换函数将这个表达式的结果转换为一个布尔值。

```js
if (i > 25)
alert("Greater than 25."); // 单行语句
else {
alert("Less than or equal to 25."); // 代码块中的语句
}

```

###### 业界普遍推崇的最佳实践是始终使用代码块