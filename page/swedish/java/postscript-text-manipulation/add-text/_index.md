---
date: 2025-12-14
description: Lär dig hur du ställer in textfärg i Java med Aspose.Page för Java, lägger
  till text i PostScript och använder konturtext för rik dokumentstil.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Ställ in textfärg i Java med Aspose.Page – Guide för textmanipulering
url: /sv/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in textfärg Java med Aspose.Page – Guide för textmanipulering

## Introduktion
Välkommen till vår steg‑för‑steg‑guide om **set text color java** när du arbetar med PostScript‑filer med Aspose.Page för Java. Aspose.Page för Java är ett kraftfullt bibliotek som låter utvecklare skapa och **generate postscript file**‑dokument, manipulera typsnitt och stilisera text med precision. I den här handledningen lär du dig hur du lägger till text, ändrar dess färg, justerar storlek och till och med **apply stroke text** för ett polerat utseende.

## Snabba svar
- **Vilket bibliotek låter mig ställa in textfärg i Java?** Aspose.Page för Java.  
- **Kan jag använda systemtypsnitt och egna typsnitt?** Ja, båda stöds.  
- **Hur ändrar jag textstorleken?** Genom att ange teckenstorleken när du skapar `Font` eller `DrFont`.  
- **Är det möjligt att både konturera och fylla text?** Absolut – använd `fillAndStrokeText`.  
- **Vilket utdataformat producerar den här handledningen?** Ett PostScript‑dokument (`.ps`).

## Vad betyder “set text color java”?
Att sätta textfärg i Java innebär att definiera ett `Color`‑objekt som renderingsmotorn (här Aspose.Page) använder när den ritar tecken på en sida. Denna operation är viktig för att skapa visuellt distinkta dokument, särskilt när **postscript documents** genereras programatiskt.

## Varför använda Aspose.Page för Java?
- **Full kontroll** över PostScript‑generering utan att behöva en inbyggd PostScript‑tolkare.  
- **Stöd för både system‑ och externa typsnitt**, så att du kan bädda in vilken typografi du behöver.  
- **Enkel API** för att fylla, konturera och **fill and stroke text**, vilket ger dig flexibilitet i styling.  
- **Plattformsoberoende** kompatibilitet – skriv en gång, kör var som helst Java körs.

## Förutsättningar
Innan du dyker ner, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page för Java‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- Nödvändiga typsnitt tillgängliga i den angivna mappen. Ytterligare detaljer finns i [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Importera paket
I ditt Java‑projekt importerar du de nödvändiga paketen för Aspose.Page för Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Steg 1: Skapa dokumentet
Först skapar vi ett nytt **PostScript‑dokument** och konfigurerar utdataalternativen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Så här ställer du in textfärg Java med systemtypsnitt
Nu demonstrerar vi **set text color java** med ett systemtillhandahållet typsnitt.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tips:** Metoden `fillText` använder automatiskt den aktuella färgen om du inte skickar ett `Color`‑argument, vilket som standard är svart.

## Använda eget typsnitt och ändra textstorlek
Du kan också **change text size** och använda ett eget typsnitt som lagras i din typsnittsmapp.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Konturera (Stroke) text – Apply Stroke Text
Att konturera text ger den en skarp kant. Här **apply stroke text** med en `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Konturera text med eget typsnitt
Samma teknik fungerar med egna typsnitt.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Steg 6: Spara dokumentet
Till sist stänger vi sidan och skriver filen till disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Vanliga problem & lösningar
| Problem | Lösning |
|-------|----------|
| **Font not found** | Se till att typsnittsfilen ligger i `necessary_fonts` och att mappvägen har lagts till korrekt via `options.setAdditionalFontsFolders`. |
| **Color not applied** | Kontrollera att du anropar overload‑versionen av `fillText` eller `outlineText` som inkluderar ett `Color`‑argument. |
| **Stroke appears too thin** | Öka bredden på `BasicStroke` (t.ex. `new BasicStroke(3)`). |
| **Document not opening** | Bekräfta att den genererade `.ps`‑filen sparas med rätt filändelse och att din visare stödjer PostScript. |

## Vanliga frågor

**Q:** Kan jag använda egna typsnitt med Aspose.Page för Java?  
**A:** Ja, du kan använda egna typsnitt genom att ange typsnittsnamnet och storleken i `DrFont`‑klassen.

**Q:** Hur kan jag ändra färgen på texten?  
**A:** Du kan sätta önskad färg med `Color`‑klassen när du fyller eller konturerar texten.

**Q:** Är det möjligt att lägga till flera sidor i ett PostScript‑dokument?  
**A:** Absolut! Du kan skapa flera sidor genom att upprepa stegen för dokumentskapande och sparande.

**Q:** Vad är syftet med `ExternalFontCache`‑klassen?  
**A:** `ExternalFontCache` används för att hämta egna typsnitt, så att de är tillgängliga för textmanipulering.

**Q:** Kan jag applicera olika strokes på den konturerade texten?  
**A:** Ja, du kan anpassa bredd och färg på strokern med `Stroke`‑klassen och `Color`‑klassen respektive.

## Slutsats
Grattis! Du vet nu hur du **set text color java**, ändrar teckenstorlekar, **apply stroke text** och **create postscript document**‑filer med Aspose.Page för Java. Experimentera med olika typsnitt, färger och konturstilar för att producera professionella PostScript‑utdata.

---

**Senast uppdaterad:** 2025-12-14  
**Testat med:** Aspose.Page för Java 23.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}