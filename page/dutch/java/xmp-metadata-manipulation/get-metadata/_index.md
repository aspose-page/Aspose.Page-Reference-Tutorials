---
title: Haal metadata op van XMP met behulp van Java
linktitle: Haal metadata op van XMP met behulp van Java
second_title: Aspose.Page Java-API
description: Ontgrendel de kracht van Aspose.Page voor Java om moeiteloos XMP-metagegevens te extraheren. Verbeter documentanalyse met onze stapsgewijze handleiding!
type: docs
weight: 18
url: /nl/java/xmp-metadata-manipulation/get-metadata/
---
## Invoering
Welkom bij onze stapsgewijze handleiding over het gebruik van Aspose.Page voor Java om metagegevens uit XMP-bestanden te extraheren. XMP (Extensible Metadata Platform) biedt een gestandaardiseerde manier om metadata in bestanden op te slaan. Deze tutorial richt zich op het ophalen van essentiële informatie uit XMP met behulp van Java en biedt inzicht in documentdetails.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK): Zorg ervoor dat Java op uw computer is geïnstalleerd.
-  Aspose.Page voor Java: Download en installeer de Aspose.Page-bibliotheek, die u kunt vinden[hier](https://releases.aspose.com/page/java/).
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Stap 1: Initialiseer de invoer-EPS-bestandsstroom
Begin met het instellen van het pad naar uw documentmap en het initialiseren van de invoer-EPS-bestandsstroom.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Stap 2: XMP-metagegevens ophalen
Haal XMP-metagegevens op uit het EPS-bestand. Als het bestand geen XMP-metagegevens heeft, wordt er een nieuw bestand gegenereerd met waarden uit PS-metagegevensopmerkingen.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Stap 3: CreatorTool-informatie extraheren
Controleer en druk de "CreatorTool"-waarde uit de XMP-metagegevens af.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Stap 4: Extract CreateDate-informatie
Controleer en druk de waarde "CreateDate" uit de XMP-metagegevens af.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Stap 5: Haal de miniatuurbreedte op
Als er miniaturen bestaan, extraheert u de breedte van de eerste miniatuur en drukt u deze af.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Stap 6: Formaatinformatie extraheren
Controleer en druk de "format"-waarde uit de XMP-metagegevens af.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Stap 7: DocumentID ophalen
Controleer de waarde "DocumentID" uit de XMP-metagegevens en druk deze af.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u XMP-metagegevens kunt extraheren met Aspose.Page voor Java. Deze handleiding biedt een uitgebreid overzicht van het proces, zodat u op een effectieve manier essentiële informatie uit uw documenten kunt halen.
## Veel Gestelde Vragen
### Kan ik Aspose.Page voor Java gebruiken met andere programmeertalen?
 Ja, Aspose.Page ondersteunt meerdere talen, waaronder Java, .NET en meer. Controleer de[documentatie](https://reference.aspose.com/page/java/) voor details.
### Is er een gratis proefversie beschikbaar voor Aspose.Page voor Java?
 Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Waar kan ik ondersteuning vinden voor Aspose.Page voor Java?
 Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapssteun.
### Hoe verkrijg ik een tijdelijke licentie voor Aspose.Page voor Java?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Zijn er aanvullende bronnen voor Aspose.Page voor Java?
 Ontdek het volledige[documentatie](https://reference.aspose.com/page/java/) en download de bibliotheek[hier](https://releases.aspose.com/page/java/).