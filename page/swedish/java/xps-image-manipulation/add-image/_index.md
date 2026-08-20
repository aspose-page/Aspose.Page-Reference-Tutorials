---
date: 2026-03-16
description: Lär dig hur asp asp och hur du lägger till en bild i XPS‑dokument i Java
  med Aspose.Page. Den här guiden visar dig hur du snabbt lägger till bilder.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: asp asp – Lägg till bild i Java XPS-dokument med Aspose.Page
url: /sv/java/xps-image-manipulation/add-image/
weight: 10
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp asp – Lägg till bild i Java XPS-dokument med Aspose.Page

Att lägga till bilder i XPS‑filer är ett vanligt behov för Java‑utvecklare som vill berika rapporter, fakturor eller andra visuella dokument. I den här handledningen lär du dig **hur du lägger till en bild** i ett XPS‑dokument med det kraftfulla Aspose.Page för Java‑biblioteket, och du får se varför **asp asp**‑metoden gör processen pålitlig och snabb. Vi går igenom varje steg, förklarar varför varje rad är viktig och ger praktiska tips för att undvika vanliga fallgropar.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page för Java  
- **Kan jag lägga till flera bilder?** Ja – upprepa stegen för bildinfogning för varje bild  
- **Vilka bildformat stöds?** TIFF, JPEG, PNG, GIF (och andra som stöds av .NET)  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion  
- **Typisk implementeringstid?** Cirka 10‑15 minuter för en grundläggande bildinfogning  

## asp asp: Lägg till bilder i XPS‑dokument
Den **asp asp**‑metodologi som kretsar kring ett enkelt, återanvändbart mönster: skapa ett dokument, definiera en sökväg, applicera en bildborste och spara. Detta mönster håller koden ren och gör det enkelt att infoga ytterligare grafik senare.

## Vad är Aspose.Page för Java?
Aspose.Page är ett dedikerat API som låter dig skapa, redigera och rendera XPS‑ (XML Paper Specification) dokument utan att behöva Microsoft XPS Viewer. Det abstraherar de lågnivå‑detaljer som hör till XPS‑markup, så att du kan fokusera på den visuella layouten av dina dokument.

## Varför lägga till bilder i XPS?
- **Professionellt utseende:** Bilder som logotyper, diagram eller produktfoton ger dina dokument ett polerat intryck.  
- **Varumärkeskonsistens:** Genom att bädda in ditt företagslogo säkerställer du att varje genererad faktura eller rapport bär ditt varumärke.  
- **Dynamiskt innehåll:** Du kan programatiskt infoga QR‑koder, streckkoder eller användargenererad grafik vid körning.

## Introduktion
Att lägga till bilder i XPS‑dokument är ett vanligt krav i många Java‑applikationer, från rapportgenerering till dokumentbehandling. Aspose.Page för Java förenklar denna uppgift genom effektiva metoder för att sömlöst integrera bilder i dina XPS‑filer. I den här handledningen visar vi hur du lägger till en bild i ett XPS‑dokument med Aspose.Page för Java.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
1. **Aspose.Page för Java‑bibliotek** – Ladda ner och installera Aspose.Page för Java‑biblioteket från [website](https://releases.aspose.com/page/java/).  
2. **Java‑utvecklingsmiljö** – Säkerställ att du har en Java‑utvecklingsmiljö installerad på din maskin.

Nu går vi vidare till nästa steg.

## Importera paket
I ditt Java‑projekt importerar du de nödvändiga Aspose.Page för Java‑paketen för att få åtkomst till de klasser och metoder som krävs.

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
För att lägga till en bild, skapa en sökväg i XPS‑dokumentet och ange bildborsten med den angivna bildfilen och koordinaterna.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Steg 4: Spara det resulterande XPS‑dokumentet
Spara det modifierade XPS‑dokumentet till den katalog du specificerat.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Upprepa dessa steg för att lägga till fler bilder eller anpassa de befintliga enligt dina projektkrav.

## Vanliga problem och lösningar
- **Bilden blir utdragen:** Kontrollera att källrektangeln (`new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f)`) matchar bildens faktiska dimensioner. Justera destinationsrektangeln för att behålla bildförhållandet.  
- **Vattenstämpel visas:** Om du kör koden utan en giltig licens lägger Aspose till en vattenstämpel. Aktivera din licens tidigt i applikationen för att undvika detta.  
- **FileNotFoundException:** Säkerställ att `dataDir` pekar på rätt mapp och att bildfilens namn (`QL_logo_color.tif`) stämmer med filen på disken.

## Slutsats
Grattis! Du har nu lärt dig **hur du lägger till en bild** i ett XPS‑dokument med Aspose.Page för Java. Denna färdighet är ovärderlig för att förbättra det visuella uttrycket i dina Java‑applikationer och dokument. Genom att följa **asp asp**‑mönstret kan du enkelt utöka exemplet för att infoga flera grafikobjekt, skala dem dynamiskt eller till och med generera diagram i farten.

### Vanliga frågor
### Kan jag lägga till flera bilder i samma XPS‑dokument med Aspose.Page för Java?
Ja, du kan lägga till flera bilder genom att upprepa stegen som beskrivs i den här handledningen för varje bild.

### Vilka bildformat stöds av Aspose.Page för Java?
Aspose.Page för Java stöder olika bildformat, inklusive TIFF, JPEG, PNG och GIF.

### Finns det en provversion av Aspose.Page för Java?
Ja, du kan skaffa en gratis provversion av Aspose.Page för Java via [this link](https://releases.aspose.com/).

### Hur får jag en tillfällig licens för Aspose.Page för Java?
Du kan få en tillfällig licens via [this link](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta ytterligare support eller diskutera frågor relaterade till Aspose.Page för Java?
Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att få hjälp, dela erfarenheter och ansluta till Aspose.Page‑gemenskapen.

---

**Senast uppdaterad:** 2026-03-16  
**Testat med:** Aspose.Page för Java 23.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}