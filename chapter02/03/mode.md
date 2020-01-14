<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [文档模式](#%E6%96%87%E6%A1%A3%E6%A8%A1%E5%BC%8F)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 文档模式

最初的两种文档模式是：**混杂模式**（quirks mode）和**标准模式**（standards mode）。

混杂模式会让IE 的行为与（包含非标准特性的）IE5 相同，而标准模式则让IE 的行为更接近标准行为。

如果在文档开始处没有发现文档类型声明，则所有浏览器都会默认开启混杂模式。

不同浏览器在混杂模式下的行为差异非常大，所以要在开头声明文档类型：
```js
<!-- HTML 5 -->
<!DOCTYPE html>
```