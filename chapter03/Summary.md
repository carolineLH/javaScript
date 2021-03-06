# 小结

目前大多数实现所遵循的都是ECMA-262第3版，但很多也已经着手实现第5版了。以下简要总结了ECMAScript中基本的要素。

* ECMAScript中的基本数据类型包括Undefined、Null、Boolean、Number和String。
* 与其他语言不同，ECMAScript没有为整数和浮点数值分别定义不同个的数据类型，Number类型可用于表示所有数值。
* ECMAScript中也有一种复杂的数据类型，即object类型，该类型是这门语言中所有对象的基本类型。
* 严格模式为这门语言中容易出错的地方施加了限制。
* ECMAScript提供了很多与C及其他类C语言中相同的基本操作符，包括算术操作符、布尔操作符、关系操作符、相等操作符及赋值操作符等。
* ECMAScript从其他语言中借鉴了很多流控制语句，例如if语句、for语句和switch语句等。ECMAScript中的函数与其他语言中的函数有诸多不同之处。
* 无须指定函数的返回值，因为任何ECMAScript函数都可以在任何时候返回任何值。
* 实际上，未指定返回值的函数返回的是一个特殊的undefined值。
* ECMAScript中也没有返回函数签名的概念，因为其函数参数是以一个包含零或多个值的数组的形式传递的。
* 可以向ECMAScript函数传递任意数量的参数，并且可以通过arguments对象来访问这些参数。
* 由于不存在函数签名的特性，ECMAScript函数不能重载。