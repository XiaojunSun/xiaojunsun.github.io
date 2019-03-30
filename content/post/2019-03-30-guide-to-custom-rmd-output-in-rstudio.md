---
title: "如何在RStudio中定制.Rmd编译网页的效果"
author: "Xiaojun Sun"
date: '2019-03-30'
slug: guide-to-custom-rmd-output-in-rstudio
tags:
- R
- Markdown
categories: Tutorial
---

.Rmd是一种将R语言与Markdown语法结合起来的文档格式，一般在Rstudio中使用。.Rmd文件可以用来写笔记、论文和报告，文档与代码穿插，展示过程清晰，而且可被重复验证。.Rmd文件可以编译成一篇完整的文档，主要有网页、PDF和Word三种格式。一般来说，网页是最常用的输出格式。虽然RStudio提供了一些主题和选项来丰富文档展示效果。但是这输出效果并不十分美观，而且很不灵活。本文介绍一种灵活的定制网页输出效果的方法。

众所周知，CSS文件是用来控制网页渲染效果的。本文采用的方法就是用定制化的CSS文件来编译.Rmd文件，这主要归功于RStudio和knitr包提供的扩展功能。
在RStudio中新建或打开.Rmd文件，点击齿轮图表可以看到Output Options，这里可以设置.Rmd文件的编译选项。勾选Apply CSS file，输入CSS文件路径，就可以使用自定义的CSS文件编译.Rmd文件了。勾选Apply CSS file后最好不要勾选Apply theme，以免出现冲突。

![](/images/20190330102223.png)

使用CSS文件编译前后的效果可以可以参考下图：

![](/images/20190330102526.png)

编写CSS文件需要一定的CSS知识基础，但是也有一些简单的办法。首先你可以复制一份别人的CSS文件进行编译，然后在浏览器中打开网页文件，鼠标右键选择‘检查’或Ctrl+Shift+I（以Chrome为例）。在样式栏里可以对一些参数进行修改尝试，找到满意的参数后再回来修改CSS文件，如此反复最后就能得到一套自己满意的CSS样式设置了。以后编写和编译.Rmd文件，直接调用这个CSS文件就大功告成了。
![](/images/20190330102651.png)

