# Number类型


除了十进制表示外，证书还可以通过八进制（以8为基数）或十六进制（以16为基数）的字面值来表示。其中，八进制字面值的第一位必须是零（0），然后是八进制数字序列（0~7）。如果字面值中的数值超出了范围，那么前导零将被忽略，后面的数值将被当做十进制数值解析。
```js
var octalNum1 = 070; // 八进制的56
var octalNum2 = 079; // 无效的八进制数值——解析为79
var octalNum3 = 08; // 无效的八进制数值——解析为8
```
###### 八进制字面量在严格模式下是无效的，会导致支持的JavaScript引擎抛出错误。

十六进制字面量的前两位必须是0x，后跟任何十六进制数字（0~9及A~F）。其中，字母A~F可以大写，也可以小写。如下面的例子所示：
```js
var hexNum1 = 0xA; // 十六进制的10
var hexNum2 = 0x1f; // 十六进制的31
```
在进行算数计算时，所有以八进制和十六进制表示的数值最终都将被转换成十进制数值。


#### 浮点数值

所谓浮点数值，就是该数值中必须包含一个小数点，并且小数点后面必须至少有一位数字。

由于保存浮点数值需要的内存空间是保存整数值的两倍，因此ECMAScript会不失时机地将浮点数值转换为整数值。显然，如果小数点后面没有跟任何数字，那么这个数值就可以作为整数值来保存。

在默认情况下，ECMAScript会将那些小数点后面带有6个零以上的浮点数值转换为以e表示法表示的数值（例如：0.0000003会被转换成3e.7）。

IEEE754标准导致的误差：
```js
var sum=0.1+0.2
sum==0.3 //false sum=0.30000000000000004
```

#### 数值范围

最小数值：Number.MIN_VALUE，5e-324

最大数值：Number.MAX_VALUE，1.7976931348623157e+308

超出数值范围：-Infinity（负无穷）Infinity（正无穷）

判断一个数值是不是**有穷**数值：isFinite()
```js
var result = Number.MAX_VALUE + Number.MAX_VALUE;
alert(isFinite(result)); //false
```

#### NaN

NaN，即非数值（Not a Number）是一个特殊的数值。用于表示一个本来要返回数值的操作数为返回数值的情况。比如任何数值除以0都会返回NaN。

NaN的两个特性：
* 任何涉及NaN的操作都会返回NaN
* NaN与任何值都不相等，包括NaN本身

针对NaN的这两个特点，ECMAScript定义了isNaN()函数。这个函数接受一个参数，该参数可以是任何类型，而函数会帮我们确定这个参数是否“不是数值”。

isNaN()在接收到一个值后，会尝试将这个值转换为数值。某些不是数值的值会直接转换为数值，而任何不能被转换为数值的值都会导致这个函数返回true。
```js
alert(isNaN(NaN));    //true
alert(isNaN(10));    //false(10是一个整数)
alert(isNaN('10'));    //false(可以被转换成数值10)
alert(isNaN('blue'));    //true(不能转换成数值)
alert(isNaN(true));    //false(可以被转换成数值1)
```

#### 数值转换

有3个函数可以把非数值转换为数值：Number()、parseInt()和parseFloat()

Number()函数转换规则：
* true和false将分别被转换为1和0
* 如果是数字值，只是简单地传入和返回
* 如果是null值，返回0
* 如果是undefined，返回NaN
* 如果是字符串，遵循下列规则：
  * 如果字符串中只包含数字（包括前面带正号或负号的情况），则将其转换为十进制数值，即"1"会变成1，"123"会变成123，而"011"会变成11（忽略前导零）
  * 如果字符串中包含游侠的浮点格式，如"1.1"，则将其转换为对应的浮点数值（忽略前导零）
  * 如果字符串中包含有效的十六进制格式，例如"0xf"，则将其转换为相同大小的十进制整数值
  * 如果字符串是空的（不包含任何字符），则将其转换为0
  * 如果字符串中包含除上述格式之外的字符，则将其转换成NaN

Number()函数使用举例：
```js
var num1 = Number("Hello world!"); //NaN
var num2 = Number(""); //0
var num3 = Number("000011"); //11
var num4 = Number(true); //1
```

parseInt()函数转换规则：
* 在转换字符串时，会忽略字符串前面的空格，直至找到第一个非空格字符
* 如果是空字符串会返回NaN
* 如果第一个字符是数字字符，会继续解析第二个字符，直到解析完所有后续字符或者遇到了一个非数字字符
* 如果字符串中的第一个字符是数字字符，parseInt()也能识别出各种整数格式


parseInt()函数举例：
```js
var num1 = parseInt("1234blue"); // 1234
var num2 = parseInt(""); // NaN
var num3 = parseInt("0xA"); // 10（十六进制数）
var num4 = parseInt(22.5); // 22
var num5 = parseInt("070"); // 在ES3下等于56（八进制数）在ES5下等于70（十进制）
var num6 = parseInt("70"); // 70（十进制数）
var num7 = parseInt("0xf"); // 15（十六进制数）
var num8 = parseInt(".12");//NaN
```

###### 为了避免错误的解析，建议parseInt()无论在什么情况下都明确指定基数。


parseFloat()转换与parseInt()的区别是:
* parseFloat()始终都会忽略前导的零。
* parseFloat()只解析十进制，所以没有用第二个参数指定基数的用法。


parseFloat()函数使用举例：
```js
var num1 = parseFloat("1234blue"); //1234 （整数）
var num2 = parseFloat("0xA"); //0
var num3 = parseFloat("22.5"); //22.5
var num4 = parseFloat("22.34.5"); //22.34
var num5 = parseFloat("0908.5"); //908.5
var num6 = parseFloat("3.125e7"); //31250000
```