<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [嵌入代码与外部文件](#%E5%B5%8C%E5%85%A5%E4%BB%A3%E7%A0%81%E4%B8%8E%E5%A4%96%E9%83%A8%E6%96%87%E4%BB%B6)
          - [并不存在必须使用外部文件的硬性规定](#%E5%B9%B6%E4%B8%8D%E5%AD%98%E5%9C%A8%E5%BF%85%E9%A1%BB%E4%BD%BF%E7%94%A8%E5%A4%96%E9%83%A8%E6%96%87%E4%BB%B6%E7%9A%84%E7%A1%AC%E6%80%A7%E8%A7%84%E5%AE%9A)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 嵌入代码与外部文件

使用外部文件的优点：
* **可维护性**：遍及不同HTML页面的JavaScript会造成维护问题。但把所有JavaScript文件都放在一个文件夹中，维护起来就轻松多了。而且开发人员因此也能够在不触及HTML标记的情况下，集中精力编辑JavaScript代码。

* **可缓存**：浏览器能够根据具体的设置缓存链接的所有外部JavaScript文件。也就是说，如果有两个页面都使用同一个文件，那么这个文件只需要下载一次。因此，最终结果就是能够加快页面加载的速度。

* **适应未来**：通过外部文件来包含JavaScript无须使用前面提到的XHTML或注释hack。HTML和XHTML包含外部文件的语法是相同的。

###### 并不存在必须使用外部文件的硬性规定