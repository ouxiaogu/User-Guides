# MarkDown Note
---

MarkDown is a simple technique for marking up text files so that they can be post-processed into other forms.

There are some brief introduction:
  - Simplified Chinese Version: http://wowubuntu.com/markdown/basic.html
  - English Version: https://help.github.com/articles/markdown-basics/

## Renders
Several on line renders:

1. [IPython Notebook](http://ipython.org/)

    - support languages: python 2 3, R, bash ...
    - Integrated in [Anaconda (32-bit)](https://3230d63b5fc54e62148e-c95ac804525aac4b6dba79b00b39d1d3.ssl.cf1.rackcdn.com/Anaconda-2.3.0-Windows-x86.exe) 
    - support equation!
1. [Github](https://www.zybuluo.com/mdeditor)
  
    Not support equation, but have the best syntax highlighter and layout 
2. [StackEditor](https://stackedit.io/editor)
3. [zybuluo CMD editor](https://www.zybuluo.com/mdeditor)

  The characters of StackEditor and zybuluo CMD editor:
  - support math expression, flow chart, table
  - support TOC
4. [Pandoc](http://pandoc.org/README.html): If you need to convert files from one markup format into another, pandoc is your swiss-army knife. 
  
## conversion

### 1. from html to github style markdown

Above all, introduce a wonderful website, [table generator](http://www.tablesgenerator.com/markdown_tables):

It can convert the from the clipboard or html or csv or excel into these five format of tables.

| 1            | 2           | 3           | 4               | 5                |
|--------------|-------------|-------------|-----------------|------------------|
| LaTeX Tables | HTML Tables | Text Tables | Markdown Tables | MediaWiki Tables |

Maybe, more specifically, I can title this paragraph as **How to convert confluence page to github style markdown ?**.

```shell
pandoc -o LuaAPI.md -f html  -t markdown_github LuaAPI.html
```

- `-o`: output to a file
- `-f`: The input format can be specified using the `-r`/`--read` or `-f`/`--from` options
- `-t`: the output format using the `-w/--write` or `-t`/`--to` options

This Syntax means use pandoc to out put a file named "LuaAPI.md", format is from a html file to a github style markdown, the input file is [LuaAPI.html](), the output file can be found at [LuaAPI.md, the markdown source file for FEM+ Lua API]().

## Usage Tips

### 1. List item with multiple lines paragraphs 

```md
1.  This is a list item with two line.  <br />
    End a line by `<br />` compulsorily.
2.  This is a list item with two paragraphs.

    Use table in line head, and a blank line
3.  List item 3 
```

### 2. Table by markdown

```md
| Name |  Remark | Date |
---- | ---- | ---- | --- 
Peng-cheng | Initial draft | 04/01/2015|
| Reviewed |  |  |
| Approved |  |  |
```

=======
1. [StackEditor](https://stackedit.io/editor)
2. [作业部落CMD editor](https://www.zybuluo.com/mdeditor)
前面这两个站点有如下几个特点：
  - 扩展效果支持良好 math expression, flow chart, table
  - render 效果紧凑
3. [github](https://www.zybuluo.com/mdeditor)
  - 不支持公式，但是对代码的显示是最漂亮的
>>>>>>> origin/master
