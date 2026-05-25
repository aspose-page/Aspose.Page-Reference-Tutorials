---
date: 2026-05-25
description: Lär dig hur du lägger till gradient i XPS-dokument i Java med Aspose.Page.
  Denna steg‑för‑steg‑guide visar hur du lägger till en diagonal gradient, använder
  linjära gradientpenslar och skapar professionella XPS-filer.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Lägg till diagonal gradient i Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Hur man lägger till gradient: Diagonal gradient i Java XPS'
url: /sv/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så lägger du till gradient: Diagonal gradient i Java XPS

## Introduktion
I modern Java‑utveckling ger behärskning av **how to add gradient** till XPS‑dokument dina rapporter ett polerat, iögonfallande utseende som sticker ut. Denna handledning guidar dig genom att skapa en XPS‑fil från grunden, lägga till en diagonal gradient och spara resultatet — allt med Aspose.Page för Java. Du kommer att förstå varför gradienter är viktiga, se de exakta API‑anropen och få praktiska tips för att undvika vanliga fallgropar.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.Page for Java  
- **Vilken metod lägger till gradienten?** `createLinearGradientBrush` med gradientstopp  
- **Behöver jag en licens?** En provversion fungerar för utveckling; en kommersiell licens krävs för produktion  
- **Hur lång tid tar implementeringen?** Cirka 10‑15 minuter för en grundläggande diagonal gradient  
- **Kan jag använda detta med andra Java‑ramverk?** Ja, API:et är ramverks‑agnostiskt  

## Vad är en diagonal gradient i ett XPS-dokument?
En diagonal gradient är en mjuk färgövergång som löper från ett hörn av en form till motsatt hörn, vilket skapar en snedställd visuell effekt. I XPS definieras denna effekt av en linjär gradientpensel som innehåller ordnade gradientstopp som specificerar färger och relativa positioner längs den diagonala linjen.

## Varför lägga till en diagonal gradient med Aspose.Page?
Aspose.Page levererar **100 % renderingsfidelity** för gradienter i mer än 20 XPS‑visare, och det stödjer **30+ XPS‑funktioner** såsom text, bilder och vektorgrafik. API:et abstraherar den komplexa XPS‑markupen, så att du kan fokusera på design samtidigt som du garanteras att samma fil ser identisk ut på Windows, macOS och Linux‑plattformar.

## Förutsättningar
- Grundläggande kunskaper i Java‑programmering.  
- JDK installerat på din maskin.  
- Aspose.Page för Java‑biblioteket – ladda ner det **[här](https://releases.aspose.com/page/java/)**.  
- En IDE såsom IntelliJ IDEA eller Eclipse.

## Importera paket
Börja med att importera de klasser du behöver. Dessa importeringar ger dig åtkomst till geometri, gradienthantering och skapande av XPS‑dokument.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Steg 1: Ställ in ditt projekt
Skapa ett nytt Java‑projekt i din föredragna IDE och lägg till Aspose.Page‑JAR‑filerna i projektets byggsökväg.

## Steg 2: Definiera dokumentkatalog
Ange var den genererade XPS‑filen ska sparas.

```java
String dataDir = "Your Document Directory";
```

## Steg 3: Skapa XPS-dokument
`XpsDocument` är kärnobjektet som representerar en XPS‑fil i minnet. Att instansiera det ger dig en canvas för att lägga till sidor, former och penslar.

```java
XpsDocument doc = new XpsDocument();
```

## Steg 4: Lägg till diagonal gradientväg
Skapa en rektangulär bana som ska ta emot gradienten. Banans geometri använder ett enkelt move‑line‑close‑kommando.  
XpsPath definierar en vektorform i XPS‑dokumentet, såsom en rektangel eller anpassad geometri.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Steg 5: Definiera linjära gradientstopp
Ställ in färgerna och deras positioner. Varje stopp definierar en punkt i gradienten där en specifik färg visas.  
XpsGradientStop representerar ett enskilt färgstopp i en gradient, och specificerar en färg samt dess offset.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Steg 6: Tillämpa linjär gradient på vägen
`XpsLinearGradientBrush` är Aspose.Page:s penseltyp för linjära färgövergångar. Den tar två punkter som definierar gradientens riktning och en samling gradientstopp som bestämmer färgerna längs den linjen.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Steg 7: Spara dokumentet
Spara XPS‑filen på disk. Filen kommer att innehålla rektangeln fylld med den diagonala gradient du definierade.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Hur lägger man till gradient i Java XPS?
Läs in XpsDocument, skapa en `XpsLinearGradientBrush` med startpunkt `(0,0)` och slutpunkt `(width,height)`, fäst gradientstopp, tilldela penseln till en forms `Fill`, och anropa slutligen `save`. Detta koncisa flöde låter dig bädda in en diagonal gradient med bara ett fåtal API‑anrop, vilket håller din kod ren och underhållbar.

## Vanliga fallgropar & tips
- **Gradientriktning** – se till att start- och slutpunkterna för penseln speglar den diagonal du vill ha; att byta dem vänder gradienten.  
- **Färgprecision** – Aspose använder ARGB; inkludera alfa‑kanalen om du behöver transparens.  
- **Filsökväg** – använd alltid en absolut sökväg eller verifiera att den relativa sökvägen pekar på en befintlig skrivbar katalog.

## Ytterligare FAQ

**Q: Hur gör jag **how to add gradient** till en befintlig XPS‑form?**  
A: Skapa en `XpsLinearGradientBrush`, definiera gradientstopp och tilldela den till formens `Fill`‑egenskap som visas i Steg 6.

**Q: Vad gör **apply linear gradient** egentligen bakom kulisserna?**  
A: Det genererar en penseldefinition i XPS‑paketet som refererar till start-/slutpunkterna och en samling gradientstopp, vilka visaren renderar som en mjuk färgövergång.

**Q: Finns det ett snabbt sätt att **how to use aspose** för andra XPS‑funktioner?**  
A: Ja, Aspose.Page‑API:et innehåller metoder för att lägga till bilder, text och anpassade former — utforska helt enkelt `XpsDocument`‑klassen för ytterligare hjälpfunktioner.

**Q: Kan jag **add gradient path** till icke‑rektangulära former?**  
A: Absolut. Definiera vilken geometri som helst med `createPathGeometry` och sätt sedan dess `Fill` till en gradientpensel.

**Q: Påverkar gradienten filstorleken avsevärt?**  
A: Endast marginellt; gradientdefinitioner är lätta XML‑poster i XPS‑paketet.

---

**Senast uppdaterad:** 2026-05-25  
**Testat med:** Aspose.Page for Java 24.11  
**Författare:** Aspose

## Relaterade handledningar

- [Aspose Page XPS Gradient‑tillägg](/page/java/xps-gradient-addition/)
- [Java XPS Text‑tillägg – Aspose.Page‑handledning](/page/java/xps-text-manipulation/add-text/)
- [Hur man lägger till bild i Java XPS‑dokument – En enkel guide med Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}