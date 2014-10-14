tool kits

Markdown, 是一种轻量级标记语言，它允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”。
sublime text 2, probably the best text editor in windows.
git , 是一个分布式版本控制／软件配置管理软件，原是Linux内核开发者林纳斯·托瓦兹（Linus Torvalds）为更好地管理Linux内核开发而设计。
GitHub 是一个共享虚拟主机服务，用于存放使用Git版本控制的软件代码和内容项目。GitHub同时提供付费账户和为开源项目提供的免费账户。


## 1. MarkDown

语法比较简单，具体见stackeditor, 或者我的findBestFocus.md 写法对照。

几个解析器如下：

1. [StackEditor](https://stackedit.io/editor)
2. [作业部落CMD editor](https://www.zybuluo.com/mdeditor)
前面这两个站点有如下几个特点：
  - 扩展效果支持良好 math expression, flow chart, table
  - render 效果紧凑
3. [github](https://www.zybuluo.com/mdeditor)
  - 不支持公式，但是对代码的显示是最漂亮的
4. Pandoc


## 2. sublime text

Go [here](https://github.com/ouxiaogu/tool_st2.git) to download sublime text 2 with all my settings and package 
You can find all the sublime text 2 package under its [package center](https://sublime.wbond.net),

```json
{
  "installed_packages":
  [
    "MarkdownEditing",
    "SublimeREPL"
  ]
}
```

(1) "MarkdownEditing"
Powerful Markdown package for Sublime Text with better syntax understanding and good color schemes .
(2) "SublimeREPL"
SublimeREPL - run an interpreter inside ST2 (Lua, Python , R, Ruby, Scala...)

**how to work**
1. make sure you have add the interpreter file folder into env path, e.g. , add lua51's folder C:\Localdata\D\Program Files\lua
2. after install SublimeREPL package, open it `Tools | SublimeREPL | lua...` .
3. Keybindings
  - <kbd>ctrl+,</kbd>, <kbd>f</kbd> Evaluate the whole File in REPL: 
  - <kbd>ctrl+shift+,</kbd>, <kbd>f</kbd> Only copy the whole File in REPL: 
  - besides file , `b` : block, `s` : selection, `l` : line

> **note**
> SublimeREPL is not the key for all problems, it can not run the recursive call, it have few debug information, sometime it even have false bug alarm.

## 3. Git  

**github sync steps** 
1. add all the file hierachy  under this folder to a git repository 
```shell
git add *
```
2. commit all the modification into the repository
```shell git commit -m "1st comment" ```
3. push to github web server, origin is src name, mater is dst branch name.
```shell git push origin master  ```