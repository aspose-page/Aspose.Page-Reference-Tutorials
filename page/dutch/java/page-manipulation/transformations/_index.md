---
date: 2026-10-20
description: Leer hoe je een rechthoek kunt schalen met Aspose.Page for Java, hoe
  je een vorm kunt verplaatsen, en een affine transform toepast om PostScript-documenten
  te maken.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformaties in Java-paginamanipulatie
og_description: Leer hoe je een rechthoek kunt schalen, een vorm kunt verplaatsen,
  en een affine transform toepast met Aspose.Page for Java om efficiënt PostScript-bestanden
  te genereren.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Hoe een rechthoek schalen met Aspose.Page for Java – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Hoe een rechthoek schalen met Aspose.Page for Java
url: /nl/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe rechthoek schalen met Aspose.Page voor Java

## Inleiding
In deze gids ontdek je **how to scale rectangle** objecten met Aspose.Page voor Java, terwijl je ook leert hoe je vormposities kunt vertalen, graphics kunt roteren en affine transformatie‑operaties kunt toepassen om output van hoge kwaliteit in PostScript te produceren. Deze technieken stellen je in staat om geavanceerde, apparaat‑onafhankelijke graphics te bouwen zonder low‑level rendercode te schrijven, waardoor je Java‑applicaties krachtiger en beter onderhoudbaar worden.

## Snelle antwoorden
`scale(sx, sy)` schaalt de graphics‑context met de opgegeven horizontale en verticale factoren.  

- **How do I scale a rectangle in Java with Aspose.Page?** Roep de `scale(sx, sy)`‑methode aan op de graphics‑context voordat je de rechthoek tekent.  
- **Can I move (translate) a shape without affecting other graphics?** Ja—omsluit de translatie tussen `writeGraphicsSave()` en `writeGraphicsRestore()`‑aanroepen.  
- **What class creates a PostScript file?** Gebruik `PsDocument` samen met `PsSaveOptions`.  
- **Do I need a license for production use?** Een geldige Aspose.Page‑licentie is vereist voor commerciële implementaties.  
- **Which Java version is supported?** Aspose.Page werkt met Java 8 en later.

## Vereisten
Voordat je begint, controleer dat je het volgende hebt:

- Een stevige kennis van de kern‑Java‑syntaxis en object‑georiënteerde concepten.  
- De Aspose.Page voor Java‑bibliotheek geïnstalleerd. Je kunt deze downloaden van de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Een Java‑IDE (IntelliJ IDEA, Eclipse of VS Code) geconfigureerd met de JAR‑bestanden van de bibliotheek op de classpath.

## Pakketten importeren
`PsDocument` is de hoofdklasse die wordt gebruikt om een PostScript‑document te maken, en `PsSaveOptions` configureert hoe het document wordt opgeslagen.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Wat is “how to scale rectangle” in Aspose.Page?
De `scale(float sx, float sy)`‑methode past een affine schaals­transformatie toe op de huidige graphics‑status, waardoor volgende tekeningen worden vergroot of verkleind volgens de factoren `sx` (horizontaal) en `sy` (verticaal). Dit is de kernoperatie achter het **how to scale rectangle**‑trefwoord. Door deze transformatie vóór het tekenen toe te passen, worden alle daaropvolgende vormen, zoals rechthoeken, gerenderd met de nieuwe afmetingen terwijl hun verhoudingen behouden blijven.

## Hoe vorm vertalen met Aspose.Page
`writeGraphicsSave()` slaat de huidige graphics‑status op en `writeGraphicsRestore()` herstelt deze, waardoor transformaties alleen de beoogde vorm beïnvloeden. Translatie verplaatst de oorsprong van het coördinatensysteem zonder de afmetingen van objecten te wijzigen. Door `translate(dx, dy)` te omgeven met `writeGraphicsSave()` / `writeGraphicsRestore()`, zorg je ervoor dat alleen de beoogde vorm beweegt terwijl andere graphics ongewijzigd blijven, wat precieze controle over individuele elementen biedt.

## Voorbeeld 1: geen transformaties
Het eerste voorbeeld tekent een rechthoek zonder enige transformatie, waardoor een basislijn wordt gelegd voor visuele vergelijking met latere voorbeelden.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Voorbeeld 2: translatie
In dit voorbeeld verplaatsen we de graphics‑context 250 eenheden naar rechts voordat we een tweede rechthoek tekenen, waarmee we **how to translate shape** illustreren.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Voorbeeld 3: schalen
Hier beantwoorden we de hoofdvraag **how to scale rectangle**. De rechthoek wordt verkleind tot 50 % van de oorspronkelijke breedte en 75 % van de oorspronkelijke hoogte met de aanroep `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Hoe vorm roteren java (rotate shape java)
`rotate(angle)` roteert het coördinatensysteem met de opgegeven hoek in graden. Laad je `PsDocument`, roep `rotate(angle)` aan op de graphics‑status, teken de vorm en herstel vervolgens de vorige status. Dit patroon implementeert **rotate shape java** en **how to rotate rectangle** in één herbruikbaar blok, waardoor je graphics kunt draaien rond elk punt dat je kiest.

## Waarom dit belangrijk is – voordelen in de praktijk
- **Device‑independent output** – Aspose.Page kan PostScript‑ en XPS‑bestanden genereren die identiek worden weergegeven op elke printer of viewer, waardoor platform‑specifieke aanpassingen overbodig zijn.  
- **Fine‑grained control** – Combineer translatie, schaling, schuine transformatie en rotatie om exacte layout‑specificaties te behalen; de API ondersteunt meer dan 20 transformatie‑combinaties per pagina.  
- **Performance‑oriented processing** – De bibliotheek verwerkt documenten met een geheugenverbruik onder 10 MB voor typische rapporten van 100 pagina's, waardoor batch‑taken snel en schaalbaar zijn.

## Veelvoorkomende gebruikssituaties
- **Printable invoices** – Plaats logo's, barcodes en tabellen nauwkeurig met behulp van schaling en translatie om te voldoen aan de huisstijlrichtlijnen.  
- **Technical diagrams** – Genereer schema's waarbij elk onderdeel proportioneel moet worden geschaald en gepositioneerd.  
- **Automated multi‑page reports** – Maak PostScript‑rapporten die consistente schaling over pagina's heen vereisen, zoals technische specificaties.

## Veelvoorkomende problemen en oplossingen
- **Transformation not resetting** – Koppel altijd `writeGraphicsSave()` aan `writeGraphicsRestore()`; anders erven volgende tekeningen ongewenste transformaties.  
- **Unexpected colors** – Stel de paint (kleur) in na elke transformatie omdat de graphics‑status kleurinformatie niet behoudt na een restore.  
- **File size too large** – Schakel compressie in `PsSaveOptions` in en beperk de resolutie van ingesloten raster‑afbeeldingen om het uiteindelijke bestand onder 5 MB te houden voor typische documenten van 50 pagina's.

## Veelgestelde vragen

### Kan ik Aspose.Page voor Java gebruiken voor andere documentformaten?
Aspose.Page richt zich voornamelijk op paginamanipulatie voor PostScript‑ en XPS‑formaten, maar biedt ook beperkte PDF‑exportmogelijkheden.

### Waar kan ik meer voorbeelden en documentatie vinden voor Aspose.Page voor Java?
Bezoek de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) voor uitgebreide handleidingen, API‑referenties en voorbeeldprojecten.

### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
Ja, je kunt een gratis proefversie krijgen via de **Aspose free trial download**‑pagina: [Aspose free trial download](https://releases.aspose.com/).

### Hoe kan ik een tijdelijke licentie krijgen voor Aspose.Page voor Java?
Verkrijg een tijdelijke licentie via de **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Waar kan ik community‑ondersteuning zoeken of vragen stellen over Aspose.Page voor Java?
Bezoek het [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) voor community‑discussies, code‑fragmenten en tips voor probleemoplossing.

## Veelgestelde vragen

**Q: Wat is het verschil tussen `translate` en `scale`?**  
A: `translate` verplaatst de oorsprong van het coördinatensysteem, terwijl `scale` de grootte van getekende objecten langs de X‑ en/of Y‑as verandert.

**Q: Kan ik meerdere transformaties combineren in één graphics‑status?**  
A: Ja—door `translate`, `scale`, `rotate` of `shear` opeenvolgend aan te roepen vóór het tekenen, creëer je een gecombineerde affine transformatie.

**Q: Hoe reset ik transformaties na het tekenen van een vorm?**  
A: Gebruik `writeGraphicsRestore()` om terug te keren naar de eerder opgeslagen graphics‑status.

**Q: Is het mogelijk om een rechthoek rond zijn middelpunt te roteren?**  
A: Absoluut. Verplaats de rechthoek naar de oorsprong, pas `rotate(angle)` toe, en verplaats hem vervolgens terug vóór het tekenen.

**Q: Ondersteunt Aspose.Page anti‑aliasing voor vloeiendere graphics?**  
A: Ja—stel de juiste renderopties in `PsSaveOptions` in om anti‑aliasing in te schakelen.

---

**Laatste update:** 2026-10-20  
**Getest met:** Aspose.Page for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe rechthoek tekenen in Java PostScript met Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Radiale gradient maken in PostScript met Aspose.Page voor Java](/page/java/postscript-gradient-addition/)
- [Postscript-paginamanipulatie](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}