# 标签的位置

习惯上会把JavaScript引用放在head中间，这样是为了统一外部引用的文件都放在同一个地方。

但是页面是到body才开始解析显示到页面上的。所以放在head中就会出现页面空白很久的情况。

为了避免这种问题的出现，把script内容放在body中元素页面内容的后面：
```js
<!DOCTYPE html>
<html>
    <head>
        <title>Example HTML Page</title>
    </head>
    <body>
        <!-- 这里放内容 -->
        <script type="text/javascript" src="example1.js"></script>
        <script type="text/javascript" src="example2.js"></script>
    </body>
</html>
```