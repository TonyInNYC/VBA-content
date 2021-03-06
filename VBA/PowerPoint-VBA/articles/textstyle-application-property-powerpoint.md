---
title: TextStyle.Application Property (PowerPoint)
keywords: vbapp10.chm579001
f1_keywords:
- vbapp10.chm579001
ms.prod: powerpoint
api_name:
- PowerPoint.TextStyle.Application
ms.assetid: 348c8173-7527-2b69-4b2d-2b5136784bea
ms.date: 06/08/2017
---


# TextStyle.Application Property (PowerPoint)

Returns an  **[Application](application-object-powerpoint.md)** object that represents the creator of the specified object.


## Syntax

 _expression_. **Application**

 _expression_ A variable that represents a **TextStyle** object.


### Return Value

Application


## Example

In this example, a  **[Presentation](presentation-object-powerpoint.md)** object is passed to the procedure. The procedure adds a slide to the presentation and then saves the presentation in the folder where Microsoft PowerPoint is running.


```vb
Sub AddAndSave(pptPres As Presentation)

    pptPres.Slides.Add 1, 1

    pptPres.SaveAs pptPres.Application.Path &; "\Added Slide"

End Sub
```

This example displays the name of the application that created each linked OLE object on slide one in the active presentation.




```vb
For Each shpOle In ActivePresentation.Slides(1).Shapes

    If shpOle.Type = msoLinkedOLEObject Then

        MsgBox shpOle.OLEFormat.Application.Name

    End If

Next
```


## See also


#### Concepts


[TextStyle Object](textstyle-object-powerpoint.md)

