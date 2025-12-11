---
date: 2025-12-09
description: Lär dig hur du skapar PostScript‑dokument i Java och flyttar samt roterar
  en bild med Aspose.Page för sömlös bildmanipulation.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Skapa PostScript-dokument i Java – Lägg till bild i Java PostScript
url: /sv/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PostScript-dokument Java – Lägg till bild i Java PostScript

## Introduktion
I den här handledningen kommer du att lära dig hur du **create a PostScript document Java** och bädda in bilder med hjälp av Aspose.Page for Java-biblioteket. Vi går igenom varje steg, från att skapa dokumentet till att tillämpa transformationer som **translate and rotate image**-operationer. I slutet kommer du att kunna generera rika PostScript-filer programatiskt och anpassa bildplacering för att passa dina exakta layoutbehov.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page for Java  
- **Kan jag lägga till flera bilder?** Ja – upprepa transform- och ritstegen  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion  
- **Vilken Java-version stöds?** Java 8 och senare  
- **Stöds bildrotation?** Absolut – använd `AffineTransform.rotate()`

## Vad är att skapa ett PostScript-dokument i Java?
Ett PostScript-dokument är en fil i sidbeskrivningsspråket som beskriver text, grafik och bilder. Med Aspose.Page kan du programatiskt generera dessa filer i Java, vilket ger dig full kontroll över layout, grafikstatus och bildhantering utan att behöva en PostScript-tolk.

## Varför använda Aspose.Page för bildmanipulering?
- **High‑level API:** Förenklar komplexa PostScript-kommandon.  
- **Cross‑platform:** Fungerar på alla OS som stödjer Java.  
- **Full graphics state control:** Lätt att spara, återställa, översätta, skala och rotera grafik.  
- **No external dependencies:** Hanterar bildladdning och konvertering internt.

## Förutsättningar
Innan vi dyker in i koden, se till att du har:

- Java Development Kit (JDK) installerat på ditt system.  
- Aspose.Page for Java-biblioteket. Du kan ladda ner det [here](https://releases.aspose.com/page/java/).  
- Grundläggande kunskap om Java-programmering.

## Importera paket
För att komma igång, importera de nödvändiga paketen i ditt Java-projekt. Använd följande kodsnutt som referens:

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
Det första steget innebär att skriva graphics save till dokumentet. Detta säkerställer att eventuella transformationer eller ändringar som görs efteråt kan återställas om det behövs.

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

## Steg 2: Översätt och transformera (translate and rotate image)
Nästa steg är att översätta dokumentet och skapa ett `BufferedImage`-objekt från bildfilen. Applicera en serie transformationer som skalning och rotation med `AffineTransform`. Här sker **translate and rotate image**-operationen.

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
- **FileNotFoundException:** Se till att `dataDir`-sökvägen slutar med en filseparator (`/` eller `\\`) och att bildfilens namn matchar exakt.  
- **ImageIO.read returns null:** Verifiera att bildformatet stöds (t.ex. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` förväntar sig radianer. Konvertera grader till radianer (`Math.toRadians(degrees)`) om det behövs.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page for Java med andra programmeringsspråk?**  
A: Aspose.Page stödjer främst Java, men det finns versioner tillgängliga för andra programmeringsspråk också.

**Q: Finns det en gratis provversion av Aspose.Page for Java?**  
A: Ja, du kan komma åt den gratis provversionen [here](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Page for Java?**  
A: Du kan få en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta community-support och diskussioner relaterade till Aspose.Page for Java?**  
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för community-support.

**Q: Finns det ytterligare resurser för att köpa Aspose.Page for Java?**  
A: Du kan köpa biblioteket [here](https://purchase.aspose.com/buy).

## Slutsats
Grattis! Du har nu framgångsrikt lärt dig hur du **create a PostScript document Java** och bäddar in bilder med Aspose.Page for Java. Utforska [documentation](https://reference.aspose.com/page/java/) för mer avancerade funktioner och möjligheter, såsom vektorgrafik, textrendering och anpassade sidstorlekar.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}