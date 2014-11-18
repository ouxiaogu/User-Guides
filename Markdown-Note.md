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


PRD Template

# Show source symmetric information after loading source

##  Documentation History

| Name |  Remark | Date |
--- | --- | --- |
Peng-cheng | Initial draft | 11/18/2014
 | Reviewed |  
  | Approved   |

## Product Background, Requirement understanding

###  1.  Background 

Some essential utility functions in the gauge table should also be supported in the Sem Spec table.
  
The ticket created is PLT-29276 .

###  2.  Requirement understanding

#### GUI requirements

\#1. **edit cell** : 

We should enable some cells' editing in the SEM spec table, i.e. , CENTER_X, CENTER_Y, COST_WT, DETECT_EGDE, ALGN_EDGE.
currently , there are three methods to do it , but all have its limits.

- edit in the SEM condition setting pane, but it can not see GDS 
- edit in the Sem ALGN dialog , change the parameter and apply that in server, however, this method only suit for adjust in a small range
- use text editor such as vim ,and reload the spec file

\#2. **delete the selected Row** : 

scenario : after Sem ALGN, we found invalid SEM image is loaded  , we just want to delete it in the SEM Spec table, go back the SEM condition to delete it is  unfriendly .

\#3. add function **save out Sem Spec with/wo result**, like the **save out the gaugeset with/wo results**.

These two additional functions can be visible only if the Sem Spec table is opened.

\#4. add function **save contour point result**

usage : sometimes, we have to save out the error result of the edge point for further analysis.

## Successful criteria

### Functionality criteria

Add the utility functions in the GUI and the behavior of these function are designed as the requirement.
