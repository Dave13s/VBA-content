
# Application.GanttBarFormatEx Method (Project)

Changes the formatting of Gantt bars from their default styles, where colors can be hexadecimal RGB values.


## Syntax

 _expression_ . **GanttBarFormatEx**( **_TaskID_** , **_GanttStyle_** , **_StartShape_** , **_StartType_** , **_StartColor_** , **_MiddleShape_** , **_MiddlePattern_** , **_MiddleColor_** , **_EndShape_** , **_EndType_** , **_EndColor_** , **_LeftText_** , **_RightText_** , **_TopText_** , **_BottomText_** , **_InsideText_** , **_Reset_** , **_ProjectName_** )

 _expression_ An expression that returns an **Application** object.


### Parameters



|**Name**|**Required/Optional**|**Data Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _TaskID_|Optional| **Long**|The identification number of the task to be changed on the Gantt chart. The default is to change the Gantt bars of the selected tasks.|
| _GanttStyle_|Optional| **Integer**|The style applied to the Gantt bar to be formatted. The value for GanttStyle is based on the position of the bar style in the  **Bar Styles** dialog box. For example, the value 3 returns the third bar style in the list.|
| _StartShape_|Optional| **Integer**|The start shape of the Gantt bar. Can be one of the  **[PjBarEndShape](0598711b-46ad-1940-103b-12345f32efd8.md)** constants.|
| _StartType_|Optional| **Integer**|The start type of the Gantt bar. Can be one of the  **[PjBarType](abc6a0b2-90bd-48d4-283a-a53618856692.md)** constants.|
| _StartColor_|Optional| **Long**|The color of the start shape of the Gantt bar. Can be a hexadecimal RGB value, where red is the last byte. For example, &amp;H00FFFF is yellow. |
| _MiddleShape_|Optional| **Integer**|The middle shape of the Gantt bar. Can be one of the  **[PjBarShape](057356dc-9cab-fbdc-563e-f81cc54a2c33.md)** constants.|
| _MiddlePattern_|Optional| **Integer**|The middle pattern of the Gantt bar. Can be one of the  **[PjFillPattern](4f6af32c-5efd-42b6-4017-20a1497c1b6d.md)** constants.|
| _MiddleColor_|Optional| **Long**|The color of the middle section Gantt bar. Can be a hexadecimal RGB value, where red is the last byte. For example, &amp;HFF00FF is purple. |
| _EndShape_|Optional| **Integer**|The end shape of the Gantt bar. Can be one of the  **PjBarEndShape** constants.|
| _EndType_|Optional| **Integer**|The end type of the Gantt bar. Can be one of the following  **PjBarType** constants: **pjDashed** , **pjFramed** , or **pjSolid** .|
| _EndColor_|Optional| **Long**|The color of the end shape of the Gantt bar. Can be a hexadecimal RGB value, where red is the last byte. For example, &amp;HFFFF00 is blue-green. |
| _LeftText_|Optional| **String**|The task field to display to the left of the Gantt bar.|
| _RightText_|Optional| **String**|The task field to display to the right of the Gantt bar.|
| _TopText_|Optional| **String**|The task field to display above the Gantt bar.|
| _BottomText_|Optional| **String**|The task field to display below the Gantt bar.|
| _InsideText_|Optional| **String**|The task field to display inside the Gantt bar.|
| _Reset_|Optional| **Boolean**| **True** if the bar formatting is reset to the default formatting of the style in the **Bar Styles** dialog box; otherwise, **False** .|
| _ProjectName_|Optional| **String**|The name of the project containing  **TaskID** if consolidation is involved. The default value is the name of the active project.|

### Return Value

 **Boolean**


## Remarks

Using the  **GanttBarFormatEx** method without specifying any arguments displays the **Format Bar** dialog box.

 To define the default styles where colors can be hexadecimal RGB values, use the **[GanttBarEditEx](b574b975-a869-31ba-e525-df8775330b0a.md)** method.


## Example

The following example displays a medium red diamond shape for the start of the task with the Task ID of 3.


```vb
Sub GanttBar_Format() 
 
    'Activate Gantt Chart view 
    ViewApply Name:="&amp;Gantt Chart" 
    GanttBarFormatEx TaskID:=3, StartShape:=pjDiamond, StartType:=pjSolid, StartColor:=&amp;H8888FF
End Sub
```

