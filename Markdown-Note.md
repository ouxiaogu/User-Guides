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

Basically , there are only 4 types of behavior of all the load model scenario in FEM+ calibration job.

1. ADI : $src_model = optical model, change the optical parameter.
 
 - if load model | model type = optical , keep $dst_job's type
 - if load model | model type = resist , because your $src_model = optical model,  giving a warning "The model you loaded is a pure optical model, there are not resist terms."
 - if load model | model type = all, 
  - if  $dst_job's model type != None, sync it to None , and give the default warning message box.
  - if  $dst_job's model type = None, just load the pure optical model.

2. ADI : $src_model = ADI model with Resist part , and load model | model type = resist .

- $src_model = ADI model with Resist part, it means fem, femslg, generic, harmonic or harmonic2 , but not include None .
- just change the resist term, but do not change the optical parameters,  and sync  it with model type of the $src_model , also give the default warning message box.


3. ADI : $src_model = ADI model with Resist part , and load model | model type = all .

- change the resist terms and the optical parameters,  and sync  it with model type of the $src_model , also give the default warning message box.

4. AEI : load model to change etch terms

- if $src_model = ADI Model , give a waring message box "The loaded model is an ADI model, it is invalid for Etch terms."
- if $src\_model = AEI Model , when model type of $src\_model != $dst\_job, sync that of $dst\_job , and change the parameters of etch terms as the $src\_model .
