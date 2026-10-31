---
date: 2026-10-31
description: Lär dig hur man set paint color och fill ellipse i Java PostScript med
  Aspose.Page. Denna guide visar hur man fill ellipse, draw ellipse outline, och set
  stroke thickness med tydliga kodsteg.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Lägg till Ellipse i Java PostScript
og_description: Lär dig hur man fill ellipse och set paint color i Java PostScript
  med Aspose.Page. Följ steg‑för‑steg kod för att draw filled and outlined ellipses
  på några sekunder.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Hur man fill ellipse och set paint color i Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Hur man fill ellipse och set paint color i Java PostScript
url: /sv/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man fyller ellips och sätter färg för målning i Java PostScript

## Introduktion
Om du behöver **set paint color** när du ritar vektorgrafik, ger Aspose.Page for Java‑biblioteket dig full kontroll över varje penseldrag och fyllning. I den här handledningen kommer du att upptäcka hur du **set paint color**, **fill ellipse** och **draw ellipse outline** med ett enkelt, steg‑för‑steg‑förfarande. När du är klar kan du lägga till högkvalitativa PostScript‑ellipser i fakturor, rapporter eller andra utskrivbara dokument.

## Snabba svar
- **Vilket bibliotek är bäst för att rita PostScript‑grafik i Java?** Aspose.Page for Java.  
- **Kan jag fylla en ellips med en solid färg?** Ja – använd `document.setPaint(Color.YOUR_COLOR)` innan `fill`.  
- **Hur ritar jag bara konturen av en ellips?** Ställ in färg och pensel, och anropa sedan `document.draw(...)`.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs; en tillfällig licens finns tillgänglig för testning.  
- **Vilken Java‑version stöds?** Alla Java 8+‑miljöer fungerar med den aktuella Aspose.Page‑utgåvan.

## Vad är en PostScript‑ellips?
En PostScript‑ellips är en vektorform definierad av en omgivande rektangel. Till skillnad från rasterbilder skalas den utan kvalitetsförlust, vilket gör den idealisk för högupplöst utskrift och PDF‑konvertering. Eftersom formen beskrivs matematiskt kan den renderas i vilken storlek eller upplösning som helst samtidigt som skarpa kanter och mjuka kurvor bevaras.

## Varför använda Aspose.Page för att skapa en PostScript‑ellips?
Aspose.Page ger dig deterministisk kontroll över varje ritningsprimitive. Det stödjer **3 stora operativsystem (Windows, Linux, macOS)**, **0 inhemska beroenden**, och kan rendera **50+ vektorprimitiver** per sekund på en vanlig server. Biblioteket är rent Java, så du kan bädda in det i vilken Java 8+‑applikation som helst utan extra inhemska bibliotek.

## Förutsättningar
Innan du börjar, säkerställ att du har:

1. En fungerande Java‑utvecklingsmiljö (JDK 8 eller senare).  
2. Aspose.Page for Java‑biblioteket tillagt i ditt projekt. Du kan ladda ner det **[from the Aspose.Page for Java release page](https://releases.aspose.com/page/java/)**.  

## Importera paket
I din Java‑källfil importerar du de klasser som behövs för att rita och spara PostScript‑innehåll.

`java.awt`‑paketet levererar de grundläggande grafiktyperna såsom `Color`, `Ellipse2D` och `BasicStroke`. `com.aspose.page`‑paketet tillhandahåller `PsDocument`‑klassen som skriver PostScript‑utdata.

- **`Color`** – representerar en sRGB‑färg som används för målning.  
- **`Ellipse2D`** – beskriver en ellipsform definierad av en omgivande rektangel.  
- **`BasicStroke`** – specificerar linjebredd, streckmönster och ändkapstil för att rita konturer.  
- **`PsDocument`** – representerar ett PostScript‑dokument och erbjuder metoder för att rita grafik och hantera sidor.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hur man anger färg för målning för en ellips
Det första steget är att tala om för dokumentet vilken färg som ska användas för nästa ritoperation. Metoden `setPaint` anger en solid färg som kommer att tillämpas antingen på en fyllning eller en penseldrag, beroende på efterföljande anrop.

### Steg 1: Ställ in PostScript‑dokumentet
Skapa ett output‑flöde, konfigurera sidstorlek och instansiera en `PsDocument`.

`PsDocument` är kärnklassen som representerar en PostScript‑fil i minnet. Alla ritkommandon går via detta objekt, och det hanterar sidlayout, resurshantering och slutgiltig filgenerering.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Steg 2: Fyll ellips – använd set paint color
För att **fill ellipse** måste du först anropa `setPaint` med önskad fyllningsfärg, och sedan anropa `fill` med en `Ellipse2D`‑instans.

`setPaint` anger den aktuella ritfärgen som används för efterföljande fyllnings‑ eller penseldragsoperationer.  
`Ellipse2D` definierar de geometriska gränserna för ellipsen; dess konstruktor tar X‑Y‑koordinaterna för det övre vänstra hörnet samt bredd och höjd.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Steg 3: Rita ellipsens kontur och ange linjetjocklek
Efter fyllning kan du byta färg, definiera en `BasicStroke` för att kontrollera linjebredden och rita ellipsens kontur.

`BasicStroke` specificerar linjebredd, streckmönster och ändkapstil för att rita konturer. Genom att justera dess `width`‑egenskap styr du hur tjock ellipsens kant blir.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Steg 4: Stäng och spara dokumentet
Slutför sidan och skriv PostScript‑filen till disk.

Anropet `document.close()` spolar alla väntande ritkommandon och frigör resurser. Den resulterande `.ps`‑filen kan öppnas med vilken PostScript‑visare som helst eller konverteras till PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Du har nu en PostScript‑fil som innehåller två ellipser – en fylld med orange och en annan konturerad i rött. Känn dig fri att experimentera med olika koordinater, storlekar och färger för att matcha dina designbehov.

## Vanliga fallgropar och felsökning
- **Felaktig filsökväg** – Säkerställ att `dataDir` slutar med en separator (`/` eller `\\`) som passar ditt OS.  
- **Saknad licens** – Utan en giltig licens körs biblioteket i utvärderingsläge och kan lägga till vattenstämplar.  
- **Färgen appliceras inte** – Kom ihåg att anropa `document.setPaint(...)` *före* varje `fill`‑ eller `draw`‑anrop; färginställningen kvarstår inte automatiskt mellan separata operationer.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page for Java tillsammans med andra Java‑bibliotek?**  
A: Ja, Aspose.Page for Java är designat för att sömlöst integreras med andra Java‑bibliotek.

**Q: Hur får jag en tillfällig licens för Aspose.Page for Java?**  
A: Skaffa en tillfällig licens **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)** för teständamål.

**Q: Är Aspose.Page lämpligt för kommersiella projekt?**  
A: Absolut! Besök **[the Aspose purchase page](https://purchase.aspose.com/buy)** för att utforska licensalternativ för kommersiell användning.

**Q: Var kan jag söka hjälp eller diskutera frågor relaterade till Aspose.Page?**  
A: Gå med i communityn på **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** för diskussioner och support.

**Q: Finns det gratis resurser för att lära sig mer om Aspose.Page for Java?**  
A: Använd **[Aspose free trial page](https://releases.aspose.com/)** och utforska exempel i dokumentationen.

## Slutsats
Aspose.Page for Java gör det enkelt att **set paint color**, **fill ellipse** och **draw ellipse outline** — oavsett om du behöver en enkel fylld form eller en komplex konturerad grafik. Med stegen ovan kan du snabbt lägga till professionella vektorgrafiker i vilket utskrivbart dokument som helst. För djupare utforskning — som att kombinera flera former, applicera gradienter eller konvertera till PDF — se den officiella **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.

---

**Senast uppdaterad:** 2026-10-31  
**Testat med:** Aspose.Page for Java 24.11  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man ritar rektangel i Java PostScript med Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Hur man lägger till Unicode‑text i Java PostScript med Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Skapa radial gradient i PostScript med Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}