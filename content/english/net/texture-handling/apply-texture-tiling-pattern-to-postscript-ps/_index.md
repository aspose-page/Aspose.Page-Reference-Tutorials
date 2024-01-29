---
title: Apply Texture Tiling Pattern to PostScript (PS) with Aspose.Page
linktitle: Apply Texture Tiling Pattern to PostScript (PS)
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 10
url: /net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
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
    public class AddTextureTilingPatternPS
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dataDir = "Your Document Directory";

            //Create output stream for PostScript document
            using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
            {
                //Create save options with A4 size
                PsSaveOptions options = new PsSaveOptions();

                // Create new 1-paged PS Document
                PsDocument document = new PsDocument(outPsStream, options, false);

                
                document.WriteGraphicsSave();
                document.Translate(200, 100);

                //Create a Bitmap object from image file
                using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
                {
                    //Create texture brush from the image
                    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

                    //Add scaling in X direction to the mattern
                    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix(2, 0, 0, 1, 0, 0);
                    brush.Transform = transform;

                    //Set this texture brush as current paint
                    document.SetPaint(brush);
                }

                //Create rectangle path
                System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
                path.AddRectangle(new System.Drawing.RectangleF(0, 0, 200, 100));

                //Fill rectangle
                document.Fill(path);

                //Get current paint
                Brush paint = document.GetPaint();

                //Set red stroke
                document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));
                //Stroke the rectangle
                document.Draw(path);

                document.WriteGraphicsRestore();

                //Fill text with texture pattern                
                System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
                document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

                //Outline text with texture pattern
                document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));

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