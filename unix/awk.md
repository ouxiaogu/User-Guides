
SYNOPSIS

`gawk [ POSIX or GNU style options ] -f program-file [ -- ] file ...`

`awk 'pattern {action}'` 


| variable | meaning 
--- | --- 
| ARGC | 
| ARGV | 
| FILENAME | 
| FNR | 当前文件中的记录号
| FS | 输入域分隔符
| RS | 输入记录分隔符
| NF | 当前记录里域个数
| OFS | 输出域分隔符
| ORS | 输出记录分隔符

| `awk '$1 * $2 > 100' file`  |# 显示 file 中变量1与变量2的乘积大于100的行
| 




Input.txt


Output.txt




e.g

