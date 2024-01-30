---
title: Convert XPS to BMP in Java
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
description: 
type: docs
weight: 10
url: /java/xps-conversion/to-bmp/
---

## Complete Source Code
```java



import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;

public class XPStoBMP {
    public static void main(String[] args) throws Exception {
        // ExStart:XPStoBMP
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Load XPS document
        XpsDocument document = new XpsDocument(dataDir + "input.xps");
        // Initialize options object with necessary parameters.
        com.aspose.xps.rendering.BmpSaveOptions options = new com.aspose.xps.rendering.BmpSaveOptions();
        options.setSmoothingMode(com.aspose.xps.rendering.SmoothingMode.HighQuality);
        options.setResolution(300);
        options.setPageNumbers(new int[]{1, 2, 6});

        // Create rendering device for PDF format
        com.aspose.xps.rendering.ImageDevice device = new com.aspose.xps.rendering.ImageDevice();

        document.save(device, options);

        // Iterate through document partitions (fixed documents, in XPS terms)
        for (int i = 0; i < device.getResult().length; i++) {
            // Iterate through partition pages
            for (int j = 0; j < device.getResult()[i].length; j++) {
                // Initialize image output stream
                FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
                // Write image
                imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
                
                imageStream.close();
            }
        }
        // ExEnd:XPStoBMP
    }
}


```
