---
date: 2026-02-20
description: Lär dig hur du sätter textfärg i Java med Aspose.Page för Java, ändrar
  teckenstorlek i Java, genererar en PostScript‑fil, fyller och konturerar text samt
  använder anpassade teckensnitt i Java när du skapar ett PostScript‑dokument.
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
Välkommen till vår steg‑för‑steg‑guide om **set text color java** när du arbetar med PostScript‑filer med Aspose.Page för Java. Aspose.Page för Java är ett kraftfullt bibliotek som låter utvecklare **create postscript document**‑filer, manipulera typsnitt och stilisera text med precision. I den här handledningen kommer du att lära dig hur du lägger till text, ändrar dess färg, **change font size java**, och till och med **apply fill and stroke text** för ett polerat utseende.

## Snabba svar
- **Vilket bibliotek låter mig ställa in textfärg i Java?** Aspose.Page for Java.  
- **Kan jag använda systemtypsnitt och anpassade typsnitt?** Ja, båda stöds, och du kan **use custom fonts java** enkelt.  
- **Hur ändrar jag textstorleken?** Genom att ange teckenstorleken när du skapar `Font` eller `DrFont`.  
- **Är det möjligt att både konturera och fylla text?** Absolut – använd `fillAndStrokeText`.  
- **Vilket utdataformat producerar den här handledningen?** Ett PostScript‑dokument (`.ps`), som du kan **generate postscript file** programatiskt.

## Vad är “set text color java”?
Att ställa in textfärgen i Java innebär att definiera `Color`‑objektet som renderingsmotorn (här, Aspose.Page) använder när den ritar tecken på en sida. Denna operation är avgörande för att skapa visuellt distinkta dokument, särskilt när du behöver **generate postscript file** programatiskt.

## Varför använda Aspose.Page för Java?
- **Full control** över PostScript‑generering utan att behöva en inbyggd tolk.  
- **Support for both system and external fonts**, vilket låter dig bädda in vilken typografi du behöver.  
- **Easy API** för att fylla, konturera och **fill and stroke text**, vilket ger dig flexibilitet i stil.  
- **Cross‑platform** kompatibilitet – skriv en gång, kör var som helst Java kör.  

## Förutsättningar
Innan du dyker ner, se till att du har:

- Grundläggande kunskap i Java‑programmering.  
- Aspose.Page för Java‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- Nödvändiga typsnitt tillgängliga i den angivna mappen. Ytterligare detaljer finns i [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Importera paket
I ditt Java‑projekt, importera de nödvändiga paketen för Aspose.Page för Java:

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

## Steg 1: Ställ in dokumentet
Först skapar vi ett nytt **PostScript document** och konfigurerar utdataalternativen.

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

## Hur man ställer in textfärg Java med systemtypsnitt
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

## Använda anpassat typsnitt och ändra textstorlek
Du kan också **change font size java** och använda ett anpassat typsnitt lagrat i din typsnittsmapp.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Konturera (Stroke) text – Applicera Stroke Text
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

## Konturera text med anpassat typsnitt
Samma teknik fungerar med anpassade typsnitt.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Steg 6: Spara dokumentet
Till sist, stäng sidan och skriv filen till disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Varför detta är viktigt
Att kunna **set text color java** och kombinera fyllning med kontur ger dig full konstnärlig kontroll över den slutliga PostScript‑utdata. Oavsett om du genererar fakturor, certifikat eller anpassad grafik, ger möjligheten att **create postscript document**‑filer med exakt stil minskad behov av efterbehandling i grafikredigerare.

## Vanliga problem & lösningar
| Problem | Lösning |
|-------|----------|
| **Font not found** | Se till att teckensnittsfilen är placerad i `necessary_fonts` och att mappvägen har lagts till korrekt via `options.setAdditionalFontsFolders`. |
| **Color not applied** | Verifiera att du anropar överlagringen av `fillText` eller `outlineText` som inkluderar ett `Color`‑argument. |
| **Stroke appears too thin** | Öka bredden på `BasicStroke` (t.ex. `new BasicStroke(3)`). |
| **Document not opening** | Bekräfta att den genererade `.ps`‑filen är sparad med rätt filändelse och att din visare stödjer PostScript. |

## Vanliga frågor

**Q:** Kan jag använda mina egna anpassade typsnitt med Aspose.Page för Java?  
A: Ja, du kan **use custom fonts java** genom att ange typsnittsnamnet och storleken i `DrFont`‑klassen.

**Q:** Hur kan jag ändra färgen på texten?  
A: Du kan ange önskad färg med `Color`‑klassen när du fyller eller konturerar texten.

**Q:** Är det möjligt att lägga till flera sidor i ett PostScript‑dokument?  
A: Absolut! Du kan skapa flera sidor genom att upprepa stegen för dokumentskapande och sparande.

**Q:** Vad är syftet med klassen `ExternalFontCache`?  
A: `ExternalFontCache` används för att hämta anpassade typsnitt, så att de är tillgängliga för textmanipulering.

**Q:** Kan jag applicera olika konturer på den konturerade texten?  
A: Ja, du kan anpassa bredden och färgen på konturen med `Stroke`‑klassen respektive `Color`‑klassen.

## Slutsats
Grattis! Du vet nu hur du **set text color java**, **change font size java**, **apply fill and stroke text**, och **create postscript document**‑filer med Aspose.Page för Java. Experimentera med olika typsnitt, färger och konturstilar för att producera professionellt utseende PostScript‑utdata.

---

**Senast uppdaterad:** 2026-02-20  
**Testad med:** Aspose.Page för Java 23.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}