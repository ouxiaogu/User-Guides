# PLT-26989, Update gauge line address through cutline drawn in RTS window

##  Documentation History

| Name |  Remark | Date |
--- | --- | --- |
Peng-cheng | Initial draft | 06/17/2014
Peng-cheng | Revised | 03/11/2015
 | Reviewed |  
  | Approved   |


## 1.  User Scenario 

1. If we see some hard bridging or necking, we can put a gauge line there (but model has CD) and specify waferCD=0
2. If we want LMC detector can capture it, we can specify waferCD<<LMC detector threshold.
3. If we have “ghost contour” in some pattern (not gauge pattern), we can put a gauge line there to use tightConstraint=1 to prevent center wrong tone_sgn
4. For R3D and SRAF model, user may add more gauge line to specify printability

The ticket created is PLT-26989 .

## 2. Requirement

### UI requirements

1. Add a radio button in **Info -> Measure Mode**: **Draw a Gauge Line**, the drawing mode is identical to  **H/V/45/135**
2. Click measure icon, drag the left mouse click to draw a line, pop up a information MessageBox(a new window is OK), add a **CANCEL** button in this MessageBox.

### Functionality requirements

1. Click **Draw a Gauge Line** mode, draw a line and pop out a the distance information MessageBox
 - If click **OK**: add a row in the GaugeFile, use the coordination of the drawn line as the  *(head_x, head_y) & (base_x, base_y)*, let the wafercd = 0, all the other columns keep the same with currently viewed gauge.
 - If click **CANCEL**: do nothing.

## 3. Successful criteria

The new gauge is correctly added

## 4. Scope of function

GDSViewer

## 5. Other Product Impact

If the code is shared in GDS viewer, then LMC, OPC, SMO will also have this function
