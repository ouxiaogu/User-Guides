
SYNOPSIS

`gawk [ POSIX or GNU style options ] -f program-file [ -- ] file ...`

`awk 'pattern {act
ion}'` 


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


1.  Scenario 1: swap two columns of the file

    `awk 'BEGIN{FS=OFS="\t"}{print $3, $2, $1} test.txt > test_o.txt'`
2.  Scenario 2: delete file before a time
    `ls -l | awk '$5 == "46" {print $9}' | xargs rm`



