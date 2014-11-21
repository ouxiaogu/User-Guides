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


PRD Template

# iCal Improvements to support HHT contour

## Product Background, Requirement understanding

###  1.  Background 

Currently, iCal requires user to supply SEM images (in .pgm or .tiff formats), and uses its Brion internal contour-tracing algorithm to extract contours from the SEM images. 

Its drawbacks: the contours extracted by Brion's Algorithm  are very likely different from the contours & gauge  extracted by customer's SEM machine .

Its consequence of the drawbacks: When CD-SEM-extracted gauges are fitted together with iCal-extracted contours,  the linear solver may hard to  find an optimal solution, even fail to converge.
  
The solution: The gauge and SEM contours are extracted by Hitachi Hi-Frame.

The extracted contours are typically stored in a certain layer of a .gds (or .oas) file. Which may contain other layers such as a design layer, a pre-RET layer, a post-RET layer, and a bounding box layer (which bounds the SEM image).

Besides, Hitachi Hi-Frame provides an option to average several extracted contours to produce an average contour, which is also useful in detecting “flyer” contours .

The ticket created is PLT-28765 & MOD-5426.

###  2.  Requirement understanding
 
#### Function requirements

\#1. currently, we have a standalone tool: GDS2SEMSpec.  
  
  - This tool can read in GDS file with extracted SEM contour, and output corresponding SEM spec file and edge point file.
  - but This tool will only handle GDS files that put bounding box to layer 20:0, and contours to layer 100:0.
 
\#2. Target: For future development, we need to expand the flexibility that user can specify the layer number of input data. 

\#3. other module compact:  iCal-based SRAF gauge generation.

Basically, we can bypass the internal contour tracing algorithm and directly use Hitachi contours of SRAF patterns to determine each SRAF’s printability (i.e., must-print, must-not-print). User can input a GDS file containing the SRAF contours, and the output of the SRAF gauge generation tool should be a Tachyon SRAF gauge file ready to be used in SRAF model calibration.

\#4. Risk: accurate alignment

About the SEM contour alignment ,  these SEM contours may have been pre-aligned by Hitachi Hi-Frame based on the design patterns, and therefore may not be perfectly accurate. However, these pre-aligned contours will  be re-aligned by iCal during the job run. We can rely on the current alignment functionality of iCal. 

\#5. backward-compatibility : 

iCal should continue to support a “mix-and-match” SEM Spec file , which contains  SEM images or edge point files from Hitachi contour or both.

####  Interface requirements

\#1.  Add a button to current iCAL setup GUI.
\#2.  Upon clicking new button, new dialog window will pop up:

  - Browse GDS Path to open GDS file with contour. 
  - Four input edit box to input the user defined layer :
    - BBox layer ID : for defining layer/datatype of bounding box. (20)
    - Contour layer ID : for defining layer/datatype of contour . (100)
    - Shift X[nm]  : the amount to be shifted on X direction. This shift_x will be added to center\_X (0)
    - Shift Y[nm] : the amount to be shifted on Y direction. and shift_Y will be added to center\_Y.  (0) 
  -  click "Gen Sem Spec" to process  contours and save output (SEM spec and edge point file) to right place in job setup.
  - For each contour, Center_X and Center_Y are automatically populated according to the bounding box coordinates.
  - User can edit/add/delete individual contours.

\#3.  GUI should allow preview of the Hitachi contours.

## Scope, limitations and assumptions
 
###  Scope

1. Support TFLEX FEM+ only.
2. Can be used for ADI models in DUV and EUV.
3. Compatible with M3D, R3D, W3D, SRAF, and AEI model.
4.  The resulting model should support all applications in LMC/OPC/FMO/SMO, and real-time simulation (RTS).

### Assumptions
1. Hitachi Hi-Frame contours are accurately extracted and/or averaged.
2. Hitachi Hi-Frame contours are consistent with the gauges measured with Hitachi CD-SEM (i.e., same algorithm and settings are used).


##  Usage scenario

1.  User opens “Condition Setting” dialog box and inputs SEM Spec file for a given FEM condition.
2.  User can click a button to call GDS2SEMSpec. This will pop up a window to ask for GDS with contour. 
3.  With the binary, corresponding SEM spec items will be populated in to the SEM spec window. The corresponding edge points will be save to local job setup location.
4.  For these Hitachi contours, iCal’s internal contour tracing algorithm is turned off.
5.  User can also input traditional SEM pictures (in .tiff or .pgm formats), for which iCal’s internal contour tracing algorithm is turned on.
6.  User can preview the Hitachi contours and also contours traced by iCal from the supplied SEM pictures.
7.  User can perform model calibration with any mix of the following: regular CD-based gauges, Hitachi contours, and contours traced from SEM images.
8.  If user inputs GDS files containing SRAF contours, user can run a special lua to automatically generate SRAF gauges 


## Successful criteria

### Model Fitting and prediction Performance criteria 

1.  Models calibrated with Hitachi contours (mainly 2D) together with gauges should have better fitting and prediction accuracy than models calibrated with SEM images (mainly 2D) and gauges, due to higher consistency of the former

###  Stability requirements

1.  Grid dependency should not be worse than the current model.
2.  The model stability can be explicitly controlled by job options and/or application tools.

###  Benchmark requirements

1.  Benchmark model calibration speed with new features turned ON/OFF.
2.  OPC/LMC/SMO integration test. For example, compare OPC outputs of new and old models with different layer/technode cases. Make sure that the new model has "production line quality".

##  Document requirements

Chapter 6. Image-Assistant Calibration (iCal)
Chapter 8. Section: iCal-based SRAF Gauge Generation

##  Reference

1.  Assessing SEM contour based OPC models quality using rigorous simulation, F. Weisbuch et al., Proc. of SPIE. 9051, Advances in Patterning Materials and Processes XXXI, 90510A. (March 27, 2014)
2.  Bringing SEM contour based OPC to production, F. Weisbuch et. al., Proc. of SPIE. 9052, Optical Microlithography XXVII, 905224. (March 31, 2014)

## Additional Description in GUI side

\#1. Input:

- GDS Path :
- Layer & Shift Edit Box
  - BBox layer ID : for defining layer/datatype of bounding box. (20)
  - Contour layer ID : for defining layer/datatype of contour . (100)
  - Shift X[nm]  : the amount to be shifted on X direction. This shift\_x will be added to center\_X (0)
  - Shift Y[nm] : the amount to be shifted on Y direction. and shift\_Y will be added to center\_Y.  (0) 
- Chip X/Y v.s. Processing Windows mapping file
  - In most cases , format of the mapping file is `Chip_X Chip_Y  Delta_Focus(nm) Delta_Dose(%)`
  - For "mix and match" chip ID , e.g. Test#-002#-001 , then `Chip_X` and `Chip_Y` will be empty.
  - For Double Pattern Job, format of the mapping file is like `Chip_X Chip_Y  PSM:Delta_Focus(nm) PSM:Delta_Dose(%) binary:Delta_Focus(nm), binary:Delta_Dose(%)`

\#2. output:

- contour edge file and contour Spec file

\#3. material&job:

gds @ bcnode060:/h/user/peyang/training/ical/hht_setup
job @ bcnode060:/h/user/peyang/training/ical/

|  job | GDS | Normal `Chip_X & Chip_Y`
--- | ---| ---
`HHT_t1` | `All_Chip_20.gds` | Yes 
`HHT_t1` | `All_Chip_invalid_cell_name.gds` | Yes 
`HHT_t2` | `Averaged_All_Chip.gds` | Yes 
`HHT_t2_mixname` | `Averaged_All_Chip_renamed.gds` | `chip_00_01` rename to cell1 
