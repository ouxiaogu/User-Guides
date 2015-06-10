#  shell

## 1. general

**shell** as the interface between the user and **kernel**, its usage:

- translate the user command to kernel
- translate and show the kernel running result to the user

_table 1. the shell meta character( 关键字符) in shell_

| shell meta characters | meaning
--- | --- 
| `=` | initialization
| `$` | command substitution , 命令替换，两种方式 _\`A\`_ 或 _$A_
| `>` | redirect to stdout
| `<` | redirect to stdin
| `|` | pipeline
| `*` | File substitution , zero or more characters 
| `?` | File substitution , one character
| `&` | default redirect to file descriptor , 或将命令置于背境执行。
| `( )`| Group commands, nested subshell 
| `{ }`| Group commands, non-named function
| `;` | Command sequence,在前一个命令结束时，而忽略其返回值，继续执行下一个命令。
| `&&` | AND conditional execution 在前一个命令结束时，若返回值为 true，继续执行下一个命令。
| `||` | OR conditional execution 在前一个命令结束时，若返回值为 false，继续执行下一个命令。
| `!` | default执行 history 列表中的命令
| hard quote: `' '` | (单引号)，凡在 hard quote 中的所有 meta 均被关闭。
| soft quote: `" "` | (双引号)，在 soft quoe 中大部份 meta都会被关闭，但某些则保留(如 $ )
| escape: `\` | Prevent or escape interpretation of the next character

>note
>*meta : 对 shell 来说，具有特定功能的特殊保留字符。


## 2. 


##  4 `" "`(雙引號) 與 `' '`(單引號)差在哪？

\#1. **Hard quota** and **soft quota** in bash

```bash
bash-4.1$ A="A B"
bash-4.1$ echo '$A'
$A
bash-4.1$ echo "$A"
A B
```

\#2. **shell meta** v.s. **command meta**

- When as shell meta, brace `{ }`  is used to group some non-named functions (_command block_);
- When as command mega, brace is used to mark one group of **awk statement** , or delimit the **BEGIN, MAIN, END**

```bash
bash-4.1$ awk '{print $0}' 1.txt
bash-4.1$ awk "{print \$0}" 1.txt  
bash-4.1$ awk \{print \$0\} 1.txt  
bash-4.1$ x=0
bash-4.1$ awk "{print \$$x}" 1.txt
total 243M
-rw-rw-r-- 1 peyang peyang    0 Nov 24 15:13 1.txt
bash-4.1$ awk {print $1} 1.txt
awk: cmd. line:1: {print
awk: cmd. line:1:       ^ unexpected newline or end of string
bash-4.1$ awk '{print $0}' 1.txt # error empty line
```

Another example show how to use the brace to expand the value of a variable.

```bash
bash-4.1$ a=b:c
bash-4.1$ a=$a:d
bash-4.1$ echo $a
b:c:d
bash-4.1$ a=${a}e
bash-4.1$ echo $a
b:c:de
```

## 7 exec 跟 source 差在哪？

**fork**
- --> execute Parent process 
  - --> execute child process
  - --> done child process
- --> back to Parent process 


