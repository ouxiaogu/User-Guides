
PRD Template

##  Documentation History

| Name |  Remark | Date |
--- | --- | --- |
Peng-cheng | Initial draft | 11/18/2014
 | Reviewed |  
  | Approved   |

## 1. Product definition, Motivation and objectives

The ticked filled is MOD-6788, variable name validation check in DM.load_variables.

### 1.1. Background and Motivation

In model calibration, we used to try some Lua terms, not only for NTD cases but also for all customerized lua terms.

There will be several separated parameters to add for every customerised term, in which case typo is very common. Since we don't have Lua debugger, it is better for us to have clarity check on the added Lua terms and related resist variables in binary.

###  1.2. Objective

Add some assertions and output specific log message in binary, so job can abort early and user can get the precise instruction to debug the typo.

## 2. User Scenario, requirement and criteria 

table 1. scenario, current behavior and expectation



## 3. Scope, limitations and assumptions

### 3.1 Scope and limitations

Jobs with customerised terms and *load_variable()* are all in the scope of the variable name sanity check function.

*Table 1. scope and limitations of this release*

| Release Scope of Solution | Limitations Affecting Scope |
--- | --- |
| ADI, AEI Model Calibration in DUV, EUV with customerised Lua terms| no
| ADI, AEI Model generation in DUV, EUV with customerised Lua terms | no 
| ADI, AEI Model check | no

## 4 Document requirements

no
