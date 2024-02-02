---
title: Stel het dekkingsmasker in Java XPS in
linktitle: Stel het dekkingsmasker in Java XPS in
second_title: Aspose.Page Java-API
description: Ontdek de kracht van het instellen van dekkingsmaskers in Java XPS met Aspose.Page. Volg onze stapsgewijze handleiding voor een visueel verbeterde documentervaring.
type: docs
weight: 11
url: /nl/java/xps-transparency/set-opacity-mask/
---
## Invoering
Welkom bij onze uitgebreide handleiding over het instellen van dekkingsmaskers in Java XPS met Aspose.Page. In deze zelfstudie begeleiden we u bij het maken van een XPS-document, het toevoegen van een canvas en het toepassen van een dekkingsmasker op een rechthoek met behulp van de krachtige functies van Aspose.Page voor Java.
## Vereisten
Voordat u in deze zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:
- Een basiskennis van Java-programmeren.
-  Aspose.Page voor Java-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/page/java/).
-  Een geldige licentie voor Aspose.Page. Als u er niet over beschikt, kunt u een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
- Een ontwikkelomgeving die is ingericht om Java-applicaties uit te voeren.
## Pakketten importeren
Begin met het importeren van de benodigde pakketten in uw Java-project. Zorg ervoor dat de Aspose.Page-bibliotheek correct is geïntegreerd. Hieronder vindt u een fragment om u te begeleiden:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Laten we nu de voorbeeldcode in meerdere stappen opsplitsen:
## Stap 1: Maak een nieuw XPS-document
```java
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```
## Stap 2: Voeg een canvas toe
```java
// Nieuw doek
XpsCanvas canvas = doc.addCanvas();
```
## Stap 3: Voeg een rechthoek toe met dekkingsmasker
```java
// Rechthoek in het midden links met dekking gemaskeerd door ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Stap 4: Stel het dekkingsmasker in met ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Stap 5: Sla het resulterende XPS-document op
```java
// Sla het resulterende XPS-document op
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Volg deze stappen zorgvuldig om dekkingsmaskers in uw Java XPS-document op te nemen met behulp van Aspose.Page.
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u dekkingsmaskers kunt instellen in Java XPS met Aspose.Page. Deze functie voegt een laag visuele rijkdom toe aan uw documenten, waardoor ze aantrekkelijker en dynamischer worden.
## Veelgestelde vragen
### Is Aspose.Page compatibel met alle Java-ontwikkelomgevingen?
Ja, Aspose.Page is ontworpen om naadloos samen te werken met verschillende Java-ontwikkelomgevingen.
### Kan ik Aspose.Page gebruiken zonder licentie?
Hoewel u Aspose.Page zonder licentie kunt gebruiken, is het raadzaam er een aan te schaffen voor het volledige scala aan functies en ondersteuning.
### Zijn er beperkingen op de proefversie?
De proefversie heeft mogelijk enkele functiebeperkingen. Het is raadzaam om de documentatie te raadplegen voor details.
### Hoe kan ik ondersteuning krijgen voor Aspose.Page?
 U kunt een bezoek brengen aan de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor community-ondersteuning of koop een licentie voor premium-ondersteuning.
### Is er een geld-terug-garantie voor Aspose.Page?
 Verwijs naar de[aankooppagina](https://purchase.aspose.com/buy) voor informatie over het restitutiebeleid.