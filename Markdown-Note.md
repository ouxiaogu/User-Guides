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

Dec 26-28

## Training

1. Resist Model 
  - basic knowledge about resist, truncation terms, term cancellation
  - advanced resist form, and corresponding constraints
  - resist template selection by result review, 1D & 2D error distribution
2. Model Report
3. autoCal job setup

## calibration 

I have completed the resist template selection(Template C, RMS = 2.26), and fine tune resist model(RMS=1.97)

## new situation

However, at a late time of Dec 26, I was informed about the model calibration flow in GFS . They use PW gauge for Optical Model Calibration only, and use full site gauges for Resist Model calibration.
  - As to the criteria of PW gauge, Put How’s words here, The PW gauge points were decide by the Previous Owner during the sitelist preparation. Normally, for the PW points, it shall include Thru-Pitch, INV-Pitch, 1D and 2D with CD variations & miscellaneous structures at Design rule variations.

The full site gauges data are delivered to me on Dec 28.

So my workflow is re-planned: 

1.  Use the new full gauge to validate my best optical model? If the result is good, use this optical model for next stage’s tuning; if not, redo optical model fine tuning.
2.  Redo the resist model tuning.

But  optical model validation result is not so good.(gauge checked full site gauge result, RMS=24.65; It turn out gauge check wrongly modify the tone_sign of some SRIF pattern, after I rectify this error the check job RMS=8.28 ).
Hence, it seems I have to redo the model calibration flow.
