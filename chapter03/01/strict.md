# 严格模式

ECMAScript5引入了严格模式(strict mode)的概念。

在严格模式下，ECMAScript3中的一些不确定的行为将得到处理，而且对某些不安全的操作也会抛出错误。

要在整个脚本中启用严格模式，可以在顶部添加如下代码：
```js
"use strict";
```

这行代码看起来像是字符串，而且也没有赋值给任何变量，但其实它是一个编译指示（pragma）,用于告诉支持的JavaScript引擎切换到严格模式。这是为不破坏ECMAScript3语法而特意选定的语法。

在函数内部的上方包含这条编译指示，也可以指定函数在严格模式下执行：
```js
function doSomething(){
    "use strict";
    //函数体
}
```