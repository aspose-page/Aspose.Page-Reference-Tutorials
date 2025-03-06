---
title: Wijzig het formaat van EPS-bestanden in Java met Aspose.Page
linktitle: Formaat van EPS-bestand wijzigen in Java
second_title: Aspose.Page Java-API
description: Leer hoe u moeiteloos het formaat van EPS-bestanden in Java kunt wijzigen met Aspose.Page voor Java. Volg onze uitgebreide handleiding voor stapsgewijze instructies.
weight: 11
url: /nl/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wijzig het formaat van EPS-bestanden in Java met Aspose.Page

## Invoering
Welkom bij onze stapsgewijze handleiding voor het wijzigen van de grootte van EPS-bestanden in Java met behulp van de krachtige Aspose.Page-bibliotheek. Als u ooit de afmetingen van uw EPS-afbeeldingen programmatisch heeft moeten aanpassen, bent u hier op de juiste plek. In deze zelfstudie verkennen we verschillende opties voor het wijzigen van de grootte, waaronder punten, inches, millimeters en percentages, waardoor u de flexibiliteit krijgt die u nodig heeft voor uw specifieke vereisten.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:
- Java Development Kit (JDK) op uw computer geïnstalleerd.
-  Aspose.Pagina voor Java-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/page/java/).
- Een basiskennis van Java-programmeren.
## Pakketten importeren
Zorg ervoor dat u in uw Java-project over de benodigde importbestanden beschikt om de Aspose.Page-functionaliteiten te gebruiken. Hier is een voorbeeld:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Laten we nu de tutorial opsplitsen in meerdere stappen voor elke optie voor het wijzigen van het formaat:
## Pas het formaat van EPS aan met behulp van punten
### Stap 1: Stel de invoerstroom in
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Stap 2: Initialiseer het PsDocument-object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Stap 3: Extraheer de huidige grootte van de EPS-afbeelding
```java
Dimension oldSize = doc.extractEpsSize();
```
### Stap 4: Maak een uitvoerstream
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Stap 5: Formaat wijzigen en opslaan in punten
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Formaat van EPS wijzigen met inches
Volg vergelijkbare stappen als voorbeeld 1, waarbij u "Punten" vervangt door "Inches" en de nieuwe grootte dienovereenkomstig aanpast.
## Pas het formaat van EPS aan met behulp van millimeters
Volg vergelijkbare stappen als voorbeeld 1, waarbij u "Punten" vervangt door "Millimeters" en de nieuwe grootte dienovereenkomstig aanpast.
## Formaat van EPS wijzigen met behulp van percentages
Volg vergelijkbare stappen als voorbeeld 1, waarbij u "Punten" vervangt door "Percentages" en de nieuwe grootte dienovereenkomstig aanpast.
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u de grootte van EPS-bestanden in Java kunt wijzigen met behulp van Aspose.Page. Deze handleiding biedt u veelzijdige opties, zodat u het formaatwijzigingsproces kunt aanpassen aan uw specifieke behoeften.

## Veelgestelde vragen
### Kan ik deze bibliotheek voor andere afbeeldingsformaten gebruiken?
Nee, Aspose.Page is specifiek ontworpen voor het verwerken van PostScript- en EPS-bestanden.
### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
Ja, u kunt de gratis proefperiode verkennen[hier](https://releases.aspose.com/).
### Waar kan ik aanvullende hulp en discussies vinden?
 Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapssteun.
### Hoe kan ik een tijdelijke licentie verkrijgen?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Zijn er voorbeeldprojecten beschikbaar?
 Ja, controleer de documentatie[hier](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
