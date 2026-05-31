---
date: 2026-01-23
description: Leer hoe u een PostScript‑bestand genereert en cirkelvormige ellipsen
  toevoegt met Aspose.Page voor .NET. Volg deze stapsgewijze handleiding om snel ellipsen
  te tekenen met C#‑code.
linktitle: Add Circle Ellipse to PostScript (PS)
second_title: Aspose.Page .NET API
title: Genereer PostScript‑bestand & Voeg cirkel en ellips toe – Aspose.Page
url: /nl/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript-bestand genereren & cirkelvormige ellips toevoegen – Aspose.Page

## Inleiding

In deze tutorial ontdek je **hoe je een PostScript-bestand genereert** en een perfecte cirkelvormige ellips invoegt met behulp van de Aspose.Page .NET API. Of je nu een rapportage‑engine bouwt, vectorafbeeldingen maakt, of programmatisch een ellips moet tekenen in C#, deze gids leidt je door elke stap — van het opzetten van de omgeving tot het opslaan van het uiteindelijke PS‑document.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Twee ellipsen (gevuld en omrand) toevoegen aan een PostScript‑bestand met Aspose.Page voor .NET.  
- **Welk primair trefwoord wordt getarget?** *generate postscript file*.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basis‑ellipsvoorbeeld.

## Wat betekent “generate postscript file”?

Een PostScript‑bestand genereren betekent programmatisch een .ps‑document maken dat de paginainhoud beschrijft met behulp van de PostScript‑taal. Dit formaat wordt veel gebruikt voor afdrukken, grafisch ontwerp en PDF‑conversiepijplijnen.

## Waarom een cirkel‑ellips toevoegen met Aspose.Page?

- **Precisie** – Vector‑gebaseerd tekenen garandeert verliesloze schaalvergroting.  
- **Cross‑platform** – Hetzelfde PS‑bestand kan worden gerenderd op elke PostScript‑compatibele printer.  
- **C#‑vriendelijk** – De API abstraheert low‑level PS‑commando's, zodat je *draw ellipse* kunt gebruiken met vertrouwde .NET‑typen.

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Aspose.Page for .NET** – Download en installeer de bibliotheek van [hier](https://releases.aspose.com/page/net/).  
2. **Een .NET‑ontwikkelomgeving** – Visual Studio, Rider, of de .NET‑CLI geïnstalleerd op je machine.

Nu alles klaar is, laten we beginnen met coderen.

## Namespaces importeren

Breng eerst de benodigde namespaces in scope zodat de Aspose.Page‑klassen beschikbaar zijn.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stapsgewijze gids

### Stap 1: Documentmap instellen

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

> **Pro tip:** Vervang `"Your Document Directory"` door een absoluut of relatief pad waar je applicatie naar kan schrijven.

### Stap 2: Output‑stream maken voor PostScript‑document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

De `FileStream` opent (of maakt) *AddEllipse_outPS.ps* waar de gegenereerde PS‑inhoud wordt opgeslagen.

### Stap 3: Opslaan‑opties en PS‑document maken

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Hier geven we een A4‑paginasize op en maken we een één‑pagina `PsDocument` aan.

### Stap 4: Graphics‑pad maken voor de eerste ellips

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

De `GraphicsPath` bevat de geometrische definitie van een ellips geplaatst op (250, 100) met een breedte van 150 pts en een hoogte van 100 pts.

### Stap 5: Paint instellen en de ellips vullen

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

We vullen de eerste ellips met een levendige oranje kleur.

### Stap 6: Graphics‑pad maken voor de tweede ellips

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Een tweede ellips wordt lager op de pagina gedefinieerd (y‑coördinaat 300).

### Stap 7: Stroke instellen en de ellips tekenen

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

Deze keer *draw ellipse* we met een rode pen met een dikte van 3 pts, waardoor een omrand contour ontstaat.

### Stap 8: Huidige pagina sluiten en het document opslaan

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Het sluiten van de pagina finaliseert de inhoud, en `Save()` schrijft de PostScript‑output naar de stream die we eerder hebben aangemaakt.

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Bestand niet aangemaakt** | `dataDir` verwijst naar een niet‑bestaande map. | Zorg ervoor dat de map bestaat of gebruik `Directory.CreateDirectory(dataDir);` voordat je de stream opent. |
| **Ellips ziet er vervormd uit** | Onjuiste rechthoekafmetingen (breedte ≠ hoogte). | Gebruik gelijke breedte en hoogte voor een perfecte cirkel; pas de `RectangleF`‑waarden dienovereenkomstig aan. |
| **Licentie‑exception** | Uitvoeren zonder een geldige Aspose.Page‑licentie in productie. | Pas een tijdelijke of permanente licentie toe zoals beschreven in de Aspose‑documentatie. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Page voor .NET gebruiken met andere documentformaten?**  
A: Aspose.Page richt zich voornamelijk op PostScript, maar Aspose biedt extra bibliotheken voor PDF, DOCX en andere formaten. Zie de [Aspose-documentatie](https://reference.aspose.com/page/net/) voor de volledige lijst.

**Q: Waar kan ik extra ondersteuning en community‑discussies vinden?**  
A: Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) om vragen te stellen, voorbeelden te delen en hulp te krijgen van andere ontwikkelaars.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page?**  
A: Ja, je kunt een gratis proefversie downloaden van de [gratis proefversie](https://releases.aspose.com/) pagina om de bibliotheek te evalueren voordat je koopt.

**Q: Hoe krijg ik een tijdelijke licentie voor testen?**  
A: Een tijdelijke licentie kan [hier](https://purchase.aspose.com/temporary-license/) worden aangevraagd en is 30 dagen geldig.

**Q: Waar kan ik een volledige licentie voor Aspose.Page kopen?**  
A: Aankoopopties staan vermeld op de officiële [koop‑pagina](https://purchase.aspose.com/buy).

## Conclusie

Je weet nu hoe je **een PostScript‑bestand genereert** en **ellipse**‑vormen tekent met Aspose.Page voor .NET. Door de bovenstaande stappen te volgen, kun je eenvoudig vectorafbeeldingen integreren in elke afdruk‑ of render‑workflow. Experimenteer met verschillende kleuren, lijndiktes en posities om meer complexe illustraties te maken.

---

**Laatst bijgewerkt:** 2026-01-23  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}