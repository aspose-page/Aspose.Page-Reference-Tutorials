---
title: Add Ellipse in Java PostScript
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
description: 
type: docs
weight: 10
url: /java/postscript-shapes/add-ellipse/
---

## Complete Source Code
```java


import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;


public class AddEllipsePS {

	public static void main(String[] args) throws Exception
	{ 
		//ExStart:AddText
		// The path to the documents directory.
		String dataDir = "Your Document Directory";
		
		//Create output stream for PostScript document
		FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
		//Create save options with A4 size
		PsSaveOptions options = new PsSaveOptions();
		
		// Create new PS Document with the page opened
        PsDocument document = new PsDocument(outPsStream, options, false);
		
        //Set paint for filling rectangle
        document.setPaint(Color.ORANGE);        
        //Fill the first ellipse
        document.fill(new Ellipse2D.Float(250, 100, 150, 100));
        
        //Set paint for stroking rectangle
        document.setPaint(Color.RED);
        //Set stroke
        document.setStroke(new BasicStroke(3));
        //Stroke (outline) the second ellipse
        document.draw(new Ellipse2D.Float(250, 300, 150, 100));

        //Close current page
		document.closePage();
		//Save the document
		document.save();
	 }
}

```
