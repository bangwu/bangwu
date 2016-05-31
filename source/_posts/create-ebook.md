---
title: Create you own ebook
date: 2016-05-31 08:00:00
description: "我来教你如何把一个gitbook电子书生成一本离线的电子书。"
tags: JavaScript
category: 工具
---
在我们的生活中，有时我们需要把一个gitbook点子书转换成`pdf`,`epub`或者`mobi`等格式的文档，我们可以通过下面的方式来完成这件事。
## 下载你要转换的文档

>你可以从gitbook上下载任何一个你想要转换的电子书。

### 你可以通过以下步骤创建你自己的点子书

* install Calibre
* add it to your path:


```
$ ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin
```

* install gitbook using npm:

```
$ npm install gitbook-cli -g
```

* in the root folder of your Redux clone (e.g. ~/repositories/redux/), run:

```
$ gitbook pdf . docs/redux-documentation.pdf
$ gitbook epub . docs/redux-documentation.epub
$ gitbook mobi . docs/redux-documentation.mobi
```

* I use the create-docs script from this repository and run it in a clone of the official Redux repository.