---
date: 2026-02-13
description: Lär dig hur du fyller en form med gradient och ritar en cirkel med gradient
  i Java PostScript med Aspose.Page. Steg‑för‑steg‑guide med kod och tips.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Fyll form med gradient: Java PostScript radialexempel'
url: /sv/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fyll form med gradient: Java PostScript radialexempel

## Introduktion
I den här handledningen lär du dig hur du **fill shape with gradient** genom att bygga ett radialgradientexempel för ett PostScript‑dokument med Aspose.Page för Java. Vi går igenom varje steg—från att sätta upp projektet till att rendera en cirkel fylld med en mjuk radialgradient—så att du snabbt kan lägga till iögonfallande grafik i dina Java‑applikationer.

## Snabba svar
- **Vad skapar den här handledningen?** En PostScript‑fil (`.ps`) som innehåller en cirkel fylld med en radialgradient.  
- **Vilket bibliotek krävs?** Aspose.Page for Java (senaste versionen).  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett fungerande exempel.  
- **Behöver jag en licens?** En tillfällig eller full licens krävs för produktionsbruk; en gratis provversion fungerar för utveckling.  
- **Kan jag återanvända koden för PDF eller SVG?** Ja—Aspose.Page stödjer flera utdataformat med minimala ändringar.

## Hur man fyller form med gradient i PostScript
Innan vi dyker ner i koden, låt oss klargöra varför **fill shape with gradient** är viktigt. Att använda gradienter ger din grafik ett professionellt, tredimensionellt intryck utan att behöva rasterbilder. Med Aspose.Page kan du applicera samma gradientlogik på vilken vektorform som helst—cirklar, rektanglar eller anpassade banor—över alla stödda utdataformat (PostScript, PDF, SVG).

## Vad är en radialgradient?
En radialgradient övergår färger från en central punkt och skapar en mjuk, cirkulär blandning. Den är idealisk för högdagrar, knappbakgrunder eller någon visuell komponent som behöver en naturlig “glöd‑effekt”.

## Varför använda Aspose.Page för radialgradienter?
- **Device‑independent rendering** – fungerar likadant på PostScript, PDF, SVG och mer.  
- **Full Java integration** – ingen native kod, bara rena Java‑API:er.  
- **High‑quality output** – stödjer anti‑aliasing och färgrymdskontroll.

## Förutsättningar
Innan vi går vidare, se till att du har:

- Grundläggande kunskap i Java‑programmering.  
- JDK 8 eller nyare installerat på din maskin.  
- Aspose.Page for Java‑biblioteket (ladda ner från [Aspose.Page Java-dokumentation](https://reference.aspose.com/page/java/)).  

## Importera paket
Först importerar vi de klasser vi behöver. Dessa inkluderar standard‑AWT‑grafiktyper och Aspose.Page‑API:n.

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

## Steg 1: Ställ in dokumentkatalogen
Definiera mappen där den genererade PostScript‑filen ska sparas. Ersätt platshållaren med en faktisk sökväg på ditt system.

```java
String dataDir = "Your Document Directory";
```

## Steg 2: Skapa utdataflöde
Öppna ett `FileOutputStream` som pekar på mål‑`.ps`‑filen. Detta flöde matar de binära data som genereras av Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Steg 3: Skapa sparalternativ
Instansiera `PsSaveOptions`. Du kan anpassa sidstorlek, komprimering osv., men standardinställningarna räcker för detta exempel.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Steg 4: Skapa PS‑dokument
Skapa `PsDocument`‑objektet, skicka in utdataflödet och sparalternativen. Flaggan `false` talar om för Aspose.Page att inte automatiskt öppna en sida (vi gör det manuellt).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Steg 5: Skapa en cirkel
Vi ritar en cirkel med `Ellipse2D.Float`. Parametrarna är `(x, y, width, height)`. Att sätta `width = height` skapar en perfekt cirkel.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Hur man ritar cirkel med gradient
Nu när vi har en form är nästa steg att **draw circle with gradient**. Genom att applicera ett `RadialGradientPaint` på cirkeln kommer fyllningsoperationen automatiskt att använda den gradient vi definierar.

## Steg 6: Definiera gradientfärger
Förbered två arrayer: en för färgerna som ska visas i gradienten och en för motsvarande fraktionella positioner (0 = centrum, 1 = kant).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Steg 7: Skapa AffineTransform
`AffineTransform` skalar och translaterar gradienten så att den passar vår cirkel. Matrisen `(scaleX, 0, 0, scaleY, translateX, translateY)` gör jobbet.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Steg 8: Skapa Radial Gradient Paint
Nu bygger vi `RadialGradientPaint`‑objektet. Det tar mittpunkten, radien, fokuspunkten, färgfraktionerna, färgarrayen, cykelmetoden, färgrymden och den transform vi just definierat.

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

## Steg 9: Ställ in Paint och fyll cirkel
Applicera gradient‑painten på dokumentet och fyll den tidigare definierade cirkeln. Detta är kärnan i vårt **radial gradient example** och demonstrerar hur man **fill shape with gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Steg 10: Stäng sida och spara dokument
Slutför sidan, skriv innehållet till disk och stäng flödet. Din PostScript‑fil är nu klar att visas med någon PS‑visare.

```java
document.closePage();
document.save();
```

Grattis! Du har framgångsrikt skapat ett radialgradientexempel i Java PostScript med Aspose.Page. Du har nu ett återanvändbart mönster för **fill shape with gradient** som kan anpassas till andra former och utdataformat.

## Vanliga problem och lösningar
| Problem | Lösning |
|---------|----------|
| **FileNotFoundException** när du öppnar utdataflödet | Verifiera att `dataDir` pekar på en befintlig mapp och att du har skrivrättigheter. |
| Gradienten ser platt ut eller saknas | Se till att `fractions`‑arrayen har samma längd som `colors`‑arrayen och att `AffineTransform` skalar korrekt. |
| Färgerna visas omvända | Byt ordning på färgerna i `colors`‑arrayen eller justera koordinaterna för `focus`‑punkten. |

## Vanliga frågor

**Q: Var kan jag hitta dokumentationen för Aspose.Page för Java?**  
A: Den fullständiga API‑referensen finns tillgänglig [här](https://reference.aspose.com/page/java/).

**Q: Hur kan jag ladda ner Aspose.Page för Java?**  
A: Hämta den senaste JAR‑filen från [releases‑sidan](https://releases.aspose.com/page/java/).

**Q: Finns en gratis provversion tillgänglig?**  
A: Ja—ladda ner en provversion [här](https://releases.aspose.com/).

**Q: Kan jag få en tillfällig licens för testning?**  
A: Absolut, begär en från [tillfällig licens‑sida](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag få community‑support?**  
A: Gå med i diskussionen på [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39).

## Slutsats
I den här guiden byggde vi ett komplett **radial gradient example** för ett PostScript‑dokument med Aspose.Page för Java. Genom att följa stegen har du nu ett återanvändbart mönster för **fill shape with gradient**, som du kan anpassa till PDF, SVG eller något annat format som stöds av Aspose.Page. Experimentera med olika färger, radier och former för att berika dina Java‑grafikprojekt.

---

**Senast uppdaterad:** 2026-02-13  
**Testat med:** Aspose.Page for Java 24.11 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}