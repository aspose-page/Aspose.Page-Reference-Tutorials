---
date: 2025-12-11
description: Leer hoe je rechthoekvormen tekent in Java PostScript met Aspose.Page.
  Deze stapsgewijze gids laat zien hoe je verf instelt, de rechthoekkleur in Java
  instelt en levendige graphics maakt.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Hoe een rechthoek te tekenen in Java PostScript met Aspose.Page
url: /nl/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een rechthoek tekenen in Java PostScript met Aspose.Page

## Inleiding
If you need to **how to draw rectangle** shapes inside a Java PostScript file, you’ve come to the right place. In this tutorial we’ll walk through using Aspose.Page for Java to add colorful rectangles, control their fill and stroke, and save the result as a PostScript document. You’ll see exactly **how to set paint**, how to define the rectangle’s geometry, and why this approach is ideal for generating printable graphics programmatically.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java  
- **Kan ik de kleuren van de rechthoek wijzigen?** Ja – gebruik `setPaint` met elke `java.awt.Color`  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie  
- **Welke paginagrootte wordt in het voorbeeld gebruikt?** A4 (standaard `PsSaveOptions`)  
- **Is de code compatibel met Java 8+?** Absoluut – het gebruikt standaard AWT‑klassen  

## Vereisten
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Basiskennis van Java‑programmeren.  
- Aspose.Page for Java library installed. If not, download it from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Een Java‑ontwikkelomgeving geïnstalleerd op uw machine.

## Importeer pakketten
In your Java project, start by importing the necessary packages:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hoe een rechthoek tekenen in Java PostScript
Below is the complete workflow broken into clear steps. Each step includes a short explanation followed by the original code block (unchanged).

### Stap 1: Paint instellen voor het vullen van de rechthoek  
**Hoe paint instellen** – we kiezen een oranje vulkleur voor de eerste rechthoek.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Stap 2: Paint instellen voor het omlijnen van de rechthoek  
**Rechthoekkleur instellen java** – nu veranderen we de paint naar rood en definiëren we een lijnbreedte.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Stap 3: Huidige pagina sluiten en document opslaan  
After drawing, we close the page and persist the file.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Waarom Aspose.Page gebruiken voor rechthoekgrafieken?
- **Cross‑platform**: Genereert standaard PostScript dat op elke printer werkt.  
- **Fijne controle**: U kunt vulkleuren, lijnkleuren en lijndiktes onafhankelijk instellen.  
- **Geen externe afhankelijkheden**: Gebruikt alleen de ingebouwde AWT‑geometryklassen.  

## Veelvoorkomende problemen & tips
- **Bestandspadfouten** – zorg ervoor dat `dataDir` eindigt met een scheidingsteken (`/` of `\\`).  
- **Licentie‑uitzonderingen** – de proefversie voegt een watermerk toe; verkrijg een volledige licentie voor productiegebruik.  
- **Kleurzichtbaarheid** – sommige printers kunnen bepaalde RGB‑waarden anders interpreteren; test eerst met een eenvoudige zwarte rechthoek.

## Conclusie
In this guide we demonstrated **how to draw rectangle** shapes in a Java PostScript document, covered **how to set paint**, and showed how to **set rectangle color java** using Aspose.Page. Feel free to experiment with different shapes, colors, and line styles to create rich printable graphics for reports, invoices, or custom prints.

## Veelgestelde vragen

### Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?
Aspose.Page primarily supports Java, but similar libraries are available for other languages.

### Is er een proefversie van Aspose.Page voor Java beschikbaar?
Yes, you can explore the features of Aspose.Page for Java with the [free trial version](https://releases.aspose.com/).

### Waar kan ik extra hulp en discussies vinden?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to engage with the community and get assistance.

### Hoe kan ik een tijdelijke licentie voor Aspose.Page voor Java verkrijgen?
Get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Waar kan ik een gelicentieerde versie van Aspose.Page voor Java kopen?
Buy a licensed version [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Kan ik de grootte van de rechthoek dynamisch wijzigen?*  
**A:** Ja – wijzig eenvoudig de `Rectangle2D.Float(x, y, width, height)` parameters voordat u `fill` of `draw` aanroept.

**Q:** *Is het mogelijk om tekst binnen de rechthoek toe te voegen?*  
**A:** Absoluut. Na het tekenen van de rechthoek, gebruik `document.drawString(...)` met het gewenste lettertype en positie.

**Q:** *Ondersteunt Aspose.Page andere vormen zoals cirkels of polygonen?*  
**A:** Ja, de API biedt methoden zoals `drawEllipse` en `drawPolygon` voor diverse vectorafbeeldingen.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}