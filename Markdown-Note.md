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

#Make SEM Contour Exaction Parameters edit box active

##  Documentation History

| Name |  Remark | Date |
--- | --- | --- |
Peng-cheng | Initial draft | 11/18/2014
 | Reviewed |
  | Approved   |

## Product Background, Requirement understanding

###  1.  Background

Both iCal job and iCal-based SRAF gauge generation need to tune the contour exaction parameters ( i.e., **SK-Sigma**, **RT-Thres-Low** and **RT-Thres-High**)  in GUI manually.

#### current status

- setup a pair of new (**SK-Sigma**, **RT-Thres-Low** and **RT-Thres-High**)
- unable to preview the result contour right now
- have to click OK , exit condition dialog , reopen the condition dialog, find a specific SEM image, Toggle Preview to contour preview ...

###  2.  Requirement understanding

#### Interface requirements

No need to change. 

Though adding a "apply" button can also achieve the requirement, but this is inconsistent with the condition dialog.

#### Function requirements

1. Use keyboard "ENTER" button in **SK-Sigma**, **RT-Thres-Low** and **RT-Thres-High** edit box, to evoke another round of contour exaction of all the SEM images in the job.
2. If a contour is shown in the **SEM Contour Preview** subpane while the user press "ENTER" button, refresh the contour image.
3. Exception Scenario: if there are no SEM images, but only the edge files in the SEM condition, do nothing when press "ENTER". 

## Successful criteria

### Functionality criteria

1. Compared with the former release, all the SEM contour can be correctly exacted with the new contour exaction response of "ENTER" button.
2. The contour can be normally previewed. Toggle Preview: the SEM image is also normally previewed.



