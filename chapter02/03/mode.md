# 文档模式

最初的两种文档模式是：**混杂模式**（quirks mode）和**标准模式**（standards mode）。

混杂模式会让IE 的行为与（包含非标准特性的）IE5 相同，而标准模式则让IE 的行为更接近标准行为。

如果在文档开始处没有发现文档类型声明，则所有浏览器都会默认开启混杂模式。

不同浏览器在混杂模式下的行为差异非常大，所以要在开头声明文档类型：
```js
<!-- HTML 5 -->
<!DOCTYPE html>
```