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


Dec 24 - Dec 25

## Optical Tuning Result

**findBestFocus**: bestfocus = -70 nm

**OpticalTunning**: RMS = 2.397, please refer to current setting & result in attached ppt, OpticalTuningResult.pptx

## Clarification

1. (a) Bright Field --> Binary Bright Field 
2. (c) Mask info

  mask Film n k Thickness (nm)
1 #Qz     1.563 0 35.000 --> 350.00
2 #MoSi Shading 1.76  2.14  48.000
3 #Mosi AR  1.99  0.88  12.000

3. (f) Machine ASML 1900i --> Machine Type: NXT:1950i

## Training

1. Gauge Check, FEM data check
2. SFF file setting
  - The MSD and OuterSigma value would not been loaded in, when the machine type in SFF and in tachyon GUI are not the same. With Qi-tong's help, unzip the SFF file, change MachineType in ADELler.xml from *AT:NXT1950i* to *NXT:1950i*, then generate the new SFF, and use it in job. The new SFF have been sent to How.
  - loading SFF function in current tachyon UI is very confused, give a guide flow in PLT-26633.
3. Cost Weight adjustment
  - condition weight
  - anchor pattern
  - gauge clean based on the CD through focus curve
4. Result Review
  - Overview & Statistics
  - Load Reference Job results
5. SearchConstraintsFunc:
  - "ai_location"&"defocus"
  - "InnerCorner"&"OuterCorner"
6. Resist Model 
  - introduce the Resist Model Formula
  - under fitting & over fitting 
  - Simple Resist Form in Optical Tuning, and the corresponding resist constraints


