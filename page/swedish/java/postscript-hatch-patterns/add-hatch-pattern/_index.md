---
date: 2026-02-15
description: Lär dig hur du lägger till skraffering i Java PostScript‑filer med Aspose.Page
  Java. Denna steg‑för‑steg‑guide visar den kompletta koden och tips.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Hur man lägger till skraffurmönster i Java PostScript med Aspose.Page
url: /sv/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till skraffärmönster i Java PostScript

## Introduction
Om du arbetar med **Aspose.Page Java** och undrar **hur man lägger till skraffärmönster** i ditt PostScript‑utdata, är skraffärmönster en snabb och flexibel lösning. I den här handledningen går vi igenom **hur man lägger till skraffering** i ett PostScript‑dokument, förklarar varför de är användbara och ger dig ett komplett, färdigt kodexempel. I slutet kommer du att kunna skapa visuellt tilltalande skraffade former och text med bara några rader Java.

## Quick Answers
- **Vilket bibliotek behöver jag?** Aspose.Page for Java (det “aspose page java” SDK).  
- **Vilken visuell effekt lägger vi till?** Skraffärmönster (t.ex. diagonala linjer, korsskraffering).  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **Hur många kodrader?** Ungefär 70 rader, uppdelade i tydliga steg.  
- **Kan jag använda samma metod för PDF?** Ja—Aspose.Page stödjer flera utdataformat, inklusive PDF.

## How to Add Hatch Pattern – Overview
Skraffärmönster är vektorbaserade texturer som renderas rent i alla upplösningar och fungerar bra på monokroma skrivare. Med Aspose.Page Java kan du applicera dessa mönster på former, banor och till och med text utan att behöva hantera låg‑nivå PostScript‑kommandon.

## Prerequisites
Innan du börjar, se till att du har:

- **Java‑utvecklingsmiljö** – JDK 8 eller högre och en IDE du föredrar.  
- **Aspose.Page för Java‑bibliotek** – Ladda ner den senaste JAR‑filen från den officiella sidan [here](https://releases.aspose.com/page/java/).  
- **Skrivbehörighet** till en mapp där den genererade PostScript‑filen kommer att sparas.

## Import Packages
Först, importera de nödvändiga klasserna till ditt projekt. Dessa imports ger dig tillgång till ritningsprimitiver, färghantering och Aspose.Page‑API.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Initial Parameters
Skapa output‑strömmen, konfigurera sidstorleken (A4) och definiera några layoutvariabler som kommer att återanvändas när varje skraffad kvadrat ritas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Step 2: Save Graphics State and Translate
Att spara grafik‑tillståndet låter oss återgå till det ursprungliga koordinatsystemet senare, medan `translate` flyttar origo till en bekväm startpunkt.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
Definiera en återanvändbar rektangel som kommer att representera varje skraffad cell.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
En `BasicStroke` på 2 punkter ger en skarp kontur runt varje kvadrat.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
Loopa igenom varje värde i `HatchStyle`‑enum, fyll varje kvadrat med motsvarande textur och rita sedan dess kontur. Detta är kärnan i **lägg till skraffärmönster**‑funktionaliteten.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
Återgå till det ursprungliga koordinatsystemet efter att vi har ritat rutnätet av kvadrater.

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
Här demonstrerar vi hur man målar text med en skrafferingstextur. Exemplet fyller ordet “ABC” med ett diagonal‑kors‑mönster.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
Nu konturerar vi samma text, men den här gången med en 70 % skraffering och en tjockare linje.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
Slutför sidan, skriv filen till disk och frigör resurser.

```java
document.closePage();
document.save();
```

Följ dessa steg så får du en PostScript‑fil som visar en komplett uppsättning skraffärmönster applicerade på både former och text—allt drivet av **aspose page java**.

## Why Use Hatch Patterns with Aspose.Page Java?
- **Visuell distinktion** – Skraffering fungerar även när skrivare är begränsade till monokrom utdata.  
- **Prestanda** – Texturer genereras i farten, så du undviker stora bildfiler.  
- **Stöd för flera format** – Samma kod kan rikta sig mot PDF, EPS eller SVG med minimala ändringar.

## Common Pitfalls & Tips
- **Fel i filsökväg** – Se till att `dataDir` slutar med rätt filseparator (`/` eller `\`).  
- **Ej stöd för vissa färger** – Vissa äldre PostScript‑tolkare hanterar kanske inte vissa färgrymder; håll dig till grundläggande RGB för maximal kompatibilitet.  
- **Licensvarningar** – Att köra exemplet utan en giltig licens kommer att bädda in ett vattenmärke i utdata.

## Conclusion
Att integrera skraffärmönster kan avsevärt förbättra läsbarheten och estetiken i tekniska ritningar, kartor eller annan grafik som genereras av Java. Med **Aspose.Page Java** får du ett koncist API som abstraherar låg‑nivå PostScript‑kommandon, så att du kan fokusera på design snarare än filformat‑detaljer. Nu vet du **hur man lägger till skraffärmönster** i dina PostScript‑dokument—experimentera med olika `HatchStyle`‑värden för att skapa exakt det utseende du behöver.

## Frequently Asked Questions

**Q: Kan jag använda Aspose.Page Java med andra Java‑ramverk?**  
A: Ja, biblioteket är ramverks‑agnostiskt och fungerar med Spring, Jakarta EE, Android (begränsat) och ren Java SE.

**Q: Finns en provversion av Aspose.Page Java?**  
A: Absolut. Ladda ner en gratis 30‑dagars provversion [here](https://releases.aspose.com/).

**Q: Hur får jag en tillfällig licens för utveckling?**  
A: Begär en tillfällig licens [here](https://purchase.aspose.com/temporary-license/). Den tar bort utvärderingsvattenmärken.

**Q: Var kan jag hitta fler handledningar och community‑stöd?**  
A: Besök det officiella forumet [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) för ytterligare exempel och Q&A.

**Q: Finns det omfattande dokumentation för alla klasser och metoder?**  
A: Ja, den fullständiga API‑referensen finns [here](https://reference.aspose.com/page/java/).

**Q: Kan jag rendera samma skraffärmönster till PDF istället för PostScript?**  
A: Absolut. Ändra `PsSaveOptions` till `PdfSaveOptions` (eller motsvarande) så förblir resten av koden oförändrad.

**Q: Vad ska jag göra om den genererade filen är tom?**  
A: Kontrollera att output‑strömmen pekar på en skrivbar katalog och att `document.save()` anropas efter alla ritningsoperationer.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}