# LaTex Math Expression Frequently Used Symbols

标签（空格分隔）： User-Guides
[TOC]
---

Reference

1. [art of problem solving.com/Wiki/LaTeX/Math](http://www.artofproblemsolving.com/Wiki/index.php/LaTeX:Math)
2. [常用符号的LaTex表示](http://mohu.org/info/symbols/symbols.htm)
3. [wikibooks: LaTex Mathematics](http://en.wikibooks.org/wiki/LaTeX/Mathematics)


## 1. Frequently Used Symbols

### special characters
_Table 1. LATEX 2ε Escapable “Special” Characters_
```
$ \$    % \%    _ \_   } \}   & \&   # \#   { \{
```
### symbols

- <kbd>\propto</kbd> : 正比于 $\propto$ 
- <kbd>\leq</kbd> : 小于等于 $\leq$ 
- <kbd>\times</kbd> :  乘以 
- <kbd>\frac</kbd> :  分数
- <kbd>_</kbd> :  下标 subscript
- <kbd>^</kbd> :  上标 superscript
- <kbd>\sum\limits_{i=0}^{n} </kbd> :  上标 superscript


## 3. space adjustment

_table 1. LaTex中调节公式文字间距的指令表_

|正距离    | 样例    | 负距离   | 样例    
----       | ----    | ----     | -----
|`$ab$`      | $ab$      |          |   
|`$a b$`     | $a b$      |          |   
|`$a\ b$`    | $a\ b$     |          |   
|`$a\,b$` (a\thinspace b)| $a\,b$ |`$a\!b$`| $a\!b$
|`$a\:b$` (a\medspace b)| $a\:b$| `$a\negmedspace b$`| $a\negmedspace b$
|`$a\;b$` (a\thickspace b)| $a\;b$| `$a\negthickspace b$`| $a\negthickspace b$
|`$a\quad b$`| $a\quad b$| |     
|`$a\text{---}b$`| $a\text{---}b$ | |    
|`$a\qquad b$`| $a\qquad b$| |    
|`$a\hspace{0.5cm}b$`| $a\hspace{0.5cm}b$ | |    
|`$a\hspace{-0.5cm}b$`| $a\hspace{-0.5cm}b$ | |    
|`$a\phantom{xx}b$`| $a\phantom{xx}b$ | |  
|`$axxb$`| $axxb$| |    |


## 4.examples

### 4.1 SEM_RMS

$$ SEM\_RMS = \sqrt {\frac {\sum \limits _i COST\_WT _i \times ( RMS\_X_i^2+RMS\_Y_i^2)} {\sum \limits _i COST\_WT _i}} $$


$$ W_{edge\_pt^{(k)}}=\frac {W_g \times W_{cond}} {\sum \limits _{i=1}^ {n} W_{geom^{(i)}}} \times W_{geom}^{(k)} = \frac { \left( W_{SEMWeight} \times W_{COST\_WT} \right) \times W_{cond}} {\sum \limits _{i=1}^ {n} W_{geom^{(i)}}} \times W_{geom}^{(k)}  $$

$$ W_{edge\_pt^{(k)}}=\frac { W_g \times W_{cond}} {\sum \limits _{i=1} ^{n} W_{geom^{(i)}}} \times W_{geom}^{(k)} = \frac { \left( W_{SEMWeight} \times W_{COST\_WT} \right) \times W_{cond} } {NUM _ {edge\_pt\_in\_SEM}}  $$

X:\data\r201501\PLT26685\check_ical_job_multiconds\h\cache\dummydb\result\calibrate\job1

SEM\_RESULT = \sqrt {\frac {\sum \limits _{k=1} ^n W_{geom}^{(k)}  \times ( RMS\_X_k^2+RMS\_Y_k^2)} {\sum \limits_{k=1} ^n W_{geom}^{(k)}  } }

SEM\_COND = \sqrt {\frac {\sum \limits _i COST\_WT _i \times SEM\_RESULT_i ^2 } {\sum \limits _i COST\_WT _i}}


 W_{SEMWeight} 

 RMS\_COND = \sqrt { \frac { { \sum \limits _i  \left( W_{SEMWeight} \times W_{COST\_WT} ^{(i)} \right) \times SEM\_RESULT _ i ^2 } + {\sum \limits _j gauge\_wt ^{(j)} \times Gauge\_err _j ^2 } } {  {\sum \limits _i  \left( W_{SEMWeight} \times W_{COST\_WT} ^{(i)} \right) } + { \sum \limits _j gauge\_wt ^{(j)}  } } }  

  RMS\_Job = \sqrt { \frac { { \sum \limits _{i,m}  \left( W_{SEMWeight} \times W_{COST\_WT} ^{(i)} \right) \times W_{cond} ^ {(m)} \times SEM\_RESULT _ i ^2 } + {\sum \limits _{j,n} gauge\_wt ^{(j)} \times W_{cond} ^ {(n)} \times Gauge\_err _j ^2 } } {  {\sum \limits _{i,m}  \left( W_{SEMWeight} \times W_{COST\_WT} ^{(i)} \right) \times W_{cond} ^ {(m)} } + { \sum \limits _{j,n} gauge\_wt _j \times W_{cond} ^ {(n)}   } } }


  X_{edge\_pt} = \frac { X_{sample\_pt} - CENTER\_X } {PIXEL}
  Y_{edge\_pt} = - \frac { Y_{sample\_pt} - CENTER\_Y } {PIXEL}

init\_wt = \frac {1}{ \sqrt \sigma } 
uncertaintyMSE = \frac {\sum (perturb\_err - base\_err)^2 * init\_wt} {\sum init\_wt }

abs\_err\_diff = | {perturb\_err} | - |{base\_err}|

\[ sgn = \left\{ 
  \begin{array}{l l}
    1 & \quad \text{if $abs\_err\_diff > 0 $}\\
    -1 & \quad \text{if $abs\_err\_diff <= 0 $}
  \end{array} \right.\]

uncertaintyDiff = \frac {\sum wt * sgn * | 
(abs\_err\_diff)} {\sum wt} |

deltaRMS = pertub\_rms - base\_rms