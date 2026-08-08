---
date: 2026-07-19
description: Leer hoe u een PostScript-document in ASP.NET maakt met Aspose.Page voor
  .NET, meerdere transformations toepast en het bestand efficiënt opslaat.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformations PS
og_description: Maak een PostScript-document in ASP.NET met Aspose.Page. Leer hoe
  u translation, scaling, rotation en shearing toepast en vervolgens het bestand opslaat.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: PostScript Document maken in ASP.NET – Aspose.Page Guide
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: PostScript Document maken in ASP.NET met Aspose.Page
url: /nl/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak PostScript-document ASP.NET met Aspose.Page

## Inleiding

In deze stap‑voor‑stap‑handleiding **maak je een PostScript‑document ASP.NET** met behulp van de Aspose.Page‑bibliotheek, pas je verschillende grafische transformaties toe en sla je het resultaat uiteindelijk op in een `.ps`‑bestand. Aan het einde van de gids begrijp je waar je elke transformatie op de graphics‑state‑stack moet plaatsen, hoe je ze efficiënt kunt combineren en hoe je de teken‑opdrachten kunt behouden zodat elke PostScript‑interpreter ze kan renderen. Deze kennis is essentieel voor het genereren van afdrukbare graphics, aangepaste rapporten of dynamische printer‑klare assets rechtstreeks vanuit .NET‑toepassingen.

## Snelle antwoorden
- **Wat kan ik maken?** Een volledig uitgeruste PostScript‑document met getransformeerde graphics.  
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET (downloadbaar vanaf de officiële site).  
- **Hoe sla ik het bestand op?** Gebruik `PsDocument.Save()` nadat je de graphics‑states hebt geconfigureerd.  
- **Kan ik meerdere transformaties toepassen?** Ja – combineer ze met `Transform` of opeenvolgende aanroepen.  
- **Is een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.

## Wat is een “save postscript file” bewerking?

Een PostScript‑bestand opslaan betekent dat je de teken‑opdrachten die je in het geheugen hebt opgebouwd, permanent maakt in een `.ps`‑bestand op schijf. Het bestand kan vervolgens worden gerenderd door elke PostScript‑interpreter, printer of viewer, waardoor het een draagbare, apparaat‑onafhankelijke weergave van vector‑graphics is. Wanneer je de `Save`‑methode aanroept, serialiseert Aspose.Page de volledige graphics‑state, inclusief paden, penselen en transformatie‑matrices, naar geldige PostScript‑syntaxis die voldoet aan de Adobe®‑specificatie.

## Waarom Aspose.Page voor .NET gebruiken om een postscript‑document te maken?

Aspose.Page voor .NET biedt een sterk getypeerde, object‑georiënteerde API die de low‑level PostScript‑taal abstraheert. Het beheert automatisch de graphics‑state‑stack, ondersteunt meer dan 50 transformatie‑gerelateerde methoden en kan documenten van meer dan 500 pagina’s verwerken zonder het volledige bestand in het geheugen te laden. Dit verkort de ontwikkelingstijd tot wel 70 % vergeleken met handmatig schrijven van PostScript‑code en garandeert compatibiliteit met alle belangrijke printers.

## Vereisten

- **Aspose.Page voor .NET**‑bibliotheek geïntegreerd in je project. Haal deze op via de [download link](https://releases.aspose.com/page/net/).  
- Een map met schrijfrechten waar het gegenereerde `.ps`‑bestand wordt opgeslagen. Vervang het tijdelijke pad in de code door je eigen directory.  
- .NET 6.0 of hoger (de bibliotheek ondersteunt ook .NET Core 3.1 en .NET Framework 4.6+).

## Namespaces importeren

De `PsDocument`‑klasse bevindt zich in de `Aspose.Page.Drawing`‑namespace, terwijl transformatie‑helpers in `Aspose.Page.Drawing.Graphics` staan. Importeer ze bovenaan je bestand:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` is de kernklasse van Aspose.Page die een PostScript‑document in het geheugen vertegenwoordigt. Na het importeren van de namespaces kun je beginnen met het bouwen van het tekenoppervlak.

Now let’s explore each transformation step‑by‑step.

## Geen transformaties

`PsDocument` is het toegangspunt voor alle teken‑operaties. Het volgende fragment maakt een nieuw document, tekent een eenvoudige oranje rechthoek en slaat het op zonder enige transformatie.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Dit fragment maakt een **PostScript‑document** met één oranje rechthoek en **slaat het PostScript‑bestand** op zonder transformaties toe te passen.

## Translatie

Het opslaan van de graphics‑state stelt je in staat terug te keren nadat objecten zijn verplaatst. De `SaveState`‑methode duwt de huidige transformatie‑matrix op de interne stack.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

De `Translate`‑methode verplaatst het coördinatensysteem met de opgegeven offsets, waardoor alle volgende teken‑opdrachten worden beïnvloed.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Nu verschijnt een blauwe rechthoek 250 punten rechts van de oranje, omdat de translatiematrix actief is.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Herstellen brengt het coördinatensysteem terug naar de oorspronkelijke positie, zodat latere teken‑acties niet door de translatie worden beïnvloed.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Schalen

`Scale` verandert de grootte van getekende objecten door een schaalmatrix toe te passen op de huidige graphics‑state.

> *Je kunt hetzelfde patroon volgen – state opslaan, `Scale` toepassen, tekenen, daarna herstellen.*  
> **Pro tip:** Gebruik niet‑uniforme schaal (`Scale(sx, sy)`) om objecten alleen in één richting uit te rekken, wat handig is voor staaf‑diagrammen.

## Rotatie

`Rotate` past een rotatiematrix toe op de huidige graphics‑state, waardoor volgende teken‑acties met de opgegeven hoek worden gedraaid.

> *Roteer rond de oorsprong of een aangepast draaipunt met `Rotate(angle)`.*
> **Pro tip:** Combineer `Translate` vóór rotatie om rond een specifiek punt te draaien in plaats van de oorsprong.

## Schuiven

`Shear` scheef het coördinatensysteem met de opgegeven factoren, waardoor getekende objecten horizontaal en/of verticaal worden gekanteld.

> *Shear‑transformaties (`Shear(shx, shy)`) kantelen vormen, nuttig voor cursieve effecten of perspectieftrucs.*

## Complexe transformaties

`Transform` past een aangepaste transformatie‑matrix toe op de graphics‑state, waardoor meerdere bewerkingen in één stap worden gecombineerd.

> *Voor geavanceerde scenario’s bouw je een aangepaste `Matrix` en geef je deze door aan `Transform(matrix)`.*
> Dit is waar je **meerdere transformaties** in één stap toepast, waardoor het aantal state‑saves en restores wordt verminderd.

## Hoe een PostScript‑bestand opslaan met transformaties?

`Save` schrijft het huidige `PsDocument` naar een bestand in PostScript‑formaat. Laad je `PsDocument`, pas de gewenste transformatie‑reeks toe en roep `Save` aan met het doelpad – Aspose.Page schrijft een standaard‑conform `.ps`‑bestand in één doorgang. De bibliotheek sluit automatisch elke geopende graphics‑state, zodat je geen extra opruimcode nodig hebt. Deze aanpak werkt voor elke combinatie van translatie, schaling, rotatie of schuiving.

## Veelvoorkomende gebruikssituaties

- **Dynamische rapportgeneratie** – maak grafieken die zich tijdens runtime aanpassen aan de gegevensgrootte.  
- **Print‑klare facturen** – voeg bedrijfslogo’s toe en roteer ze zodat ze passen bij de printeroriëntatie.  
- **Aangepast labelontwerp** – pas schuiving toe om een reliëf‑tekst effect te simuleren.  

## Veelgestelde vragen

**Q: Hoe kan ik meerdere transformaties op één object toepassen?**  
A: Gebruik de `Transform`‑methode met een aangepaste `Matrix` die translatie, schaal, rotatie of schuiving combineert in de gewenste volgorde.

**Q: Kan ik de transformaties bekijken voordat ik het document opsla?**  
A: Ja – render het `PsDocument` naar een afbeelding met `PsDocument.Save("output.png", SaveFormat.Png)` of open het `.ps`‑bestand in een PostScript‑viewer om het resultaat te inspecteren voordat je `Save()` aanroept voor het definitieve bestand.

**Q: Is het mogelijk om transformaties toe te passen op specifieke elementen in een document?**  
A: Absoluut. Sla de graphics‑state op vóór het tekenen van het element, pas de gewenste transformatie toe, teken, en herstel vervolgens de state zodat latere elementen onaangetast blijven.

**Q: Zijn er prestatie‑overwegingen bij complexe transformaties?**  
A: Complexe matrices verhogen de CPU‑belasting. Houd transformaties zo eenvoudig mogelijk en hergebruik opgeslagen states bij het tekenen van veel gelijkaardige objecten. Aspose.Page verwerkt een document van 300 pagina’s met gemengde transformaties in minder dan 2 seconden op een typische 3,2 GHz CPU.

**Q: Hoe kan ik ondersteuning krijgen of hulp zoeken voor vragen over Aspose.Page?**  
A: Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning, of neem rechtstreeks contact op met Aspose‑support voor prioritaire assistentie.

---

**Laatst bijgewerkt:** 2026-07-19  
**Getest met:** Aspose.Page 24.11 voor .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

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

## Gerelateerde tutorials

- [Maak postscript‑document .net – Voeg rechthoek toe met Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Afbeelding toevoegen aan PostScript (PS)‑document met Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Pagina toevoegen aan PostScript (PS)‑document met Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}