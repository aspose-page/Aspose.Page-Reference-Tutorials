---
date: 2026-03-03
description: Leer hoe u een aangepaste paginagrootte instelt en een tweede PS-pagina
  toevoegt aan een PostScript-document met Aspose.Page voor .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aangepaste paginagrootte instellen in PS-document met Aspose.Page
url: /nl/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pagina toevoegen aan PostScript (PS) document met Aspose.Page

## Introduction

In .NET-ontwikkeling geeft het kunnen **aangepaste paginagrootte instellen** en **een tweede PS-pagina toevoegen** aan een PostScript (PS) document je fijnmazige controle over de lay-out van gegenereerde afdrukken, rapporten of graphics. Aspose.Page voor .NET maakt deze taak eenvoudig met een schone, objectgeoriënteerde API. In deze tutorial leer je hoe je een meer‑pagina PS‑bestand maakt, een aangepaste grootte voor elke pagina definieert, en het resultaat opslaat — alles met slechts een paar regels C#‑code.

## Quick Answers
- **Kan ik een aangepaste paginagrootte instellen?** Ja – geef gewoon breedte en hoogte door bij het openen van een pagina.  
- **Hoe voeg ik een tweede PS-pagina toe?** Roep `document.OpenPage(width, height)` een tweede keer aan.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Waar kan ik Aspose.Page downloaden?** Van de officiële downloadpagina die hieronder is gelinkt.

## Prerequisites

Voordat je aan de tutorial begint, zorg ervoor dat je de volgende vereisten hebt:

- Een werkende kennis van .NET-ontwikkeling.  
- Visual Studio geïnstalleerd op je machine.  
- Aspose.Page voor .NET bibliotheek, die je kunt downloaden [hier](https://releases.aspose.com/page/net/).  
- Je gewenste documentmap voor testen.

## Import Namespaces

Zorg ervoor dat je de benodigde namespaces in je project opneemt om toegang te krijgen tot de functionaliteiten die Aspose.Page biedt. In het gegeven voorbeeld zijn de namespaces impliciet inbegrepen, maar het is essentieel om dit te dubbelchecken en aanpassingen te maken op basis van je projectstructuur.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Project

Maak een nieuw .NET-project aan in Visual Studio en stel de benodigde configuraties in. Zorg ervoor dat je de Aspose.Page‑bibliotheek in je project opneemt.

## Set Custom Page Size and Add Second PS Page

Deze sectie toont precies hoe je **een aangepaste paginagrootte** voor elke pagina instelt en hoe je **een tweede ps-pagina** aan hetzelfde document toevoegt.

### Step 2: Initialize the Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Step 3: Add the First Page (default size)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Step 4: Add the Second Page with a Different (Custom) Size

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Step 5: Save the Document

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Volg deze stappen nauwkeurig, en je zult succesvol **een aangepaste paginagrootte** instellen en een **tweede PS-pagina** toevoegen aan een PostScript‑document met Aspose.Page voor .NET.

## Why This Matters

- **Precisie‑lay-out** – Aangepaste paginadimensies laten je printerspecificaties matchen of unieke brochure‑formaten creëren.  
- **Meerdere pagina's** – Het toevoegen van een tweede pagina (of meer) maakt meer‑pagina rapporten mogelijk zonder externe samenvoeg‑tools.  
- **Cross‑platform** – Het gegenereerde PS‑bestand kan worden gerenderd op elk PostScript‑compatibel apparaat of later naar PDF worden geconverteerd.

## Common Pitfalls & Troubleshooting

- **Onjuist pad** – Zorg ervoor dat `dataDir` eindigt met een pad‑scheidingsteken of gebruik `Path.Combine`.  
- **Licentieproblemen** – Zonder een geldige licentie kan de bibliotheek een watermerk toevoegen of het aantal pagina's beperken.  
- **Eenheidsverwarring** – Breedte en hoogte worden gemeten in points (1 point = 1/72 inch). Pas dit dienovereenkomstig aan.

## Frequently Asked Questions

**Q1: Is Aspose.Page compatibel met verschillende documentformaten?**  
A1: Aspose.Page richt zich voornamelijk op het manipuleren van PostScript‑documenten. Voor andere formaten kun je Aspose‑bibliotheken verkennen die zijn afgestemd op specifieke behoeften.

**Q2: Kan ik de paginagrootte aanpassen in Aspose.Page?**  
A2: Zeker! Zoals in de tutorial getoond, kun je verschillende groottes voor elke pagina opgeven volgens je vereisten.

**Q3: Waar kan ik meer voorbeelden en documentatie vinden?**  
A3: Bezoek de [documentatie](https://reference.aspose.com/page/net/) voor uitgebreide informatie en diverse voorbeelden.

**Q4: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Page?**  
A4: Ga naar [deze link](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor testdoeleinden te verkrijgen.

**Q5: Waar kan ik community‑ondersteuning zoeken of vragen stellen?**  
A5: Word lid van het [Aspose.Page community‑forum](https://forum.aspose.com/c/page/39) om in contact te komen met andere ontwikkelaars, ervaringen te delen en hulp te zoeken.

---

**Laatst bijgewerkt:** 2026-03-03  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}