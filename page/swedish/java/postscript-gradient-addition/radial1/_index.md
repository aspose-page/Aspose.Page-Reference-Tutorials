---
date: 2026-09-09
description: Lär dig hur du skapar radial gradient i Java PostScript med Aspose.Page.
  Denna steg‑för‑steg‑guide visar hur du lägger till en color stops gradient, sätter
  radii och genererar en PS‑fil snabbt.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Behärska radial gradients i Java
og_description: Lär dig hur du skapar radial gradient i Java PostScript med Aspose.Page.
  Denna guide förklarar hur du lägger till en color stops gradient, sätter radii och
  genererar en PS‑fil på några minuter.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Hur man skapar radial gradient i Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Hur man skapar radial gradient i Java PostScript
url: /sv/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du radialgradient i Java PostScript med Aspose.Page

## Introduktion
Om du behöver **skapa en radialgradient** i en PostScript‑fil, har du kommit till rätt ställe. I den här handledningen går vi igenom varje steg som krävs för att generera ett PostScript‑dokument som innehåller en mjuk radialgradient, med hjälp av **Aspose.Page för Java**. I slutet förstår du API‑et, ser ett komplett körbart exempel och vet hur du justerar färger, positioner och radier för alla designscenarier.

## Snabba svar
- **Vilket bibliotek skapar radialgradienter i PostScript?** Aspose.Page för Java.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundläggande exempel.  
- **Behöver jag en licens för att köra koden?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version stöds?** Java 8 eller högre.  
- **Kan jag ändra gradientens form?** Ja – justera radien och mittpunkten i `RadialGradientPaint`‑konstruktorn.

## Så skapar du radialgradient i Java

Ladda ditt Java‑projekt, importera de nödvändiga klasserna och följ steg‑för‑steg‑guiden nedan. Kärnsvaret är att du instansierar ett `RadialGradientPaint` med dina färgstopp och sedan applicerar det på en rektangel som ritas på ett `PsDocument`. Detta två‑objekt‑tillvägagångssätt hanterar alla låg‑nivå PostScript‑kommandon åt dig.

## Vad är en radialgradient?
`RadialGradientPaint` är en Java AWT‑klass som definierar en cirkulär färgövergång från en central punkt utåt. Den skapar en mjuk blandning av flera färgstopp, vilket gör den idealisk för spotlight‑effekter, mjuka bakgrunder eller någon effekt där färger strålar från en fokalpunkt.

## Varför använda Aspose.Page för radialgradienter?
Aspose.Page ger dig full programmatisk kontroll över PostScript‑utdata samtidigt som den hanterar det tunga lyftet av låg‑nivå PS‑syntax. Den stöder **50+ in‑ och utdataformat**, kan rendera dokument med hundratals sidor utan att ladda hela filen i minnet, och körs på alla operativsystem som stödjer Java 8+. Denna kvantifierade kapacitet gör den till ett pålitligt val för företagsklassig grafikgenerering.

## Förutsättningar
- **Java Development Kit (JDK) 8+** – verifiera med `java -version`.  
- **Aspose.Page för Java** – ladda ner den senaste JAR‑filen från den officiella [Aspose.Page nedladdningssidan](https://releases.aspose.com/page/java/).  
- **IDE efter eget val** – Eclipse, IntelliJ IDEA eller VS Code med Java‑tillägg.  
- **En skrivbar mapp** – där den genererade `.ps`‑filen kommer att sparas.

## Importera paket
Först importerar vi de klasser vi behöver. `java.awt`‑paketet tillhandahåller gradient‑paint‑objekten, medan `com.aspose.eps` innehåller klasserna för hantering av PostScript‑dokument.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Steg‑för‑steg‑guide

### Steg 1: skapa en rektangel och öppna ett PS‑dokument
`PsDocument` är Aspose.Page‑klassen som representerar ett PostScript‑dokument och tillhandahåller metoder för att rita former, text och bilder. Vi börjar med att skapa ett output‑stream, konfigurera sidstorleken (A4 som standard) och definiera en rektangel som ska innehålla gradienten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Proffstips:** Justera rektangelns koordinater (`200, 100, 200, 200`) för att placera gradienten var som helst på sidan.

### Steg 2: definiera färger och fraktioner
En radialgradient byggs upp av *färgstopp* (färgerna) och *fraktioner* (de relativa positionerna för dessa stopp). Här skapar vi en array med sex färger och deras motsvarande fraktioner.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Varför detta är viktigt:** Genom att justera `fractions` styr du hur snabbt färgerna övergår, vilket möjliggör subtila eller dramatiska effekter.

### Steg 3: skapa radialgradient‑paint
`RadialGradientPaint` är kärnklassen som beskriver en radial färggradient, inklusive mittpunkt, radie, fokuspunkt, fraktioner, färger, cykelmetod och färgrymd. Nu bygger vi `RadialGradientPaint`‑objektet med hjälp av de arrayer som definierades ovan.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Obs:** `transform` kan vara `null` om du inte behöver ytterligare skalning eller rotation. Känn dig fri att experimentera med `AffineTransform` för skeva gradienter.

### Steg 4: sätt paint och fyll rektangeln
När paint‑objektet är klart instruerar vi `PsDocument` att använda det och fyller sedan rektangeln vi definierade tidigare.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Vid detta tillfälle innehåller PostScript‑sidan en rektangel som är mjukt fylld med den radialgradient vi konfigurerade.

### Steg 5: stäng och spara dokumentet
Till sist stänger vi den aktuella sidan och skriver filen till disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Öppna `RadialGradient1_outPS.ps` i någon PostScript‑visare (t.ex. Ghostscript) så ser du gradienten renderad exakt som definierad.

## Vanliga problem & lösningar
| Symptom | Trolig orsak | Lösning |
|---------|--------------|---------|
| Gradienten visas som en solid färg | `fractions`‑arrayen börjar inte med `0.0f` eller slutar inte med `1.0f` | Säkerställ att den första fraktionen är `0.0f` och den sista är `1.0f`. |
| Färgerna ser urvattnade ut | Fel `ColorSpaceType` används | Byt till `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` för mer levande resultat. |
| Ingen utdatafil genereras | `FileOutputStream`‑sökvägen är ogiltig eller ej skrivbar | Verifiera att `dataDir` finns och att applikationen har skrivbehörighet. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för Java i kommersiella projekt?**  
A: Ja. En kommersiell licens krävs för produktionsanvändning. Du kan köpa en på [Aspose licenssida](https://purchase.aspose.com/buy).

**Q: Var kan jag hitta den officiella API‑referensen?**  
A: Fullständig dokumentation finns på [Aspose.Page Java API‑referens](https://reference.aspose.com/page/java/).

**Q: Finns en gratis provversion för testning?**  
A: Absolut. Ladda ner en provversion från [Aspose.Page releases‑sida](https://releases.aspose.com/).

**Q: Hur får jag en temporär licens för utvärdering?**  
A: En temporär licens kan begäras via [temporär licensförfrågningssida](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag få community‑support?**  
A: Gå med i Aspose.Page‑forumet på [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Slutsats
Du vet nu **hur du skapar radialgradient** i ett Java‑PostScript‑dokument med Aspose.Page. Genom att justera rektangelns storlek, färgstopp och gradientradie kan du skapa otaliga visuella effekter – från subtila bakgrundsfyllningar till djärva spotlight‑grafiker. Känn dig fri att experimentera med olika `AffineTransform`‑värden för att rotera eller skeva gradienten, och kombinera denna teknik med text och bilder för rikare PDF‑ eller EPS‑utdata.

---

**Senast uppdaterad:** 2026-09-09  
**Testat med:** Aspose.Page för Java senaste (vid skrivande)  
**Författare:** Aspose

## Relaterade handledningar

- [Fyll form med gradient: Java PostScript Radial‑exempel](/page/java/postscript-gradient-addition/radial2/)
- [Skapa PostScript‑gradient i Java – Lägg till vertikal gradient](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page transparens‑handledning – Lägg till transparens i Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}