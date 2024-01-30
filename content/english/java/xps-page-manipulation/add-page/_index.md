---
title: Add Page in Java XPS
linktitle: Add Page in Java XPS
second_title: Aspose.Page Java API
description: 
type: docs
weight: 10
url: /java/xps-page-manipulation/add-page/
---

## Complete Source Code
```java
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */



import com.aspose.xps.XpsDocument;


public class AddPageXPS {

    public static void main(String[] args) throws Exception
    {
        //ExStart:AddPage
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create new XPS Document
        XpsDocument doc = new XpsDocument(dataDir + "Aspose.xps");

        // Insert an empty page at beginning of pages list
        doc.insertPage(1, true);

        // Save resultant XPS document
        doc.save(dataDir + "AddPages_out.xps");
        //ExEnd:AddPage
    }
    
}

```
