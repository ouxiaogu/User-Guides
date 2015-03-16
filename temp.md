
## 1.  User Scenario

1. Model Generation 

The ticket created is PLT-26989 .

## 2. Requirement Understanding

###  2.1. all the terms relationship

Use the terms shown in GUI to explain the relevant term in this ticket

1. **Model Explorer**->**Model Details** -> **TCC** table
  - *cdose*
  - *dose*
2. Model Windows -> **Detailed Properties**
  - **Dose Fine Tuning**: corresponding to  model's *cdose* parameter,  *cdose* will be loaded into here, but we can also set a range here.
  - **delta dose(%)**: corresponding to  model's *dose* parameter,  *dose* will be loaded into here, but we can also set a range here.
3. Model Windows -> **Conditions**: 
  - **Delta\_Dose(%)**: we can set the **Delta_Dose** condition here. 

###  2.2. non-zero dose model generation formula

` Dose (generated model) = (1+Dose(base model) )*(1+ cdose * Delta_Dose) - 1`

## 3. Scope and Other Products Impact 

Model generation module.
 
OPC, LMC will be affected if model generation module is called.
