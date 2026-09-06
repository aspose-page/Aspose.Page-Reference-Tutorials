---
date: 2026-08-18
description: Lär dig hur du lägger till skraffurmönster i Java PostScript-filer med
  Aspose.Page Java. Denna steg-för-steg-guide visar den kompletta koden och tips.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Lägg till skraffurmönster i Java PostScript
og_description: Lär dig hur du lägger till skraffurmönster i Java PostScript med Aspose.Page.
  Följ denna steg-för-steg-handledning för att snabbt skapa grafik fylld med skraffur.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Hur man lägger till skraffurmönster i Java PostScript – Aspose.Page-guide
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Hur man lägger till skraffurmönster i Java PostScript
url: /sv/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till hatch-mönster i Java PostScript

## Introduktion
Om du arbetar med **Aspose.Page Java** och undrar **hur man lägger till hatch-mönster** i ditt PostScript-utdata, är hatch-mönster en snabb och flexibel lösning. I den här handledningen går vi igenom **hur man lägger till hatch**-designer i ett PostScript-dokument, förklarar varför de är användbara och ger dig ett komplett, färdigt kodexempel. I slutet kommer du att kunna skapa visuellt tilltalande hatch-fyllda former och text med bara några rader Java.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Page för Java (det “aspose page java” SDK).  
- **Vilken visuell effekt lägger vi till?** Hatch-mönster (t.ex. diagonala linjer, korshatch).  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **Hur många kodrader?** Ungefär 70 rader, uppdelade i tydliga steg.  
- **Kan jag använda samma metod för PDF?** Ja—Aspose.Page stöder flera utdataformat, inklusive PDF.

## Vad är ett hatch-mönster?
Ett hatch-mönster är en vektorbaserad fyllning bestående av upprepade linjer eller former som skapar en textur‑effekt. Eftersom det definieras matematiskt skalas mönstret utan kvalitetsförlust, vilket gör det idealiskt för högupplöst utskrift och monokrom utdata.

## Varför använda hatch-mönster med Aspose.Page Java?
Aspose.Page stöder **10+ utdataformat** (inklusive PostScript, PDF, EPS, SVG och XPS) och kan rendera hatch-fyllningar i dokument upp till **500 sidor** utan att ladda in hela filen i minnet. Detta innebär att du får snabb prestanda, lågt minnesutnyttjande och konsekventa visuella resultat över alla stödda format.

## Så lägger du till hatch-mönster – översikt
Hatch-mönster är vektorbaserade texturer som renderas rent vid vilken upplösning som helst och fungerar bra på monokroma skrivare. Med Aspose.Page Java kan du applicera dessa mönster på former, banor och även text utan att behöva hantera låg‑nivå PostScript‑kommandon.

## Förutsättningar
- **Java-utvecklingsmiljö** – JDK 8 eller högre och en IDE du föredrar.  
- **Aspose.Page för Java‑bibliotek** – Ladda ner den senaste JAR‑filen från den officiella **Aspose.Page för Java‑nedladdningssidan** [here](https://releases.aspose.com/page/java/).  
- Du kan också bläddra bland andra Aspose‑utgåvor [here](https://releases.aspose.com/).  
- **Skrivbehörighet** till en mapp där den genererade PostScript‑filen kommer att sparas.

## Importera paket
Importerna nedan inkluderar standard Java AWT-klasser för grafikprimitiver såsom färger, penslar och geometriska former, samt Aspose.Page-klasser som tillhandahåller dokumentmodellen, hatch‑stildefinitioner och sparalternativ som krävs för att generera en PostScript‑fil.  
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

## Vad är klassen `Document`?
`Document`‑klassen är Aspose.Page:s översta objekt som representerar en enda PostScript‑fil i minnet. Alla ritoperationer utförs via detta objekt.

## Hur ställer du in output‑strömmen?
För att skriva utdata, skapa en `FileOutputStream` som pekar på den önskade filsökvägen; denna ström hanterar låg‑nivå byte‑skrivning. `PsSaveOptions` konfigurerar hur dokumentet sparas, inklusive sidstorlek och komprimering. Skapa sedan ett `Document` med ett `PsSaveOptions`‑objekt som specificerar sidstorlek, komprimering och andra PostScript‑specifika inställningar.  
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

## Hur sparar du grafik‑tillståndet och förflyttar ursprunget?
Att spara grafik‑tillståndet fångar den aktuella transformationsmatrisen, klippningsområdet och ritattributen, vilket gör att du kan återgå senare. Efter sparandet, anropa `translate(x, y)` på grafik‑objektet för att flytta ursprunget till en lämplig plats för att rita ett rutnät av hatch‑rutor.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Hur skapar du en återanvändbar ruta för varje mönster?
`Rectangle2D` representerar en rektangulär form definierad av dess position och storlek. Genom att skapa en enda instans som matchar cellens dimensioner kan du återanvända den för varje hatch‑fylld ruta, vilket minskar objektallokering och håller rit‑loopen effektiv.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Hur ställer du in en penna för mönster‑rutans kontur?
`BasicStroke` beskriver konturens tjocklek, streckmönster och ändkapslar för vektorformer. Att använda en 2‑punkts `BasicStroke` ger en tydlig kant runt varje hatch‑fylld cell, vilket säkerställer att fyllningen visuellt separeras från intilliggande rutor.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Hur itererar du genom hatch-mönster?
`HatchStyle` är en uppräkning som listar alla fördefinierade hatch‑mönster såsom diagonala, kors‑ och prickade stilar. Att loopa över `HatchStyle.values()` låter dig applicera varje mönster i tur och ordning, fylla rektangeln med en `HatchBrush` och sedan rita dess kontur.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Hur återställer du grafik‑tillståndet efter ritning?
Att anropa `restore()` på grafik‑objektet återställer transformationsmatrisen och ritinställningarna till det tidigare sparade tillståndet, vilket förhindrar kumulativa förflyttningar eller skalningar från att påverka efterföljande ritoperationer. Detta säkerställer att senare innehåll startar från det ursprungliga koordinatsystemet och använder standardattribut.  
```java
document.writeGraphicsRestore();
```

## Hur fyller du text med ett hatch-mönster?
`TextFragment` representerar ett textstycke som kan positioneras och stylas oberoende. Genom att tilldela ett `HatchBrush` med en vald `HatchStyle` till fragmentets fyllning, renderas tecknen med hatch‑texturen istället för en solid färg.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Hur konturerar du text med en annan hatch-stil?
`HatchBrush` kan också användas för konturering. För att rita en kontur, sätt fragmentets stroke till ett `HatchBrush` med en annan `HatchStyle` (t.ex. 70 % hatch) och öka penselbredden via `setStrokeWidth`. Detta renderar textens kant med sitt eget hatch‑mönster samtidigt som den fyllda insidan bevaras.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Hur stänger och sparar du dokumentet?
`document.save()` skriver det minnes‑lagrade dokumentet till den angivna output‑strömmen. Efter att alla ritkommandon är slutförda, anropa denna metod och stäng sedan `FileOutputStream` för att frigöra systemresurser och säkerställa att filen korrekt skrivs till disk.  
```java
document.closePage();
document.save();
```

Följ dessa steg, så får du en PostScript‑fil som visar en komplett uppsättning hatch‑mönster applicerade på både former och text—allt drivet av **aspose page java**.

## Vanliga fallgropar & tips
- **Filvägsfel** – Se till att `dataDir` slutar med rätt filseparator (`/` eller `\`).  
- **Ej stödda färger** – Vissa äldre PostScript‑tolkare hanterar kanske inte vissa färgrymder; håll dig till grundläggande RGB för maximal kompatibilitet.  
- **Licensvarningar** – Att köra exemplet utan en giltig licens kommer att bädda in ett vattenmärke i utdata.

## Vanligt förekommande frågor

**Q: Kan jag använda Aspose.Page Java med andra Java‑ramverk?**  
A: Ja, biblioteket är ramverks‑agnostiskt och fungerar med Spring, Jakarta EE, Android (begränsat) och ren Java SE.

**Q: Finns en provversion tillgänglig för Aspose.Page Java?**  
A: Absolut. Ladda ner en gratis 30‑dagars provversion [Aspose trial download page](https://releases.aspose.com/).

**Q: Hur får jag en tillfällig licens för utveckling?**  
A: Begär en tillfällig licens [temporary license request page](https://purchase.aspose.com/temporary-license/). Den tar bort utvärderingsvattenmärken.

**Q: Var kan jag hitta fler handledningar och community‑stöd?**  
A: Besök det officiella forumet [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) för ytterligare exempel och Q&A.

**Q: Finns det omfattande dokumentation för alla klasser och metoder?**  
A: Ja, den fullständiga API‑referensen finns [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Kan jag rendera samma hatch‑mönster till PDF istället för PostScript?**  
A: Absolut. Ändra `PsSaveOptions` till `PdfSaveOptions` (eller motsvarande) så förblir resten av koden oförändrad.

**Q: Vad ska jag göra om den genererade filen är tom?**  
A: Verifiera att output‑strömmen pekar på en skrivbar katalog och att `document.save()` anropas efter alla ritoperationer.

---

**Senast uppdaterad:** 2026-08-18  
**Testad med:** Aspose.Page för Java 24.12 (senaste vid skrivande tidpunkt)  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa textur‑mönster i PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Hur man lägger till gradient: Diagonal gradient i Java PostScript med Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Hur man konverterar PostScript till PDF med Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}