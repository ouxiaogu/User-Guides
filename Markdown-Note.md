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


This is an more advanced improvement requirement of PLT-27991.

- it it more convenient to make the function as a check box beside **Center(um) & Pixel size(nm)**
- currently, in PLT-27991 : check **Keep zoomed scale when switch gauge**, the center and pixel size will be kept
- further requirement: if **keep GDS viewer option** is enabled ,the user checked term i.e. AI , RI , will be kept and redrawn after the action such as zoom in /out , shift center , switch gauge and switch SEM spec entry. Currently , only **Sem ALGN** can be kept.

Sorry for the workload , but this improvement have been in PPT list for a long time , until I saw function **Keep zoomed scale when switch gauge** recently.
