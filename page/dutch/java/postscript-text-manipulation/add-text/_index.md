---
date: 2026-02-20
description: Leer hoe je tekstkleur instelt in Java met Aspose.Page for Java, de lettergrootte
  wijzigt in Java, een PostScript‑bestand genereert, tekst vult en omlijnt, en aangepaste
  lettertypen gebruikt in Java bij het maken van een PostScript‑document.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Tekstkleur instellen in Java met Aspose.Page – Gids voor tekstmanipulatie
url: /nl/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tekstkleur instellen Java met Aspose.Page – Gids voor Tekstmanipulatie

## Introductie
Welkom bij onze stapsgewijze gids over **set text color java** tijdens het werken met PostScript‑bestanden met Aspose.Page voor Java. Aspose.Page voor Java is een krachtige bibliotheek die ontwikkelaars in staat stelt **create postscript document** bestanden te maken, lettertypen te manipuleren en tekst nauwkeurig te stijlen. In deze tutorial leer je hoe je tekst toevoegt, de kleur wijzigt, **change font size java**, en zelfs **apply fill and stroke text** voor een gepolijste uitstraling.

## Snelle antwoorden
- **Welke bibliotheek laat me tekstkleur instellen in Java?** Aspose.Page for Java.  
- **Kan ik systeemlettertypen en aangepaste lettertypen gebruiken?** Ja, beide worden ondersteund, en je kunt **use custom fonts java** gemakkelijk.  
- **Hoe wijzig ik de tekstgrootte?** Door de lettergrootte op te geven bij het maken van de `Font` of `DrFont`.  
- **Is het mogelijk om tekst zowel te omranden als te vullen?** Absoluut – gebruik `fillAndStrokeText`.  
- **Welk uitvoerformaat produceert deze tutorial?** Een PostScript (`.ps`) document, dat je programmatically **generate postscript file** kunt maken.

## Wat is “set text color java”?
Het instellen van de tekstkleur in Java betekent het definiëren van het `Color`‑object dat de renderengine (hier, Aspose.Page) gebruikt bij het tekenen van tekens op een pagina. Deze bewerking is essentieel voor het maken van visueel onderscheidende documenten, vooral wanneer je programmatically **generate postscript file** moet maken.

## Waarom Aspose.Page voor Java gebruiken?
- **Full control** over PostScript generation zonder een native interpreter nodig te hebben.  
- **Support for both system and external fonts**, waardoor je elke gewenste typografie kunt insluiten.  
- **Easy API** om te vullen, omranden en **fill and stroke text**, wat je flexibiliteit in styling geeft.  
- **Cross‑platform** compatibiliteit – één keer schrijven, overal uitvoeren waar Java draait.  

## Vereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page voor Java bibliotheek geïnstalleerd. Je kunt het downloaden van de [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- Noodzakelijke lettertypen beschikbaar in de opgegeven map. Extra details staan in de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Pakketten importeren
Importeer in je Java‑project de benodigde pakketten voor Aspose.Page voor Java:

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

## Stap 1: Document instellen
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

## Hoe tekstkleur instellen Java met systeemlettertype
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

## Aangepast lettertype gebruiken en tekstgrootte wijzigen
Je kunt ook **change font size java** en een aangepast lettertype gebruiken dat in je lettertype‑map is opgeslagen.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Tekst omranden (Stroke) – Stroke toepassen
Tekst omranden geeft een scherpe rand. Hier **apply stroke text** met een `BasicStroke`.

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

## Tekst omranden met aangepast lettertype
Dezelfde techniek werkt met aangepaste lettertypen.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Stap 6: Document opslaan
Tot slot sluit je de pagina en schrijf je het bestand naar schijf.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Waarom dit belangrijk is
In staat zijn om **set text color java** te doen en vullen te combineren met omranden geeft je volledige artistieke controle over de uiteindelijke PostScript‑output. Of je nu facturen, certificaten of aangepaste graphics genereert, de mogelijkheid om **create postscript document** bestanden met precieze styling te maken, vermindert de noodzaak voor nabewerking in grafische editors.

## Veelvoorkomende problemen & oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Font not found** | Zorg ervoor dat het lettertypebestand in `necessary_fonts` staat en dat het mappad correct is toegevoegd via `options.setAdditionalFontsFolders`. |
| **Color not applied** | Controleer of je de overload van `fillText` of `outlineText` aanroept die een `Color`‑argument bevat. |
| **Stroke appears too thin** | Verhoog de breedte van `BasicStroke` (bijv. `new BasicStroke(3)`). |
| **Document not opening** | Bevestig dat het gegenereerde `.ps`‑bestand is opgeslagen met de juiste extensie en dat je viewer PostScript ondersteunt. |

## Veelgestelde vragen

**Q:** Kan ik mijn eigen aangepaste lettertypen gebruiken met Aspose.Page voor Java?  
**A:** Ja, je kunt **use custom fonts java** door de lettertype‑naam en -grootte op te geven in de `DrFont`‑klasse.

**Q:** Hoe kan ik de kleur van de tekst wijzigen?  
**A:** Je kunt de gewenste kleur instellen met de `Color`‑klasse bij het vullen of omranden van de tekst.

**Q:** Is het mogelijk om meerdere pagina's toe te voegen aan een PostScript‑document?  
**A:** Absoluut! Je kunt meerdere pagina's maken door de documentcreatie‑ en opslagniveaus te herhalen.

**Q:** Wat is het doel van de `ExternalFontCache`‑klasse?  
**A:** `ExternalFontCache` wordt gebruikt om aangepaste lettertypen op te halen, zodat ze beschikbaar zijn voor tekstmanipulatie.

**Q:** Kan ik verschillende strokes toepassen op de omrande tekst?  
**A:** Ja, je kunt de breedte en kleur van de stroke aanpassen met respectievelijk de `Stroke`‑klasse en de `Color`‑klasse.

## Conclusie
Gefeliciteerd! Je weet nu hoe je **set text color java**, **change font size java**, **apply fill and stroke text**, en **create postscript document** bestanden kunt gebruiken met Aspose.Page voor Java. Experimenteer met verschillende lettertypen, kleuren en omrandingsstijlen om professioneel uitziende PostScript‑output te produceren.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}