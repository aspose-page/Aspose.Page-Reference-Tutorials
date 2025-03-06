---
title: Lägg till rektangel i Java XPS
linktitle: Lägg till rektangel i Java XPS
second_title: Aspose.Page Java API
description: Lär dig hur du lägger till rektanglar i Java XPS med Aspose.Page. Följ vår steg-för-steg-guide för sömlös dokumenthantering. #JavaXPS #AsposePage
weight: 11
url: /sv/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till rektangel i Java XPS

## Introduktion
Välkommen till den här omfattande guiden om att lägga till rektanglar i Java XPS med Aspose.Page! Oavsett om du är en erfaren utvecklare eller precis har börjat med Java XPS, kommer den här handledningen att leda dig genom processen med steg-för-steg-instruktioner, vilket säkerställer att du får en djup förståelse av ämnet.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande kunskaper i programmeringsspråket Java.
-  Aspose.Page-biblioteket installerat. Om inte kan du ladda ner den från[Aspose.Page Java-dokumentation](https://reference.aspose.com/page/java/).
- En fungerande Java-utvecklingsmiljö.
## Importera paket
För att komma igång, importera nödvändiga paket till ditt Java-projekt. Se till att Aspose.Page-biblioteket läggs till korrekt i din klassväg. Här är ett grundläggande exempel:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Låt oss nu dela upp exemplet i flera steg för att lägga till en rektangel i Java XPS.
## Steg 1: Ställ in dokumentkatalogen
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
```
Ersätt "Din dokumentkatalog" med sökvägen till din önskade katalog.
## Steg 2: Skapa ett nytt XPS-dokument
```java
// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```
Detta initierar ett nytt XPS-dokument.
## Steg 3: Lägg till en CMYK-rektangel med fast färg
```java
// CMYK (blå) enfärgad rektangel i den nedre vänstra delen
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Det här steget lägger till en struken rektangel med en CMYK-färg.
## Steg 4: Spara det resulterande XPS-dokumentet
```java
// Spara resulterande XPS-dokument
doc.save(dataDir + "AddRectangle_out.xps");
```
Slutligen, spara det modifierade XPS-dokumentet med den tillagda rektangeln.
Upprepa dessa steg, justera parametrar efter behov, för att anpassa dina rektanglar ytterligare.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till rektanglar i Java XPS med Aspose.Page. Denna handledning ger en solid grund för dina XPS-dokumentmanipuleringssträvanden.
## Vanliga frågor
### Kan jag lägga till flera rektanglar i ett enda XPS-dokument?
Ja, du kan lägga till så många rektanglar som behövs genom att upprepa stegen som beskrivs i handledningen.
### Hur kan jag ändra färgen på rektangeln?
 Ändra färgvärdena i`createColor` metod för att uppnå önskad färg.
### Är Aspose.Page lämplig för att hantera komplexa XPS-dokumentmanipulationer?
Absolut! Aspose.Page tillhandahåller en robust uppsättning funktioner för att hantera olika XPS-dokumentuppgifter.
### Var kan jag hitta ytterligare exempel och stöd?
 Utforska[Aspose.Page forum](https://forum.aspose.com/c/page/39)för fler exempel och sök hjälp från samhället.
### Kan jag prova Aspose.Page innan jag köper?
 Ja, du kan utforska en[gratis provperiod](https://releases.aspose.com/) att uppleva funktionerna i Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
