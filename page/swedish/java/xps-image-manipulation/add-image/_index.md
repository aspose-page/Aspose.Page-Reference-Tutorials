---
date: 2025-12-28
description: Lär dig hur du lägger till en bild i XPS‑dokument i Java med Aspose.Page.
  Denna steg‑för‑steg‑guide visar dig hur du enkelt lägger till bilder och förbättrar
  din dokumentbehandling.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Hur man lägger till en bild i Java XPS-dokument – En enkel guide med Aspose.Page
url: /sv/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Image to Java XPS Documents with Aspose.Page

Att lägga till bilder i XPS-filer är ett vanligt krav för Java‑utvecklare som behöver berika rapporter, fakturor eller andra visuella dokument. I den här handledningen kommer du att upptäcka **hur man lägger till bild** i ett XPS‑dokument med det kraftfulla Aspose.Page för Java‑biblioteket. Vi går igenom varje steg, förklarar varför varje rad är viktig och ger dig tips för att undvika vanliga fallgropar.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page for Java  
- **Kan jag lägga till flera bilder?** Ja – upprepa bild‑läggningsstegen för varje bild  
- **Vilka bildformat stöds?** TIFF, JPEG, PNG, GIF (och andra som stöds av .NET)  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion  
- **Typisk implementeringstid?** Ungefär 10‑15 minuter för en grundläggande bildinfogning

## Introduktion
Att lägga till bilder i XPS-dokument är ett vanligt krav i många Java‑applikationer, från rapportgenerering till dokumentbehandling. Aspose.Page för Java förenklar denna uppgift genom att erbjuda effektiva metoder för att sömlöst integrera bilder i dina XPS‑filer. I den här handledningen visar vi hur man lägger till en bild i ett XPS‑dokument med Aspose.Page för Java.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
1. **Aspose.Page for Java Library** – Ladda ner och installera Aspose.Page för Java‑biblioteket från [webbplatsen](https://releases.aspose.com/page/java/).  
2. **Java Development Environment** – Säkerställ att du har en Java‑utvecklingsmiljö installerad på din maskin.

Nu går vi vidare till nästa steg.

## Importera paket
I ditt Java‑projekt importerar du de nödvändiga Aspose.Page för Java‑paketen för att få åtkomst till de erforderliga klasserna och metoderna.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Steg 1: Ställ in dokumentkatalog
Definiera sökvägen till din dokumentkatalog där XPS‑dokumentet och bildfilerna kommer att lagras.

```java
String dataDir = "Your Document Directory";
```

## Steg 2: Skapa ett nytt XPS‑dokument
Initiera ett nytt XPS‑dokument med följande kodsnutt:

```java
XpsDocument doc = new XpsDocument();
```

## Steg 3: Lägg till bild i XPS‑dokument
För att lägga till en bild, skapa en bana i XPS‑dokumentet och sätt bildpenseln med den angivna bildfilen och koordinaterna.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Steg 4: Spara resulterande XPS‑dokument
Spara det modifierade XPS‑dokumentet till den angivna katalogen.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Upprepa dessa steg för att lägga till fler bilder eller anpassa de befintliga enligt dina projektkrav.

## Slutsats
Grattis! Du har nu framgångsrikt lärt dig **hur man lägger till bild** i ett XPS‑dokument med Aspose.Page för Java. Denna färdighet är ovärderlig för att förbättra det visuella uttrycket i dina Java‑applikationer och dokument.

### Vanliga frågor
### Kan jag lägga till flera bilder i samma XPS‑dokument med Aspose.Page för Java?
Ja, du kan lägga till flera bilder genom att upprepa stegen som beskrivs i den här handledningen för varje bild.

### Vilka bildformat stöds av Aspose.Page för Java?
Aspose.Page för Java stöder olika bildformat, inklusive TIFF, JPEG, PNG och GIF.

### Finns det en provversion av Aspose.Page för Java tillgänglig?
Ja, du kan få en gratis provversion av Aspose.Page för Java från [den här länken](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
Du kan få en tillfällig licens från [den här länken](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta ytterligare support eller diskutera problem relaterade till Aspose.Page för Java?
Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för att få hjälp, dela erfarenheter och ansluta till Aspose.Page‑gemenskapen.

## Ytterligare tips & vanliga fallgropar
- **Path Geometry Accuracy** – Säkerställ att SVG‑stilens bansträng matchar bildens dimensioner; annars kan bilden bli utdragen eller avklippt.  
- **Image Brush Scaling** – Metoden `createImageBrush` tar käll‑ och destinationsrektanglar; genom att justera dessa värden kan du exakt kontrollera positionering och skalning.  
- **License Activation** – Om du kör koden utan en giltig licens kommer Aspose att lägga till ett vattenmärke i den genererade XPS‑filen.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}