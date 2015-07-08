1. the spec criteria

`=IF(D3="1D",IF(L3>100,2%*L3,2),IF(L3>100,5%*L3,5))`
`=IF(Gauge_Type="1D",IF(Wafer_CD>100,2%*Wafer_CD,2),IF(Wafer_CD>100,5%*Wafer_CD,5))`

####  2. LOOKUP

##### SYNTAX

LOOKUP(lookup_value,  lookup_vector,  [result_vector])

The LOOKUP function vector form syntax has the following arguments (argument: A value that provides information to an action, an event, a method, a property, a function, or a procedure.):

lookup_value  Required. A value that LOOKUP searches for in the first vector. Lookup_value can be a number, text, a logical value, or a name or reference that refers to a value.
lookup_vector  Required. A range that contains only one row or one column. The values in lookup_vector can be text, numbers, or logical values.
Important  The values in lookup_vector must be placed in ascending order: ..., -2, -1, 0, 1, 2, ..., A-Z, FALSE, TRUE; otherwise, LOOKUP might not return the correct value. Uppercase and lowercase text are equivalent.

result_vector  Optional. A range that contains only one row or column. The result_vector argument must be the same size as lookup_vector. 


##### condition statistics

`{=MAX(IF($B6:$O6<>0,$B$5:$O$5))} `

Use `IF` constraints for `MAX`, `MEDIAN`, `MIN` .

Don't forget to use <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Enter</kbd> to make it works.

##### <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Enter</kbd>

In general when you use ranges in formulas or functions that normally only apply to single cells then you need <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Enter</kbd>.....so if you use

`=IF(A1=3,1,0)`

that's a straightforward formula which can be normally used with <kbd>Enter</kbd>......but if you change it to

`=SUM(IF(A1:A10=3,1,0))`

.....then you now need <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Enter</kbd>