# Sublime text 2 User Guide


## 1. general intro

Go [here](https://github.com/ouxiaogu/tool_st2.git) to download sublime text 2 with all my settings and package .

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

(1) **MarkdownEditing**
[MarkdownEditing](https://github.com/SublimeText-Markdown/MarkdownEditing) is a Powerful Markdown package for Sublime Text with better syntax understanding and good color schemes .

(2) **SublimeREPL**
SublimeREPL - run an interpreter inside ST2 (Lua, Python , R, Ruby, Scala, PowerShell...)

`PowerShell`:

  Very fancy to support Linux style grep by :

    ```shell
    Select-string 'def savefig' .\*.py -ca
    ```


**Open in ST as Context Menu**

```shell
@echo off
SET st2Path=D:\Program Files\sublime_text\sublime_text.exe
 
rem add it for all file types
@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 2"         /t REG_SZ /v "" /d "Open with Sublime Text 2"   /f
@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 2"         /t REG_EXPAND_SZ /v "Icon" /d "%st2Path%,0" /f
@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 2\command" /t REG_SZ /v "" /d "%st2Path% \"%%1\"" /f
 
rem add it for folders
@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 2"         /t REG_SZ /v "" /d "Open with Sublime Text 2"   /f
@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 2"         /t REG_EXPAND_SZ /v "Icon" /d "%st2Path%,0" /f
@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 2\command" /t REG_SZ /v "" /d "%st2Path% \"%%1\"" /f
pause
```

## Appendix 1. frequently used sublime shortcut

### text editting

1. `ctrl` + `/` : comment
2. `ctrl` + `shift` + `D` : line copy
3. cursor
  - `Ctrl` + `M`: move between '()' and '{}'
  - `home` : line head
  - `end` : line tail
  - `ctrl` + `end` : code tail
  - `ctrl` + `home` : code head
  - multiple cursors
    + `ctrl` + mouse click 
  - `Alt` + `home` : select a line , can use to delete
4. Upper/ Lower Case
  - `ctrl + k + u`: upper_case 
  - `ctrl + k + l`: lower_case
5. SublimeREPL 
  - `ctrl + ,` + `f`: run the file in REPL, recursive  


## Appendix 2. FAQ

Q1.  [Change the default syntax associated to some specific file type](http://stackoverflow.com/questions/7574502/set-default-syntax-to-different-filetype-in-sublime-text-2/8014142#8014142) ?

A : `View -> Syntax -> Open all with current extension as... ->[your syntax choice].`



