---
title: Voeg een horizontaal verloop toe in Java XPS
linktitle: Voeg een horizontaal verloop toe in Java XPS
second_title: Aspose.Page Java-API
description: Leer hoe u een verbluffend horizontaal verloop kunt toevoegen aan XPS-documenten in Java met behulp van Aspose.Page. Volg onze stapsgewijze handleiding voor een naadloze integratie.
weight: 11
url: /nl/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een horizontaal verloop toe in Java XPS

## Invoering
Welkom bij deze stapsgewijze handleiding voor het toevoegen van een horizontaal verloop in Java XPS met Aspose.Page voor Java. Aspose.Page voor Java is een krachtige bibliotheek waarmee ontwikkelaars naadloos met XPS-documenten (XML Paper Specification) kunnen werken.
In deze zelfstudie begeleiden we u bij het maken van een Java-toepassing waarmee u een horizontaal verloop aan een XPS-document kunt toevoegen. Volg de onderstaande stappen om dit gemakkelijk te bereiken.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java-ontwikkelomgeving: Zorg ervoor dat Java op uw systeem is geïnstalleerd. Als dit niet het geval is, download en installeer dan de nieuwste versie van Java van[java.com](https://www.java.com).
2.  Aspose.Page voor Java-bibliotheek: u hebt de Aspose.Page voor Java-bibliotheek nodig. Je kunt het downloaden van de[Aspose.Page voor Java-documentatie](https://reference.aspose.com/page/java/).
## Pakketten importeren
Begin met het importeren van de benodigde pakketten voor uw Java-applicatie. Neem de Aspose.Page voor Java-bibliotheek op in uw project. U kunt dit doen door de volgende regels code toe te voegen:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Stap 1: Initialiseer het document
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
//Initialiseer document
XpsDocument doc = new XpsDocument();
```
## Stap 2: Maak een horizontaal verloop
```java
// Horizontale gradiënt
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Stap 3: Pad met verloop toevoegen
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Stap 4: Sla het document op
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Herhaal deze stappen indien nodig en pas de parameters aan op basis van uw specifieke vereisten.
## Conclusie
Gefeliciteerd! U hebt met succes een horizontaal verloop aan een XPS-document toegevoegd met Aspose.Page voor Java. Deze tutorial bood een uitgebreide handleiding voor ontwikkelaars die hun Java-applicaties wilden verbeteren met gradiënteffecten.
## Veelgestelde vragen
### Vraag: Kan ik meerdere verlopen toepassen in één XPS-document?
Ja, u kunt meerdere paden met verschillende verlopen toevoegen om complexe ontwerpen te maken.
### Vraag: Is Aspose.Page compatibel met de nieuwste Java-versies?
Aspose.Page voor Java wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste Java-releases te garanderen.
### Vraag: Zijn er andere verlooptypen beschikbaar in Aspose.Page?
Ja, naast lineaire gradiënten ondersteunt Aspose.Page radiale gradiënten voor meer diverse effecten.
### Vraag: Kan ik de kleuren en posities van verloopstops aanpassen?
Absoluut! U heeft volledige controle over de kleuren en posities van elke verloopstop.
### Vraag: Is er een communityforum voor Aspose.Page waar ik hulp kan zoeken?
 Ja, u kunt een bezoek brengen aan de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) om verbinding te maken met de gemeenschap en hulp te krijgen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
