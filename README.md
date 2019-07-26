# CSUIS-md2docx

本项目想为中南信安学子提供一个更方便、程序员风格的书写实验报告的方式。

程序员书写文档时候，一个很自然的选择就是使用markdown来进行书写。markdown作为一个标记语言，语法简单、满足基本需求，还有各种在上进行拓展的东西。但是markdown作为标记语言，和最终老师的需求是不一样的，老师需要的是带有排版信息的文档，也就是Office Open XML。

借由这个需求，我尝试给出一些从markdown生成最后的实验报告的解决方案，目前来说已经完成以下方案：

- [pandoc](./pandoc/README.md)

还有以下方案正在尝试中：

- [markdown parser & python-docx](./parse/README.md)
- [LaTeX](./latex/README.md)
