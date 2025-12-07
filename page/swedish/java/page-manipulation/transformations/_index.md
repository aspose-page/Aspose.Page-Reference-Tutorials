---
date: 2025-12-07
description: Lär dig hur du skalar en rektangel, förflyttar en form och tillämpar
  en affin transformation i Java med Aspose.Page för att skapa PostScript‑dokument.
language: sv
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Hur man skalar en rektangel och tillämpar transformationer med Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skalar du en rektangel och tillämpar transformationer med Aspose.Page

## Introduktion
Välkommen till en omfattande guide om hur du utnyttjar de kraftfulla funktionerna i **Aspose.Page for Java** för att utföra en mängd olika sidtransformationer. I den här handledningen lär du dig **how to scale rectangle**, översätter former, roterar objekt och **apply affine transform** tekniker när du skapar ett **PostScript document**. Dessa möjligheter låter dig bygga rika, grafikintensiva Java‑applikationer utan att behöva hantera låg‑nivå renderingskod.

## Snabba svar
- **Hur skalar jag en rektangel i Java med Aspose.Page?** Använd `document.scale()`‑metoden innan du ritar formen.  
- **Kan jag flytta (översätta) en form utan att påverka annan grafik?** Ja—spara grafik‑tillståndet, anropa `document.translate(x, y)`, rita, och återställ sedan tillståndet.  
- **Vilken klass skapar en PostScript‑fil?** `PsDocument` tillsammans med `PsSaveOptions`.  
- **Behöver jag en licens för produktionsanvändning?** En giltig Aspose.Page‑licens krävs för kommersiella distributioner.  
- **Vilken Java‑version stöds?** Aspose.Page fungerar med Java 8 och senare.

## Förutsättningar
Innan vi dyker ner i steg‑för‑steg‑guiden, se till att du har följande förutsättningar på plats:

- Grundläggande kunskaper i Java‑programmering.
- Aspose.Page for Java‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page for Java-dokumentationen](https://reference.aspose.com/page/java/).
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

## Vad betyder “how to scale rectangle” i Aspose.Page?
Att skala en rektangel ändrar dess storlek längs X‑ och Y‑axlarna samtidigt som formen bevaras. Aspose.Page tillhandahåller metoden `scale(float sx, float sy)`, som tillämpar en **affine transform** på det aktuella grafik‑tillståndet. Detta är den centrala tekniken bakom nyckelordet **how to scale rectangle**.

## Hur man översätter en form med Aspose.Page
Översättning flyttar en form till en ny plats utan att ändra dess dimensioner. Detta är kärnan i **how to translate shape**. Genom att spara grafik‑tillståndet, tillämpa `translate(dx, dy)`, rita och sedan återställa tillståndet, påverkas inte andra objekt.

## Exempel 1: Inga transformationer
Det första exemplet ritar en enkel rektangel utan någon transformation tillämpad. Detta fungerar som en grundlinje för jämförelse med senare exempel.

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
Detta exempel svarar på huvudfrågan **how to scale rectangle**. Vi minskar rektangeln till 50 % av dess ursprungliga bredd och 75 % av dess höjd.

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

## Hur man roterar en form i Java (rotate shape java)
Rotation är en annan vanlig affin operation. Även om kodsnuttarna för rotation utelämnas för korthetens skull, är mönstret identiskt: spara grafik‑tillståndet, anropa `document.rotate(angle)`, rita formen och återställ sedan. Detta demonstrerar **rotate shape java** och **how to rotate rectangle** i praktiken.

## Varför använda Aspose.Page för dessa transformationer?
- **Enhetsoberoende**: Skriv en gång, generera PostScript eller XPS utan plattforms‑specifik kod.  
- **Fin‑granulär kontroll**: Direkt åtkomst till grafik‑tillståndet låter dig kombinera översättning, skalning, skevning och rotation.  
- **Prestanda**: Låg‑overhead API som är lämpligt för batch‑bearbetning av stora dokument.  

## Vanliga användningsområden
- Generera utskrivbara fakturor med dynamiska streckkoder och logotyper.  
- Skapa tekniska diagram där exakt skalning och positionering krävs.  
- Automatisera produktionen av flersidiga rapporter i PostScript‑format.

## Slutsats
I den här handledningen utforskade vi olika transformationer i Java‑sidmanipulering med Aspose.Page for Java, med fokus på **how to scale rectangle**, **how to translate shape** och andra affina operationer. Genom att följa dessa exempel kan du förbättra dina Java‑applikationer med avancerade sidmanipuleringsmöjligheter och **create PostScript document**‑utdata som uppfyller professionella publiceringsstandarder.

## Vanliga frågor
### Kan jag använda Aspose.Page for Java för andra dokumentformat?
Aspose.Page fokuserar främst på sidmanipulering för PostScript‑ och XPS‑format.

### Var kan jag hitta fler exempel och dokumentation för Aspose.Page for Java?
Besök [Aspose.Page for Java-dokumentationen](https://reference.aspose.com/page/java/) för omfattande information.

### Finns det en gratis provversion av Aspose.Page for Java?
Ja, du kan få tillgång till en gratis provversion [här](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Page for Java?
Skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag söka gemenskapsstöd eller ställa frågor om Aspose.Page for Java?
Besök [Aspose.Page for Java‑forumet](https://forum.aspose.com/c/page/39) för gemenskapsdiskussioner.

## Vanligt förekommande frågor

**Q: Vad är skillnaden mellan `translate` och `scale`?**  
A: `translate` flyttar koordinatsystemets ursprung, medan `scale` ändrar storleken på ritade objekt längs X‑ och/eller Y‑axlarna.

**Q: Kan jag kombinera flera transformationer i ett enda grafik‑tillstånd?**  
A: Ja—genom att anropa `translate`, `scale`, `rotate` eller `shear` i följd innan du ritar, skapar du en kombinerad affin transformation.

**Q: Hur återställer jag transformationer efter att ha ritat en form?**  
A: Använd `document.writeGraphicsRestore()` för att återgå till det tidigare sparade grafik‑tillståndet.

**Q: Är det möjligt att rotera en rektangel kring dess centrum?**  
A: Absolut. Översätt rektangeln till origo, tillämpa `rotate(angle)`, och översätt sedan tillbaka innan du ritar.

**Q: Stöder Aspose.Page anti‑aliasing för mjukare grafik?**  
A: Ja—ställ in lämpliga renderingsalternativ i `PsSaveOptions` för att aktivera anti‑aliasing.

**Senast uppdaterad:** 2025-12-07  
**Testad med:** Aspose.Page for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}