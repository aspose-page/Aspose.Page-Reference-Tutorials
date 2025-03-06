---
title: Wijzig waarden in XMP met behulp van Java
linktitle: Wijzig waarden in XMP met behulp van Java
second_title: Aspose.Page Java-API
description: Verbeter EPS-documenten met Aspose.Page voor Java. Wijzig moeiteloos XMP-metagegevens voor op maat gemaakte en professionele inhoud. #JavaOntwikkeling
weight: 17
url: /nl/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wijzig waarden in XMP met behulp van Java

## Invoering
Op het gebied van documentverwerking en -manipulatie onderscheidt Aspose.Page voor Java zich als een krachtig hulpmiddel. Deze tutorial gaat in op het proces van het wijzigen van XMP-waarden (Extensible Metadata Platform) in EPS-documenten (Encapsulated PostScript) met behulp van Java met de Aspose.Page-bibliotheek. Door de meegeleverde stapsgewijze handleiding te volgen, leert u hoe u moeiteloos metagegevens kunt wijzigen, zodat uw documenten zijn afgestemd op uw specifieke vereisten.
## Vereisten
Voordat we aan deze zelfstudie beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java-ontwikkelomgeving: Zorg ervoor dat u een werkende Java-ontwikkelomgeving op uw computer heeft.
2.  Aspose.Page voor Java-bibliotheek: Download en installeer de Aspose.Page voor Java-bibliotheek. U kunt het benodigde pakket vinden[hier](https://releases.aspose.com/page/java/).
## Pakketten importeren
Begin met het importeren van de vereiste pakketten in uw Java-project. Deze pakketten zijn essentieel voor de interactie met en het manipuleren van EPS-documenten.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Stap 1: XMP-metagegevens ophalen
Haal XMP-metagegevens op uit het EPS-document. Als het EPS-bestand geen XMP-metagegevens bevat, wordt er een nieuw bestand gemaakt met waarden uit opmerkingen over PS-metagegevens, zoals %%Creator, %%CreateDate en %%Title.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Initialiseer invoer-EPS-bestandsstroom
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// XMP-metagegevens ophalen. Als het EPS-bestand geen XMP-metagegevens bevat, wordt er een nieuw bestand gemaakt met waarden uit PS-metagegevensopmerkingen
XmpMetadata xmp = document.getXmpMetadata();
```
## Stap 2: Wijzig de waarde "ModifyDate".
Wijzig de waarde "ModifyDate" in de XMP-metagegevens om de gewenste datum weer te geven.
```java
// Wijzig de waarde 'ModifyDate'
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Stap 3: Wijzig de waarde 'Creator'
Werk de waarde 'Creator' in de XMP-metagegevens bij om de maker van het document te specificeren.
```java
// Wijzig de waarde van 'maker'
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Stap 4: Wijzig de waarde van "Titel".
Wijzig de waarde "Titel" in de XMP-metagegevens om een geschikte titel voor het document in te stellen.
```java
//Wijzig de waarde van "titel".
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Stap 5: Document opslaan met gewijzigde XMP-metagegevens
Sla het document met de bijgewerkte XMP-metagegevens op in een nieuw EPS-bestand.
```java
// Initialiseer de uitvoer-EPS-bestandsstroom
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Sla het document op met gewijzigde XMP-metagegevens
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusie
Gefeliciteerd! U hebt met succes door het proces van het wijzigen van XMP-waarden in EPS-documenten genavigeerd met Aspose.Page voor Java. Deze tutorial heeft u de kennis gegeven om metagegevens aan te passen, zodat uw documenten naadloos aansluiten op uw specifieke vereisten.
## Veelgestelde vragen
### Vraag: Hoe kan ik omgaan met tijdzoneoverwegingen bij het wijzigen van XMP-waarden?
 Gebruik`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` om consistentie in de tijdzone-instellingen te garanderen.
### Vraag: Kan ik meerdere XMP-waarden in één bewerking wijzigen?
 Ja, door gebruik te maken van de`put` methode voor elke gewenste waarde kunt u meerdere XMP-waarden tegelijkertijd wijzigen.
### Vraag: Waar kan ik aanvullende documentatie vinden voor Aspose.Page voor Java?
 Ontdek de uitgebreide documentatie[hier](https://reference.aspose.com/page/java/).
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
 Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor Java?
 Vraag een tijdelijke licentie aan[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
