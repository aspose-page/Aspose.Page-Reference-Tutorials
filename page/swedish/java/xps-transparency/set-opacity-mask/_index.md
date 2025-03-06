---
title: Ställ in Opacitetsmask i Java XPS
linktitle: Ställ in Opacitetsmask i Java XPS
second_title: Aspose.Page Java API
description: Upptäck kraften i att ställa in opacitetsmasker i Java XPS med Aspose.Page. Följ vår steg-för-steg-guide för en visuellt förbättrad dokumentupplevelse.
weight: 11
url: /sv/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in Opacitetsmask i Java XPS

## Introduktion
Välkommen till vår omfattande guide för att ställa in opacitetsmasker i Java XPS med Aspose.Page. I den här handledningen går vi igenom processen att skapa ett XPS-dokument, lägga till en arbetsyta och applicera en opacitetsmask på en rektangel med de kraftfulla funktionerna i Aspose.Page för Java.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande:
- En grundläggande förståelse för Java-programmering.
-  Aspose.Page för Java-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/page/java/).
-  En giltig licens för Aspose.Page. Om du inte har en, kan du få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
- En utvecklingsmiljö inrättad för att köra Java-applikationer.
## Importera paket
Börja med att importera de nödvändiga paketen till ditt Java-projekt. Se till att du har Aspose.Page-biblioteket korrekt integrerat. Nedan är ett utdrag som vägleder dig:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Låt oss nu dela upp exempelkoden i flera steg:
## Steg 1: Skapa ett nytt XPS-dokument
```java
// Skapa ett nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```
## Steg 2: Lägg till en canvas
```java
// Ny canvas
XpsCanvas canvas = doc.addCanvas();
```
## Steg 3: Lägg till en rektangel med opacitetsmask
```java
// Rektangel i mitten till vänster med opacitet maskerad av ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Steg 4: Ställ in Opacitetsmask med ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Steg 5: Spara det resulterande XPS-dokumentet
```java
// Spara resulterande XPS-dokument
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Följ dessa steg noggrant för att införliva opacitetsmasker i ditt Java XPS-dokument med Aspose.Page.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du ställer in opacitetsmasker i Java XPS med Aspose.Page. Den här funktionen lägger till ett lager av visuell rikedom till dina dokument, vilket gör dem mer engagerande och dynamiska.
## Vanliga frågor
### Är Aspose.Page kompatibel med alla Java-utvecklingsmiljöer?
Ja, Aspose.Page är designad för att fungera sömlöst med olika Java-utvecklingsmiljöer.
### Kan jag använda Aspose.Page utan licens?
Även om du kan använda Aspose.Page utan licens, rekommenderas det att du skaffar en för alla funktioner och support.
### Finns det några begränsningar för testversionen?
Provversionen kan ha vissa funktionsbegränsningar. Det är tillrådligt att kontrollera dokumentationen för detaljer.
### Hur kan jag få support för Aspose.Page?
 Du kan besöka[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd eller köp en licens för premiumhjälp.
### Finns det en pengarna-tillbaka-garanti för Aspose.Page?
 Referera till[köpsidan](https://purchase.aspose.com/buy) för information om återbetalningspolicyer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
