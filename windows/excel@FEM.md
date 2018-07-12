1. the spec criteria

`=IF(D3="1D",IF(L3>100,2%*L3,2),IF(L3>100,5%*L3,5))`
`=IF(Gauge_Type="1D",IF(Wafer_CD>100,2%*Wafer_CD,2),IF(Wafer_CD>100,5%*Wafer_CD,5))`

####  2. LOOKUP

##### SYNTAX

1. LOOKUP(lookup_value,  lookup_vector,  [result_vector])

The LOOKUP function vector form syntax has the following arguments (argument: A value that provides information to an action, an event, a method, a property, a function, or a procedure.):

lookup_value  Required. A value that LOOKUP searches for in the first vector. Lookup_value can be a number, text, a logical value, or a name or reference that refers to a value.
lookup_vector  Required. A range that contains only one row or one column. The values in lookup_vector can be text, numbers, or logical values.
Important  The values in lookup_vector must be placed in ascending order: ..., -2, -1, 0, 1, 2, ..., A-Z, FALSE, TRUE; otherwise, LOOKUP might not return the correct value. Uppercase and lowercase text are equivalent.

result_vector  Optional. A range that contains only one row or column. The result_vector argument must be the same size as lookup_vector. 


2. VLOOKUP(lookup_value,  lookup_vector,  [result_vector])

VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])The VLOOKUP function syntax has the following arguments (argument: A value that provides information to an action, an event, a method, a property, a function, or a procedure.):

lookup_value  Required. The value to search in the first column of the table or range. The lookup_value argument can be a value or a reference. If the value you supply for the lookup_value argument is smaller than the smallest value in the first column of the table_array argument, VLOOKUP returns the #N/A error value.
table_array  Required. The range of cells that contains the data. You can use a reference to a range (for example, A2:D8), or a range name. The values in the first column of table_array are the values searched by lookup_value. These values can be text, numbers, or logical values. Uppercase and lowercase text are equivalent. 
col_index_num  Required. The column number in the table_array argument from which the matching value must be returned. A col_index_num argument of 1 returns the value in the first column in table_array; a col_index_num of 2 returns the value in the second column in table_array, and so on.
If the col_index_num argument is:

Less than 1, VLOOKUP returns the #VALUE! error value.
Greater than the number of columns in table_array, VLOOKUP returns the #REF! error value.
range_lookup  Optional. A logical value that specifies whether you want VLOOKUP to find an exact match or an approximate match:

##### Usage

```
S2 = LOOKUP(A2, 'DF-15'!A:A)
T2 = IF(S2=A2, "PW", "NM")
```


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



##### Find the index of the minimum value

1. Output the address of the minimum cell

`=CELL("ADDRESS", INDEX(E2:E2001, MATCH(MIN(E2:E2001), E2:E2001, 0)))`

Among them,

    - `MIN`: is to find the minimum value of a cell
    - `MATCH`: similar with `lookup`, but return the relative position of the value in an array.
    - `INDEX`: Returns the value of an element in a table or an array by row and column number.



returns the number 2, because 25 is the second item in the range.


INDEX(E2:E2001, MATCH(MIN(E2:E2001), E2:E2001, 0))

