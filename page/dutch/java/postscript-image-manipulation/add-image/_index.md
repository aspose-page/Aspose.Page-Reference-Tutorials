---
date: 2026-02-15
description: Leer hoe u PostScript‑Java‑documenten kunt maken en PostScript‑documentbestanden
  kunt genereren met afbeeldingsverschuiving en rotatie met behulp van Aspose.Page
  voor Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript in Java maken – Afbeelding toevoegen in Java‑PostScript
url: /nl/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak PostScript Java – Afbeelding toevoegen in Java PostScript

## Introductie
In deze tutorial leer je hoe je **create postscript java** documenten maakt en afbeeldingen insluit met de Aspose.Page for Java bibliotheek. We lopen stap voor stap door het proces, van het initialiseren van een nieuw PostScript‑bestand tot het toepassen van **translate and rotate image** transformaties. Aan het einde kun je programmatically PostScript‑bestanden genereren en de plaatsing van afbeeldingen pixel‑perfect regelen — ideaal voor geautomatiseerde rapportage, afdruk‑workflows of elke situatie waarin je **generate postscript document** output vanuit Java nodig hebt.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java  
- **Kan ik meerdere afbeeldingen toevoegen?** Ja – herhaal de transformatie‑ en tekenstappen  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie  
- **Welke Java‑versie wordt ondersteund?** Java 8 en later  
- **Wordt afbeeldingsrotatie ondersteund?** Absoluut – gebruik `AffineTransform.rotate()`  

## Wat is create postscript java?
Een **create postscript java** operatie produceert een PostScript‑pagina‑beschrijvingsbestand dat tekst, vector‑graphics en raster‑afbeeldingen codeert. Met Aspose.Page kun je deze bestanden direct vanuit Java‑code bouwen, waardoor je volledige programmeerbare controle hebt over lay‑out, schaling en rotatie zonder een aparte PostScript‑interpreter nodig te hebben.

## Waarom Aspose.Page gebruiken voor afbeeldingsmanipulatie?
- **High‑level API:** Abstracteert low‑level PostScript‑commando's naar eenvoudige Java‑methoden.  
- **Cross‑platform:** Werkt op elk OS dat Java ondersteunt.  
- **Full graphics‑state control:** Sla op, herstel, vertaal, schaal en roteer graphics naar wens.  
- **No external dependencies:** Behandelt het laden van afbeeldingen, formaatconversie en insluiten intern.

## Vereisten
- Java Development Kit (JDK) geïnstalleerd op uw systeem.  
- Aspose.Page for Java bibliotheek. U kunt deze downloaden [hier](https://releases.aspose.com/page/java/).  
- Een basisbegrip van Java‑programmeren.  

## Pakketten importeren
Om te beginnen importeer je de benodigde pakketten in je Java‑project. Gebruik de volgende code‑snippet als referentie:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Stap 1: Grafische status opslaan
De eerste stap omvat het schrijven van de graphics save naar het document. Dit zorgt ervoor dat eventuele transformaties of aanpassingen die daarna worden gedaan, indien nodig, ongedaan kunnen worden gemaakt.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Stap 2: Vertalen en transformeren (translate and rotate image)
Vervolgens vertaal je het document en maak je een `BufferedImage`‑object aan vanuit het afbeeldingsbestand. Pas een reeks transformaties toe, zoals schalen en rotatie, met behulp van `AffineTransform`. Hier vindt de **translate and rotate image** operatie plaats.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Stap 3: Afbeelding toevoegen aan document
Voeg nu de getransformeerde afbeelding toe aan het document.

```java
document.drawImage(image, transform, null);
```

## Stap 4: Grafische status herstellen
Na het toevoegen van de afbeelding schrijf je de graphics restore om de aangebrachte wijzigingen definitief te maken.

```java
document.writeGraphicsRestore();
```

## Stap 5: Huidige pagina sluiten en opslaan
Sluit de huidige pagina en sla het document op.

```java
document.closePage();
document.save();
```

Je kunt deze stappen herhalen om meerdere afbeeldingen toe te voegen of de transformaties aan te passen op basis van je vereisten.

## Veelvoorkomende problemen en oplossingen
- **FileNotFoundException:** Zorg ervoor dat het `dataDir`‑pad eindigt met een scheidingsteken (`/` of `\\`) en dat de bestandsnaam van de afbeelding exact overeenkomt.  
- **ImageIO.read returns null:** Controleer of het afbeeldingsformaat wordt ondersteund (bijv. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` verwacht radialen. Converteer graden naar radialen (`Math.toRadians(degrees)`) indien nodig.  

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere programmeertalen?**  
A: Aspose.Page ondersteunt voornamelijk Java, maar er zijn ook versies beschikbaar voor andere programmeertalen.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt de gratis proefversie benaderen [hier](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page for Java?**  
A: Je kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar vind ik community‑ondersteuning en discussies over Aspose.Page for Java?**  
A: Bezoek het [Aspose.Page Forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.

**Q: Zijn er extra bronnen voor het aanschaffen van Aspose.Page for Java?**  
A: Je kunt de bibliotheek kopen [hier](https://purchase.aspose.com/buy).

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je **create postscript java** documenten maakt en afbeeldingen insluit met Aspose.Page for Java. Verken de [documentatie](https://reference.aspose.com/page/java/) voor meer geavanceerde functies en mogelijkheden, zoals vector‑graphics, tekst‑rendering en aangepaste paginagroottes.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}