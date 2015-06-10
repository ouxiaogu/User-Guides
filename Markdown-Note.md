# MarkDown Note
---

MarkDown is a simple technique for marking up text files so that they can be post-processed into other forms.

There are some brief introduction:
  - Simplified Chinese Version: http://wowubuntu.com/markdown/basic.html
  - English Version: https://help.github.com/articles/markdown-basics/

## Renders
Several on line renders:

1. [Github](https://www.zybuluo.com/mdeditor)
  
    Not support to equation, but have the best syntax highlighter and layout 
2. [StackEditor](https://stackedit.io/editor)
3. [zybuluo CMD editor](https://www.zybuluo.com/mdeditor)

  The characters of StackEditor and zybuluo CMD editor:
  - support math expression, flow chart, table
  - support TOC
4. [Pandoc](http://pandoc.org/README.html): If you need to convert files from one markup format into another, pandoc is your swiss-army knife. 
  
## conversion

### 1. from html to github style markdown

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

