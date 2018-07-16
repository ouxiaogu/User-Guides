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


## Appendix 3. ST Preference user

```json
{
  "auto_complete_commit_on_tab": true,
  "color_scheme": "Packages/Color Scheme - Default/Monokai Bright.tmTheme",
  "dictionary": "Packages/Language - English/en_US.dic",
  "draw_white_space": "all",
  "file_exclude_patterns": ["*.pyc", "*.pyo", "*.exe", "*.dll", "*.obj","*.o", "*.a", "*.lib", "*.so", "*.dylib", "*.ncb", "*.sdf", "*.suo", "*.pdb", "*.idb", ".DS_Store", "*.class", "*.psd", "*.db", "*.sublime-workspace"],
  "folder_exclude_patterns": [".svn", ".git", ".hg", "CVS", "_*", ".*"],
  "font_size": 14.0,
  "highlight_line": true,
  "ignored_packages":
  [
    "Vintage",
    "Lua Dev",
    "FileHeader"
  ],
  "ignored_words":
  [
    "iterable"
  ],
  "indent_guide_options":
  [
    "draw_normal",
    "draw_active"
  ],
  "phoenix_color_blue": true,
  "phoenix_highlight_current_tab": true,
  "rulers":
  [
    80, 120
  ],
  "spell_check": true,
  "tab_size": 4,
  "theme": "Phoenix Dark.sublime-theme",
  "translate_tabs_to_spaces": true,
  "use_simple_full_screen": true,
  "vintage_start_in_command_mode": true,
  "word_wrap": true,
  "wrap_width": 120
}

```