---
date: 2026-09-09
description: Lär dig hur du skapar gradient i Java PostScript och lägger till gradient
  på en form med Aspose.Page. Följ den här steg‑för‑steg‑guiden med kod och tips.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript radial gradient med Aspose.Page
og_description: Lär dig hur du skapar gradient i Java PostScript och lägger till gradient
  på en form med Aspose.Page. Följ den här steg‑för‑steg‑guiden med kod och tips.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Hur du skapar gradient i Java PostScript med radial fyllning
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Hur du skapar gradient i Java PostScript med radial fyllning
url: /sv/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar gradient i Java PostScript med radiell fyllning

## Introduktion
I den här handledningen kommer du att lära dig **hur man skapar gradient** grafik i ett PostScript-dokument med Java och Aspose.Page. Vi går igenom varje steg—från projektuppsättning till rendering av en cirkel fylld med en mjuk radiell gradient—så att du kan **lägga till gradient i form**-objekt omedelbart och förbättra den visuella kvaliteten i dina Java-applikationer.

## Snabba svar
- **Vad skapar den här handledningen?** A PostScript file (`.ps`) containing a circle filled with a radial gradient.  
- **Vilket bibliotek krävs?** Aspose.Page for Java (latest version).  
- **Hur lång tid tar implementeringen?** Approximately 10‑15 minutes for a working example.  
- **Behöver jag en licens?** A temporary or full license is required for production use; a free trial works for development.  
- **Kan jag återanvända koden för PDF eller SVG?** Yes—Aspose.Page supports multiple output formats with minimal changes.

## Hur man fyller form med gradient i PostScript
Du kan fylla en form med en radiell gradient i PostScript genom att skapa ett `PsDocument`, definiera ett `RadialGradientPaint`, applicera det på målformen och slutligen spara dokumentet. Detta koncisa arbetsflöde låter dig producera professionellt utseende vektorgrafik utan rasterbilder, och samma kod kan återanvändas för PDF- eller SVG-utmatning. Processen är enkel och fungerar konsekvent över alla stödda format.

## Vad är en radiell gradient?
En radiell gradient övergår färger utåt från en central punkt och skapar en mjuk, cirkulär blandning. Den är idealisk för högdagrar, knappbakgrunder eller någon visuell komponent som behöver en naturlig “glöd”-effekt. Genom att variera färgstopp och radie kan du simulera belysning, djup och materialegenskaper i ren vektorform.

## Varför använda Aspose.Page för radiella gradienter?
Aspose.Page låter dig generera enhetsoberoende vektorgrafik med ett enda Java‑API. Det stödjer över 50 in‑ och utdataformat—inklusive PostScript, PDF och SVG—samtidigt som det bevarar färgprecision och anti‑aliasing för högupplöst utdata. Biblioteket erbjuder också lättanvända gradientklasser, vilket gör komplexa visuella effekter enkla att implementera.

## Förutsättningar
- Grundläggande kunskap om Java‑programmering.  
- JDK 8 eller nyare installerat på din maskin.  
- Aspose.Page för Java‑biblioteket (ladda ner från [Aspose.Page Java-dokumentationen](https://reference.aspose.com/page/java/)).  

## Importera paket
Först importerar du de klasser vi behöver. Dessa inkluderar standard AWT‑grafiktyper och Aspose.Page‑API:n.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Steg 1: konfigurera dokumentkatalog
Definiera mappen där den genererade PostScript‑filen ska sparas. Ersätt platshållaren med en faktisk sökväg på ditt system.

```java
String dataDir = "Your Document Directory";
```

## Steg 2: skapa utdataflöde
`FileOutputStream` skriver råa byte till en fil, vilket möjliggör sparande av binär data. Att öppna ett som riktar sig mot en `.ps`‑fil låter Aspose.Page strömma den genererade PostScript‑datan direkt till disken.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Steg 3: skapa sparalternativ
`PsSaveOptions` konfigurerar hur en PostScript‑fil sparas, inklusive sidstorlek och komprimering. Du kan anpassa dessa inställningar, men standardvärdena fungerar för detta exempel.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Steg 4: skapa ps-dokument
`PsDocument` representerar ett PostScript‑dokument i minnet och tillhandahåller metoder för att lägga till sidor och grafik.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Steg 5: skapa en cirkel
`Ellipse2D.Float` beskriver en ellipsform; när bredd = höjd blir den en perfekt cirkel. Detta objekt kommer att fungera som canvas för vår gradientfyllning.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Hur man ritar cirkel med gradient
För att rita en cirkel med en radiell gradient laddar du ett `RadialGradientPaint` i grafik‑kontexten och fyller sedan den tidigare definierade ellipsen. Denna enkla operation målar formen med en mjuk färgövergång från centrum utåt, vilket skapar en visuellt tilltalande effekt.

## Steg 6: definiera gradientfärger
Förbered två arrayer: en för färgerna som kommer att visas i gradienten och en annan för motsvarande fraktionella positioner (0 = centrum, 1 = kant).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Steg 7: skapa AffineTransform
`AffineTransform` är en matris som kan translatera, rotera, skala eller skeva grafikobjekt. Här skalar och translaterar den gradienten så att den passar exakt inom cirkeln.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Steg 8: skapa radial gradient paint
`RadialGradientPaint` skapar en radiell färggradient baserad på en central punkt, radie och färgstopp.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Steg 9: sätt paint och fyll cirkel
Applicera gradient‑paint på dokumentet och fyll den tidigare definierade cirkeln. Detta är kärnan i vårt **radial gradient‑exempel** och visar hur man **fyller form med gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Steg 10: stäng sida och spara dokument
Slutför sidan, skriv innehållet till disk och stäng strömmen. Din PostScript‑fil är nu klar att visas med någon PS‑visare.

```java
document.closePage();
document.save();
```

Grattis! Du har framgångsrikt skapat ett radiellt gradient‑exempel i Java PostScript med Aspose.Page. Du har nu ett återanvändbart mönster för **fill shape with gradient** som kan anpassas till andra former och utdataformat.

## Vanliga problem och lösningar
| Problem | Lösning |
|---------|----------|
| **FileNotFoundException** när du öppnar utdataflödet | Verifiera att `dataDir` pekar på en befintlig mapp och att du har skrivbehörighet. |
| Gradienten ser platt ut eller saknas | Se till att `fractions`‑arrayen matchar längden på `colors`‑arrayen och att `AffineTransform` skalar korrekt. |
| Färgerna visas omvända | Byt ordning på färgerna i `colors`‑arrayen eller justera koordinaterna för `focus`‑punkten. |

## Vanliga frågor

**Q: Var kan jag hitta dokumentationen för Aspose.Page för Java?**  
A: Den fullständiga API‑referensen finns i [Aspose.Page Java API-dokumentationen](https://reference.aspose.com/page/java/).

**Q: Hur kan jag ladda ner Aspose.Page för Java?**  
A: Hämta den senaste JAR‑filen från [releases‑sidan](https://releases.aspose.com/page/java/).

**Q: Finns det en gratis provversion tillgänglig?**  
A: Ja—ladda ner en provversion från [Aspose gratis provnedladdningssida](https://releases.aspose.com/).

**Q: Kan jag få en tillfällig licens för testning?**  
A: Absolut, begär en från [tillfällig licens‑sida](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag få gemenskapsstöd?**  
A: Gå med i diskussionen på [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39).

## Slutsats
I den här guiden byggde vi ett komplett **radial gradient‑exempel** för ett PostScript‑dokument med Aspose.Page för Java. Genom att följa stegen har du nu ett återanvändbart mönster för **fill shape with gradient**, som du kan anpassa till PDF, SVG eller något annat format som stöds av Aspose.Page. Experimentera med olika färger, radier och former för att berika dina Java‑grafikprojekt.

---

**Senast uppdaterad:** 2026-09-09  
**Testad med:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa PostScript‑gradient i Java – Lägg till vertikal gradient](/page/java/postscript-gradient-addition/vertical/)
- [Skapa textur‑mönster i PostScript med Aspose.Page för Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page transparens‑handledning – Lägg till transparens i Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}