---
date: 2026-04-24
description: Lär dig hur du skapar XPS‑dokument i Java med en ellips med radiell gradient.
  Denna steg‑för‑steg‑guide visar hur du ställer in linjetjocklek och definierar bangeometri
  med Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Lägg till ellips i Java XPS
second_title: Aspose.Page Java API
title: Skapa XPS-dokument i Java – Lägg till en ellips med radiell gradient
url: /sv/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till en ellips med radiell gradient med Aspose.Page

## Introduktion
I den här handledningen kommer du att lära dig hur du **create XPS document Java** med en vacker ellips med radielgradientlinje med hjälp av Aspose.Page för Java. Aspose.Page är ett robust bibliotek som abstraherar de lågnivå XPS‑detaljerna, så att du kan fokusera på design snarare än filformatets komplexitet. I slutet av guiden har du en färdig XPS‑fil som du kan bädda in i rapporter, fakturor eller någon dokumentgenereringsprocess.

## Snabba svar
- **Vad producerar den här koden?** En enkelsidig XPS‑fil som innehåller en ellips med en flerkärnig radiell gradientlinje.  
- **Vilket primärt API används?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Behöver jag en licens för att köra exemplet?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka nyckelegenskaper sätter vi?** Stroke‑pensel (radiell gradient), spridningsmetod, gradientstoppunkter och linjetjocklek.  
- **Kan jag ändra ellipsens storlek?** Ja – ändra sträng för sökvägsgeometri eller koordinaterna för gradientpenseln.

## Vad är “create XPS document Java”?
Att skapa ett XPS‑dokument i Java innebär att programmässigt generera en XML Paper Specification (XPS)‑fil — ett fast layout‑dokumentformat liknande PDF — direkt från Java‑kod. Aspose.Page tillhandahåller en hög‑nivå objektmodell (`XpsDocument`, `XpsCanvas`, etc.) som abstraherar XML‑markupen, vilket gör processen lika enkel som att arbeta med vanliga Java‑objekt.

## Varför använda en ellips med radiell gradient?
En radiell gradient ger en tredimensionell känsla, perfekt för visuella höjdpunkter, logotyper eller dekorativa element i rapporter. Jämfört med en enfärgad linje ger gradienten djup utan att öka filstorleken avsevärt, och XPS‑formatet bevarar vektor‑kvaliteten vid skalning.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
- Java Development Kit (JDK) installerat på din maskin.
- Aspose.Page för Java‑biblioteket nedladdat. Du kan hämta det [här](https://releases.aspose.com/page/java/).
- En kodredigerare efter eget val (Eclipse, IntelliJ, etc.) för att skriva och köra Java‑kod.

## Importera paket
Se till att du har de nödvändiga paketen importerade i ditt Java‑projekt för att använda Aspose.Page. Lägg till följande import‑satser högst upp i din Java‑fil:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Steg 1: Ställ in dokumentkatalogen
Definiera sökvägen till din dokumentkatalog där XPS‑dokumentet kommer att sparas:

```java
String dataDir = "Your Document Directory";
```

## Steg 2: Skapa XPS‑dokument
Initiera ett nytt XPS‑dokument med följande kod:

```java
XpsDocument doc = new XpsDocument();
```

## Steg 3: Definiera radiella gradientstopp
Skapa en lista med gradientstopp för den radiella gradientlinjen på ellipsen:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Steg 4: Skapa sökvägsgeometri
Definiera en ellips med radiell gradientlinje med hjälp av sökvägsgeometri:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Steg 5: Lägg till canvas och sökväg
Lägg till en ny canvas i dokumentet och lägg till sökvägen med den definierade geometrin:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Steg 6: Ställ in linje och gradient
Konfigurera linjen på sökvägen med en radiell gradientpensel:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Steg 7: Ställ in linjetjocklek
Specificera **set stroke thickness** för sökvägen:

```java
path.setStrokeThickness(12f);
```

## Steg 8: Spara dokumentet
Spara det resulterande XPS‑dokumentet:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Grattis! Du har framgångsrikt lagt till en ellips med radiell gradientlinje medan du **create XPS document Java** med Aspose.Page.

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Ellipsen ser platt ut** | Använder `XpsSpreadMethod.Pad` istället för `Reflect` | Ändra spridningsmetoden till `XpsSpreadMethod.Reflect` som visas i Steg 6. |
| **Ingen utdatafil** | `dataDir` pekar på en icke‑existerande mapp | Se till att katalogen finns eller använd en absolut sökväg. |
| **Gradientfärger ser felaktiga ut** | Felaktig ordning på gradientstoppunkterna | Verifiera att `offset`‑värdena (0 → 1) ökar monotont. |
| **Kompileringsfel** | Saknade Aspose.Page‑JAR‑filer i klassvägen | Lägg till `aspose-page-xx.jar` till ditt projekts beroenden. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Page för Java kan integreras med andra Java‑bibliotek sömlöst.

**Q: Är Aspose.Page lämplig för storskalig dokumentbehandling?**  
A: Absolut! Aspose.Page är designat för att hantera storskalig dokumentbehandling effektivt.

**Q: Var kan jag hitta fler handledningar och exempel för Aspose.Page för Java?**  
A: Besök [Aspose.Page för Java‑dokumentationen](https://reference.aspose.com/page/java/) för omfattande handledningar och exempel.

**Q: Hur kan jag få en tillfällig licens för Aspose.Page för Java?**  
A: Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Finns det community‑forum för Aspose.Page‑diskussioner?**  
A: Ja, gå med i [Aspose.Page community‑forum](https://forum.aspose.com/c/page/39) för att interagera med andra utvecklare och få hjälp.

---

**Senast uppdaterad:** 2026-04-24  
**Testad med:** Aspose.Page för Java 24.11 (senaste vid skrivande)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}