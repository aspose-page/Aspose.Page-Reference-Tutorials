---
date: 2025-12-07
description: Leer hoe je een rechthoek schaalt, een vorm verplaatst en een affiene
  transformatie toepast in Java met Aspose.Page om PostScript‑documenten te maken.
language: nl
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Hoe een rechthoek schalen en transformaties toepassen met Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een rechthoek schalen en transformaties toepassen met Aspose.Page

## Introductie
Welkom bij een uitgebreide gids over het benutten van de krachtige functies van **Aspose.Page for Java** om diverse paginatransformaties uit te voeren. In deze tutorial leert u **hoe een rechthoek te schalen**, vormen te verplaatsen, objecten te roteren en **affine transformaties** toe te passen tijdens het maken van een **PostScript‑document**. Deze mogelijkheden stellen u in staat om rijke, grafisch intensieve Java‑toepassingen te bouwen zonder low‑level rendering‑code te hoeven schrijven.

## Snelle antwoorden
- **Hoe schaal ik een rechthoek in Java met Aspose.Page?** Gebruik de `document.scale()`‑methode vóór het tekenen van de vorm.  
- **Kan ik een vorm (transleren) verplaatsen zonder andere graphics te beïnvloeden?** Ja—sla de graphics‑state op, roep `document.translate(x, y)` aan, teken, en herstel vervolgens de state.  
- **Welke klasse maakt een PostScript‑bestand?** `PsDocument` samen met `PsSaveOptions`.  
- **Heb ik een licentie nodig voor productiegebruik?** Een geldige Aspose.Page‑licentie is vereist voor commerciële implementaties.  
- **Welke Java‑versie wordt ondersteund?** Aspose.Page werkt met Java 8 en hoger.

## Voorvereisten
Voordat we in de stap‑voor‑stap‑gids duiken, zorg ervoor dat u de volgende voorwaarden hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page for Java‑bibliotheek geïnstalleerd. U kunt deze downloaden via de [Aspose.Page for Java‑documentatie](https://reference.aspose.com/page/java/).  
- Een Java Integrated Development Environment (IDE) geïnstalleerd op uw machine.

## Pakketten importeren
Importeer in uw Java‑project de benodigde pakketten om Aspose.Page for Java te gebruiken:

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
Het schalen van een rechthoek verandert de grootte langs de X‑ en Y‑as terwijl de vorm behouden blijft. Aspose.Page biedt de `scale(float sx, float sy)`‑methode, die een **affine transform** toepast op de huidige graphics‑state. Dit is de kerntechniek achter het **how to scale rectangle**‑trefwoord.

## Hoe een vorm vertalen met Aspose.Page
Translatie verplaatst een vorm naar een nieuwe locatie zonder de afmetingen te wijzigen. Dit is de essentie van **how to translate shape**. Door de graphics‑state op te slaan, `translate(dx, dy)` toe te passen, te tekenen en vervolgens de state te herstellen, blijven andere objecten onaangetast.

## Voorbeeld 1: Geen transformaties
Het eerste voorbeeld tekent een eenvoudige rechthoek zonder enige transformatie. Dit dient als basislijn voor vergelijking met latere voorbeelden.

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

## Voorbeeld 2: Translatie
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

## Hoe een vorm roteren in Java (rotate shape java)
Rotatie is een andere veelvoorkomende affine bewerking. Hoewel de code‑fragmenten voor rotatie om beknoptheid te behouden zijn weggelaten, is het patroon identiek: sla de graphics‑state op, roep `document.rotate(angle)` aan, teken de vorm, en herstel vervolgens. Dit demonstreert **rotate shape java** en **how to rotate rectangle** in de praktijk.

## Waarom Aspose.Page gebruiken voor deze transformaties?
- **Device‑independent**: Schrijf één keer code, genereer PostScript of XPS zonder platform‑specifieke code.  
- **Fine‑grained control**: Directe toegang tot de graphics‑state stelt u in staat translatie, schaling, shear en rotatie te combineren.  
- **Performance**: Low‑overhead API geschikt voor batchverwerking van grote documenten.  

## Veelvoorkomende gebruikssituaties
- Het genereren van afdrukbare facturen met dynamische barcodes en logo's.  
- Het maken van technische diagrammen waarbij nauwkeurige schaling en positionering vereist zijn.  
- Het automatiseren van de productie van meerpagina‑rapporten in PostScript‑indeling.

## Conclusie
In deze tutorial hebben we verschillende transformaties in Java‑pagina‑manipulatie onderzocht met Aspose.Page for Java, met focus op **how to scale rectangle**, **how to translate shape** en andere affine bewerkingen. Door deze voorbeelden te volgen, kunt u uw Java‑applicaties verrijken met geavanceerde paginamanipulatiemogelijkheden en **PostScript‑document**‑uitvoer genereren die voldoen aan professionele publicatiestandaarden.

## Veelgestelde vragen
### Kan ik Aspose.Page voor Java gebruiken voor andere documentformaten?
Aspose.Page richt zich voornamelijk op paginamanipulatie voor PostScript‑ en XPS‑formaten.

### Waar kan ik meer voorbeelden en documentatie vinden voor Aspose.Page voor Java?
Bezoek de [Aspose.Page for Java‑documentatie](https://reference.aspose.com/page/java/) voor uitgebreide informatie.

### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
Ja, u kunt een gratis proefversie verkrijgen [hier](https://releases.aspose.com/).

### Hoe kan ik een tijdelijke licentie krijgen voor Aspose.Page voor Java?
Vraag een tijdelijke licentie aan [hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik community‑ondersteuning vinden of vragen stellen over Aspose.Page voor Java?
Bezoek het [Aspose.Page for Java‑forum](https://forum.aspose.com/c/page/39) voor discussies binnen de community.

## Veelgestelde vragen

**Q: Wat is het verschil tussen `translate` en `scale`?**  
A: `translate` verplaatst de oorsprong van het coördinatensysteem, terwijl `scale` de grootte van getekende objecten langs de X‑ en/of Y‑as wijzigt.

**Q: Kan ik meerdere transformaties combineren in één graphics‑state?**  
A: Ja—door `translate`, `scale`, `rotate` of `shear` opeenvolgend aan te roepen vóór het tekenen, creëert u een gecombineerde affine transformatie.

**Q: Hoe reset ik transformaties na het tekenen van een vorm?**  
A: Gebruik `document.writeGraphicsRestore()` om terug te keren naar de eerder opgeslagen graphics‑state.

**Q: Is het mogelijk om een rechthoek rond zijn middelpunt te roteren?**  
A: Absoluut. Vertaal de rechthoek naar de oorsprong, pas `rotate(angle)` toe, en vertaal vervolgens terug voordat u tekent.

**Q: Ondersteunt Aspose.Page anti‑aliasing voor vloeiendere graphics?**  
A: Ja—stel de juiste rendering‑opties in `PsSaveOptions` in om anti‑aliasing in te schakelen.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}