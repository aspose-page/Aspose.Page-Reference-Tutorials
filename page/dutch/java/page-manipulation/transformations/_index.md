---
date: 2026-02-07
description: Leer hoe je een rechthoek kunt schalen met Aspose.Page voor Java, hoe
  je een vorm kunt verplaatsen, en een affiene transformatie kunt toepassen om PostScript‑documenten
  te maken.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Hoe een rechthoek te schalen met Aspose.Page voor Java
url: /nl/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een rechthoek schalen met Aspose.Page voor Java

## Inleiding
Welkom bij een uitgebreide gids over het benutten van de krachtige functies van **Aspose.Page for Java** om verschillende paginatransformaties uit te voeren. In deze tutorial leer je **how to scale rectangle**, vormen vertalen, objecten roteren en **apply affine transform** technieken toepassen tijdens het maken van een **PostScript document**. Deze mogelijkheden stellen je in staat om rijke, grafisch intensieve Java‑applicaties te bouwen zonder je bezig te houden met low‑level rendering‑code.

## Snelle antwoorden
- **Hoe schaal ik een rechthoek in Java met Aspose.Page?** Gebruik de `document.scale()`‑methode vóór het tekenen van de vorm.  
- **Kan ik een vorm verplaatsen (vertalen) zonder andere graphics te beïnvloeden?** Ja—sla de graphics‑status op, roep `document.translate(x, y)` aan, teken, en herstel vervolgens de status.  
- **Welke klasse maakt een PostScript‑bestand?** `PsDocument` samen met `PsSaveOptions`.  
- **Heb ik een licentie nodig voor productiegebruik?** Een geldige Aspose.Page‑licentie is vereist voor commerciële implementaties.  
- **Welke Java‑versie wordt ondersteund?** Aspose.Page werkt met Java 8 en hoger.

## Voorvereisten
Voordat we in de stap‑voor‑stap‑gids duiken, zorg ervoor dat je de volgende vereisten hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page for Java‑bibliotheek geïnstalleerd. Je kunt deze downloaden van de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Een Java Integrated Development Environment (IDE) geïnstalleerd op je machine.

## Pakketten importeren
Importeer in je Java‑project de benodigde pakketten om Aspose.Page for Java te gebruiken:

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
Het schalen van een rechthoek verandert de grootte langs de X‑ en Y‑assen terwijl de vorm behouden blijft. Aspose.Page biedt de `scale(float sx, float sy)`‑methode, die een **affine transform** toepast op de huidige graphics‑status. Dit is de kerntechniek achter het **how to scale rectangle**‑trefwoord.

## Hoe een vorm vertalen met Aspose.Page
Vertalen verplaatst een vorm naar een nieuwe locatie zonder de afmetingen te wijzigen. Dit is de essentie van **how to translate shape**. Door de graphics‑status op te slaan, `translate(dx, dy)` toe te passen, te tekenen en vervolgens de status te herstellen, blijven andere objecten onaangetast.

## Voorbeeld 1: Geen transformaties
Het eerste voorbeeld tekent een eenvoudige rechthoek zonder toegepaste transformatie. Dit dient als basislijn voor vergelijking met latere voorbeelden.

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

## Voorbeeld 2: Vertaling
Hier demonstreren we **how to translate shape** door de graphics‑context 250 eenheden naar rechts te verplaatsen vóór het tekenen van een tweede rechthoek.

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

## Voorbeeld 3: Schalen
Dit voorbeeld beantwoordt de hoofdvraag **how to scale rectangle**. We verkleinen de rechthoek tot 50 % van de oorspronkelijke breedte en 75 % van de oorspronkelijke hoogte.

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

## Hoe een vorm roteren Java (rotate shape java)
Rotatie is een andere veelvoorkomende affine bewerking. Terwijl de code‑fragmenten voor rotatie om beknoptheid te behouden weggelaten zijn, is het patroon identiek: sla de graphics‑status op, roep `document.rotate(angle)` aan, teken de vorm, en herstel vervolgens. Dit demonstreert **rotate shape java** en **how to rotate rectangle** in de praktijk.

## Waarom dit belangrijk is – Praktische voordelen
- **Apparaatonafhankelijke output** – Eén keer schrijven en PostScript of XPS genereren zonder platformspecifieke aanpassingen.  
- **Fijne controle** – Combineer vertaling, schalen, schuiven en rotatie om exact aan layout‑eisen te voldoen.  
- **Prestatiegericht** – Low‑overhead API ideaal voor batchverwerking van grootschalige documenten.  

## Veelvoorkomende gebruikssituaties
- Het genereren van afdrukbare facturen – bijvoorbeeld een **printable invoice java**‑oplossing die logo’s en barcodes nauwkeurig plaatst.  
- Het maken van technische diagrammen waarbij precieze schaal en positionering vereist zijn.  
- Het automatiseren van de productie van meer‑pagina rapporten in PostScript‑formaat.

## Veelvoorkomende problemen en oplossingen
- **Transformatie wordt niet gereset** – Koppel altijd `document.writeGraphicsSave()` met `document.writeGraphicsRestore()` om ongewenste voortzettingseffecten te voorkomen.  
- **Onverwachte kleuren** – Zorg ervoor dat je de verf instelt na elke transformatie; de graphics‑status behoudt geen eerdere kleuropties na een herstel.  
- **Bestandsgrootte te groot** – Gebruik `PsSaveOptions` om compressie in te schakelen of de beeldresolutie te verlagen bij het insluiten van raster‑graphics.

## Veelgestelde vragen
### Kan ik Aspose.Page for Java voor andere documentformaten gebruiken?
Aspose.Page richt zich voornamelijk op paginamanipulatie voor PostScript‑ en XPS‑formaten.

### Waar kan ik meer voorbeelden en documentatie voor Aspose.Page for Java vinden?
Bezoek de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) voor uitgebreide informatie.

### Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?
Ja, je kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

### Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java krijgen?
Verkrijg een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik community‑ondersteuning zoeken of vragen stellen over Aspose.Page for Java?
Bezoek het [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) voor community‑discussies.

## Veelgestelde vragen

**Q: Wat is het verschil tussen `translate` en `scale`?**  
A: `translate` verplaatst de oorsprong van het coördinatensysteem, terwijl `scale` de grootte van getekende objecten langs de X‑ en/of Y‑assen wijzigt.

**Q: Kan ik meerdere transformaties combineren in één graphics‑status?**  
A: Ja—door `translate`, `scale`, `rotate` of `shear` opeenvolgend aan te roepen vóór het tekenen, creëer je een gecombineerde affine transformatie.

**Q: Hoe reset ik transformaties na het tekenen van een vorm?**  
A: Gebruik `document.writeGraphicsRestore()` om terug te keren naar de eerder opgeslagen graphics‑status.

**Q: Is het mogelijk om een rechthoek rond zijn middelpunt te roteren?**  
A: Absoluut. Vertaal de rechthoek naar de oorsprong, pas `rotate(angle)` toe, en vertaal vervolgens terug vóór het tekenen.

**Q: Ondersteunt Aspose.Page anti‑aliasing voor vloeiendere graphics?**  
A: Ja—stel de juiste rendering‑opties in `PsSaveOptions` in om anti‑aliasing in te schakelen.

---

**Laatst bijgewerkt:** 2026-02-07  
**Getest met:** Aspose.Page for Java 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}