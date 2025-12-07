---
date: 2025-12-07
description: Ismerje meg, hogyan adhat hozzá vízszintes színátmenetet Java PostScriptben
  a Linear Gradient Paint Java használatával az Aspose.Page for Java segítségével.
language: hu
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Gradiens hozzáadása Java PostScripthez lineáris Gradient Paint használatával
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Gradient in Java PostScript using Linear Gradient Paint Java

## Introduction
Ebben a átfogó útmutatóban megtanulja, hogyan hozhat létre egy szép vízszintes átmenetet egy PostScript dokumentumban a **Linear Gradient Paint Java** használatával. Az Aspose.Page for Java egyszerűvé teszi a PostScript, PDF és egyéb vektorgrafikus formátumok kezelését, a `LinearGradientPaint` osztály pedig finomhangolt vezérlést biztosít a színátmenetek felett. A leírás végére képes lesz a gradienteket alakzatokra **és** szövegre alkalmazni, így dokumentumai professzionális, szemrevaló hatást keltenek.

## Quick Answers
- **Milyen könyvtár szükséges?** Aspose.Page for Java (támogatja a Linear Gradient Paint Java‑t).  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy egyszerű gradient elkészítéséhez.  
- **Szükség van licencre?** Ideiglenes vagy teljes licenc szükséges a termelési környezetben.  
- **Melyik JDK verzió működik?** Java 8 vagy újabb.  
- **Használhatom a gradientet alakzatokra és szövegre egyaránt?** Igen – ugyanazzal a gradienttel töltheti ki az alakzatokat, valamint festheti vagy kitöltheti a szöveget.

## Prerequisites
Mielőtt a kódba merülnél, győződj meg róla, hogy a következők rendelkezésre állnak:

- Telepített Java Development Kit (JDK) a gépeden.  
- Aspose.Page for Java könyvtár. Letöltheted a [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) oldalról.

## Import Packages
Kezdjük a szükséges csomagok importálásával a Java projektedben. Ezek az importok hozzáférést biztosítanak a grafikai primitívekhez, a gradient kezeléséhez és az Aspose.Page API‑hoz.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Rectangle
Először állítsd be a kimeneti streamet, a dokumentumot, és egy téglalapot, amely a gradientet fogja tartalmazni.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 2: Create Horizontal Linear Gradient Paint
Itt hozunk létre egy **Linear Gradient Paint Java** objektumot, amely egy vízszintes színátmenetet definiál. Az `AffineTransform` méretezi a gradientet, hogy illeszkedjen a téglalap szélességéhez és magasságához.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Step 3: Fill the Rectangle
Most töltsd ki a téglalapot a most létrehozott gradienttel.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
Ugyanezt a gradientet alkalmazhatod szövegre is, így erőteljes vizuális hatást érhetsz el.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
Végül körvonalazd a szöveget úgy, hogy a gradient legyen a vonal színe.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| Gradient appears stretched | Incorrect `AffineTransform` scaling | Ensure the transform’s width and height match the rectangle’s dimensions (200 × 100 in the example). |
| Colors look faded | Alpha values set too low | Increase the alpha component (the fourth value in `new Color(r,g,b,alpha)`). |
| Text is not visible | Paint not set before drawing text | Call `document.setPaint(paint)` **before** any `fillAndStrokeText` or `outlineText` calls. |

## Frequently Asked Questions
### Can I use Aspose.Page for Java in commercial projects?
Yes, Aspose.Page for Java can be used in commercial projects. For licensing details, visit [Aspose.Purchase](https://purchase.aspose.com/buy).

### Is there a free trial available?
Yes, you can access a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).

### Where can I find additional documentation and support?
Visit the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) for comprehensive resources. For community support, check the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### How can I obtain a temporary license?
You can obtain a temporary license from [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### What are the system requirements for Aspose.Page for Java?
Refer to the [documentation](https://reference.aspose.com/page/java/) for detailed system requirements.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}