---
date: 2026-01-02
description: Lär dig hur du lägger till en opacitetsmask i XPS‑dokument med Aspose.Page
  Java. Steg‑för‑steg‑guide för att skapa en opacitetsmask‑rektangel och förbättra
  den visuella kvaliteten.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Ställ in opacitetsmask i Java XPS med Aspose.Page Java
url: /sv/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in opacitetsmask i Java XPS med Aspose.Page Java

## Introduction
Välkommen till vår omfattande guide om **aspose page java** opacitetsmasker. I den här handledningen kommer du att lära dig hur du skapar ett XPS-dokument, lägger till en canvas och applicerar en opacitetsmask på en rektangel – allt med det kraftfulla Aspose.Page Java API:et. I slutet kommer du att kunna lägga till opacitetsmask‑rektanglar som ger dina XPS-filer ett polerat, halvgenomskinligt utseende.

## Quick Answers
- **What does an opacity mask do?** Vad gör en opacitetsmask? Den definierar varierande transparensnivåer för en form, så att underliggande innehåll kan visas igenom.  
- **Which library is required?** Vilket bibliotek krävs? Aspose.Page for Java (aspose page java).  
- **Do I need a license?** Behöver jag en licens? En tillfällig licens fungerar för testning; en full licens krävs för produktion.  
- **How many lines of code?** Hur många kodrader? Ungefär 20 rader Java plus några installationssatser.  
- **Can I reuse the mask on multiple shapes?** Kan jag återanvända masken på flera former? Ja, du kan tilldela samma ImageBrush till flera vägar.

## What is an Opacity Mask in XPS?
En opacitetsmask är en bitmap eller vektor som styr alfan (transparensen) för varje pixel i en form. När den appliceras på en rektangel blir delar av rektangeln helt ogenomskinliga, delvis genomskinliga eller helt genomskinliga, vilket skapar sofistikerade visuella effekter.

## Why Use Aspose.Page Java for Opacity Masks?
- **Full .NET‑style API in Java** – intuitiv objektmodell.  
- **No external dependencies** – fungerar med ren Java.  
- **High‑fidelity rendering** – maskerna renderas exakt enligt XPS‑specifikationen.  
- **Cross‑platform** – körs på Windows, Linux eller macOS utan ändringar.

## Prerequisites
Innan du börjar, se till att du har:
- En grundläggande förståelse för Java‑programmering.  
- Aspose.Page for Java‑biblioteket installerat. Du kan ladda ner det **[here](https://releases.aspose.com/page/java/)**.  
- En giltig licens för Aspose.Page. Om du inte har en, skaffa en tillfällig licens **[here](https://purchase.aspose.com/temporary-license/)**.  
- En utvecklingsmiljö som kan kompilera och köra Java‑applikationer (t.ex. IntelliJ IDEA, Eclipse eller VS Code).

## Import Packages
Starta med att importera de nödvändiga klasserna från Aspose.Page‑biblioteket. Detta säkerställer att API:et är tillgängligt för ditt projekt.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Step‑by‑Step Guide

### Step 1: Create a New XPS Document
Först, instansiera ett nytt XPS‑dokument som kommer att innehålla all vår grafik.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Step 2: Add a Canvas
En canvas fungerar som en rityta inne i XPS‑sidan.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Step 3: Add a Rectangle and Apply a Solid Fill
Här skapar vi en rektangelväg och ger den en solid röd fyllning. Denna rektangel kommer senare att få en opacitetsmask.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Step 4: Add Opacity Mask Using an ImageBrush
Vi laddar en TIFF‑bild, definierar käll‑ och destinationsrektanglar och sätter penseln till tile‑läge så att masken upprepas om det behövs.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Step 5: Save the Resultant XPS Document
Slutligen sparar vi dokumentet till disk. Utdatafilen kommer att innehålla rektangeln med den applicerade opacitetsmasken.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Följ dessa steg noggrant för att integrera **add opacity mask**‑funktionalitet i ditt Java XPS‑dokument med Aspose.Page.

## Common Issues & Troubleshooting
- **Image not found** – Bilden hittades inte – Verifiera att `dataDir` pekar på rätt mapp och att `R08SY_NN.tif` finns.  
- **Mask appears solid** – Masken ser solid ut – Säkerställ att källbilden faktiskt innehåller varierande alfa‑värden; en helt ogenomskinlig bild visar ingen transparens.  
- **Tile mode not respected** – Tile‑läget respekteras inte – Destinationsrektangeln måste vara mindre än källrektangeln för att tiling ska märkas.

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with all Java development environments?**  
A: Ja, Aspose.Page är designat för att fungera sömlöst med olika Java‑IDE:er och byggverktyg.

**Q: Can I use Aspose.Page without a license?**  
A: Även om du kan utvärdera biblioteket med en tillfällig licens, krävs en full licens för produktionsanvändning.

**Q: Are there any limitations on the trial version?**  
A: Utvärderingsversionen kan ha storleks‑ eller funktionsbegränsningar; konsultera den officiella dokumentationen för detaljer.

**Q: How can I get support for Aspose.Page?**  
A: Besök **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** för community‑hjälp eller köp en licens för premium‑support.

**Q: Is there a money‑back guarantee for Aspose.Page?**  
A: Se **[purchase page](https://purchase.aspose.com/buy)** för information om återbetalningspolicy.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Page Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}