---
date: 2026-02-07
description: Lär dig hur du ändrar storlek på EPS‑filer i Java och ändrar EPS‑dimensioner
  med Aspose.Page. Denna steg‑för‑steg‑guide visar hur du ändrar storlek på EPS med
  punkter, tum, millimeter eller procent.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Hur man ändrar storlek på EPS‑filer i Java med Aspose.Page
url: /sv/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ändrar storlek på EPS-filer i Java med Aspose.Page

## Introduction
Om du letar efter ett pålitligt sätt **how to resize EPS** filer programatiskt, har du kommit till rätt ställe. I den här handledningen går vi igenom hur man ändrar storlek på EPS‑bilder i Java med Aspose.Page‑biblioteket. Oavsett om du behöver dubbla storleken, minska den till ett specifikt mått eller arbeta med procent, ger stegen nedan dig full kontroll över utmatningsdimensionerna. Att förstå **how to resize eps** är avgörande när du behöver anpassa grafik för olika trycklayouter eller skärmupplösningar.

## Quick Answers
- **Vilket bibliotek behövs?** Aspose.Page for Java  
- **Kan jag ändra storlek med punkter, tum eller millimeter?** Ja – API‑et stödjer alla tre enheterna plus procent.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Vilken Java‑version krävs?** Java 8 eller senare.  
- **Är koden trådsäker?** Varje `PsDocument`‑instans är isolerad, så du kan bearbeta filer parallellt.  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) är ett populärt vektorformat som används inom publicering och tryck. Ibland skapas den ursprungliga EPS‑filen i en storlek som inte matchar ditt måloutput – till exempel kan en logotyp designad i 72 pt behöva vara 144 pt för en större broschyr. Att veta **how to resize eps** låter dig behålla vektor‑kvaliteten samtidigt som du anpassar dimensionerna till vilket arbetsflöde som helst.

## Why Use Aspose.Page for Resizing EPS?
- **Full kontroll över enheter** – punkter, tum, millimeter eller procent.  
- **Inga externa beroenden** – ren Java‑API, inga inhemska bibliotek.  
- **Hög prestanda** – lämplig för batch‑bearbetning på servrar.  
- **Bevarar vektorfidelitet** – utdata förblir skalbar utan rasterisering.

## Prerequisites
Innan vi dyker ner i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.Page for Java‑biblioteket. Du kan ladda ner det **[here](https://releases.aspose.com/page/java/)**.  
- En grundläggande förståelse för Java‑programmering.  

## Import Packages
I ditt Java‑projekt, inkludera de nödvändiga importerna så att du kan arbeta med Aspose.Page‑objekt och standard‑I/O‑strömmar.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
Biblioteket låter dig **change eps dimensions** enkelt genom att välja rätt `Units`‑enum. Nedan går vi igenom samma fem‑stegs‑mönster för punkter, tum, millimeter och procent. Det enda som förändras är enheten du skickar till `resizeEps`.

## How to Resize EPS Using Points
Nedan är ett komplett, steg‑för‑steg‑exempel som fördubblar storleken på en EPS‑fil med punkter som måttenhet.

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
Samma fem‑stegs‑mönster gäller; ersätt bara `Units.Points` med `Units.Inches` och justera skalfaktorn till önskat tumvärde.

## How to Resize EPS Using Millimeters
Följ åter samma steg, men byt enheten till `Units.Millimeters`. Detta är praktiskt när du behöver metriska dimensioner för tryckarbetsflöden.

## How to Resize EPS Using Percentages
För procentbaserad skalning, behåll enheten som `Units.Percent`. Multiplicera den ursprungliga bredden och höjden med önskad procent (t.ex. `0.5` för en 50 % minskning).

## Common Pitfalls & Tips
- **Stäng alltid strömmar** – I produktionskod, omslut strömmar med try‑with‑resources för att undvika fil‑lås.  
- **Bevara bildförhållandet** – Multiplicera både bredd och höjd med samma faktor om du inte avsiktligt vill ha förvrängning.  
- **Kontrollera DPI** – Ändring av storlek ändrar inte DPI; om du behöver ett annat DPI, justera det separat efter skalning.  
- **Trådsäkerhet** – Skapa ett nytt `PsDocument` per tråd; delning av samma instans kan leda till oväntade resultat.  

## Frequently Asked Questions

**Q: Kan jag använda detta bibliotek för andra bildformat?**  
A: Nej, Aspose.Page är specialiserat på PostScript‑ och EPS‑filer endast.

**Q: Finns det en gratis provversion av Aspose.Page för Java?**  
A: Ja, du kan utforska den gratis provversionen **[here](https://releases.aspose.com/)**.

**Q: Var kan jag hitta ytterligare hjälp och diskussioner?**  
A: Besök **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** för gemenskapsstöd.

**Q: Hur kan jag få en tillfällig licens?**  
A: Du kan få en tillfällig licens **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Finns det exempelprojekt tillgängliga?**  
A: Ja, se dokumentationen **[here](https://reference.aspose.com/page/java/)**.

---

**Senast uppdaterad:** 2026-02-07  
**Testat med:** Aspose.Page for Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}