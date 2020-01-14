<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [延迟脚本](#%E5%BB%B6%E8%BF%9F%E8%84%9A%E6%9C%AC)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 延迟脚本

延迟脚本在执行时不会影响页面的构造，延迟脚本会被延迟到整个页面都解析完毕后再运行。因此，在<script>元素中设置defer属性，相当于告诉浏览器立即下载，但延迟执行。

eg：
```js
<!DOCTYPE html>
<html>
    <head>
        <title>Example HTML Page</title>
    <script type="text/javascript" defer="defer" src="example1.js"></script>
    <script type="text/javascript" defer="defer" src="example2.js"></script>
    </head>
    <body>
        <!-- 这里放内容 -->
    </body>
</html>
```

在这个例子中，虽然我们把<script>元素放在了文档的<head>元素中，但其中包含的脚本将延迟到浏览器遇到</html>标签后再执行。

在现实当中，延迟脚本并不一定会按照顺序执行，也不一定会在DOMContentLoaded 事件触发前执行，因此最好只包含一个延迟脚本。

支持HTML5的实现会忽略给嵌入脚本设置的defer属性。因此，把延迟脚本放在页面底部仍然是最佳选择。

