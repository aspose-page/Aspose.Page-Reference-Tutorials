---
date: 2026-03-21
description: Leer hoe je een PostScript‑document in C# maakt met Unicode‑tekst met
  behulp van Aspose.Page voor .NET – een snelle manier om documentmanipulatie te verbeteren.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: PostScript-document maken in C# met Unicode‑tekst – Aspose.Page
url: /nl/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tekst toevoegen met Unicode‑reeks aan PostScript (PS) met Aspose.Page

## Inleiding

Als je **een PostScript‑document in C# wilt maken** en Unicode‑tekens wilt insluiten, maakt Aspose.Page voor .NET het proces eenvoudig. In deze tutorial lopen we stap voor stap een volledig, praktisch voorbeeld door dat laat zien hoe je Japanse tekst (of elke Unicode‑reeks) aan een PS‑bestand toevoegt, een aangepast lettertype kiest en het resultaat opslaat. Aan het einde heb je een herbruikbare code‑snippet die je in elk C#‑project kunt gebruiken.

## Snelle antwoorden
- **Wat behandelt deze tutorial?** Unicode‑tekst toevoegen aan een PostScript‑bestand met Aspose.Page in C#.
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET (nieuwste versie).
- **Heb ik een speciaal lettertype nodig?** Elk TrueType/OpenType‑lettertype dat het gewenste Unicode‑bereik ondersteunt, bijv. *Arial Unicode MS*.
- **Hoeveel regels code?** Ongeveer 30 regels, verdeeld over duidelijke stappen.
- **Is een licentie nodig?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.

## Wat is “create postscript document c#”?
Een PostScript‑document maken in C# betekent programmatic een .ps‑bestand genereren dat voldoet aan de PostScript‑taalspecificaties. Aspose.Page abstraheert de low‑level details, zodat je je kunt concentreren op inhoud zoals tekst, grafische elementen en lettertypen.

## Waarom Aspose.Page gebruiken voor Unicode‑tekst?
- **Volledige Unicode‑ondersteuning** – renderen van tekens uit elke taal zonder handmatige codering.
- **Apparaatonafhankelijk** – dezelfde code werkt voor PS, EPS en PDF uitvoer.
- **Geen externe afhankelijkheden** – de bibliotheek behandelt lettertype‑laden en glyph‑mapping intern.

## Voorvereisten

- Basiskennis van C# en .NET‑ontwikkeling.
- Aspose.Page voor .NET‑bibliotheek geïnstalleerd. Je kunt deze downloaden via de [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Een map met de lettertypen die je wilt gebruiken (bijv. *Arial Unicode MS*).

## Namespaces importeren

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stap 1: Documentmap en lettertype‑map instellen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Stap 2: Uitvoerstream voor PostScript‑document maken

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Stap 3: Unicode‑tekst toevoegen met aangepast lettertype

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Stap 4: Huidige pagina sluiten

```csharp
document.ClosePage();
```

## Stap 5: Document voltooien en opslaan

```csharp
document.Save();
```

## Veelvoorkomende problemen en oplossingen

- **Lettertype niet gevonden** – Zorg ervoor dat het pad `AdditionalFontsFolders` wijst naar de map met de .ttf/.otf‑bestanden en dat de lettertype‑naam exact overeenkomt.
- **Vreemde tekens** – Controleer of de bronreeks is gecodeerd als UTF‑8 in je C#‑bronbestand (gebruik `#pragma warning disable 1591` indien nodig).
- **Bestand niet aangemaakt** – Controleer schrijfrechten op `dataDir` en zorg dat de stream correct wordt vrijgegeven (het `using`‑blok regelt dit).

## Veelgestelde vragen

**Q: Kan ik Aspose.Page voor .NET gebruiken met andere programmeertalen?**  
A: Aspose.Page is primair ontworpen voor .NET, maar er zijn Java‑equivalenten beschikbaar.

**Q: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Page voor .NET?**  
A: Bezoek [Temporary License](https://purchase.aspose.com/temporary-license/) voor het verkrijgen van een tijdelijke licentie.

**Q: Is er een community‑forum voor Aspose.Page‑discussies?**  
A: Ja, bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning.

**Q: Met welke formaten kan Aspose.Page voor .NET werken?**  
A: Aspose.Page ondersteunt diverse formaten, waaronder XPS, PS, EPS, PDF en meer.

**Q: Kan ik het uiterlijk van de toegevoegde tekst aanpassen?**  
A: Ja, je kunt het lettertype, de grootte, kleur en andere eigenschappen van de tekst aanpassen in Aspose.Page.

## Conclusie

In deze tutorial hebben we laten zien hoe je **een PostScript‑document in C# maakt** en Unicode‑tekst insluit met Aspose.Page. Door de bovenstaande stappen te volgen kun je snel meertalige tekstreproductie integreren in elke .NET‑applicatie, met volledige controle over documentgeneratie en lay‑out.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}