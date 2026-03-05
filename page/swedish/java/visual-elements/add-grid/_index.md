---
date: 2026-03-05
description: Lär dig hur du lägger till ett rutnät med Visual Brush i Java med Aspose.Page.
  Följ en steg‑för‑steg‑guide för att enkelt förbättra dokumentets visuella utseende.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Hur man lägger till ett rutnät med Visual Brush i Java
url: /sv/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till rutnät med Visual Brush i Java

## Introduktion
Om du letar efter **hur man lägger till rutnät** i dina Java‑genererade dokument, gör Aspose.Page:s Visual Brush‑funktion det förvånansvärt enkelt. I den här handledningen går vi igenom varje steg, förklarar varför en Visual Brush är idealisk för rutnätsmönster och visar dig ett komplett, körbart exempel.

## Snabba svar
- **Vad är en Visual Brush?** Ett återanvändbart visuellt element som kan tile‑läggas eller sträckas för att fylla ett område.  
- **Varför använda ett rutnät?** Rutnät hjälper till att strukturera layouter, skapa bakgrundsmönster eller markera sektioner i XPS‑dokument.  
- **Förkunskaper?** Java JDK, Aspose.Page för Java och en grundläggande förståelse för Java‑grafik.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter när biblioteket är installerat.  
- **Kan jag anpassa färger?** Ja – du styr fyllningsfärger, opacitet och tile‑storlek direkt i koden.

## Varför använda Visual Brush för att lägga till ett rutnät?
Visual Brush låter dig definiera ett litet visuellt element (”tile”) en gång och sedan upprepa det över vilken form som helst. Detta tillvägagångssätt är minnes‑effektivt och håller din kod ren, särskilt när du behöver applicera samma mönster på flera canvases.

## Förkunskaper
Innan vi dyker ner i koden, se till att du har följande förkunskaper:
- Grundläggande förståelse för Java‑programmering.  
- Aspose.Page‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page för Java-dokumentationen](https://reference.aspose.com/page/java/).  
- Java Development Kit (JDK) installerat på din maskin.

## Importera paket
Se till att du har de nödvändiga paketen importerade i ditt Java‑projekt:
```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

### Steg 1: Ställ in ditt projekt
Först, skapa en `XpsDocument`‑instans och peka på den mapp där utdata ska sparas.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Steg 2: Skapa magentat rutnäts‑Visual Brush
Vi bygger en liten magentafärgad tile som kommer att upprepas. Path‑geometrin definierar tile‑ens form.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Steg 3: Definiera geometri för magentat rutnäts‑Visual Brush
Här beskriver vi området som kommer att ta emot den tile‑ade brushen.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Steg 4: Skapa en ny canvas
En ny canvas läggs till i dokumentet, och vi applicerar en translations‑transform så att rutnätet visas på önskad plats.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Steg 5: Lägg till rutnät på canvas
Nu binder vi visual brush till geometrin och ställer in tiling‑läget.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Steg 6: Lägg till en röd transparent rektangel
För att demonstrera lagerläggning lägger vi en halvtransparent röd rektangel ovanpå rutnätet.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Steg 7: Spara det resulterande XPS‑dokumentet
Slutligen skriver vi XPS‑filen till disk.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Följ dessa steg så kommer du att lyckas lägga till ett visuellt tilltalande rutnät med Visual Brush i din Java‑applikation med Aspose.Page.

## Vanliga användningsområden
- **Rapportbakgrunder:** Lägg till subtila rutnätsmönster i finansiella eller tekniska rapporter för bättre läsbarhet.  
- **Designmallar:** Skapa återanvändbara sidmallar där samma rutnät upprepas över flera sidor.  
- **Markera sektioner:** Överlagra färgade rutnät för att dra uppmärksamhet till specifika dokumentområden.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Rutnätet ser utdraget ut** | Verify that `TileMode` is set to `XpsTileMode.Tile` and that the source and destination rectangles have the same size. |
| **Färgerna ser felaktiga ut** | Ensure you use the correct RGBA values when creating the solid color brush (`createColor(alpha, red, green, blue)`). |
| **Dokumentet sparas inte** | Check that `dataDir` points to an existing writable folder and that you have proper file system permissions. |

## Slutsats
Grattis! Du har lärt dig **hur man lägger till rutnät** med Aspose.Page:s Visual Brush i Java. Denna teknik ger dig fin‑granulär kontroll över mönsterrendering samtidigt som din kod förblir ren och underhållbar.

## Vanliga frågor
### Är Aspose.Page lämplig för professionell dokumentgenerering?
Ja, Aspose.Page är ett robust bibliotek designat för professionell dokumentgenerering i Java.

### Kan jag anpassa rutnätsfärgerna med Visual Brush?
Absolut! Visual Brush låter dig måla med olika färger, vilket ger flexibilitet i anpassning.

### Var kan jag hitta ytterligare support för Aspose.Page?
Besök [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) för community‑support och diskussioner.

### Finns det en gratis provversion av Aspose.Page?
Ja, du kan komma åt den [gratis provversionen](https://releases.aspose.com/) för att utforska Aspose.Page:s funktioner.

### Hur kan jag skaffa en tillfällig licens för Aspose.Page?
Skaffa en [tillfällig licens](https://purchase.aspose.com/temporary-license/) för teständamål.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose