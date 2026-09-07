---
date: 2026-09-04
description: Lär dig hur du skapar horizontal gradient java i en PostScript-fil med
  Linear Gradient Paint Java och Aspose.Page för Java. Steg-för-steg kod, vanliga
  fallgropar och vanliga frågor.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Skapa horizontal gradient java i PostScript med Aspose
og_description: Skapa horizontal gradient java i PostScript med Linear Gradient Paint
  Java. Denna Aspose.Page-handledning visar dig de exakta stegen, förutsättningarna
  och felsökningstipsen på under 15 minuter.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Skapa horizontal gradient java i PostScript med Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Skapa horizontal gradient java i PostScript med Aspose
url: /sv/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till ett horisontellt gradient i Java PostScript med Linear Gradient Paint

## Introduktion
I den här omfattande handledningen kommer du att lära dig **hur man skapar horisontell gradient java** i ett PostScript-dokument genom att använda **Linear Gradient Paint Java**-klassen som levereras med Aspose.Page för Java. Vi går igenom varje steg—från att sätta upp projektet till att rendera gradienten på både former och text—så att du kan skapa polerad, utskriftsklar grafik på några minuter. Oavsett om du bygger en rapporteringsmotor, ett design‑automatiseringsverktyg eller en anpassad skrivardrivrutin, ger den här guiden dig exakt den kod du behöver.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page for Java (includes Linear Gradient Paint Java).  
- **Hur lång tid tar implementeringen?** About 10‑15 minutes for a basic horizontal gradient.  
- **Behöver jag en licens?** A temporary or full license is required for production use.  
- **Vilken JDK-version fungerar?** Java 8 or newer.  
- **Kan jag använda gradienten på både former och text?** Yes – the same `LinearGradientPaint` instance can fill shapes and be applied to text strokes or fills.

## Vad är en horisontell gradient och varför använda den?
En horisontell gradient blandar färger från objektets vänstra kant till dess högra kant, vilket skapar en mjuk övergång som ger djup och visuellt intresse. Den är idealisk för moderna UI-komponenter, markerade rubriker eller subtila bakgrundsskuggningar i PDF- eller PostScript-rapporter. Genom att använda **Linear Gradient Paint Java** kan du exakt kontrollera start‑ och slutfärger, opacitet och skalning, vilket säkerställer att resultatet ser skarpt ut på alla enheter eller skrivare.

## Förutsättningar
Innan du dyker ner i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.Page for Java library. Du kan ladda ner det från [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Importera paket
Börja med att importera de nödvändiga paketen i ditt Java‑projekt. Dessa importeringar ger dig åtkomst till grafikprimitive, gradient‑hantering och Aspose.Page‑API:n.

Klassen `PsDocument` representerar ett PostScript‑dokument som du kan rita grafik på.  

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

## Steg 1: skapa en rektangel
Först, konfigurera output‑strömmen, dokumentet och en rektangel som ska hysa gradienten.

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

## Steg 2: skapa horisontell linjär gradientfärg
`LinearGradientPaint` är kärnklassen som definierar en linjär färgövergång.  
Klassen `LinearGradientPaint` representerar ett paint‑objekt som renderar en gradient längs en rak linje; du specificerar start‑/slutpunkter, färgstopp och en valfri `AffineTransform` för att skala den till din form.

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

## Steg 3: fyll rektangeln
Fyll nu rektangeln med den gradient vi just definierade.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Steg 4: fyll en text med gradienten
Du kan också applicera samma gradient på text, vilket skapar en slående visuell effekt.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Steg 5: konturera en text med gradienten
Till sist, konturera text med gradienten som färg för linjen.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Gradienten ser utdragen ut | Fel `AffineTransform`‑skalning | Se till att transformens bredd och höjd matchar rektangelns dimensioner (200 × 100 i exemplet). |
| Färgerna ser bleka ut | Alphavärdena är för låga | Öka alfakomponenten (det fjärde värdet i `new Color(r,g,b,alpha)`). |
| Texten är inte synlig | Paint har inte satts innan text ritas | Anropa `document.setPaint(paint)` **innan** någon `fillAndStrokeText` eller `outlineText`‑anrop. |

## Vanliga frågor
**Q:** Kan jag använda Aspose.Page för Java i kommersiella projekt?  
**A:** Ja, Aspose.Page för Java kan användas i kommersiella projekt. För licensdetaljer, besök [Aspose.Purchase](https://purchase.aspose.com/buy) sidan.

**Q:** Finns det en gratis provperiod tillgänglig?  
**A:** Ja, du kan få en gratis provperiod av Aspose.Page för Java på [Aspose.Page for Java free trial](https://releases.aspose.com/) sidan.

**Q:** Var kan jag hitta ytterligare dokumentation och support?  
**A:** Besök [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) för omfattande resurser. För gemenskapsstöd, kolla [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Hur kan jag få en tillfällig licens?  
**A:** Du kan få en tillfällig licens från [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q:** Vad är systemkraven för Aspose.Page för Java?  
**A:** Se [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) för detaljerade systemkrav.

---

**Senast uppdaterad:** 2026-09-04  
**Testad med:** Aspose.Page för Java 24.11  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa PostScript-gradient i Java – Lägg till vertikal gradient](/page/java/postscript-gradient-addition/vertical/)
- [Hur man lägger till gradient: Diagonal gradient i Java PostScript med Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Skapa PostScript-gradient – Radiell gradient i Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}