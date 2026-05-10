---
date: 2026-03-21
description: Leer hoe u tekst kunt invullen en tekst kunt toevoegen aan PS‑documenten
  met Aspose.Page voor .NET. Stapsgewijze handleiding met codevoorbeelden.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Hoe tekst in PostScript (PS)-documenten in te vullen met Aspose.Page
url: /nl/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe tekst invullen in PostScript (PS) documenten met Aspose.Page

## Introductie

Als u **tekst moet invullen** in een PostScript (PS) bestand, maakt Aspose.Page voor .NET het eenvoudig. Of u nu rapporten, facturen of aangepaste grafische afbeeldingen genereert, tekst toevoegen en opmaken is een kernvereiste. In deze tutorial lopen we het volledige proces door—van het opzetten van de omgeving tot het opslaan van het uiteindelijke PS‑document—zodat u met vertrouwen tekst kunt toevoegen aan PS‑bestanden in uw .NET‑toepassingen.

## Snelle antwoorden
- **Wat betekent “fill text”?** Het rendert tekens met een solide penseel, waarbij de glyphs direct op de pagina worden geschilderd.  
- **Kan ik aangepaste lettertypen gebruiken?** Ja—Aspose.Page ondersteunt aangepaste lettertypen via de `add custom font ps`‑functie.  
- **Hoe sla ik het PS‑document op?** Roep `document.Save()` aan na het sluiten van de pagina; dit schrijft het bestand naar schijf (`save ps document`).  
- **Wordt “fill and stroke text” ondersteund?** Absoluut; gebruik `FillAndStrokeText` om zowel vulling als omtrek toe te passen.  
- **Welke .NET‑versies zijn vereist?** Elke .NET Framework 4.5+ of .NET Core/5/6+ runtime.

## Wat betekent “tekst invullen” in een PS‑document?

Tekst invullen betekent het schilderen van de tekens met een effen kleur (of penseel) zonder omtrek. In PostScript is dit analoog aan de `fill`‑operator. Aspose.Page abstraheert dit naar gemakkelijk te gebruiken methoden zoals `FillText` en `FillAndStrokeText`.

## Waarom Aspose.Page gebruiken voor het toevoegen van aangepaste lettertype‑ps?

- **Volledige lettertype‑ondersteuning** – systeemlettertypen en externe TrueType/OpenType‑lettertypen werken direct uit de doos.  
- **Precieze positionering** – u beheert X/Y‑coördinaten, grootte en stijl.  
- **Rijke opmaak** – combineer vullingen, omtrekken en pennen voor effecten zoals “fill and stroke text”.  
- **Cross‑platform** – werkt op Windows, Linux en macOS met dezelfde API.

## Voorvereisten

- **Aspose.Page for .NET** – download de bibliotheek van de [Aspose.Page .NET documentatie](https://reference.aspose.com/page/net/).  
- **Documentdirectory** – een map op uw computer waar de bron‑ en uitvoer‑PS‑bestanden worden opgeslagen (verwijst in de code naar *Your Document Directory*).  
- **Lettertype‑map** – een submap die alle aangepaste lettertypen bevat die u wilt gebruiken.

## Namespaces importeren

Importeer eerst de benodigde namespaces zodat de compiler weet waar de klassen die we gaan gebruiken zich bevinden:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stapsgewijze handleiding

### Stap 1: Maak een output‑stream voor PS‑document

We openen een `FileStream` die het gegenereerde PS‑bestand zal bevatten, configureren `PsSaveOptions` om naar onze aangepaste lettertype‑map te wijzen, en maken een `PsDocument` aan.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro‑tip:** Houd de `using`‑block aan om ervoor te zorgen dat de stream automatisch wordt gesloten, wat tevens het PS‑bestand finaliseert (`save ps document`).

### Stap 2: Tekst invullen met een systeemlettertype

Hier demonstreren we de basis **tekst invullen**‑operatie met het ingebouwde *Times New Roman*‑lettertype.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Stap 3: Tekst invullen met een aangepast lettertype

Als u een specifieke uitstraling nodig heeft, laad dan een aangepast lettertype uit de lettertype‑map met `ExternalFontCache.FetchDrFont`. Dit voldoet aan de **add custom font ps**‑vereiste.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Stap 4: Tekst omranden (stroke) met een systeemlettertype

Omranden tekent de contour van de glyph. Combineer dit met een vulling voor een “fill and stroke”‑effect.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Waarom dit belangrijk is:** De `FillAndStrokeText`‑aanroep laat zien hoe u **fill and stroke text** in één stap kunt toepassen, waardoor u meer typografische controle krijgt.

### Stap 5: Tekst omranden met een aangepast lettertype

Dezelfde omrandtechniek werkt met elk aangepast lettertype dat u hebt geladen.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Stap 6: Pagina sluiten en het document opslaan

Afronden is eenvoudig: sluit de huidige pagina en roep `Save()` aan om het PS‑bestand naar schijf te schrijven.

```csharp
document.ClosePage();
document.Save();
}
```

> **Resultaat:** U vindt `AddText_outPS.ps` in *Your Document Directory*, met zowel gevulde als omrande tekst die is gerenderd met systeem‑ en aangepaste lettertypen.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oplossing |
|----------|-----------|
| **Aangepast lettertype niet gevonden** | Controleer of het lettertype‑bestand (.ttf/.otf) bestaat in de map die wordt aangeduid door `AdditionalFontsFolders`. |
| **Tekst verschijnt op verkeerde positie** | Pas de X/Y‑coördinaten aan die aan `FillText`/`OutlineText` worden doorgegeven. Onthoud dat PostScript punten gebruikt (1/72 inch). |
| **Kleuren zien er anders uit** | Zorg ervoor dat u `SolidBrush` of `Pen` gebruikt met de juiste `Color`‑waarden. |
| **Document wordt niet opgeslagen** | Bevestig dat de `using`‑block voltooid wordt zonder uitzonderingen en dat de applicatie schrijfrechten heeft voor de doelmap. |

## Veelgestelde vragen

**V: Kan ik Aspose.Page gebruiken met andere .NET‑bibliotheken?**  
A: Ja, Aspose.Page integreert soepel met andere .NET‑componenten, waardoor u PDF-, afbeelding‑ of grafiek‑bibliotheken in dezelfde oplossing kunt combineren.

**V: Zijn aangepaste lettertypen essentieel voor dit proces?**  
A: Hoewel systeemlettertypen prima werken, geven aangepaste lettertypen u volledige ontwerpvrijheid en zijn ze nuttig wanneer merk‑specifieke typografie vereist is.

**V: Is Aspose.Page geschikt voor grootschalige documentverwerking?**  
A: Absoluut. De bibliotheek is geoptimaliseerd voor scenario's met hoge doorvoersnelheid en kan efficiënt duizenden PS‑bestanden verwerken.

**V: Kan ik de positie van de tekst in het PS‑document aanpassen?**  
A: Zeker—verander eenvoudig de numerieke X/Y‑waarden in de `FillText`‑ of `OutlineText`‑aanroepen.

**V: Waar kan ik hulp zoeken voor Aspose.Page‑gerelateerde vragen?**  
A: Bezoek het [Aspose.Page Forum](https://forum.aspose.com/c/page/39) om contact te maken met de community en deskundige hulp te krijgen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-21  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose