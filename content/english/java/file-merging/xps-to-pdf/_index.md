---
title: Convert XPS to PDF in Java
linktitle: Convert XPS to PDF in Java
second_title: Aspose.Page Java API
description: 
type: docs
weight: 11
url: /java/file-merging/xps-to-pdf/
---

## Complete Source Code
```java

import com.aspose.page.utilities.Utils;
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;

public class XPStoPDF {
    public static void main(String[] args) throws Exception {
        // ExStart:XPStoPDF
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Initialize PDF output stream
        FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");

        // Load XPS document
        XpsDocument document = new XpsDocument(dataDir + "input.xps");

        // Initialize options object with necessary parameters.
        com.aspose.xps.rendering.PdfSaveOptions options = new com.aspose.xps.rendering.PdfSaveOptions();
        options.setJpegQualityLevel(100);
        options.setImageCompression(com.aspose.xps.rendering.PdfImageCompression.Jpeg);
        options.setTextCompression(com.aspose.xps.rendering.PdfTextCompression.Flate);
        options.setPageNumbers(new int[] { 1, 2, 6 });

        // Create rendering device for PDF format
        com.aspose.xps.rendering.PdfDevice device = new com.aspose.xps.rendering.PdfDevice(pdfStream);

        document.save(device, options);
        // ExEnd:XPStoPDF
    }
}
```