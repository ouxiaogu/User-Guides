## Usage

1. Opening Excel Workbooks in Two Separate Windows ?

Answer: start Excel a second time from the Start menu or from a shortcut on your desktop to start another excel program instance.

## Cell Rename

Formula Description (Result)
=LEFT(A2, LEN(A2)-2)  Removes last two characters from contents of A2 (Vitamin)
=RIGHT(A3, LEN(A3)-8) Removes first 8 characters from A3 (B1)


= Concatenate ("Food - ", A1)

```VBA
Sub AddTextOnRight()
'Updateby20131128
  Dim Rng As Range
  Dim WorkRng As Range
  Dim addStr As String
  'On Error Resume Next
  xTitleId = "KutoolsforExcel"
  Set WorkRng = Application.Selection
  Set WorkRng = Application.InputBox("Range", xTitleId, WorkRng.Address, Type:=8)
  addStr = Application.InputBox("Add text", xTitleId, "", Type:=2)
  For Each Rng In WorkRng
    Rng.Value = Rng.Value & addStr
  Next
End Sub
```

## Nested If function

1. The syntax for the nesting the IF function is:

`IF( condition1, value_if_true1, IF( condition2, value_if_true2, value_if_false2 ))`

```
IF condition1 THEN
   value_if_true1
ELSEIF condition2 THEN
   value_if_true2
ELSE
   value_if_false2
END IF
```
2. Logical AND

`AND(A2>=0,A2<=50)`


