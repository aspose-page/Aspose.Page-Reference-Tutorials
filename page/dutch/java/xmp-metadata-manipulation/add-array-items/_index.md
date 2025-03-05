---
title: Voeg array-items toe aan XMP-metagegevens met behulp van Java
linktitle: Voeg array-items toe aan XMP-metagegevens met behulp van Java
second_title: Aspose.Page Java-API
description: Verbeter EPS-bestanden met Aspose.Page voor Java. Leer moeiteloos array-items aan XMP-metadata toevoegen. Volg nu onze stapsgewijze handleiding!
type: docs
weight: 10
url: /nl/java/xmp-metadata-manipulation/add-array-items/
---
## Invoering
Welkom bij onze stapsgewijze handleiding over het gebruik van Aspose.Page voor Java om array-items toe te voegen aan XMP-metagegevens. Aspose.Page is een krachtige Java-bibliotheek waarmee u verschillende documentformaten kunt manipuleren en ermee kunt werken, inclusief EPS-bestanden. In deze zelfstudie concentreren we ons op de specifieke taak van het toevoegen van array-items aan XMP-metagegevens met behulp van Java.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Aspose.Page voor Java-bibliotheek geïnstalleerd.
- Basiskennis van Java-programmeren.
- Een geldig EPS-bestand met bestaande XMP-metagegevens of PS-metagegevensopmerkingen.
## Pakketten importeren
Om aan de slag te gaan, moet u de benodigde pakketten importeren om met Aspose.Page te werken. Voeg de volgende regels toe aan het begin van uw Java-bestand:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Stap 1: XMP-metagegevens ophalen
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Initialiseer invoer-EPS-bestandsstroom
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP-metagegevens ophalen. Als het EPS-bestand geen XMP-metagegevens bevat, krijgen we een nieuwe gevuld met waarden uit PS-metagegevensopmerkingen (%%Creator, %%CreateDate, %%Title, enz.)
XmpMetadata xmp = document.getXmpMetadata();
```
In deze stap halen we de bestaande XMP-metagegevens uit het EPS-bestand op. Als het EPS-bestand nog geen XMP-metagegevens bevat, genereert Aspose.Page een nieuwe en vult deze met waarden uit opmerkingen over PS-metagegevens.
## Stap 2: Voeg het array-item "dc:title" toe
```java
// Voeg nog een array-item "dc:title" toe
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nu voegen we een nieuw array-item toe aan de eigenschap "dc:title" in de XMP-metagegevens. Vervang "NieuweTitel" door de gewenste titel.
## Stap 3: Voeg het array-item "dc:creator" toe
```java
// Voeg nog een array-item "dc:creator" toe
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Op dezelfde manier voegen we een nieuw array-item toe aan de eigenschap "dc:creator" in de XMP-metagegevens. Vervang "NewCreator" door de gewenste makerinformatie.
## Stap 4: Initialiseer de uitvoer-EPS-bestandsstroom
```java
// Initialiseer de uitvoer-EPS-bestandsstroom
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Bereid de uitvoer-EPS-bestandsstroom voor waarin het gewijzigde document met bijgewerkte XMP-metagegevens wordt opgeslagen.
## Stap 5: Document opslaan met gewijzigde XMP-metagegevens
```java
//Sla het document op met gewijzigde XMP-metagegevens
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Sla het document met de bijgewerkte XMP-metagegevens op in het uitvoer-EPS-bestand.
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u array-items kunt toevoegen aan XMP-metagegevens met behulp van Aspose.Page voor Java. Deze krachtige bibliotheek vereenvoudigt het proces van het manipuleren van EPS-bestanden en biedt uitgebreide functionaliteit voor documentverwerking.
## Veel Gestelde Vragen

### Kan ik Aspose.Page voor Java gebruiken met andere documentformaten?
Ja, Aspose.Page ondersteunt verschillende documentformaten, waaronder EPS, PDF en XPS.
### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
 Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Waar kan ik de documentatie voor Aspose.Page voor Java vinden?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/page/java/).
### Hoe kan ik Aspose.Page voor Java kopen?
 U kunt het product kopen[hier](https://purchase.aspose.com/buy).
### Zijn er tijdelijke licenties beschikbaar voor Aspose.Page voor Java?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).