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


\1. Cell edit : 

we should enable some cells' editing in the SEM spec table, i.e. , CENTER_X, CENTER_Y, COST_WT, DETECT_EGDE, ALGN_EDGE.
currently , there are three methods to do it , but all have its limits.

- edit in the SEM condition setting pane, but it can not see GDS 
- edit in the Sem ALGN dialog , change the parameter and apply that in server, however, this method only suit for adjust in a small range
- use text editor such as vim ,and reload the spec file

\2. Row delete: 

scenario : after Sem ALGN, we found invalid SEM image is loaded  , we just want to delete it in the SEM Spec table, go back the SEM condition to delete it is  unfriendly .

\3. add function **save out Sem Spec with/wo result**, like the **save out the gaugeset with/wo results**.

\4. add function **save contour point result**

usage : sometimes, we have to save out the point error result out for further analysis.
