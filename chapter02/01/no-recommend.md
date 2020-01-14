<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [不推荐使用的语法](#%E4%B8%8D%E6%8E%A8%E8%8D%90%E4%BD%BF%E7%94%A8%E7%9A%84%E8%AF%AD%E6%B3%95)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 不推荐使用的语法

在最早引入<script>元素的时候，该元素与传统HTML 的解析规则是有冲突的。

早期不支持JavaScript 的浏览器会把<script>元素的内容直接输出到页面中，会破坏页面的。 布局和外观。

让不支持<script>元素的浏览器能够隐藏嵌入的JavaScript 代码，把JavaScript 代码包含在一个HTML 注释中：
```js
<script><!--
function sayHi(){
    alert("Hi!");
}
//--></script>
```

由于所有浏览器都已经支持JavaScript，因此也就没有必要再使用这种格式了，不推荐。