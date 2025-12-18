---
date: 2025-12-18
description: Lär dig hur du lägger till ett rutnät och en transparent rektangel i
  Java XPS‑dokument med Aspose.Page. Steg‑för‑steg‑guide för att spara XPS‑dokument
  effektivt.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Hur man lägger till ett rutnät med Visual Brush i Java
url: /sv/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så lägger du till rutnät med Visual Brush i Java

## Introduktion
Om du letar efter **hur man lägger till rutnät** i dina Java‑genererade XPS‑dokument, har du kommit till rätt ställe. I den här handledningen går vi igenom hur du lägger till ett rutnät med en Visual Brush, lägger ett transparent rektangel ovanpå, och slutligen **sparar XPS‑dokument** med hjälp av Aspose.Page Java‑API. När du är klar har du en polerad visuell komponent som kan återanvändas i rapporter, fakturor eller någon annan dokumenttung applikation.

## Snabba svar
- **Vad gör en Visual Brush?** Den målar ett definierat område med återanvändbart visuellt innehåll, perfekt för upprepade mönster som rutnät.  
- **Kan jag ändra rutnätsfärgen?** Ja – ändra brushens solid‑color‑inställningar.  
- **Hur lägger jag till ett transparent rektangel ovanpå rutnätet?** Använd `setOpacity` på en path fylld med en solid färg.  
- **Vilken metod sparar filen?** `doc.save(...)` skriver XPS‑filen till disk.  
- **Behöver jag en licens?** En temporär eller fullständig licens krävs för produktionsanvändning.

## Vad är ett Visual Brush‑rutnät?
En Visual Brush låter dig definiera en liten visuell komponent (rutnätsmönstret) och sedan tile‑a den över ett större område. Detta tillvägagångssätt är mer minnes‑effektivt än att rita varje linje individuellt och ger pixel‑perfekt upprepning.

## Varför använda Aspose.Page för denna uppgift?
- **Cross‑platform** – Fungerar på alla OS som stödjer Java.  
- **High‑fidelity rendering** – Precisionskontroll över färger, opacitet och tile‑ning.  
- **Inga externa beroenden** – Allt hanteras via Aspose.Page‑biblioteket.

## Förutsättningar
Innan vi dyker ner, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page‑biblioteket installerat – du kan ladda ner det från [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 eller senare installerat på din utvecklingsmaskin.

## Importera paket
Först importerar du de nödvändiga klasserna så att kompilatorn vet var den ska hitta typerna vi ska använda:

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

## Steg‑för‑steg‑guide

### Steg 1: Ställ in ditt projekt
Skapa en ny `XpsDocument`‑instans och peka på den mapp där du vill spara utdatafilen.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Steg 2: Skapa en magenta Visual Brush för rutnätet
Vi definierar en liten magenta form som kommer att tile‑as över rutnätsområdet.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Steg 3: Definiera geometri för rutnäts‑brushen
Ställ in det rektangulära området som ska ta emot den tile‑ade visuella komponenten.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Steg 4: Skapa en ny canvas för dokumentet
Lägg till en canvas i dokumentet och placera den där rutnätet ska visas.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Steg 5: Lägg till rutnätet på canvasen
Applicera visual brush på geometrin, vilket möjliggör tile‑ning.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Steg 6: Lägg till ett transparent rött rektangel (sekundär funktion)
Här demonstrerar vi **add transparent rectangle** ovanpå rutnätet för att framhäva.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Steg 7: Spara det resulterande XPS‑dokumentet
Till sist skriver vi dokumentet till disk – detta är **save XPS document**‑steget.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Följ dessa steg så får du ett professionellt utseende rutnät med ett transparent lager, allt genererat programatiskt.

## Vanliga problem & tips

- **Felaktig tile‑storlek:** Säkerställ att `Rectangle2D` som används för brushen matchar den avsedda upprepningsstorleken; annars kan mönstret bli utdraget.
- **Opacitet inte tillämpad:** Kom ihåg att anropa `setOpacity` på den path du vill göra transparent; det påverkar inte själva brushen.
- **Filen sparas inte:** Kontrollera att `dataDir` pekar på en befintlig mapp och att din applikation har skrivbehörighet.

## Vanliga frågor

**Q: Är Aspose.Page lämpligt för professionell dokumentgenerering?**  
A: Ja, Aspose.Page är ett robust bibliotek designat för högkvalitativ XPS‑ och PDF‑generering i Java.

**Q: Kan jag anpassa rutnätsfärgerna med Visual Brush?**  
A: Absolut! Ändra parametrarna i `createColor` i brushens `setFill`‑anrop till vilka RGBA‑värden du önskar.

**Q: Var kan jag hitta ytterligare support för Aspose.Page?**  
A: Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för community‑hjälp och officiella svar.

**Q: Finns det en gratis provversion av Aspose.Page?**  
A: Ja, du kan komma åt [free trial](https://releases.aspose.com/) för att utforska alla funktioner innan du köper.

**Q: Hur kan jag skaffa en temporär licens för testning?**  
A: Skaffa en [temporary license](https://purchase.aspose.com/temporary-license/) som fungerar för utveckling och utvärdering.

---

**Senast uppdaterad:** 2025-12-18  
**Testad med:** Aspose.Page for Java 23.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}