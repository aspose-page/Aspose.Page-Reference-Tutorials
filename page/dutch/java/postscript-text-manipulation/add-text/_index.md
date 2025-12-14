---
date: 2025-12-14
description: Leer hoe je tekstkleur in Java instelt met Aspose.Page voor Java, tekst
  toevoegt aan PostScript en stroke‑tekst toepast voor rijke documentopmaak.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Tekstkleur instellen in Java met Aspose.Page – Gids voor tekstmanipulatie
url: /nl/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tekstkleur Instellen in Java met Aspose.Page – Gids voor Tekstmanipulatie

## Inleiding
Welkom bij onze stapsgewijze gids over **set text color java** tijdens het werken met PostScript‑bestanden met Aspose.Page voor Java. Aspose.Page voor Java is een krachtige bibliotheek die ontwikkelaars in staat stelt **generate postscript file** documenten te maken, lettertypen te manipuleren en tekst nauwkeurig te stijlen. In deze tutorial leer je hoe je tekst toevoegt, de kleur wijzigt, de grootte aanpast en zelfs **apply stroke text** voor een gepolijste uitstraling.

## Snelle Antwoorden
- **Welke bibliotheek laat me tekstkleur instellen in Java?** Aspose.Page for Java.
- **Kan ik systeemlettertypen en aangepaste lettertypen gebruiken?** Ja, beide worden ondersteund.
- **Hoe wijzig ik de tekstgrootte?** Door de lettergrootte op te geven bij het maken van de `Font` of `DrFont`.
- **Is het mogelijk om tekst zowel te omranden als te vullen?** Absoluut – gebruik `fillAndStrokeText`.
- **Welk uitvoerformaat produceert deze tutorial?** Een PostScript (`.ps`) document.

## Wat is “set text color java”?
Het instellen van de tekstkleur in Java betekent het definiëren van het `Color`‑object dat de renderengine (hier, Aspose.Page) gebruikt bij het tekenen van tekens op een pagina. Deze bewerking is essentieel voor het maken van visueel onderscheidende documenten, vooral bij het programmatisch genereren van **postscript documents**.

## Waarom Aspose.Page voor Java gebruiken?
- **Volledige controle** over PostScript‑generatie zonder een native PostScript‑interpreter nodig te hebben.
- **Ondersteuning voor zowel systeem- als externe lettertypen**, waardoor je elke gewenste typografie kunt insluiten.
- **Eenvoudige API** om tekst te vullen, te omranden en **fill and stroke text**, wat je flexibiliteit in styling geeft.
- **Cross‑platform compatibiliteit** – één keer schrijven, overal uitvoeren waar Java draait.

## Vereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

- Basiskennis van Java‑programmering.
- Aspose.Page for Java bibliotheek geïnstalleerd. Je kunt deze downloaden van de [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Noodzakelijke lettertypen beschikbaar in de opgegeven map. Extra details staan in de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Importeer Pakketten
In je Java‑project importeer je de benodigde pakketten voor Aspose.Page for Java:

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

## Stap 1: Document Instellen
Eerst maken we een nieuw **PostScript document** en configureren we de uitvoeropties.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Hoe Tekstkleur Instellen in Java met Systeemlettertype
Nu demonstreren we **set text color java** met een door het systeem geleverd lettertype.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** De `fillText`‑methode gebruikt automatisch de huidige kleur als je geen `Color`‑argument doorgeeft, wat standaard zwart is.

## Aangepast Lettertype Gebruiken en Tekstgrootte Wijzigen
Je kunt ook **change text size** en een aangepast lettertype gebruiken dat in je lettertype‑map is opgeslagen.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Tekst Omranden (Stroke) – Stroke Tekst Toepassen
Tekst omranden geeft het een scherpe rand. Hier **apply stroke text** met een `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Tekst Omranden met Aangepast Lettertype
Dezelfde techniek werkt met aangepaste lettertypen.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Stap 6: Document Opslaan
Tot slot sluit je de pagina en schrijf je het bestand naar de schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Veelvoorkomende Problemen & Oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Lettertype niet gevonden** | Zorg ervoor dat het lettertype‑bestand in `necessary_fonts` staat en dat het mappad correct is toegevoegd via `options.setAdditionalFontsFolders`. |
| **Kleur niet toegepast** | Controleer of je de overload van `fillText` of `outlineText` aanroept die een `Color`‑argument bevat. |
| **Stroke is te dun** | Verhoog de breedte van de `BasicStroke` (bijv. `new BasicStroke(3)`). |
| **Document opent niet** | Bevestig dat het gegenereerde `.ps`‑bestand met de juiste extensie is opgeslagen en dat je viewer PostScript ondersteunt. |

## Veelgestelde Vragen

**Q:** Kan ik mijn eigen aangepaste lettertypen gebruiken met Aspose.Page voor Java?  
**A:** Ja, je kunt aangepaste lettertypen gebruiken door de lettertype‑naam en -grootte op te geven in de `DrFont`‑klasse.

**Q:** Hoe kan ik de kleur van de tekst wijzigen?  
**A:** Je kunt de gewenste kleur instellen met de `Color`‑klasse bij het vullen of omranden van de tekst.

**Q:** Is het mogelijk om meerdere pagina's toe te voegen aan een PostScript‑document?  
**A:** Absoluut! Je kunt meerdere pagina's maken door de stappen voor het maken en opslaan van het document te herhalen.

**Q:** Wat is het doel van de `ExternalFontCache`‑klasse?  
**A:** `ExternalFontCache` wordt gebruikt om aangepaste lettertypen op te halen, zodat ze beschikbaar zijn voor tekstmanipulatie.

**Q:** Kan ik verschillende strokes toepassen op de omrande tekst?  
**A:** Ja, je kunt de breedte en kleur van de stroke aanpassen met de `Stroke`‑klasse en respectievelijk de `Color`‑klasse.

## Conclusie
Gefeliciteerd! Je weet nu hoe je **set text color java** kunt uitvoeren, lettergroottes kunt wijzigen, **apply stroke text**, en **create postscript document** bestanden kunt maken met Aspose.Page voor Java. Experimenteer met verschillende lettertypen, kleuren en omrandingsstijlen om professioneel uitziende PostScript‑output te produceren.

---

**Laatst Bijgewerkt:** 2025-12-14  
**Getest Met:** Aspose.Page for Java 23.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}