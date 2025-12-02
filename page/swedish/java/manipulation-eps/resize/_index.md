---
date: 2025-12-02
description: Lär dig hur du enkelt ändrar storlek på EPS‑filer i Java med Aspose.Page.
  Denna steg‑för‑steg‑guide visar hur du ändrar storlek på EPS med punkter, tum, millimeter
  eller procent.
language: sv
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Hur man ändrar storlek på EPS-filer i Java med Aspose.Page
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ändrar storlek på EPS-filer i Java med Aspose.Page

## Introduktion
Om du letar efter ett pålitligt sätt **hur man ändrar storlek på EPS**-filer programmässigt, har du kommit till rätt ställe. I den här handledningen går vi igenom hur man ändrar storlek på EPS‑bilder i Java med Aspose.Page‑biblioteket. Oavsett om du behöver dubbla storleken, minska den till ett specifikt mått eller arbeta med procent, ger stegen nedan dig full kontroll över utdata-dimensionerna.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page for Java  
- **Kan jag ändra storlek med punkter, tum eller millimeter?** Ja – API:et stöder alla tre enheterna plus procent.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Vilken Java‑version krävs?** Java 8 eller senare.  
- **Är koden trådsäker?** Varje `PsDocument`‑instans är isolerad, så du kan bearbeta filer parallellt.

## Förutsättningar
Innan vi dyker ner i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.Page for Java‑biblioteket. Du kan ladda ner det **[här](https://releases.aspose.com/page/java/)**.  
- En grundläggande förståelse för Java‑programmering.  

## Importera paket
I ditt Java‑projekt, inkludera de nödvändiga importerna så att du kan arbeta med Aspose.Page‑objekt och standard‑I/O‑strömmar.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hur man ändrar storlek på EPS med punkter
Nedan är ett komplett, steg‑för‑steg‑exempel som dubblerar storleken på en EPS‑fil med punkter som måttenhet.

### Steg 1: Ställ in inmatningsströmmen
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Steg 2: Initiera `PsDocument`‑objektet
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Steg 3: Extrahera den aktuella storleken på EPS‑bilden
```java
Dimension oldSize = doc.extractEpsSize();
```

### Steg 4: Skapa en utmatningsström för den ändrade filen
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Steg 5: Ändra storlek och spara EPS med punkter
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Hur man ändrar storlek på EPS med tum
Samma fem‑stegs‑mönster gäller; ersätt bara `Units.Points` med `Units.Inches` och justera skalningsfaktorn efter behov.

## Hur man ändrar storlek på EPS med millimeter
Följ återigen samma steg, byt enheten till `Units.Millimeters`. Detta är praktiskt när du behöver metrisk baserade dimensioner för utskriftsarbetsflöden.

## Hur man ändrar storlek på EPS med procent
För procentbaserad skalning, behåll enheten som `Units.Percent`. Multiplicera den ursprungliga bredden och höjden med önskad procent (t.ex. `0.5` för 50 % minskning).

## Vanliga fallgropar & tips
- **Stäng alltid strömmar** – I produktionskod, omslut strömmar med try‑with‑resources för att undvika fil‑lås.  
- **Bevara bildförhållandet** – Multiplicera både bredd och höjd med samma faktor om du inte avsiktligt vill ha förvrängning.  
- **Kontrollera DPI** – Ändring av storlek ändrar inte DPI; om du behöver en annan DPI, justera den separat efter storleksändring.

## Slutsats
Du vet nu **hur man ändrar storlek på EPS**‑filer i Java med Aspose.Page, oavsett om du föredrar punkter, tum, millimeter eller procent. Denna flexibilitet låter dig integrera EPS‑manipulation i automatiserade pipelines, skrivbordsverktyg eller server‑sidiga tjänster.

## Vanliga frågor

**Q: Kan jag använda detta bibliotek för andra bildformat?**  
A: Nej, Aspose.Page är specialiserat på PostScript‑ och EPS‑filer endast.

**Q: Finns det en gratis provversion tillgänglig för Aspose.Page för Java?**  
A: Ja, du kan utforska den gratis provversionen **[här](https://releases.aspose.com/)**.

**Q: Var kan jag hitta ytterligare hjälp och diskussioner?**  
A: Besök **[Aspose.Page‑forumet](https://forum.aspose.com/c/page/39)** för gemenskapsstöd.

**Q: Hur kan jag få en tillfällig licens?**  
A: Du kan få en tillfällig licens **[här](https://purchase.aspose.com/temporary-license/)**.

**Q: Finns det några exempelprojekt tillgängliga?**  
A: Ja, kolla dokumentationen **[här](https://reference.aspose.com/page/java/)**.

---

**Senast uppdaterad:** 2025-12-02  
**Testad med:** Aspose.Page for Java 24.12 (senaste vid skrivande tidpunkt)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}