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

### Dev Table

#### Adding the Developer Tab in Excel 2010

1.  Click on the **File** tab of the [ribbon](http://spreadsheets.about.com/od/r/g/Ribbon.htm) to open the file menu.
2.  Click on **Options** in the menu to open the *Excel Options* [dialog box](http://spreadsheets.about.com/od/glossary/g/90304_dialogbox.htm).
3.  Click on the *Customize Ribbon* option in the left hand window to view the available options in the right hand window of the dialog box.
4.  Under the **Main Tabs** section of the options window check off the *Developer* option.
5.  Click OK .
6.  The Developer tab should now be visible in the ribbon in Excel 2010.

 

#### Adding the Developer Tab in Excel 2007

1.  In Excel 2007, click on the [Office button](http://spreadsheets.about.com/od/no/g/office_button.htm) to open the drop down menu.
2.  Click on the **Excel Options **button located at the bottom of the menu to open the *Excel Options* dialog box.
3.  Click on the *Popular *option at the top of the left hand window of the open dialog box.
4.  Click on the *Show Developer Tab in the ribbon* in the right hand window of the open dialog box.
5.  Click OK.
6.  The Developer tab should now be visible in the ribbon.


