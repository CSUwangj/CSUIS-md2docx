# pandoc方案

## TL;DR

1. 安装pandoc。
2. 按照example.md中的格式书写/调整markdown，多章节则每个章节都使用一级标题，忽视lint错误。
3. 打开powershell。
4. 执行`pandoc -o <output_file> --reference-doc=<path of for_student.docx> <input_markdown>`。
5. 打开转换过的文件，进行最后的调整，目前已知的调整包括以下：
   1. 设置页边距，页眉、页脚。
   2. 插入封面。
   3. 插入目录。
   4. 在封面、目录、摘要、各章节和结束语间插入分页符。
   5. 英文综述的标题与结束语的调整。
   6. 添加公式的序号。
   7. 参考文献。
6. 恭喜，任务完成。

## 怎样完成的

pandoc是一款开源的文档转换工具，支持多种格式之间的互相转换。

正如你在前面所看到的命令，pandoc在输出格式是docx时，支持定制的模板文件。通过更改模板文件中的样式就可以使得输出的文档获得所需的定制效果。

## 这个方案的好处

工作量很小，这意味着即便你有自己独特的需求，也不会花费太多时间给自己定制一个。

## 这个方案的不足之处

- 官方文档中说明可以定制的内容很多，但是在样式栏缺少一部分。猜测可能直接改xml有效。
- 综述的标题用标题来替代了，不够优雅。因为这个原因也没有办法让中文综述标题和英文综述标题一起出现，除非你打算让他们在markdown的同一行里，生成后修改。
- 需要进行的调整都是这个方案的不足之处。

## 补充说明

pandoc使用的并非是GFM，而是通过很多插件拓展了的markdown，如果想要了解具体的信息，请前往<https://pandoc.org/MANUAL.html#pandocs-markdown>，或许你能找到一些你需要却被我忽略的信息。

官网manual给的命令`pandoc -o custom-reference.docx --print-default-data-file reference.docx`实际上并不会输出到custom-reference.docx里而是输出到stdout里，可能会导致命令行出错，这就很迷。在powershell里，即便使用Out-File输出到文件里，结果也是错的，但是用cmd/git bash中`>`符号重定向输出，结果都是没问题的，猜测是pandoc的问题（毕竟前面这个错误已经很明确是它的了）。在kali里同样要直接用`>`

## TODO

- [ ] 检查修改xml是否可以使得一些格式变得可控，如图题图序（图片的说明文字）
