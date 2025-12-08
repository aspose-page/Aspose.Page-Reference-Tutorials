---
date: 2025-12-08
description: Lär dig hur du lägger till skraffermönster i Java‑PostScript‑dokument
  med Aspose.Page Java. Denna steg‑för‑steg‑guide visar hur du effektivt lägger till
  skraffermönstergrafik.
language: sv
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Lägg till schraffurmönster i Java PostScript'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till skraffärmönster i Java PostScript

## Introduktion
Om du arbetar med **Aspose.Page Java** och behöver berika ditt PostScript‑utdata med strukturerade grafik, är skraffärmönster en snabb och flexibel lösning. I den här handledningen går vi igenom **hur man lägger till skraffering** i ett PostScript‑dokument, förklarar varför de är användbara och ger dig ett komplett, färdigt kodexempel. När du är klar kan du skapa visuellt tilltalande skraffade former och text med bara några få rader Java.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Page för Java (det “aspose page java” SDK).  
- **Vilken visuell effekt lägger vi till?** Skraffärmönster (t.ex. diagonala linjer, korsskraffering).  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **Hur många kodrader?** Ungefär 70 rader, uppdelade i tydliga steg.  
- **Kan jag använda samma metod för PDF-filer?** Ja—Aspose.Page stödjer flera utdataformat, inklusive PDF.

## Förutsättningar
Innan du börjar, se till att du har:

- **Java-utvecklingsmiljö** – JDK 8 eller högre och en IDE du föredrar.  
- **Aspose.Page för Java-bibliotek** – Ladda ner den senaste JAR‑filen från den officiella webbplatsen [here](https://releases.aspose.com/page/java/).  
- **Skrivbehörighet** till en mapp där den genererade PostScript‑filen sparas.

## Importera paket
Först, importera de nödvändiga klasserna till ditt projekt. Dessa imports ger dig åtkomst till ritprimitive, färghantering och Aspose.Page‑API:n.

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

## Steg 1: Ställ in initiala parametrar
Skapa utdata‑strömmen, konfigurera sidstorleken (A4) och definiera några layoutvariabler som kommer att återanvändas när varje skraffad ruta ritas.

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

## Steg 2: Spara grafikstatus och översätt
Att spara grafikstatusen låter oss återgå till det ursprungliga koordinatsystemet senare, medan `translate` flyttar origo till en bekväm startpunkt.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Steg 3: Skapa kvadrat för varje mönster
Definiera en återanvändbar rektangel som kommer att representera varje skraffad cell.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Steg 4: Ställ in penna för mönsterkvadratens kontur
En `BasicStroke` på 2 punkter ger en skarp kontur runt varje ruta.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Steg 5: Iterera genom skraffärmönster
Loopa igenom varje värde i `HatchStyle`‑enum, fyll varje ruta med motsvarande textur och rita sedan dess kontur. Detta är kärnan i **att lägga till skraffärmönster**‑funktionaliteten.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Steg 6: Återställ grafikstatus
Återgå till det ursprungliga koordinatsystemet efter att vi har ritat rutnätet av rutor.

```java
document.writeGraphicsRestore();
```

## Steg 7: Fyll text med skraffärmönster
Här demonstrerar vi hur man målar text med en skraffert textur. Exemplet fyller ordet “ABC” med ett diagonal‑kors‑mönster.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Steg 8: Konturera text med skraffärmönster
Nu konturerar vi samma text, men den här gången med en 70 % skraffering och en tjockare linje.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Steg 9: Stäng och spara dokumentet
Slutför sidan, skriv filen till disk och frigör resurser.

```java
document.closePage();
document.save();
```

Följ dessa steg, så får du en PostScript‑fil som visar en komplett uppsättning skraffärmönster applicerade på både former och text—allt drivet av **aspose page java**.

## Varför använda skraffärmönster med Aspose.Page Java?
- **Visuell distinktion** – Skraffärfyllningar fungerar även när skrivare är begränsade till monokrom utskrift.  
- **Prestanda** – Texturer genereras i farten, så du undviker stora bildfiler.  
- **Stöd för flera format** – Samma kod kan rikta sig mot PDF, EPS eller SVG med minimala ändringar.

## Vanliga fallgropar & tips
- **Filvägsfel** – Se till att `dataDir` slutar med rätt filseparator (`/` eller `\`).  
- **Ej stödda färger** – Vissa äldre PostScript‑tolkare kanske inte hanterar vissa färgrymder; håll dig till grundläggande RGB för maximal kompatibilitet.  
- **Licensvarningar** – Att köra exemplet utan en giltig licens kommer att bädda in ett vattenmärke i resultatet.

## Slutsats
Att integrera skraffärmönster kan dramatiskt förbättra läsbarheten och estetiken i tekniska ritningar, kartor eller annan grafik som genereras av Java. Med **Aspose.Page Java** får du ett koncist API som abstraherar de lågnivå‑PostScript‑kommandon, så att du kan fokusera på design snarare än filformat‑detaljer.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page Java med andra Java-ramverk?**  
A: Ja, biblioteket är ramverks‑agnostiskt och fungerar med Spring, Jakarta EE, Android (begränsat) och ren Java SE.

**Q: Finns en provversion av Aspose.Page Java?**  
A: Absolut. Ladda ner en gratis 30‑dagars provversion [here](https://releases.aspose.com/).

**Q: Hur får jag en tillfällig licens för utveckling?**  
A: Begär en tillfällig licens [here](https://purchase.aspose.com/temporary-license/). Den tar bort utvärderingsvattenmärken.

**Q: Var kan jag hitta fler handledningar och community‑support?**  
A: Besök det officiella forumet [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) för ytterligare exempel och Q&A.

**Q: Finns det omfattande dokumentation för alla klasser och metoder?**  
A: Ja, den fullständiga API‑referensen finns [here](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose