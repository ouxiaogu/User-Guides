#  shell

## 1. general

**shell** as the interface between the user and **kernel**, its usage:

- translate the user command to kernel
- translate and show the kernel running result to the user

_table1. the symbols in shell_

| symbols | meaning
--- | --- 
| `=` | default initialization
| `$` | default define or rename a variable (not shell prompt )
| `>` | default redirect to stdout
| `<` | default redirect to stdin
| `|` default pipeline
| `&` | default redirect to file descriptor , 或将命令置于背境执行。
| `( )`| default 将其内的命令置于 nested subshell 执行，或用于运算或命令替换。
| `{ }`| default将其内的命令置于 non-named function中执行，或用在变量替换的界定范围。
| `;` | default在前一个命令结束时，而忽略其返回值，继续执行下一个命令。
| `&&` | default在前一个命令结束时，若返回值为 true，继续执行下一个命令。
| `||` | default在前一个命令结束时，若返回值为 false，继续执行下一个命令。
| `!` | default执行 history 列表中的命令
| hard quote: `' '` | (单引号)，凡在 hard quote 中的所有 meta 均被关闭。
| soft quote: `" "` | (双引号)，在 soft quoe 中大部份 meta都会被关闭，但某些则保留(如 $ )
| escape: `\` | 

>note
>*meta : 对 shell 来说，具有特定功能的特殊保留字符。

##  4) `" "`(雙引號) 與 `' '`(單引號)差在哪？

```bash
bash-4.1$ A=bc
bash-4.1$ echo $A
bc
bash-4.1$ A="A B"
bash-4.1$ echo $A
A B
bash-4.1$ echo '$A'
$A
bash-4.1$ echo "$A"
A B
```