---
date: 2026-01-12
description: Leer hoe u een PostScript‑bestand opslaat en een PostScript‑document
  maakt met Aspose.Page voor .NET, en meerdere transformaties toepast voor dynamische
  grafische afbeeldingen.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: PostScript‑bestand opslaan met Aspose.Page‑transformaties (.NET)
url: /nl/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript-bestand opslaan met Aspose.Page-transformaties (.NET)

## Inleiding

In deze tutorial ontdek je hoe je een **opslaan van een PostScript-bestand** kunt doen terwijl je werkt met Aspose.Page voor .NET. We lopen door het maken van een PostScript-document, het toepassen van meerdere transformaties zoals translatie, schaalvergroting, rotatie en schuine vervorming, en tenslotte het opslaan van het resultaat. Aan het einde kun je dynamische graphics programmatically maken en weet je precies waar je elke transformatie in de graphics‑state moet plaatsen.

## Snelle antwoorden
- **Wat kan ik maken?** Een volledig uitgeruste PostScript-document met getransformeerde graphics.  
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET (downloadbaar vanaf de officiële site).  
- **Hoe sla ik het bestand op?** Gebruik `PsDocument.Save()` na het configureren van de graphics‑states.  
- **Kan ik meerdere transformaties toepassen?** Ja – combineer ze met `Transform` of opeenvolgende aanroepen.  
- **Is een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.

## Wat is een “opslaan PostScript‑bestand” operatie?

Het opslaan van een PostScript‑bestand betekent dat je de tekenopdrachten die je in het geheugen hebt opgebouwd, opslaat naar een `.ps`‑bestand op schijf. Het bestand kan vervolgens worden gerenderd door elke PostScript‑interpreter, printer of viewer.

## Waarom Aspose.Page voor .NET gebruiken om een PostScript‑document te maken?

Aspose.Page biedt een high‑level, apparaat‑onafhankelijke API die de low‑level PostScript‑syntaxis abstraheert. Je krijgt:

- Sterk getypeerde C#‑objecten voor paden, penselen en transformaties.  
- Automatische afhandeling van de graphics‑state‑stack (save/restore).  
- Volledige ondersteuning voor complexe transformatie‑matrices zonder handmatige berekeningen.  

## Vereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

- **Aspose.Page voor .NET** bibliotheek geïntegreerd in je project. Haal het op via de [download link](https://releases.aspose.com/page/net/).  
- Een beschrijfbare map waar het gegenereerde `.ps`‑bestand wordt opgeslagen. Vervang het tijdelijke pad in de code door je eigen map.

## Namespaces importeren

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we nu elke transformatie stap voor stap verkennen.

## Geen transformaties

### Stap 1: Output‑stream maken

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Dit fragment maakt een **PostScript‑document** met één oranje rechthoek en **slaat het PostScript‑bestand op** zonder enige transformaties toe te passen.

## Translatie

### Stap 1: Graphics‑state opslaan

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Het opslaan van de graphics‑state stelt je in staat om terug te keren na het verplaatsen van objecten.

### Stap 2: Graphics‑state translaten

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

De translatie verplaatst alles wat na deze oproep wordt getekend 250 eenheden naar rechts.

### Stap 3: Rechthoek vullen met translatie‑transformatie

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Nu verschijnt een blauwe rechthoek 250 punten rechts van de oranje.

### Stap 4: Graphics‑state herstellen

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Herstellen zet het coördinatensysteem terug naar de oorspronkelijke positie, zodat latere tekeningen niet door de translatie worden beïnvloed.

## Schaalvergroting

> *Je kunt hetzelfde patroon volgen—state opslaan, `Scale` toepassen, tekenen, en vervolgens herstellen.*  
> **Pro tip:** Gebruik niet‑uniforme schaalvergroting (`Scale(sx, sy)`) om objecten alleen in één richting uit te rekken.

## Rotatie

> *Roteer rond de oorsprong of een aangepast draaipunt met `Rotate(angle)`.*
> **Pro tip:** Combineer `Translate` vóór rotatie om rond een specifiek punt te roteren.

## Schuine vervorming

> *Shear‑transformaties (`Shear(shx, shy)`) kantelen vormen, handig voor cursieve effecten.*

## Complexe transformaties

> *Voor geavanceerde scenario's, bouw een aangepaste `Matrix` en geef deze door aan `Transform(matrix)`.*
> Dit is waar je **meerdere transformaties toepast** in één stap.

## Conclusie

Je hebt geleerd hoe je een **opslaan van een PostScript-bestand**, **een PostScript-document maakt**, en **meerdere transformaties toepast** met Aspose.Page voor .NET. Experimenteer met verschillende transformatie‑volgordes, combineer ze, en zie hoe de graphics evolueren.

## Veelgestelde vragen

**V: Hoe kan ik meerdere transformaties op één object toepassen?**  
Gebruik de `Transform`‑methode met een aangepaste `Matrix` die translatie, schaalvergroting, rotatie of schuine vervorming combineert in de volgorde die je nodig hebt.

**V: Kan ik de transformaties bekijken voordat ik het document opsla?**  
Ja—render het `PsDocument` naar een afbeelding of gebruik een PostScript‑viewer om de output te inspecteren voordat je `Save()` aanroept.

**V: Is het mogelijk om transformaties toe te passen op specifieke elementen in een document?**  
Absoluut. Sla de graphics‑state op vóór het tekenen van het element, pas de gewenste transformatie toe, teken, en herstel vervolgens de state.

**V: Zijn er prestatie‑overwegingen bij complexe transformaties?**  
Complexe matrices verhogen de CPU‑belasting. Houd transformaties zo eenvoudig mogelijk en hergebruik opgeslagen states bij het tekenen van veel gelijkaardige objecten.

**V: Hoe kan ik ondersteuning krijgen of hulp zoeken voor Aspose.Page‑gerelateerde vragen?**  
Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑hulp, of neem direct contact op met de Aspose‑ondersteuning.

**Laatst bijgewerkt:** 2026-01-12  
**Getest met:** Aspose.Page 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}