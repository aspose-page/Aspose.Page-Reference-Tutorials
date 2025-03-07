---
title: Aspose.Page Java-tekstmanipulatie
linktitle: Tekst toevoegen in Java PostScript
second_title: Aspose.Page Java-API
description: Ontdek de kracht van Aspose.Page voor Java in onze tutorial over het toevoegen van tekst aan PostScript-documenten. Leer eenvoudig systeem- en aangepaste lettertypen gebruiken.
weight: 10
url: /nl/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java-tekstmanipulatie

## Invoering
Welkom bij onze stapsgewijze handleiding voor het toevoegen van tekst in Java PostScript met behulp van Aspose.Page voor Java. Aspose.Page voor Java is een krachtige bibliotheek waarmee ontwikkelaars PostScript-documenten gemakkelijk kunnen manipuleren. In deze zelfstudie leiden we u door het proces van het toevoegen van tekst, het gebruik van systeemlettertypen en aangepaste lettertypen, het omlijnen van tekst en het opnemen van streken voor een visueel aantrekkelijk resultaat.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van Java-programmeren.
-  Aspose.Page voor Java-bibliotheek geïnstalleerd. Je kunt het downloaden van de[Aspose.Page voor Java-downloadpagina](https://releases.aspose.com/page/java/).
-  Benodigde lettertypen beschikbaar in de opgegeven map. Meer informatie vindt u in de[Aspose.Page voor Java-documentatie](https://reference.aspose.com/page/java/).
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten voor Aspose.Page voor Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Stap 1: Stel het document in
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Maak een uitvoerstroom voor een PostScript-document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Creëer opslagopties met A4-formaat
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Een tekst om naar een PS-bestand te schrijven
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Maak een nieuw PS-document met één pagina
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Stap 2: Systeemlettertype gebruiken voor het vullen van tekst
```java
// Systeemlettertype gebruiken voor het vullen van tekst
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Vul tekst met standaard of reeds gedefinieerde kleur (zwart)
document.fillText(str, font, 50, 100);
// Vul tekst met blauwe kleur
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Stap 3: Aangepast lettertype gebruiken voor het vullen van tekst
```java
// Een aangepast lettertype gebruiken voor het vullen van tekst
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Vul tekst met standaard of reeds gedefinieerde kleur (zwart)
document.fillText(str, drFont, 50, 200);
// Vul tekst met blauwe kleur
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Stap 4: Tekst schetsen met systeemlettertype
```java
// Systeemlettertype gebruiken voor het omlijnen van tekst
document.outlineText(str, font, 50, 300);
// Omlijn de tekst met een blauwviolet gekleurde 2-punts breedtepen
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Vul de tekst met oranje kleur en lijn met een blauwgekleurde 2-punts breedtepen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Stap 5: Tekst omlijnen met een aangepast lettertype
```java
// Een aangepast lettertype gebruiken voor het omlijnen van tekst
document.outlineText(str, drFont, 50, 450);
// Omlijn de tekst met een blauwviolet gekleurde 2-punts breedtepen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Vul de tekst met oranje kleur en lijn met een blauwgekleurde 2-punts breedtepen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Stap 6: Sla het document op
```java
// Sluit huidige pagina
document.closePage();
// Bewaar het document
document.save();
```
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u tekst kunt toevoegen in Java PostScript met behulp van Aspose.Page voor Java. Experimenteer met verschillende lettertypen, kleuren en omtrekopties om uw document verder te verbeteren.
## Veel Gestelde Vragen
### Kan ik mijn eigen aangepaste lettertypen gebruiken met Aspose.Page voor Java?
 Ja, u kunt aangepaste lettertypen gebruiken door de lettertypenaam en -grootte op te geven in het`DrFont` klas.
### Hoe kan ik de kleur van de tekst wijzigen?
 Met de knop kunt u de gewenste kleur instellen`Color` klasse bij het invullen of schetsen van de tekst.
### Is het mogelijk om meerdere pagina's aan een PostScript-document toe te voegen?
Absoluut! U kunt meerdere pagina's maken door de stappen voor het maken en opslaan van documenten te herhalen.
###  Wat is het doel van de`ExternalFontCache` class?
`ExternalFontCache` wordt gebruikt om aangepaste lettertypen op te halen, zodat deze beschikbaar zijn voor tekstmanipulatie.
### Kan ik verschillende lijnen op de omlijnde tekst toepassen?
 Ja, u kunt de breedte en kleur van de lijn aanpassen met behulp van de`Stroke` klasse en`Color` klasse, respectievelijk.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
