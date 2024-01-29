---
title: Add Text in Java XPS
linktitle: Add Text in Java XPS
second_title: Aspose.Page Java API
description: 
type: docs
weight: 10
url: /java/xps-text-manipulation/add-text/
---

## Complete Source Code
```java
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */



import java.awt.Color;

import com.aspose.page.utilities.Utils;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;

public class AddTextXPS {
    
    public static void main(String[] args) throws Exception
    {   //ExStart:AddText
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create new XPS Document
        XpsDocument doc = new XpsDocument();
        //Create a brush 
        XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
        //Add glyph to the document
        XpsGlyphs glyphs = doc.addGlyphs("Arial", 12, XpsFontStyle.Regular, 300f, 450f, "Hello World!");
        glyphs.setFill(textFill);
        // Save resultant XPS document
        doc.save(dataDir + "AddText_out.xps");
        //ExEnd:AddText
    }
}

```