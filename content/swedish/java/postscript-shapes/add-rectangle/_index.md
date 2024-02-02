---
title: Anpassa Java PostScript - Lägga till rektanglar med Aspose.Page
linktitle: Lägg till rektangel i Java PostScript
second_title: Aspose.Page Java API
description: Utforska steg-för-steg-guiden för att lägga till livfulla rektanglar till Java PostScript-dokument med Aspose.Page för Java. Förbättra din dokumentanpassning utan ansträngning!
type: docs
weight: 11
url: /sv/java/postscript-shapes/add-rectangle/
---
## Introduktion
Vill du förbättra dina Java PostScript-dokument med livfulla rektanglar? Kolla inte vidare! I den här steg-för-steg-guiden kommer vi att utforska hur du använder Aspose.Page för Java för att lägga till rektanglar till dina PostScript-dokument. Aspose.Page är ett kraftfullt bibliotek som ger robusta funktioner för att arbeta med PostScript-filer, vilket gör det till ett idealiskt val för utvecklare som vill manipulera och anpassa sina dokument.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för Java-programmering.
-  Aspose.Page för Java-biblioteket installerat. Om inte, ladda ner den från[Aspose.Page för Java-dokumentation](https://reference.aspose.com/page/java/).
- En Java-utvecklingsmiljö konfigurerad på din maskin.
## Importera paket
Börja med att importera de nödvändiga paketen i ditt Java-projekt:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Handledning: Lägga till rektanglar i Java PostScript
## Steg 1: Ställ in färg för att fylla rektangel
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa utdataström för PostScript-dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Skapa sparalternativ med A4-storlek
PsSaveOptions options = new PsSaveOptions();
// Skapa ett nytt PS-dokument med sidan öppen
PsDocument document = new PsDocument(outPsStream, options, false);
// Ställ färg för att fylla rektangel
document.setPaint(Color.ORANGE);        
// Fyll den första rektangeln
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Steg 2: Ställ in färg för att stryka rektangeln
```java
// Ställ färg för att stryka rektangel
document.setPaint(Color.RED);
// Ställ in slaglängd
document.setStroke(new BasicStroke(3));
// Stryk (kontur) den andra rektangeln
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Steg 3: Stäng aktuell sida och spara dokument
```java
// Stäng aktuell sida
document.closePage();
// Spara dokumentet
document.save();
```
Grattis! Du har framgångsrikt lagt till livfulla rektanglar till ditt Java PostScript-dokument med hjälp av Aspose.Page.
## Slutsats
I den här handledningen har vi utforskat processen att förbättra dina Java PostScript-dokument med rektanglar med Aspose.Page för Java. Detta kraftfulla bibliotek öppnar upp en värld av möjligheter för utvecklare som vill anpassa och manipulera sina dokument utan ansträngning.
Ha kul med att experimentera med olika former och färger för att göra dina dokument visuellt tilltalande!
## Vanliga frågor

### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
Aspose.Page stöder i första hand Java, men liknande bibliotek finns tillgängliga för andra språk.
### Finns det en testversion av Aspose.Page för Java tillgänglig?
 Ja, du kan utforska funktionerna i Aspose.Page för Java med[gratis testversion](https://releases.aspose.com/).
### Var kan jag hitta ytterligare hjälp och diskussioner?
 Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) att engagera sig i samhället och få hjälp.
### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag köpa en licensierad version av Aspose.Page för Java?
 Köp en licensierad version[här](https://purchase.aspose.com/buy).