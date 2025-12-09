---
date: 2025-12-09
description: Leer hoe u een PostScript‑document maakt in Java en een afbeelding verplaatst
  en roteert met Aspose.Page voor naadloze beeldmanipulatie.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript‑document maken in Java – Afbeelding toevoegen in Java‑PostScript
url: /nl/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript-document maken in Java – Afbeelding toevoegen in Java PostScript

## Inleiding
In deze tutorial leer je hoe je **een PostScript-document in Java** maakt en afbeeldingen insluit met de Aspose.Page for Java bibliotheek. We lopen elke stap door, van het opzetten van het document tot het toepassen van transformaties zoals **verplaatsen en roteren van afbeelding**. Aan het einde kun je programmatically rijke PostScript-bestanden genereren en de plaatsing van afbeeldingen aanpassen aan je exacte lay-outbehoeften.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Page for Java  
- **Kan ik meerdere afbeeldingen toevoegen?** Ja – herhaal de transformatie- en tekenstappen  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie  
- **Welke Java-versie wordt ondersteund?** Java 8 en later  
- **Wordt rotatie van afbeeldingen ondersteund?** Absoluut – gebruik `AffineTransform.rotate()`  

## Wat is het maken van een PostScript-document in Java?
Een PostScript-document is een page description language‑bestand dat tekst, grafische elementen en afbeeldingen beschrijft. Met Aspose.Page kun je deze bestanden programmatically genereren in Java, waardoor je volledige controle krijgt over lay-out, grafische status en beeldverwerking zonder een PostScript‑interpreter nodig te hebben.

## Waarom Aspose.Page gebruiken voor beeldmanipulatie?
- **High‑level API:** Vereenvoudigt complexe PostScript‑commando's.  
- **Cross‑platform:** Werkt op elk OS dat Java ondersteunt.  
- **Full graphics state control:** Gemakkelijk opslaan, herstellen, verplaatsen, schalen en roteren van graphics.  
- **No external dependencies:** Behandelt het laden en converteren van afbeeldingen intern.  

## Vereisten
Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je systeem.  
- Aspose.Page for Java bibliotheek. Je kunt het downloaden [hier](https://releases.aspose.com/page/java/).  
- Een basisbegrip van Java‑programmeren.  

## Pakketten importeren
Om te beginnen, importeer je de benodigde pakketten in je Java‑project. Gebruik de volgende code‑fragment als referentie:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Stap 1: Graphics opslaan schrijven
De eerste stap omvat het schrijven van de graphics‑save naar het document. Dit zorgt ervoor dat eventuele transformaties of wijzigingen die daarna worden aangebracht, indien nodig ongedaan kunnen worden gemaakt.

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

## Stap 2: Verplaatsen en transformeren (verplaatsen en roteren van afbeelding)
Vervolgens verplaats je het document en maak je een `BufferedImage`‑object van het afbeeldingsbestand. Pas een reeks transformaties toe, zoals schalen en roteren, met behulp van `AffineTransform`. Hier vindt de **verplaatsen en roteren van afbeelding**‑operatie plaats.

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

## Stap 4: Graphics herstellen schrijven
Na het toevoegen van de afbeelding, schrijf je de graphics‑restore om de aangebrachte wijzigingen te finaliseren.

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
- **FileNotFoundException:** Zorg ervoor dat het `dataDir`‑pad eindigt met een bestandsseparator (`/` of `\\`) en dat de bestandsnaam van de afbeelding exact overeenkomt.  
- **ImageIO.read returns null:** Controleer of het afbeeldingsformaat wordt ondersteund (bijv. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` verwacht radialen. Converteer graden naar radialen (`Math.toRadians(degrees)`) indien nodig.  

## Veelgestelde vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere programmeertalen?**  
A: Aspose.Page ondersteunt voornamelijk Java, maar er zijn ook versies beschikbaar voor andere programmeertalen.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

**Q: Hoe kan ik een tijdelijke licentie voor Aspose.Page for Java verkrijgen?**  
A: Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) krijgen.

**Q: Waar kan ik community‑ondersteuning en discussies vinden over Aspose.Page for Java?**  
A: Bezoek het [Aspose.Page Forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.

**Q: Zijn er extra bronnen voor het aanschaffen van Aspose.Page for Java?**  
A: Je kunt de bibliotheek [hier](https://purchase.aspose.com/buy) kopen.

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je **een PostScript-document in Java** maakt en afbeeldingen insluit met Aspose.Page for Java. Verken de [documentatie](https://reference.aspose.com/page/java/) voor meer geavanceerde functies en mogelijkheden, zoals vectorgraphics, tekstweergave en aangepaste paginagroottes.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}