# MarkDown Note

标签（空格分隔）： User-Guides

---

## Renders
Several on line renders:

1. [StackEditor](https://stackedit.io/editor)
2. [作业部落CMD editor](https://www.zybuluo.com/mdeditor)
前面这两个站点有如下几个特点：
  - 扩展效果支持良好 math expression, flow chart, table
  - render 效果紧凑
3. [github](https://www.zybuluo.com/mdeditor)
  - 不支持公式，但是对代码的显示是最漂亮的


## Instructions

- <kbd>_</kbd> : subscript
- <kbd>^</kbd> : superscript


It seems only 8 bits bmp image is supported in binary, I test two jobs with bmp in $workpath = /gpfs/PEG/FEM/peyang/data/r201501/MOD5962/

\#1. $job = bmp_24b, using .bmp SEM image with 24 bits color depth, the job abort with the following info:

```bash
[peyang@flogin1 fnode054]$ less -NM leaf6.log | grep 8mb-9_7-1.bmp
/gpfs/PEG/FEM/peyang/data/r201501/MOD5962/bmp/h/data/dummydb/calibrate/job1/sem/c1/8mb-9_7-1.bmp: not a 8 bit bmp
/gpfs/PEG/FEM/peyang/data/r201501/MOD5962/bmp/h/data/dummydb/calibrate/job1/sem/c1/8mb-9_7-1.bmp: failed to load header 
Load SEM image /gpfs/PEG/FEM/peyang/data/r201501/MOD5962/bmp/h/data/dummydb/calibrate/job1/sem/c1/8mb-9_7-1.bmp fails
```

\#2. $job = bmp_256, 256=2^8, it means image depth = 8 bits, can be represented in 0~255, the job run successfully.
