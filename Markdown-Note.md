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


## bug scenario
after any operation on the source ,like loading a new source or click `X Mirror`

 - It is correct to enable **OK** button , thus user can confirm their modification
 - But Click `Symmetry Check` , the **OK** button is turn gray , the operation on the source can not be saved.

## Improve Suggestion: 
- ask Qunhu to modify the behavior of `X Mirror` , `Y Mirror` ,`45/135 Mirror` , when clicking `OK` in the warning message box, just save the modification by mirror operation , but do not quit the parent dialog
- LongKai don't change the status of `OK` 
