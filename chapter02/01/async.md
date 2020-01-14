<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [异步脚本](#%E5%BC%82%E6%AD%A5%E8%84%9A%E6%9C%AC)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 异步脚本

与defer类似，async只适用于外部脚本文件，并告诉浏览器立即下载文件。但与defer不同的是，标记为async的脚本并不保证按照指定它们的先后顺序执行。例如：

```js
<!DOCTYPE html>
<html>
    <head>
        <title>Example HTML Page</title>
        <script type="text/javascript" async src="example1.js"></script>
        <script type="text/javascript" async src="example2.js"></script>
    </head>
    <body>
        <!-- 这里放内容 -->
    </body>
</html>
```
以上代码中，第二个脚本文件可能会在第一个脚本文件之前执行。因此确保两者之间互不依赖非常重要。

指定async 属性的目的是不让页面等待两个脚本下载和执行，从而异步加载页面其他内容。

异步脚本一定会在页面的load 事件前执行，但可能会在DOMContentLoaded 事件触发之前或之 后执行。