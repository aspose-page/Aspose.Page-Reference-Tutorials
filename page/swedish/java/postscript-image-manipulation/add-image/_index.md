---
date: 2026-02-15
description: Lär dig hur du skapar PostScript‑Java‑dokument och genererar PostScript‑dokumentfiler
  med bildöversättning och rotation med hjälp av Aspose.Page för Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Skapa PostScript i Java – Lägg till bild i Java‑PostScript
url: /sv/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PostScript Java – Lägg till bild i Java PostScript

## Introduktion
I den här handledningen kommer du att lära dig hur man **create postscript java** dokument och bäddar in bilder med Aspose.Page för Java-biblioteket. Vi går igenom varje steg, från att initiera en ny PostScript-fil till att tillämpa **translate and rotate image** transformationer. I slutet kommer du att kunna generera PostScript-filer programatiskt och kontrollera bildplacering med pixel‑perfekt noggrannhet—perfekt för automatiserad rapportering, utskriftsarbetsflöden eller någon situation där du behöver **generate postscript document** output från Java.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page for Java  
- **Kan jag lägga till flera bilder?** Yes – repeat the transform and draw steps  
- **Behöver jag en licens för utveckling?** A free trial works for testing; a license is required for production  
- **Vilken Java-version stöds?** Java 8 and later  
- **Stöds bildrotation?** Absolutely – use `AffineTransform.rotate()`

## Vad är create postscript java?
En **create postscript java**-operation skapar en PostScript-sidbeskrivningsfil som kodar text, vektorgrafik och rasterbilder. Med Aspose.Page kan du bygga dessa filer direkt från Java-kod, vilket ger dig full programmatisk kontroll över layout, skalning och rotation utan att behöva en separat PostScript-tolk.

## Varför använda Aspose.Page för bildmanipulering?
- **High‑level API:** Abstraherar låg‑nivå PostScript-kommandon till enkla Java‑metoder.  
- **Cross‑platform:** Kör på alla OS som stödjer Java.  
- **Full graphics‑state control:** Spara, återställ, translatera, skala och rotera grafik efter behov.  
- **No external dependencies:** Hanterar bildladdning, formatkonvertering och inbäddning internt.

## Förutsättningar
Innan vi dyker ner i koden, se till att du har:

- Java Development Kit (JDK) installerat på ditt system.  
- Aspose.Page för Java-biblioteket. Du kan ladda ner det [här](https://releases.aspose.com/page/java/).  
- Grundläggande kunskap i Java-programmering.  

## Importera paket
För att komma igång, importera de nödvändiga paketen i ditt Java‑projekt. Använd följande kodsnutt som referens:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Steg 1: Skriv Graphics Save
Det första steget innebär att skriva graphics save till dokumentet. Detta säkerställer att eventuella transformationer eller ändringar som görs därefter kan återställas om det behövs.

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

## Steg 2: Translera och transformera (translate and rotate image)
Nästa steg är att translera dokumentet och skapa ett `BufferedImage`‑objekt från bildfilen. Applicera en serie transformationer som skalning och rotation med `AffineTransform`. Här sker **translate and rotate image**‑operationen.

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

## Steg 3: Lägg till bild i dokumentet
Nu lägger du till den transformerade bilden i dokumentet.

```java
document.drawImage(image, transform, null);
```

## Steg 4: Skriv Graphics Restore
Efter att ha lagt till bilden, skriv graphics restore för att slutföra de gjorda ändringarna.

```java
document.writeGraphicsRestore();
```

## Steg 5: Stäng aktuell sida och spara
Stäng den aktuella sidan och spara dokumentet.

```java
document.closePage();
document.save();
```

Du kan upprepa dessa steg för att lägga till flera bilder eller anpassa transformationerna efter dina krav.

## Vanliga problem och lösningar
- **FileNotFoundException:** Se till att `dataDir`‑sökvägen slutar med en filseparator (`/` eller `\\`) och att bildfilens namn matchar exakt.  
- **ImageIO.read returns null:** Verifiera att bildformatet stöds (t.ex. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` förväntar sig radianer. Konvertera grader till radianer (`Math.toRadians(degrees)`) om det behövs.  

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för Java med andra programmeringsspråk?**  
A: Aspose.Page stöder främst Java, men det finns versioner tillgängliga för andra programmeringsspråk också.

**Q: Finns det en gratis provversion tillgänglig för Aspose.Page för Java?**  
A: Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Page för Java?**  
A: Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta community‑support och diskussioner relaterade till Aspose.Page för Java?**  
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för community support.

**Q: Finns det ytterligare resurser för att köpa Aspose.Page för Java?**  
A: Du kan köpa biblioteket [här](https://purchase.aspose.com/buy).

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man **create postscript java** dokument och bäddar in bilder med Aspose.Page för Java. Utforska [dokumentationen](https://reference.aspose.com/page/java/) för mer avancerade funktioner och möjligheter, såsom vektorgrafik, textrendering och anpassade sidstorlekar.

---

**Senast uppdaterad:** 2026-02-15  
**Testat med:** Aspose.Page for Java 23.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}