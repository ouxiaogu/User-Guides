##  Documentation History

| Name |  Remark | Date |
--- | --- | --- |
Peng-cheng | Initial draft | 03/30/2015
 | Reviewed |  
  | Approved   |

## 1. Product definition, Motivation and objectives

TSMC ask for official release version Lua template to calculate MEEF, ILS, DOF, and BFshift in one job.

### 1.1. Background and Motivation

Benefit from automatic tool, we can get rid of the tedious click.

ILS, MEEF, BF(Shift), DOF are very important indicators for both model select in model check. 


###  1.2. Objective

Provide official release version Lua template to calculate MEEF, ILS, DOF, and BFshift in one job.
  - add **BF** & **BFShift** into process table
  - add ***ModelCD_BF***, ***ModelCD_DOF***, ***WaferCD_BFShift***, ***WaferCD_DOF***, ***AI_CD_MEEF*** & ***CD_MEEF*** into gauge table

## 2. User Scenario

The commonest user scenario is, there are several candidate models available, FEM data are sufficient, we want do model selection, then we can run this script to out ILS, MEEF, BF(Shift), DOF as indicators for the candidate models.

## 3. Scope, limitations


*Table 1. Project scope and limitations of this release*

| Release Scope of Solution | Limitations Affecting Scope |
--- | --- |
| ADI Model Calibration&Check in DUV, EUV | SEM job is not supported; BF DOF output are not supported for focus condition number < 3, job will abort.
| R3D Model is not supported | -

#### 4. Requirement Understanding
 
#### Functionality requirement

1. **ILS** is the same with *ails[gaugename] = DM.compute_ails(gauge, cd[gaugename])*
2. **MEEF** is the same with template **MEEF Calculation**, *meef_bias* can be set in the header
3. **BFShift** is the averaged wafercd best focus shift, *dof_rate* , determined DOF is calculated at best_cd*(1-dof_rate), can be set in the header. 
  - ***WaferCD_BFShift***: the WaferCD best focus shift at every gauge
  -  ***WaferCD_DOF***: the wafercd DOF of every gauge
4. **BF** is the averaged modelcd best focus. Here, the *modelcd_bestfocus = nomimal_focus + modelcd_focusshift*. *dof_rate* is the same with WaferCD's. 
 - ***ModelCD_BF***: the modelcd best focus at every gauge
 -  ***ModelCD_DOF***: the modelcd DOF of every gauge

#### GUI requirement

put *DOF_BFShift_MEEF_Integrated_4CheckJob.lua* under ../femplus/customerised/,  and add "MEEF ILS DOF and BFshift all in one" in Lua Template list to link with this Lua template.

## 5. Successful criteria

### Functionality criteria

Meet all the functionality requirements.

## 6 Document requirements

No requirement.
