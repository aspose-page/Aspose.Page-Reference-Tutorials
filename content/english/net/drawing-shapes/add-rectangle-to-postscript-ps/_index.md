---
title: Add Rectangle to PostScript (PS) with Aspose.Page for .NET
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 12
url: /net/drawing-shapes/add-rectangle-to-postscript-ps/
---

## Complete Source Code
```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;

namespace CSharp.WorkingWithShapes
{
    public class AddRectanglePS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";

            //Create output stream for PostScript document
            using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
            {
                //Create save options with A4 size
                PsSaveOptions options = new PsSaveOptions();

                // Create new 1-paged PS Document
                PsDocument document = new PsDocument(outPsStream, options, false);

                //Create graphics path from the first rectangle
                System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
                path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));
                //Set paint
                document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
                //Fill the rectangle
                document.Fill(path);

                //Create graphics path from the second rectangle
                path = new System.Drawing.Drawing2D.GraphicsPath();
                path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));
                //Set stroke
                document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
                //Stroke (outline) the rectangle
                document.Draw(path);

                //Close current page
                document.ClosePage();

                //Save the document
                document.Save();
            }
            // ExEnd:1
        }
    }
}

```