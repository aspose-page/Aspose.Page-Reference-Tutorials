---
title: Lägg till Ellipse i Java PostScript
linktitle: Lägg till Ellipse i Java PostScript
second_title: Aspose.Page Java API
description: Bemästra att skapa fantastiska PostScript-dokument i Java med Aspose.Page. Lär dig att lägga till ellipser steg för steg för visuellt tilltalande innehåll.
type: docs
weight: 10
url: /sv/java/postscript-shapes/add-ellipse/
---
## Introduktion
I Java-utvecklingens dynamiska värld är det ett vanligt krav att skapa visuellt tilltalande dokument. Aspose.Page för Java är ett kraftfullt bibliotek som ger utvecklare möjlighet att manipulera PostScript-filer utan ansträngning. I den här handledningen kommer vi att utforska hur man lägger till ellipser i PostScript-dokument med Aspose.Page för Java. Följ med för att förbättra dina färdigheter i att skapa dokument!
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar inställda:
1. Java-utvecklingsmiljö: Se till att du har en fungerande Java-utvecklingsmiljö installerad på din maskin.
2.  Aspose.Page for Java Library: Ladda ner och inkludera Aspose.Page-biblioteket i ditt Java-projekt. Du hittar biblioteket[här](https://releases.aspose.com/page/java/).
## Importera paket
Importera de nödvändiga paketen i din Java-kod för att använda Aspose.Page-funktionen. Här är ett exempel:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Steg 1: Konfigurera ditt dokument
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa utdataström för PostScript-dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Skapa sparalternativ med A4-storlek
PsSaveOptions options = new PsSaveOptions();
// Skapa ett nytt PS-dokument med sidan öppen
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Steg 2: Fyll Ellipsen med färg
```java
// Ställ färg för att fylla ellips
document.setPaint(Color.ORANGE);
// Fyll den första ellipsen
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## Steg 3: Skissera Ellipse med Stroke
```java
// Ställ färg för att stryka ellips
document.setPaint(Color.RED);
// Ställ in slaglängd
document.setStroke(new BasicStroke(3));
// Stryk (kontur) den andra ellipsen
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## Steg 4: Stäng och spara dokument
```java
// Stäng aktuell sida
document.closePage();
// Spara dokumentet
document.save();
```
Nu har du framgångsrikt lagt till ellipser till ditt PostScript-dokument med Aspose.Page för Java! Experimentera med olika koordinater och dimensioner för att anpassa dina bilder.
## Slutsats
 Aspose.Page för Java förenklar processen att skapa och manipulera PostScript-dokument. Denna handledning har utrustat dig med kunskapen att lägga till ellipser, vilket ger en solid grund för mer komplexa visualiseringar. Dyk ner i[dokumentation](https://reference.aspose.com/page/java/) för ytterligare detaljer och funktioner.
## Vanliga frågor
### F: Kan jag använda Aspose.Page för Java med andra Java-bibliotek?
S: Ja, Aspose.Page för Java är utformad för att sömlöst integreras med andra Java-bibliotek.
### F: Hur kan jag få en tillfällig licens för Aspose.Page för Java?
 S: Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för teständamål.
### F: Är Aspose.Page lämplig för kommersiella projekt?
 A: Absolut! Besök[här](https://purchase.aspose.com/buy) för att utforska licensalternativ för kommersiellt bruk.
### F: Var kan jag söka hjälp eller diskutera Aspose.Page-relaterade frågor?
 S: Gå med i gemenskapen på[Aspose.Page Forum](https://forum.aspose.com/c/page/39) för diskussioner och hjälp.
### F: Finns det några gratisresurser för att lära dig mer om Aspose.Page för Java?
 S: Använd[gratis provperiod](https://releases.aspose.com/) och utforska exempel i dokumentationen.