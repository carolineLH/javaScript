# 理解参数

JavaScript中的参数在内部是用一个数组来表示的，在函数体内可以通过arguments对象来访问这个参数数组

arguments对象只是与数组类似（它并不是Array的实例），可使用length属性来确定传递进来多少个参数

arguments对象可以与命名参数一起使用：

```js
function doAdd(num1, num2) {
    if(arguments.length == 1) {
        alert(num1 + 10);
    } else if (arguments.length == 2) {
        alert(arguments[0] + num2);
    }
}
```

arguments的值永远与对应命名参数的值保持同步

```js
function doAdd(num1, num2) {
    arguments[1] = 10;
    alert(arguments[0] + num2);
}
```

**ECMAScript 中的所有参数传递的都是值，不可能通过引用传递参数**