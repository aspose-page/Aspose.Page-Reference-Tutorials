---
date: 2026-02-07
description: Lär dig hur du skalar en rektangel med Aspose.Page för Java, hur du förflyttar
  en form och använder en affin transformation för att skapa PostScript‑dokument.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Hur man skalar rektangel med Aspose.Page för Java
url: /sv/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skalar du rektangel med Aspose.Page för Java

## Introduktion
Välkommen till en omfattande guide för att utnyttja de kraftfulla funktionerna i **Aspose.Page for Java** för att utföra en mängd sidomtransformeringar. I den här handledningen kommer du att lära dig **how to scale rectangle**, översätta former, rotera objekt och **apply affine transform**-tekniker medan du skapar ett **PostScript-dokument**. Dessa möjligheter låter dig bygga rika, grafikintensiva Java‑applikationer utan att behöva hantera låg‑nivå renderingskod.

## Snabba svar
- **How do I scale a rectangle in Java with Aspose.Page?** Använd `document.scale()`‑metoden innan du ritar formen.  
- **Can I move (translate) a shape without affecting other graphics?** Ja—spara grafik‑tillståndet, anropa `document.translate(x, y)`, rita, och återställ sedan tillståndet.  
- **What class creates a PostScript file?** `PsDocument` tillsammans med `PsSaveOptions`.  
- **Do I need a license for production use?** En giltig Aspose.Page‑licens krävs för kommersiella distributioner.  
- **Which Java version is supported?** Aspose.Page fungerar med Java 8 och senare.

## Förutsättningar
Innan vi dyker ner i steg‑för‑steg‑guiden, se till att du har följande förutsättningar på plats:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page for Java‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- En Java‑integrerad utvecklingsmiljö (IDE) installerad på din maskin.

## Importera paket
I ditt Java‑projekt, importera de nödvändiga paketen för att använda Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Vad är “how to scale rectangle” i Aspose.Page?
Att skala en rektangel ändrar dess storlek längs X‑ och Y‑axlarna samtidigt som formen bevaras. Aspose.Page exponerar metoden `scale(float sx, float sy)`, som tillämpar en **affine transform** på det aktuella grafik‑tillståndet. Detta är den centrala tekniken bakom nyckelordet **how to scale rectangle**.

## Så översätter du form med Aspose.Page
Översättning flyttar en form till en ny plats utan att ändra dess dimensioner. Detta är kärnan i **how to translate shape**. Genom att spara grafik‑tillståndet, tillämpa `translate(dx, dy)`, rita och sedan återställa tillståndet, påverkas inte andra objekt.

## Exempel 1: Inga transformationer
Det första exemplet ritar en enkel rektangel utan någon transformation tillämpad. Detta fungerar som en referens för jämförelse med senare exempel.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Exempel 2: Översättning
Här demonstrerar vi **how to translate shape** genom att flytta grafik‑kontexten 250 enheter åt höger innan en andra rektangel ritas.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Exempel 3: Skalning
Detta exempel svarar på huvudfrågan **how to scale rectangle**. Vi krymper rektangeln till 50 % av dess ursprungliga bredd och 75 % av dess höjd.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Så roterar du form i Java (rotate shape java)
Rotation är en annan vanlig affin operation. Även om kodsnuttarna för rotation utelämnas för korthetens skull, är mönstret identiskt: spara grafik‑tillståndet, anropa `document.rotate(angle)`, rita formen och återställ sedan. Detta demonstrerar **rotate shape java** och **how to rotate rectangle** i praktiken.

## Varför detta är viktigt – Verkliga fördelar
- **Device‑independent output** – Skriv en gång och generera PostScript eller XPS utan plattforms‑specifika justeringar.  
- **Fine‑grained control** – Kombinera översättning, skalning, skevning och rotation för att uppfylla exakta layout‑krav.  
- **Performance‑oriented** – Låg‑overhead API idealiskt för batch‑bearbetning av storskaliga dokument.  

## Vanliga användningsområden
- Generera utskrivbara fakturor – till exempel en **printable invoice java**‑lösning som placerar logotyper och streckkoder exakt.  
- Skapa tekniska diagram där exakt skalning och positionering krävs.  
- Automatisera produktionen av flersidiga rapporter i PostScript‑format.

## Vanliga problem och lösningar
- **Transformation not resetting** – Para alltid `document.writeGraphicsSave()` med `document.writeGraphicsRestore()` för att undvika oönskade kvarstående effekter.  
- **Unexpected colors** – Se till att du sätter färgen efter varje transformation; grafik‑tillståndet behåller inte tidigare färginställningar efter en återställning.  
- **File size too large** – Använd `PsSaveOptions` för att aktivera kompression eller minska bildens upplösning när rastergrafik bäddas in.

## FAQ
### Kan jag använda Aspose.Page for Java för andra dokumentformat?
Aspose.Page fokuserar främst på sidmanipulation för PostScript‑ och XPS‑format.

### Var kan jag hitta fler exempel och dokumentation för Aspose.Page for Java?
Besök [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) för omfattande information.

### Finns det en gratis provversion av Aspose.Page for Java?
Ja, du kan få åtkomst till en gratis provversion [här](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Page for Java?
Skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag få community‑support eller ställa frågor om Aspose.Page for Java?
Besök [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) för community‑diskussioner.

## Vanligt förekommande frågor

**Q: What is the difference between `translate` and `scale`?**  
A: `translate` flyttar origo för koordinatsystemet, medan `scale` ändrar storleken på ritade objekt längs X‑ och/eller Y‑axlarna.

**Q: Can I combine multiple transformations in a single graphics state?**  
A: Ja—genom att anropa `translate`, `scale`, `rotate` eller `shear` sekventiellt innan ritning skapar du en kombinerad affin transformation.

**Q: How do I reset transformations after drawing a shape?**  
A: Använd `document.writeGraphicsRestore()` för att återgå till det tidigare sparade grafik‑tillståndet.

**Q: Is it possible to rotate a rectangle around its center?**  
A: Absolut. Översätt rektangeln till origo, tillämpa `rotate(angle)`, och översätt sedan tillbaka innan ritning.

**Q: Does Aspose.Page support anti‑aliasing for smoother graphics?**  
A: Ja—ställ in lämpliga renderingsalternativ i `PsSaveOptions` för att aktivera anti‑aliasing.

---

**Senast uppdaterad:** 2026-02-07  
**Testat med:** Aspose.Page for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}