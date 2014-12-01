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

###Test log

Meet all the functionality criteria in rc3.

| Input Source Type | Mirror Operation on the source? | GUI Symmetry Result | Binary Symmetry Result
--- | --- | --- | ---
| None | `X Mirror` + `Y Mirror` | D2 | D2
| None | `Y Mirror` + `X Mirror` | D2 | D2
| None | `45/135 Mirror` | None | C2
| None | `45/135 Mirror` + `X Mirror` | None | C2
| D2 | no | D2 | D2
| D2 | `45/135 Mirror` | D4 | D4
| D4 | no | D4 | D4

There is only 1 bug [PLT-29590](http://jira.briontech.com/i#browse/PLT-29590) will block other functions, and it is already resolved in Longkai's debug appTflex.
