<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [在XHTML中的用法](#%E5%9C%A8xhtml%E4%B8%AD%E7%9A%84%E7%94%A8%E6%B3%95)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 在XHTML中的用法

可扩展超文本标记语言，即XHTML（Extensible HyperText Markup Language），是将HTML作为XML的应用而重新定义的一个标准。

在HTML 中，有特殊的规则用以确定<script>元素中的哪些内容可以被解析，但这些特殊的规则在XHTML 中不适用，如下。

```js
<script type="text/javascript">
function compare(a, b) {
    if (a < b) {
        alert("A is less than B");
    } else if (a > b) {
        alert("A is greater than B");
    } else {
        alert("A is equal to B");
    }
}
</script>
```

这里比较语句a < b 中的小于号（<）在XHTML 中将被当作开始一个新标签来解析。但是作为标签来讲，小于号后面不能跟空格，因此就会导致语法错误。

解决方案：用相应的HTML 实体（<）替换代码中所有的小于号（<）

在将页面的MIME类型指定为"application/xhtml+xml"的情况下回触发XHTML模式。并不是所有浏览器都支持以这种方式提供XHTML文档。

