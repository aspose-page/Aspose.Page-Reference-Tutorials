---
title: Metagegevens toevoegen in XMP met behulp van Java
linktitle: Metagegevens toevoegen in XMP met behulp van Java
second_title: Aspose.Page Java-API
description: Ontdek de naadloze integratie van Aspose.Page voor Java en leer hoe u moeiteloos XMP-metagegevens aan uw EPS-bestanden kunt toevoegen. Verbeter vandaag nog uw documentbeheerspel!
type: docs
weight: 11
url: /nl/java/xmp-metadata-manipulation/add-metadata/
---
## Invoering
Wilt u de metagegevens van uw document verbeteren door XMP-informatie toe te voegen met behulp van Java? Zoek niet verder! Deze stapsgewijze handleiding leidt u door het proces van het toevoegen van metagegevens aan een EPS-bestand met behulp van de Aspose.Page voor Java-bibliotheek. Aspose.Page is een krachtig hulpmiddel dat documentmanipulatietaken in Java-toepassingen vereenvoudigt.
## Vereisten
Voordat we in de tutorial duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:
- Basiskennis van Java-programmeren.
-  Aspose.Page voor Java-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/page/java/).
- Een EPS-bestand dat u wilt wijzigen.
## Pakketten importeren
Importeer eerst de benodigde pakketten in uw Java-programma:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Stap 1: XMP-metagegevens ophalen
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Initialiseer invoer-EPS-bestandsstroom
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// XMP-metagegevens ophalen. Als het EPS-bestand geen XMP-metagegevens bevat, wordt er een nieuw bestand gemaakt met behulp van waarden uit PS-metagegevensopmerkingen (%%Creator, %%CreateDate, %%Title, enz.)
XmpMetadata xmp = document.getXmpMetadata();
```
Zorg ervoor dat u "Uw documentenmap" vervangt door het daadwerkelijke pad waar uw documenten zijn opgeslagen.

## Stap 2: Haal de CreatorTool-waarde op
```java
// Haal de "CreatorTool"-waarde op
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Stap 3: Haal de CreateDate-waarde op
```java
// Waarde 'CreateDate' ophalen
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Stap 4: Titelwaarde ophalen
```java
// Haal de waarde 'Titel' op
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Stap 5: Formaatwaarde ophalen
```java
//Haal de waarde "formaat" op
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Stap 6: Haal de makerwaarde op
```java
// Krijg 'creator'-waarde
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Stap 7: MetadataDate-waarde ophalen
```java
// Waarde 'MetadataDate' ophalen
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Stap 8: Document opslaan met nieuwe XMP-metagegevens
```java
// Initialiseer de uitvoer-EPS-bestandsstroom
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Sla het document op met nieuwe XMP-metagegevens
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Vergeet ten slotte niet de invoer-EPS-stream te sluiten:
```java
// Sluit de invoer-EPS-stream
psStream.close();
```
Nu hebt u met succes metadata aan uw EPS-bestand toegevoegd met Aspose.Page voor Java!
## Conclusie
In deze zelfstudie hebben we het proces onderzocht van het toevoegen van XMP-metagegevens aan een EPS-bestand met behulp van de Aspose.Page voor Java-bibliotheek. Met deze krachtige tool kunt u documenten naadloos manipuleren, waardoor uw algehele documentbeheerervaring wordt verbeterd.
## Veelgestelde vragen
### Vraag: Is Aspose.Page voor Java gratis te gebruiken?
 A: Aspose.Page voor Java is een commercieel product. U kunt de functies ervan verkennen via een gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik de documentatie voor Aspose.Page voor Java vinden?
 A: De documentatie is beschikbaar[hier](https://reference.aspose.com/page/java/).
### Vraag: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor Java?
 A: U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Welke bestandsformaten ondersteunt Aspose.Page voor Java?
A: Aspose.Page voor Java ondersteunt verschillende formaten, waaronder EPS, PDF en XPS.
### Vraag: Kan ik Aspose.Page voor Java kopen?
 A: Ja, u kunt Aspose.Page voor Java kopen[hier](https://purchase.aspose.com/buy).