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

Hi Qian, 

I test some jobs of check ical model/job in tflex. 

baseline iCal job/model path : _/home/peyang/training/ical/ical1_ 

check jobs directory : /group/PEG/FEM/peyang/data/r1501/PLT26685 @bcnode060

The result is as the table below. 

| check job name | check job condition |  check model /check job | baseline model condition | result |
--- | ---| --- | ---| --- |
*check_ical_model* | F0, D0 | check model | F0, D6.42 | abort
*check_ical_model_copy* | F0, D6.42 | check model | F0, D6.42 | rms 1.981(8.483, 1.893)
*check_ical_job* | F0, D6.42 | check job | F0, D6.42 | rms 1.981(8.483, 1.893)

The error log of the aborted *check_ical_model* is "ERROR: Failed to find child model stack traceback: [C]: in function `lookup\_model' ...cal_model/h/data/dummydb/calibrate/job1/lua/job1.lua:168: in function  AppMain'" . It is irrelevant with this ticket, I have ask RD to have a look at the binary code .

So from the test result of *check_ical_model_copy* and  *check_ical_job*, we can see , the result of check ical model and check ical job are exactly the same  in tflex platform.

Maybe , it is a issue only happened in hardware tachyon.

Thanks,

Pengcheng
