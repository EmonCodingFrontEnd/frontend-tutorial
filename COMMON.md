# 记录前端通用知识

[返回列表](https://github.com/EmonCodingFrontEnd/frontend-tutorial)

[TOC]

# 列表

## 1、统一代码风格工具——EditorConfig

EditorConfig不是什么软件，而是一个名称为`.editorconfig`的自定义文件。该文件用来定义项目的编码规范，编辑器的行为会与`.editorconfig`文件中定义的一致，并且其优先级比编辑器自身的设置要高，这在多人合作开发项目时十分有用且必要。

有些编辑器默认已安装了插件，比如`Intellij Idea`和`WebStorm`;而有些编辑器则需要安装插件，比如`ATOM`、`Sublime`、`VS Code`等。

- 官网

https://editorconfig.org/

- 文件语法

`.editorconfig`配置文件需要是UTF-8字符集编码的，以回车换行或者换行作为一行的分隔符。

斜线（/）被用作一个路径分隔符，井号（#）或分号（;）被用作于注释，注释需要与注释符号写在同一行。

- 通配符

| 符号         | 描述                                                         |
| ------------ | ------------------------------------------------------------ |
| *            | 匹配除/之外的任意字符串                                      |
| **           | 匹配任意字符串                                               |
| ?            | 匹配任意单个的字符                                           |
| [name]       | 匹配name中的任意一个单一字符                                 |
| [!name]      | 匹配不存在name中的任意一个单一字符                           |
| {s1,s2,s3}   | 匹配给定的字符串中的任意一个（用逗号分隔）                   |
| {num1..num2} | 匹配num1到num2之间的任意一个整数，<br />这里的num1和num2可以为正整数也可以为负整数 |

- 属性

  所有的属性和值都是忽略大小写的，解析时它们都是小写的。

  - `indent_style` 设置锁紧风格（tab是硬缩进，space为软缩进）。
  - `indent_size` 用一个整数定义的列数来设置锁紧的宽度，如果indent_style为tab，则此属性默认为tab_width。
  - `tab_width` 用一个整数来设置tab锁紧的列数。默认是indent_size。
  - `end_of_line` 设置换行符，值位lf、cr和crlf。
  - `charset` 设置编码，值位latin1、utf-8、utf-8-bom、utf-16be和utf-16le，不建议使用utf-8-bom。
  - `trim_+trailing_whitespace` 设为true表示会去除换行行首的任意空白字符。
  - `insert_final_newline` 设为true表示使文件以一个空白行结尾。
  - `root` 表示使最顶层的配置文件，发现设为true时，才会停止查找`.editorconfig`文件


