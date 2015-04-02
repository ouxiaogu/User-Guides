##  Documentation History

| Name |  Remark | Date |
---- | ---- | ---- | --- 
Peng-cheng | Initial draft | 04/01/2015|
| Reviewed |  |  |
| Approved |  |  |

This Product Requirement Document (PRD) is prepared for <Product> ... : 

## 1. Problem description(background)

>note
- Why do we need this? 
- Clarify issue CASE or issue job for R&D so they can use it to understand the issue, development and unit test.
- Do not:
  + Assume people are familiar with the problem
  + No issue examples.

## 2. Introduction
### 2.1 Product definition 

>Note: 
  - What is going to be changed? Model form? functionality? Speed? Easy-of-use?
  - Clarify the spec by which this change is successful. (successful criteria )

1. 
2. Usage details:

### 2.2 Product objectives

*Table 1, Goals and objectives*

| Goal and Objectives | Criteria for Successful Completion 
|---| --- |
|goal 1 | criteria 1 |

### 2.3 Scope and limitations

*Table 2. Ticket scope coverage table*

(general)

| | Calibration | Gen | check
|---| --- | --- | --- 
|DUV ADI|  |   |   | 
DUV AEI|  |   |   |
NXE ADI|  |   |   |
NXE AEI|  |   |   |
R3D|  |   |   |
W3D+|   |   |   | 
SRAF| |   |   |
NTD|  |   |   |
iCal/SEM| | -- |    |

(for autocal)

| | autoCal 
|---| --- 
|DUV ADI|  |
DUV AEI|  |
NXE ADI|  |
NXE AEI|  |
NTD|    |
iCal/SEM| |

*Table 3. Project scope and limitations of this release*

| Release Scope of Solution | Limitations Affecting Scope |
|--- | --- |
| ADI Model Calibration in DUV, EUV | no
| ADI Model Calibration in DUV, EUV | ***DETECT_EDGE*** still with highest priority, so if ***DETECT_EDGE = 0***, nothing will change after redraw
| Scope1 | Limitation1

### 2.4 Assumption (optional)

*Table 4. Project assumptions and implications*  

|No. | Assumption | Implications for Project Success
|--- | --- |
01| Assumption 1 | Implication 1
02| Hitachi Hi-Frame contours are accurately extracted and/or averaged | linear solver  for all HHT contour iCal job
03| Hitachi Hi-Frame contours are consistent with the gauges measured with Hitachi CD-SEM | linear solver  for HHT contour and gauge mixed iCal job.


## 3. User Scenario

>note
- Situation that user need turn on this feature
- How dose user practice it step by step?
- How will user use the outcome?
- Think hard for all possible situation. Including applications.
- do not
  + Without clear definition of "it works". 
  + Assume R&D knows background, write a very simple flow.

| Scenario No. | User | Pre-condition | Action | Output | Post-condition
| --- | --- | --- | --- | ---- | --- |
|  1  |     |     |     |     |     |



## 4. Product Level Requirements

### 4.1  Interface Requirements

>Note
- Clarify which part of GUI, LUA  and XML need changes. Show example of interface
- Paste GUI example. 
- Do not
  + Do not mention this part at all.

1.

### 4.2 Other feature compatibility

>Note
- Any LMC/OPC/SMO usage or interface changes?
- General FEM+ function such as gauge check, gauge selection, iCal, modelgen, RTS functions
- e.g. AEI image output, then LMC image based detector, without contour based detector


### 4.3 Benchmark requirements

>Note
- Especially important on speed and model form features. Clarify what kind of test cases need to be added, which kind of model/LMC/OPC functions needs to be turned on.
- Do not: "LMC/OPC BM required"

| Benchmark | Description |
|--- | --- |
| Benchmark  definition 1 | Description 1

### 4.4 Performance requirements

>Note
- Combination of accuracy, functions, speed and easy-of-use with correct data and user inputs
- Give numbers as far as you could

1.  Grid dependency should not be worse than the current model.


| Performance | Description |
|--- | --- |
| Performance requirement 1 | Description 1

### 4.5 Stability requirements

>Note
- Behavior under noise and wrong data 
- How to recovery mis-click in GUI

### 4.6 DOC requirements

>Note 
- Specify in the table. If one PRD has multiple features, give JIRA ID in each table cells

| Document | New | Modified | Dropped | Unchanged |
---  | ---   | --- | --- | --- |
| User Manual |   |   |  |   
Release Note |  |   |   |
Application notes |   |   |   | 
Toolbox |   |   |   |   |

### 4.7 License requirements

>Note 
Usually key features on speed and accuracy can claim license control


| application | Key | Default value | Enabled
--- | --- | --- | --- |
 1    |     |     |     |

## 5. Release successful factor

>Note
- How will customer happily adopt the feature?
- Best practice development and training plan.
- Requirements of proof book.
- Do not:
  + Give reader an impression that no one will follow up after release


Success Factor | Measurable Criteria
--- | --- 
1    |

## 6. Risk

>Note
- Industry trend change to under-value the features
- Technical barrier or strong assumption may not true
- Performance degradation in some aspect is very possible and will impact acceptance.
- Change scope is too big to influence many other features and designs
- Do not:
  + Empty means no risk, solution is ready, guarantee delivery in spec


Nature of Risk | Risk Severity |  Likelihood
--- | --- | --- 
     |  Low/Medium/High   |   

## Reference

>Note
- Issue book links
- Case links
- Feasibility task links
