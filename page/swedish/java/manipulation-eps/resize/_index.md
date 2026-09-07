---
date: 2026-08-29
description: Lär dig hur du med Java vektorändrar storlek på EPS-filer med Aspose.Page.
  Denna steg‑för‑steg‑guide visar hur du ändrar storlek på EPS med points, inches,
  millimeters eller percentages.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Ändra storlek på EPS-fil i Java
og_description: Java vektorändring låter dig justera EPS-filens dimensioner direkt
  i Java. Med Aspose.Page kan du ändra storlek med points, inches, millimeters eller
  percentages samtidigt som du bevarar vector quality.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Java vektorändring: ändra EPS-dimensioner med Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Hur man med Java vektorändrar storlek på EPS-filer med Aspose.Page
url: /sv/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man Java-vektorändrar storlek på EPS-filer med Aspose.Page

## Introduktion
Om du behöver **java vector resize** EPS-filer programatiskt, är du på rätt plats. Denna handledning guidar dig genom att ändra storlek på EPS-bilder i Java med hjälp av Aspose.Page-biblioteket. Oavsett om du vill fördubbla storleken, minska den till en specifik mått, eller arbeta med procent, ger stegen nedan dig full kontroll över utdata-dimensionerna. Att behärska hur man ändrar storlek på EPS är avgörande när du anpassar grafik för olika trycklayouter, skärmupplösningar eller varumärkesriktlinjer.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page for Java  
- **Kan jag ändra storlek med punkter, tum eller millimeter?** Ja – API:et stöder alla tre enheter plus procent.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Vilken Java-version krävs?** Java 8 eller senare.  
- **Är koden trådsäker?** Varje `PsDocument`-instans är isolerad, så du kan bearbeta filer parallellt.  

## Vad är EPS och varför ändra storlek på det?
Encapsulated PostScript (EPS) är ett vektorformat som är allmänt använt för tryck och publicering. Ibland skapas den ursprungliga EPS-filen i en storlek som inte matchar ditt måloutput – till exempel kan en logotyp designad i 72 pts behöva vara 144 pts för en större broschyr. Att veta **how to resize eps** låter dig behålla vektor kvaliteten samtidigt som du anpassar dimensionerna till vilket arbetsflöde som helst.

## Varför använda Aspose.Page för att ändra storlek på EPS?
Aspose.Page erbjuder ett enkelt API som låter dig ange målstorleken i någon av de stödda enheterna samtidigt som den automatiskt bevarar vektorstrukturen. Biblioteket hanterar enhetskonvertering internt, så du kan fokusera på de önskade dimensionerna utan manuella beräkningar.

- **Stöder fyra mätenheter** – Points, Inches, Millimeters, and Percent.  
- **Inga externa beroenden** – rent Java API, inga inhemska bibliotek krävs.  
- **Högpresterande bearbetning** – kan hantera upp till 500 EPS-filer per minut på en standard 8‑kärnig server.  
- **Bevarar vektorfidelitet** – utdata förblir fullt skalbar utan rasterisering.

## Förutsättningar
Innan vi dyker ner i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.Page för Java-biblioteket. Du kan ladda ner det **[Aspose.Page för Java nedladdningssida](https://releases.aspose.com/page/java/)**.  
- En grundläggande förståelse för Java-programmering.  

## Importera paket
I ditt Java-projekt, inkludera de nödvändiga importerna så att du kan arbeta med Aspose.Page-objekt och standard I/O-strömmar.

`PsDocument` representerar ett EPS-dokument som laddas i minnet.  
`Units` är en uppräkning som definierar de mätenheter som API:et accepterar.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hur man ändrar EPS-dimensioner med olika enheter
Du kan ändra EPS-dimensioner genom att anropa `resizeEps`-metoden med önskad bredd, höjd och ett `Units`-enum‑värde; detta fungerar för punkter, tum, millimeter eller procent. Det samma femstegs‑mönstret gäller för varje enhet, vilket gör API:et förutsägbart och enkelt att integrera.

`resizeEps` ändrar storlek på EPS‑canvasen till de angivna dimensionerna samtidigt som den interna vektordatan bevaras.

## Hur man ändrar storlek på EPS med punkter
Ladda ditt EPS, ange den nya storleken i punkter och spara resultatet. Detta tillvägagångssätt fördubblar de ursprungliga dimensionerna samtidigt som bildförhållandet bevaras. Att använda punkter ger dig exakt kontroll över utskriftsklara storlekar, vilket är särskilt användbart för typografiska layouter och högupplöst output.

### Steg 1: konfigurera inmatningsströmmen
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Steg 2: initiera `PsDocument`-objektet
`PsDocument` laddar käll‑EPS‑filen och tillhandahåller metoder för manipulation.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Steg 3: extrahera den aktuella storleken på EPS‑bilden
```java
Dimension oldSize = doc.extractEpsSize();
```

### Steg 4: skapa en utmatningsström för den ändrade filen
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Steg 5: ändra storlek och spara EPS med punkter
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Hur man ändrar storlek på EPS med tum
Att ändra storlek med tum låter dig matcha specifikationer som definieras i imperiella enheter, såsom broschyrlayouter eller US‑baserade tryckstandarder. Ange målbredd och höjd i tum, så konverterar API:et dem till lämpliga interna enheter innan transformationen tillämpas.

## Hur man ändrar storlek på EPS med millimeter
När du arbetar med metriska arbetsflöden säkerställer angivning av dimensioner i millimeter konsistens med pappersstorlekar och tryckutrustning som används utanför USA. Biblioteket hanterar automatiskt konverteringen från millimeter till det interna koordinatsystemet.

## Hur man ändrar storlek på EPS med procent
Att ändra storlek med procent skalar de ursprungliga dimensionerna proportionellt, vilket är praktiskt för snabba storleksjusteringar utan att beräkna absoluta värden. Till exempel minskar en faktor på `0.5` både bredd och höjd med 50 %.

## Vanliga fallgropar och tips
- **Stäng alltid strömmar** – I produktionskod, omslut strömmar med try‑with‑resources för att undvika fil lås.  
- **Bevara bildförhållandet** – Multiplicera både bredd och höjd med samma faktor om du inte avsiktligt vill ha förvrängning.  
- **Kontrollera DPI** – Ändring av storlek ändrar inte DPI; om du behöver ett annat DPI, justera det separat efter storleksändring.  
- **Trådsäkerhet** – Skapa ett nytt `PsDocument` per tråd; delning av samma instans kan leda till oväntade resultat.  

## Vanliga frågor

**Q: Kan jag använda detta bibliotek för andra bildformat?**  
A: Nej, Aspose.Page är specialiserat för PostScript och EPS-filer endast.

**Q: Finns det en gratis provversion tillgänglig för Aspose.Page för Java?**  
A: Ja, du kan utforska gratisprovversionssidan **[Aspose gratis provversionssida](https://releases.aspose.com/)**.

**Q: Var kan jag hitta ytterligare hjälp och diskussioner?**  
A: Besök **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** för gemenskapsstöd.

**Q: Hur kan jag få en tillfällig licens?**  
A: Du kan få en tillfällig licens **[tillfällig licensförfrågningssida](https://purchase.aspose.com/temporary-license/)**.

**Q: Finns det exempelprojekt tillgängliga?**  
A: Ja, se dokumentationen **[Aspose.Page Java API-referens](https://reference.aspose.com/page/java/)**.

---

**Senast uppdaterad:** 2026-08-29  
**Testad med:** Aspose.Page för Java 24.12 (senaste vid skrivande tidpunkt)  
**Författare:** Aspose

## Relaterade handledningar

- [Ändra storlek på EPS med Aspose.Page – Java EPS-manipulation](/page/java/manipulation-eps/)
- [Hur man beskär EPS-filer i Java – Aspose.Page-guide](/page/java/manipulation-eps/crop/)
- [Hur man skalar rektangel med Aspose.Page för Java](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}