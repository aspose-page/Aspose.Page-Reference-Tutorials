---
date: 2025-12-03
description: Utforska hur du sparar som PostScript och beskär former med Aspose.Page
  för Java. Lär dig att ange linjestil och tillämpa beskärningsområde i Java‑grafikbeskärning.
language: sv
linktitle: Save as PostScript – Clipping in Java Page Manipulation
second_title: Aspose.Page Java API
title: Spara som PostScript – Klippning i Java‑sidhantering
url: /java/page-manipulation/clipping/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara som PostScript – Klippning i Java Page Manipulation

## Introduktion
När du behöver **save as PostScript** medan du skapar komplex grafik blir klippning din mest kraftfulla allierade. I Java Page Manipulation med Aspose.Page låter klippning dig definiera exakta områden där ritoperationer är synliga, vilket ger dig fin‑granulär kontroll över det slutgiltiga resultatet. Denna handledning guidar dig genom **how to clip shapes**, **set stroke style** och **apply clipping region** med hjälp av Aspose.Page för Java‑biblioteket, så att du kan producera polerade PostScript‑filer med självförtroende.

## Snabba svar
- **Vad betyder “save as PostScript”?**  
  Det skapar en .ps‑fil som lagrar vektorgrafik i PostScript‑språket, idealisk för utskrift och högupplöst rendering.  
- **Vilket bibliotek hanterar klippning i Java?**  
  Aspose.Page för Java tillhandahåller ett enkelt API för `java graphics clipping`.  
- **Behöver jag en licens för att köra exemplet?**  
  En temporär licens fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ändra streckens utseende?**  
  Ja—använd `set stroke style` med `BasicStroke` för att anpassa bredd, streckmönster och ändar.  
- **Är koden kompatibel med Java 8+?**  
  Absolut, exemplet körs på alla Java 8‑ eller nyare runtime‑miljöer.

## Vad är “save as PostScript” i Aspose.Page?
Att spara ett dokument som PostScript konverterar dina ritkommandon till PostScript‑sidbeskrivningsspråket. Den resulterande `.ps`‑filen kan öppnas av skrivare, visare eller konverteras till PDF utan kvalitetsförlust.

## Varför använda klippning i Java‑grafik?
Klippning låter dig **apply clipping region** för att begränsa ritning till specifika former—perfekt för att skapa masker, komplexa layouter eller fokusera uppmärksamheten på ett särskilt område av en sida. Det hjälper också till att minska filstorleken genom att undvika onödiga ritkommandon utanför det synliga området.

## Förutsättningar
Innan vi dyker ner, se till att du har:

- **Aspose.Page for Java** – ladda ner från [Aspose.Page documentation](https://reference.aspose.com/page/java/).  
- **Java Development Environment** – JDK 8 eller senare, med din favorit‑IDE (IntelliJ, Eclipse, etc.).

## Importera paket
I ditt Java‑projekt, importera de nödvändiga klasserna:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Dessa importeringar ger dig åtkomst till formdefinitioner, färghantering, streckkonfiguration och Aspose.Page‑API:t för att skapa ett PostScript‑dokument.

## Steg‑för‑steg guide

### Steg 1: Ställ in dokument och utmatningsström
Skapa först ett `PsDocument` och peka det mot en utmatningsström där **PostScript**‑filen ska skrivas.

```java
String dataDir = "Your Document Directory";
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Clipping_outPS.ps");
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro tip:** Behåll `dataDir` absolut eller använd `Paths.get(...)` för plattformsoberoende sökvägar.

### Steg 2: Skapa former och **hur man klipper former**
Nu definierar vi geometrin vi ska arbeta med—en rektangel och en cirkel. Vi **apply clipping region** med cirkeln så att endast den del av rektangeln som ligger innanför cirkeln renderas.

```java
Shape rectangle = new Rectangle2D.Float(0, 0, 300, 200);
document.setPaint(Color.BLUE);
// Clipping by shape
document.writeGraphicsSave();
document.translate(100, 100);
Shape circle = new Ellipse2D.Float(50, 0, 200, 200);
document.clip(circle);
document.fill(rectangle);
document.writeGraphicsRestore();
```

`writeGraphicsSave()` / `writeGraphicsRestore()`‑paret bevarar grafik‑tillståndet, vilket säkerställer att klippningen endast påverkar de avsedda ritkommandona.

### Steg 3: **Set stroke style** och rita konturen
Efter att ha fyllt den klippta rektangeln demonstrerar vi **java graphics clipping** genom att rita rektangelns kant med ett anpassat streckmönster.

```java
document.translate(100, 100);
BasicStroke stroke = new BasicStroke(2, BasicStroke.CAP_BUTT, BasicStroke.JOIN_MITER, 10.0f, new float[]{5.0f}, 0.0f);
document.setStroke(stroke);
document.draw(rectangle);
```

Här definierar `BasicStroke` en 2‑pixlar bred linje med ett 5‑pixlar streck, vilket visar hur du **set stroke style** för rikare visuella effekter.

### Steg 4: Stäng sidan och **save as PostScript**
Avsluta sidan och skriv ut filen.

```java
document.closePage();
document.save();
```

Din `Clipping_outPS.ps`‑fil innehåller nu en blå rektangel klippt av en cirkulär region, med en streckad kontur—redo för utskrift eller vidare konvertering.

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Filen hittades inte** | `dataDir`‑sökvägen är felaktig | Använd absolut sökväg eller `new File(dataDir).mkdirs()` innan du skapar strömmen. |
| **Klippning tillämpas inte** | Saknad `writeGraphicsSave()` / `writeGraphicsRestore()` | Se till att du omsluter klippningskoden med dessa anrop för att bevara tillståndet. |
| **Strecket visas som solid** | `BasicStroke` dash array not set | Verifiera att dash‑mönster‑arrayen (`new float[]{5.0f}`) skickas korrekt. |

## Vanliga frågor

### Är Aspose.Page kompatibel med olika dokumentformat?
Ja, Aspose.Page stöder flera dokumentformat, vilket ger flexibilitet i dokumentbehandlingsuppgifter.

### Kan jag använda Aspose.Page för Java i mina kommersiella projekt?
Absolut! Aspose.Page erbjuder en kommersiell licens för utvecklare, vilket möjliggör användning i både personliga och kommersiella projekt.

### Hur kan jag få en temporär licens för testning?
Skaffa en temporär licens för testning från [here](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta fler exempel och dokumentation?
Utforska [documentation](https://reference.aspose.com/page/java/) och [Aspose.Page forum](https://forum.aspose.com/c/page/39) för en mängd resurser.

### Finns det en gratis provversion?
Ja, du kan komma åt gratisprovet av Aspose.Page [here](https://releases.aspose.com/).

**Additional Q&A**

**Q:** *Vad gör “apply clipping region” egentligen med renderings‑pipeline?*  
**A:** Det instruerar grafikmotorn att ignorera alla ritkommandon som faller utanför den definierade formen, vilket effektivt maskerar utdata.

**Q:** *Kan jag kombinera flera klippningsformer?*  
**A:** Ja—anropa `document.clip()` flera gånger; varje anrop intersectar den aktuella klippningsregionen med den nya formen.

**Q:** *Är det möjligt att ändra klippningsformen efter ritning?*  
**A:** Endast inom ett sparat grafik‑tillstånd. Använd `writeGraphicsSave()` före klippning och `writeGraphicsRestore()` för att återgå.

## Slutsats
Genom att behärska **save as PostScript**, **how to clip shapes**, **set stroke style** och **apply clipping region** får du exakt kontroll över Java‑grafikrendering med Aspose.Page. Experimentera med olika geometrier, streckmönster och färger för att låsa upp hela potentialen i vektorbaserad dokumentskapande.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2025-12-03  
**Testad med:** Aspose.Page for Java 24.11  
**Författare:** Aspose