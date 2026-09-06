---
date: 2026-08-23
description: Lär dig hur du använder aspose.page image manipulation java för att bädda
  in och rotera bilder i PostScript-filer med tydliga Java-exempel.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Lägg till bild i Java PostScript
og_description: Lär dig hur du använder aspose.page image manipulation java för att
  bädda in och rotera bilder i PostScript-filer, med steg-för-steg Java-kodexempel.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Hur man använder aspose.page image manipulation java för att lägga till
  bild
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Hur man använder aspose.page image manipulation java för att lägga till bild
url: /sv/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du använder aspose.page bildmanipulering java för att lägga till en bild

## Introduktion
I den här handledningen kommer du att lära dig hur du **använder aspose.page image manipulation java** för att skapa PostScript-filer, bädda in rasterbilder och tillämpa översättnings‑ och rotationsomvandlingar. I slutet av guiden kommer du att kunna generera pixel‑perfekt PostScript‑utdata från Java — idealiskt för automatiserad rapportering, utskrifts‑pipelines eller vilket arbetsflöde som helst som kräver exakt bildplacering i ett PostScript‑dokument.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page for Java  
- **Kan jag lägga till flera bilder?** Ja – upprepa transform‑ och ritstegen för varje bild  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion  
- **Vilken Java‑version stöds?** Java 8 och senare  
- **Stöds bildrotation?** Absolut – använd `AffineTransform.rotate()`

## Vad är aspose.page bildmanipulering java?
`aspose.page image manipulation java` är Aspose.Page‑API:et som låter dig programatiskt bygga, redigera och rendera PostScript‑dokument från Java‑kod, inklusive full kontroll över bildplacering, skalning och rotation. Med detta API undviker du låg‑nivå PostScript‑syntax och låter biblioteket hantera formatkonvertering och inbäddning internt.

## Varför använda aspose.page för bildmanipulering?
Aspose.Page erbjuder **50+ bildformat** (inklusive JPEG, PNG, BMP, TIFF) och kan bädda in dem i PostScript utan att ladda hela dokumentet i minnet, vilket möjliggör bearbetning av filer med hundratals sidor samtidigt som minnesanvändningen hålls under 100 MB på en vanlig server. Det hög‑nivå API:et abstraherar komplexa PostScript‑kommandon, så du skriver koncis Java‑kod istället för råa PS‑operatorer.

## Förutsättningar
- Java Development Kit (JDK) 8 eller nyare installerat.  
- Aspose.Page för Java‑bibliotek – ladda ner det **[Aspose.Page för Java nedladdningssida](https://releases.aspose.com/page/java/)**.  
- Grundläggande kunskap om Java‑syntax och objekt‑orienterad programmering.

## Vad är create postscript java?
Att skapa en PostScript‑fil från Java innebär att programatiskt generera ett `.ps`‑dokument som beskriver sidlayout, vektorgrafik och rasterbilder med hjälp av PostScript‑språket. Aspose.Page översätter dina Java‑anrop till giltiga PostScript‑instruktioner, vilket gör att du kan producera utskriftsklara filer utan en separat PostScript‑tolk.

## Så lägger du till en bild med översättning och rotation steg för steg

Läs in din bild, applicera en `AffineTransform` och rita den på sidan. Följande steg beskriver den exakta sekvens du behöver följa.

### Steg 1: spara grafikstatus
Att spara grafikstatus isolerar dina transformationer så att du kan återgå senare. Detta motsvarar `gsave`‑operatorn i rå PostScript.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Steg 2: översätt och transformera (översätt och rotera bild)
Först skapar du en `BufferedImage` från källfilen, sedan bygger du en `AffineTransform` som översätter bilden till önskade koordinater och roterar den runt dess centrum. `AffineTransform.rotate` förväntar sig en vinkel i radianer, så konvertera grader med `Math.toRadians(degrees)`.

**AffineTransform** är en Java‑klass som representerar en 2‑D affinsk transformation såsom översättning, rotation, skalning eller skevning.  
**BufferedImage** är en Java‑klass som lagrar en bild i minnet som ett raster av pixlar.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Steg 3: lägg till bild i dokumentet
Efter att ha konfigurerat transformationen, rita bilden på den aktuella sidan. Biblioteket konverterar automatiskt `BufferedImage` till ett lämpligt PostScript‑bildström.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Steg 4: återställ grafikstatus
Att anropa återställning (`grestore`) återställer grafikstatus till det den var innan sparandet, vilket säkerställer att efterföljande ritkommandon inte påverkas av den tidigare transformationen.

```java
document.drawImage(image, transform, null);
```

### Steg 5: stäng aktuell sida och spara
Avsluta sidan, stäng dokumentet och skriv utdatafilen till disk.

```java
document.writeGraphicsRestore();
```

Du kan upprepa ovanstående sekvens för att bädda in ytterligare bilder, justera översättningskoordinaterna och rotationsvinkeln varje gång.

## Vanliga problem och lösningar
- **FileNotFoundException:** Verifiera att `dataDir` slutar med en filseparator (`/` eller `\\`) och att bildfilnamnet matchar exakt.  
- **ImageIO.read returns null:** Säkerställ att bildformatet finns i den stödjade listan (JPEG, PNG, BMP, GIF, TIFF).  
- **Fel rotationsvinkel:** `AffineTransform.rotate` arbetar med radianer; använd `Math.toRadians(degrees)` för att konvertera från grader.  
- **Minnesökningar på stora sidor:** Använd `Document.save` med `saveOptions.setCompress(true)` för att minska minnesavtrycket.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för Java med andra programmeringsspråk?**  
A: Kärnbiblioteket är endast Java, men Aspose tillhandahåller motsvarande API:er för .NET, C++ och Python, var och en anpassad för sin plattform.

**Q: Finns det en gratis provversion tillgänglig för Aspose.Page för Java?**  
A: Ja, du kan komma åt den gratis provversionssidan **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**Q: Hur kan jag få en tillfällig licens för Aspose.Page för Java?**  
A: Du kan få en tillfällig licens **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Var kan jag hitta community‑support och diskussioner relaterade till Aspose.Page för Java?**  
A: Besök **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** för community‑hjälp.

**Q: Finns det ytterligare resurser för att köpa Aspose.Page för Java?**  
A: Du kan köpa biblioteket **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Slutsats
Du har nu ett komplett, helhets‑exempel på **aspose.page image manipulation java** som skapar en PostScript‑fil, översätter och roterar en bild, och sparar resultatet. Utforska den fullständiga **[documentation](https://reference.aspose.com/page/java/)** för att upptäcka avancerade funktioner såsom vektorgrafik, anpassade sidstorlekar och textrendering.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## Relaterade handledningar

- [Hur man konverterar PostScript till PDF med Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Hur man lägger till gradient: Diagonal gradient i Java PostScript med Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Hur man lägger till schraffurmönster i Java PostScript med Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}