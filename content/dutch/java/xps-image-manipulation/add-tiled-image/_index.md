---
title: Voeg een betegelde afbeelding toe in Java XPS
linktitle: Voeg een betegelde afbeelding toe in Java XPS
second_title: Aspose.Page Java-API
description: Ontdek naadloze Java XPS-documentmanipulatie met Aspose.Page. Leer moeiteloos tegelafbeeldingen toevoegen met behulp van deze stapsgewijze handleiding.
type: docs
weight: 11
url: /nl/java/xps-image-manipulation/add-tiled-image/
---
## Invoering
In de dynamische wereld van Java-ontwikkeling wordt de behoefte aan efficiënte documentmanipulatie en -creatie steeds groter. Aspose.Page voor Java blijkt een krachtig hulpmiddel dat ontwikkelaars de mogelijkheid biedt om naadloos met XPS-documenten te werken. Deze tutorial richt zich op een specifieke taak: het toevoegen van een tegelafbeelding aan een Java XPS-document.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Page voor Java: Download en installeer Aspose.Page voor Java vanaf de[website](https://releases.aspose.com/page/java/).
3. Uw documentenmap: Kies of maak een map waarin u uw XPS-document wilt opslaan.
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten om de Aspose.Page-functionaliteiten te gebruiken:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Laten we nu het proces van het toevoegen van een tegelafbeelding aan een Java XPS-document opsplitsen in duidelijke, beheersbare stappen.
## Stap 1: Stel uw project in
Begin met het opzetten van uw Java-project en zorg ervoor dat Aspose.Page voor Java correct is geïntegreerd.
## Stap 2: Maak een XPS-document
Initialiseer een nieuw XPS-document met de volgende code:
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een nieuw XPS-document
XpsDocument doc = new XpsDocument();
```
## Stap 3: Definieer het betegelde afbeeldingspad
Geef het pad op naar de tegelafbeelding die u aan het XPS-document wilt toevoegen.
## Stap 4: Voeg een betegelde afbeelding toe
Gebruik het onderstaande codefragment om een tegelafbeelding aan het XPS-document toe te voegen:
```java
// Tegel afbeelding
// Met ImageBrush gevulde rechthoek rechts bovenaan
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Stap 5: Sla het document op
Sla ten slotte het resulterende XPS-document op met behulp van de onderstaande code:
```java
// Sla het resulterende XPS-document op
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Herhaal deze stappen om moeiteloos een tegelafbeelding in uw Java XPS-document op te nemen met behulp van Aspose.Page.
## Conclusie
Aspose.Page voor Java stroomlijnt het proces van het werken met XPS-documenten en biedt ontwikkelaars een efficiënte oplossing voor documentmanipulatie. Door deze stapsgewijze handleiding te volgen, kunt u moeiteloos een tegelafbeelding aan uw Java XPS-document toevoegen.

## Veelgestelde vragen
### Is Aspose.Page compatibel met alle Java-versies?
 Aspose.Page is ontworpen om met verschillende Java-versies te werken. Zorg voor compatibiliteit door de documentatie te controleren[hier](https://reference.aspose.com/page/java/).
### Kan ik Aspose.Page gebruiken voor commerciële projecten?
Ja, Aspose.Page biedt commerciële licenties. Koop ze[hier](https://purchase.aspose.com/buy).
### Is er een gratis proefversie beschikbaar?
 Ja, ontdek de functies van Aspose.Page met een gratis proefperiode[hier](https://releases.aspose.com/).
### Waar kan ik community-ondersteuning en discussies vinden?
 Neem deel aan de Aspose.Page-gemeenschap op de[forum](https://forum.aspose.com/c/page/39).
### Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?
 Schaf een tijdelijke licentie aan[hier](https://purchase.aspose.com/temporary-license/).