---
date: 2026-02-05
description: Leer hoe je EPS opslaat als PNG met Aspose.Page voor Java terwijl je
  een meterlicentie configureert. Stapsgewijze gids met volledig code‑voorbeeld.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: EPS opslaan als PNG met Aspose.Page Java (Metered-licentie)
url: /nl/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS opslaan als PNG met Aspose.Page Java (Metered License)

## Inleiding
Als je **EPS als PNG wilt opslaan** in een Java‑applicatie en een probleemloze manier wilt om licenties te beheren, ben je hier aan het juiste adres. Deze tutorial leidt je door het configureren van een metered‑licentie voor Aspose.Page, het laden van een PostScript (EPS)‑bestand, en het converteren ervan naar een PNG‑afbeelding — allemaal met duidelijke, hapklare stappen die je direct kunt volgen. Aan het einde begrijp je ook hoe je **EPS naar PNG rendert** en **PNG‑bestand Java** code schrijft die in productieomgevingen werkt.

## Snelle antwoorden
- **Wat betekent “save EPS as PNG”?** Het converteert een vector‑EPS‑bestand naar een raster‑PNG‑afbeelding.  
- **Waarom een metered‑licentie gebruiken?** Je betaalt alleen voor de pagina's die je verwerkt, perfect voor variabele workloads.  
- **Heb ik een internetverbinding nodig?** Nee, de metered‑sleutels worden lokaal gevalideerd.  
- **Welke Java‑versie is vereist?** Java 8 of hoger.  
- **Hoe lang duurt de installatie?** Ongeveer 10 minuten voor een basisimplementatie.  

## Wat is “save EPS as PNG”?
Het opslaan van EPS als PNG zet een schaalbaar Encapsulated PostScript‑document om naar een breed ondersteund bitmap‑formaat. PNG behoudt transparantie en biedt verliesloze compressie, waardoor het ideaal is voor web‑graphics, miniaturen en afdruk‑voorbeelden.

## Waarom EPS renderen naar PNG met Aspose.Page?
- **Pure Java API** – geen native afhankelijkheden, zodat je het overal kunt uitvoeren waar de JVM wordt ondersteund.  
- **Hoge getrouwe weergave** – vector‑graphics worden nauwkeurig gerasterd, waardoor de lijnkwaliteit behouden blijft.  
- **Metered‑licenties** – je betaalt alleen voor wat je converteert, waardoor de kosten voorspelbaar blijven.  
- **Meerdere uitvoeropties** – naast PNG kun je ook JPEG, TIFF en meer genereren, wat je flexibiliteit geeft voor verschillende projecten.

## Voorvereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page‑bibliotheek geïnstalleerd – download deze van [hier](https://releases.aspose.com/page/java/).  
- Metered publieke en private sleutels, die je kunt verkrijgen via je Aspose‑account.

## Pakketten importeren
Importeer eerst de klassen die we nodig hebben. Houd het import‑blok exact zoals weergegeven zodat de code zonder wijzigingen compileert.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Hoe EPS opslaan als PNG met Aspose.Page Java
Hieronder vind je de stapsgewijze gids die licentiëren, laden, renderen en het schrijven van het uiteindelijke PNG‑bestand combineert.

### Stap 1: Document en afbeeldingsformaat initialiseren
Hier stellen we de metered‑sleutels in en definiëren we het uitvoerformaat (PNG). Dit is de basis voor de **save EPS as PNG**‑operatie.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Stap 2: PostScript‑invoerstroom initialiseren
Open het EPS‑bestand dat je wilt converteren. De stream levert het document aan Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Stap 3: Documentlicentie controleren
Controleer altijd dat de metered‑licentie correct is toegepast voordat je verder gaat.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Stap 4: Opties en afbeeldingsapparaat initialiseren
Maak het opties‑object aan dat de conversie‑instellingen regelt en het apparaat dat de gerenderde afbeelding ontvangt.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Stap 5: EPS‑bestand opslaan als afbeelding
Dit is de kern **save EPS as PNG**‑aanroep. Het document wordt gerenderd naar het afbeeldingsapparaat met behulp van de geconfigureerde opties.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Stap 6: Afbeeldingsbytes ophalen en opslaan
Haal de PNG‑bytes uit het apparaat en schrijf ze naar een bestand op schijf. Deze stap laat zien hoe je **write PNG file Java** veilig kunt uitvoeren.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Veelvoorkomende problemen en oplossingen
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Licentie niet herkend** | Sleutels zijn onjuist of in de verkeerde volgorde geplaatst. | Controleer de publieke/private sleutel‑strings nogmaals en zorg ervoor dat `setMeteredKey` wordt aangeroepen vóór enige documentverwerking. |
| **Uitvoerbestand is leeg** | `device.getImagesBytes()` gaf `null` terug. | Controleer of het EPS‑bestand geldig is en dat de `ImageSaveOptions` niet op een canvas met nul‑grootte zijn ingesteld. |
| **OutOfMemoryError bij grote EPS** | Het renderen van grote vectorbestanden verbruikt veel geheugen. | Verwerk pagina's één voor één of vergroot de JVM‑heap (`-Xmx2g`). |

## Veelgestelde vragen

**Q: Hoe krijg ik metered publieke en private sleutels?**  
A: Je kunt deze sleutels verkrijgen via je Aspose‑account.

**Q: Is de Aspose.Page‑bibliotheek gratis?**  
A: Aspose.Page biedt zowel een gratis proefversie als betaalde versies. Bezoek [hier](https://releases.aspose.com/) voor een gratis proefversie.

**Q: Kan ik Aspose.Page gebruiken voor commerciële projecten?**  
A: Ja, Aspose.Page biedt commerciële licenties. Je kunt ze aanschaffen [hier](https://purchase.aspose.com/buy).

**Q: Waar kan ik aanvullende documentatie vinden?**  
A: Raadpleeg de documentatie [hier](https://reference.aspose.com/page/java/).

**Q: Hoe kan ik tijdelijke licenties krijgen?**  
A: Tijdelijke licenties zijn verkrijgbaar [hier](https://purchase.aspose.com/temporary-license/).

**Q: Wat als ik multi‑page EPS‑bestanden moet converteren?**  
A: Loop door elke pagina met `device.getImagesBytes()` en schrijf elke byte‑array naar een apart PNG‑bestand.

**Q: Kan ik de PNG‑kwaliteit of kleurdiepte aanpassen?**  
A: Ja, configureer `ImageSaveOptions` (bijv. `options.setCompressionLevel(...)`) vóór het aanroepen van `document.save(...)`.

---

**Laatst bijgewerkt:** 2025-12-03  
**Getest met:** Aspose.Page 24.12 for Java  
**Auteur:** Aspose  

**Laatst bijgewerkt:** 2026-02-05  
**Getest met:** Aspose.Page 24.12 for Java (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}