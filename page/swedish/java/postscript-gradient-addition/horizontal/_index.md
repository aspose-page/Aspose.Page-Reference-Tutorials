---
date: 2025-12-07
description: Lär dig hur du lägger till en horisontell gradient i Java PostScript
  med Linear Gradient Paint Java och Aspose.Page för Java.
language: sv
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Lägg till gradient i Java PostScript med Linear Gradient Paint
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till gradient i Java PostScript med Linear Gradient Paint Java

## Introduction
I den här omfattande handledningen kommer du att upptäcka hur du skapar en vacker horisontell gradient i ett PostScript-dokument genom att utnyttja **Linear Gradient Paint Java**. Aspose.Page for Java gör det enkelt att arbeta med PostScript, PDF och andra vektorformat, och klassen `LinearGradientPaint` ger dig fin kontroll över färgövergångar. I slutet av guiden kommer du att kunna rendera gradienter på former **och** text, vilket ger dina dokument ett professionellt, iögonfallande utseende.

## Quick Answers
- **Vilket bibliotek krävs?** Aspose.Page for Java (stödjer Linear Gradient Paint Java).  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande gradient.  
- **Behöver jag en licens?** En tillfällig eller fullständig licens krävs för produktionsanvändning.  
- **Vilken JDK-version fungerar?** Java 8 eller nyare.  
- **Kan jag använda gradienten på både former och text?** Ja – du kan fylla former och konturera eller fylla text med samma gradient.

## Prerequisites
Innan du dyker ner i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.Page for Java-biblioteket. Du kan ladda ner det från [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import Packages
Börja med att importera de nödvändiga paketen i ditt Java‑projekt. Dessa importeringar ger dig åtkomst till grafikprimitive, gradient‑hantering och Aspose.Page‑API:n.

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
Först, konfigurera utmatningsströmmen, dokumentet och en rektangel som kommer att hysa gradienten.

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
Här bygger vi **Linear Gradient Paint Java**‑objektet som definierar en horisontell färgövergång. `AffineTransform` skalar gradienten så att den matchar rektangelns bredd och höjd.

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
Fyll nu rektangeln med gradienten som vi just definierade.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
Du kan också applicera samma gradient på text, vilket skapar en slående visuell effekt.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
Slutligen, konturera text med gradienten som konturfärg.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Gradienten ser utdragen ut | Felaktig `AffineTransform`‑skalning | Se till att transformens bredd och höjd matchar rektangelns dimensioner (200 × 100 i exemplet). |
| Färgerna ser bleka ut | Alfavärden är för låg | Öka alfakomponenten (det fjärde värdet i `new Color(r,g,b,alpha)`). |
| Texten syns inte | Färg (Paint) har inte satts innan text ritas | Anropa `document.setPaint(paint)` **innan** några `fillAndStrokeText`‑ eller `outlineText`‑anrop. |

## Frequently Asked Questions
### Can I use Aspose.Page for Java in commercial projects?
Ja, Aspose.Page for Java kan användas i kommersiella projekt. För licensinformation, besök [Aspose.Purchase](https://purchase.aspose.com/buy).

### Is there a free trial available?
Ja, du kan få en gratis provversion av Aspose.Page for Java [här](https://releases.aspose.com/).

### Where can I find additional documentation and support?
Besök [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) för omfattande resurser. För community‑support, kolla [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### How can I obtain a temporary license?
Du kan få en tillfällig licens från [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### What are the system requirements for Aspose.Page for Java?
Se [documentation](https://reference.aspose.com/page/java/) för detaljerade systemkrav.

**Senast uppdaterad:** 2025-12-07  
**Testad med:** Aspose.Page for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}