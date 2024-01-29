---
title: Add Text using Unicode String in Java PostScript
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
description: 
type: docs
weight: 11
url: /java/postscript-text-manipulation/add-text-unicode/
---

## Complete Source Code
```java
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */



import com.aspose.page.utilities.Utils;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;

public class AddTextUsingUnicodeString {
    
    public static void main(String[] args) throws Exception
    {
        //ExStart:AddTextUsingUnicodeString
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create new XPS Document
        XpsDocument doc = new XpsDocument();
        // Add Text
        XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
        XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
        glyphs.setBidiLevel(1);
        glyphs.setFill(textFill);
        // Save resultant XPS document
        doc.save(dataDir + "AddEncodingText_out.xps");
        //ExEnd:AddTextUsingUnicodeString
    }

    
}

```