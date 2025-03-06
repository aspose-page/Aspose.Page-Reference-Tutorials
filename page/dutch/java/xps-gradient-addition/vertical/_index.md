---
title: Voeg verticaal verloop toe in Java XPS
linktitle: Voeg verticaal verloop toe in Java XPS
second_title: Aspose.Page Java-API
description: Leer hoe u een verticaal verloop kunt toevoegen aan Java XPS-documenten met Aspose.Page. Verbeter de visuele aantrekkingskracht moeiteloos. Stap-voor-stap handleiding binnenin.
weight: 12
url: /nl/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg verticaal verloop toe in Java XPS

## Invoering
In deze zelfstudie onderzoeken we hoe u een verticaal verloop kunt toevoegen in Java XPS met behulp van Aspose.Page voor Java. Door kleurverlopen aan uw XPS-documenten toe te voegen, kunt u de visuele aantrekkingskracht van uw inhoud vergroten, waardoor deze aantrekkelijker en esthetisch aantrekkelijker wordt.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Een werkende Java-ontwikkelomgeving.
-  Aspose.Pagina voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/page/java/).
- Een basiskennis van Java-programmeren.
## Pakketten importeren
Begin met het importeren van de benodigde pakketten voor uw Java-project. Zorg ervoor dat u de Aspose.Page voor Java-bibliotheek in uw projectafhankelijkheden hebt opgenomen.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
        
// Importeer Aspose.Page voor Java
```
## Stap 1: Initialiseer het document
Begin met het initialiseren van het XPS-document. Dit vormt de basis voor het toevoegen van elementen zoals paden en verlopen aan uw document.
```java
// Initialiseer document
XpsDocument doc = new XpsDocument();
```
## Stap 2: Maak een pad met verticaal verloop
Laten we nu een pad maken met een verticaal verloop. Dit omvat het definiëren van de padgeometrie en het specificeren van de gradiëntstops.
```java
// Maak een pad met geometrie
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definieer verticale verloopstops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Pas het verticale verloop toe op het pad
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Stap 3: Sla het document op
Sla ten slotte het XPS-document met het toegevoegde verticale verloop op in de gewenste map.
```java
// Bewaar het document
doc.save(dataDir + "VerticalGradient.xps");
```
Gefeliciteerd! U hebt met succes een verticaal verloop aan uw Java XPS-document toegevoegd met Aspose.Page.
## Conclusie
Het verbeteren van uw XPS-documenten met kleurverlopen kan de visuele aantrekkingskracht ervan aanzienlijk verbeteren. Aspose.Page voor Java vereenvoudigt dit proces, waardoor u eenvoudig verbluffende documenten kunt maken.

### Veelgestelde vragen
### Kan ik Aspose.Page voor Java gebruiken in commerciële projecten?
 Ja, Aspose.Page voor Java is beschikbaar voor commercieel gebruik. Je kunt het kopen[hier](https://purchase.aspose.com/buy).
### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
 Ja, u krijgt toegang tot een gratis proefperiode[hier](https://releases.aspose.com/).
### Waar kan ik de documentatie voor Aspose.Page voor Java vinden?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/page/java/).
### Hoe kan ik een tijdelijke licentie krijgen voor Aspose.Page voor Java?
 Vraag een tijdelijke licentie aan[hier](https://purchase.aspose.com/temporary-license/).
### Hulp nodig of vragen?
 Bezoek de Aspose.Page-gemeenschap[forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
