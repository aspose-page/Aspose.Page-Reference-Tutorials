---
date: 2026-04-30
description: Lär dig hur du skapar XPS‑dokument i Java och lägger till en opacitetsmask
  med Aspose.Page Java. Steg‑för‑steg‑guide med kodexempel.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Ställ in opacitetsmask i Java XPS
second_title: Aspose.Page Java API
title: Skapa XPS-dokument i Java – Ställ in opacitetsmask med Aspose.Page
url: /sv/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in Opacitetsmask i Java XPS med Aspose.Page Java

## Introduktion
I den här handledningen kommer du att **create XPS document Java** filer och lära dig hur du applicerar en opacitetsmask som ger dina grafik ett polerat, halvgenomskinligt utseende. Vi går igenom hela processen — från att initiera ett XPS-dokument, lägga till en canvas, rita en rektangel, till att fästa en bildbaserad opacitetsmask — med det intuitiva Aspose.Page Java API:et. I slutet kommer du att kunna generera professionella XPS-filer programatiskt och återanvända masken på vilken form du än behöver.

## Snabba svar
- **Vad gör en opacitetsmask?** Den definierar varierande transparensnivåer för en form, så att underliggande innehåll kan visas igenom.  
- **Vilket bibliotek krävs?** Aspose.Page for Java (aspose page java).  
- **Behöver jag en licens?** En tillfällig licens fungerar för testning; en full licens krävs för produktion.  
- **Hur många kodrader?** Ungefär 20 rader Java plus några installationssatser.  
- **Kan jag återanvända masken på flera former?** Ja, du kan tilldela samma `ImageBrush` till flera vägar.

## Vad är en opacitetsmask i XPS?
En opacitetsmask är en bitmap eller vektor som styr alfa (transparens) för varje pixel i en form. När den appliceras på en rektangel blir delar av rektangeln helt ogenomskinliga, delvis genomskinliga eller helt genomskinliga, vilket skapar sofistikerade visuella effekter utan extra ritlager.

## Varför använda Aspose.Page Java för att **create XPS document java**?
- **Pure Java API** – Inga inhemska beroenden, så samma kod körs på Windows, Linux eller macOS.  
- **Full XPS spec compliance** – Masker renderas exakt som definierat av XPS-standarden.  
- **Object‑oriented design** – Liknande .NET, vilket gör det enkelt att plocka upp om du har använt Aspose i andra språk.  
- **High performance** – Optimerad för stora dokument och batchbearbetning.

## Vanliga användningsfall
- **Watermarking** – Applicera en halvgenomskinlig logotyp över sidor.  
- **Dynamic theming** – Ändra den visuella stilen på UI-element i genererade rapporter.  
- **Print‑ready previews** – Visa hur en design ser ut med varierande opacitet innan den skickas till en skrivare.

## Förutsättningar
- Grundläggande förståelse för Java-programmering.  
- Aspose.Page för Java-biblioteket installerat. Du kan ladda ner det **[here](https://releases.aspose.com/page/java/)**.  
- En giltig licens för Aspose.Page. Om du inte har en, skaffa en tillfällig licens **[here](https://purchase.aspose.com/temporary-license/)**.  
- En utvecklingsmiljö som kan kompilera och köra Java-applikationer (t.ex. IntelliJ IDEA, Eclipse eller VS Code).

## Importera paket
Börja med att importera de nödvändiga klasserna från Aspose.Page‑biblioteket. Detta säkerställer att API:et är tillgängligt för ditt projekt.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Steg‑för‑steg guide

### Steg 1: Skapa ett nytt XPS-dokument
Först, instansiera ett nytt XPS-dokument som kommer att hålla all vår grafik.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Steg 2: Lägg till en canvas
En canvas fungerar som en rityta inne i XPS‑sidan.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Steg 3: Lägg till en rektangel och applicera en solid fyllning
Här skapar vi en rektangelväg och ger den en solid röd fyllning. Denna rektangel kommer senare att få opacitetsmasken.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Steg 4: Lägg till opacitetsmask med en ImageBrush
Vi laddar en TIFF‑bild, definierar käll‑ och destinationsrektanglar och sätter penseln till tile‑läge så att masken upprepas om det behövs.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Steg 5: Spara det resulterande XPS-dokumentet
Till sist sparar vi dokumentet till disk. Utdatafilen kommer att innehålla rektangeln med den applicerade opacitetsmasken.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Följ dessa steg noggrant för att integrera **add opacity mask**‑funktionaliteten i ditt Java XPS‑dokument med Aspose.Page.

## Vanliga problem & felsökning
- **Image not found** – Verifiera att `dataDir` pekar på rätt mapp och att `R08SY_NN.tif` finns.  
- **Mask appears solid** – Säkerställ att källbilden faktiskt innehåller varierande alfavärden; en helt ogenomskinlig bild visar ingen transparens.  
- **Tile mode not respected** – Destinationsrektangeln måste vara mindre än källrektangeln för att tilning ska märkas.

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med alla Java‑utvecklingsmiljöer?**  
A: Ja, Aspose.Page är designat för att fungera sömlöst med olika Java‑IDE:n och byggverktyg.

**Q: Kan jag använda Aspose.Page utan en licens?**  
A: Även om du kan utvärdera biblioteket med en tillfällig licens, krävs en full licens för produktionsanvändning.

**Q: Finns det några begränsningar i provversionen?**  
A: Provet kan ha storleks‑ eller funktionsbegränsningar; konsultera den officiella dokumentationen för detaljer.

**Q: Hur kan jag få support för Aspose.Page?**  
A: Besök **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** för gemenskapshjälp eller köp en licens för premiumassistans.

**Q: Finns det någon pengarna‑tillbaka‑garanti för Aspose.Page?**  
A: Se **[purchase page](https://purchase.aspose.com/buy)** för information om återbetalningspolicyer.

---

**Senast uppdaterad:** 2026-04-30  
**Testat med:** Aspose.Page Java 24.11 (senaste vid skrivande)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}