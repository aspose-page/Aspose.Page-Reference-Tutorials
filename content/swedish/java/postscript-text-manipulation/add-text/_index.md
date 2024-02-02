---
title: Aspose.Page Java Text Manipulation
linktitle: Lägg till text i Java PostScript
second_title: Aspose.Page Java API
description: Utforska kraften i Aspose.Page för Java i vår handledning om att lägga till text i PostScript-dokument. Lär dig att använda system och anpassade typsnitt med lätthet.
type: docs
weight: 10
url: /sv/java/postscript-text-manipulation/add-text/
---
## Introduktion
Välkommen till vår steg-för-steg-guide för att lägga till text i Java PostScript med Aspose.Page för Java. Aspose.Page för Java är ett kraftfullt bibliotek som tillåter utvecklare att manipulera PostScript-dokument med lätthet. I den här handledningen kommer vi att gå igenom processen att lägga till text, använda system- och anpassade typsnitt, beskriva text och införliva streck för ett visuellt tilltalande resultat.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java-programmering.
-  Aspose.Page för Java-biblioteket installerat. Du kan ladda ner den från[Aspose.Page för Java nedladdningssida](https://releases.aspose.com/page/java/).
-  Nödvändiga teckensnitt tillgängliga i den angivna mappen. Du kan hitta ytterligare information i[Aspose.Page för Java-dokumentation](https://reference.aspose.com/page/java/).
## Importera paket
I ditt Java-projekt, importera de nödvändiga paketen för Aspose.Page for Java:
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
## Steg 1: Konfigurera dokumentet
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Skapa utdataström för PostScript-dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Skapa sparalternativ med A4-storlek
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// En text att skriva till PS-fil
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Skapa nytt 1-sidigt PS-dokument
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Steg 2: Använda systemteckensnitt för att fylla i text
```java
// Använda systemteckensnitt för att fylla text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fyll text med standardfärg eller redan definierad färg (svart)
document.fillText(str, font, 50, 100);
// Fyll text med blå färg
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Steg 3: Använd anpassat teckensnitt för att fylla text
```java
// Använda anpassat teckensnitt för att fylla text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fyll text med standardfärg eller redan definierad färg (svart)
document.fillText(str, drFont, 50, 200);
// Fyll text med blå färg
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Steg 4: Skissera text med systemteckensnitt
```java
// Använda systemteckensnitt för att konturera text
document.outlineText(str, font, 50, 300);
// Konturtext med blåviolett färgad 2-punktspenna
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fyll text med orange färg och streck med blåfärgad 2-punktspenna
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Steg 5: Konturer text med anpassat teckensnitt
```java
// Använda anpassat teckensnitt för att konturera text
document.outlineText(str, drFont, 50, 450);
// Konturtext med blåviolett färgad 2-punktspenna
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fyll text med orange färg och streck med blåfärgad 2-punktspenna
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Steg 6: Spara dokumentet
```java
// Stäng aktuell sida
document.closePage();
// Spara dokumentet
document.save();
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till text i Java PostScript med Aspose.Page för Java. Experimentera med olika typsnitt, färger och konturalternativ för att förbättra ditt dokument ytterligare.
## Vanliga frågor
### Kan jag använda mina egna anpassade typsnitt med Aspose.Page för Java?
 Ja, du kan använda anpassade teckensnitt genom att ange teckensnittets namn och storlek i`DrFont` klass.
### Hur kan jag ändra färgen på texten?
 Du kan ställa in önskad färg med hjälp av`Color` klass när du fyller i eller beskriver texten.
### Är det möjligt att lägga till flera sidor i ett PostScript-dokument?
Absolut! Du kan skapa flera sidor genom att upprepa stegen för att skapa och spara dokument.
###  Vad är syftet med`ExternalFontCache` class?
`ExternalFontCache` används för att hämta anpassade typsnitt, vilket säkerställer att de är tillgängliga för textmanipulering.
### Kan jag använda olika streck på den konturerade texten?
 Ja, du kan anpassa linjens bredd och färg med hjälp av`Stroke` klass och`Color` klass, respektive.