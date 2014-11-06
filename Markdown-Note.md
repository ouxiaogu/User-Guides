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
- <kbd>__ __</kbd>: __underline__ 


>**Usage**
  >>Copy a TFlex LMC job

>**Syntax**
  >> <code>$TFLEX_INSTALL_ROOT/bin/tachyon_perl $TFLEX_INSTALL_ROOT/perl/clonejob.pl <source_job_dir> <destination_job_dir> [-result] [-r installroot/app/release or release name or installroot]</code>
  
  >> the mkdir of dst first

>**Example**
  >><code>/gpfs/software/tachyon_flex_20150100/qa21_v2/SGE/bin/tachyon_perl /gpfs/software/tachyon_flex_20150100/qa21_v2/SGE/perl/clonejob.pl  /gpfs/DEV/FEM/xixie/fem+/ical_jpg /gpfs/PEG/FEM/peyang/data/r201501/MOD5962/test3_v0 -result</code>

**Usage**
  >Copy a TFlex LMC job

**Syntax**
  > `$TFLEX_INSTALL_ROOT/bin/tachyon_perl $TFLEX_INSTALL_ROOT/perl/clonejob.pl <source_job_dir> <destination_job_dir> [-result] [-r installroot/app/release or release name or installroot]`
  
  > should mkdir of dst first

**Example**
  >`/gpfs/software/tachyon_flex_20150100/qa21_v2/SGE/bin/tachyon_perl /gpfs/software/tachyon_flex_20150100/qa21_v2/SGE/perl/clonejob.pl  /gpfs/DEV/FEM/xixie/fem+/ical_jpg /gpfs/PEG/FEM/peyang/data/r201501/MOD5962/test3_v0 -result`
