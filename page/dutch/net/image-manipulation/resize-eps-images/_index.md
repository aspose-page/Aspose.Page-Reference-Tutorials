---
date: 2026-03-03
description: Leer hoe u EPS‑afbeeldingen in .NET kunt schalen met Aspose.Page – een
  stap‑voor‑stap gids over hoe u EPS kunt schalen met punten, inches, millimeters
  of percentages.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Hoe EPS-afbeeldingen te verkleinen met Aspose.Page voor .NET
url: /nl/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe EPS‑afbeeldingen te schalen met Aspose.Page voor .NET

## Inleiding

Zoek je **hoe EPS‑afbeeldingen te schalen** op een naadloze manier met Aspose.Page voor .NET? Deze tutorial is jouw uitgebreide gids om moeiteloos de grootte van EPS‑afbeeldingen te manipuleren in verschillende eenheden zoals punten, inches, millimeters en percentages. Aspose.Page voor .NET biedt een krachtige set‑tools, en in deze tutorial lopen we stap voor stap het proces met je door.

## Snelle antwoorden
- **Welke bibliotheek behandelt EPS‑schaalvergroting?** Aspose.Page voor .NET  
- **Welke eenheden worden ondersteund?** Punten, Inches, Millimeters en Percentages  
- **Heb ik een licentie nodig voor productie?** Ja – een commerciële licentie is vereist  
- **Kan ik meerdere bestanden tegelijk schalen?** Absoluut – loop gewoon door de bestanden heen  
- **Wordt .NET Core ondersteund?** Ja, de API werkt met .NET Framework en .NET Core  

## Wat is EPS‑schaalvergroting?
Encapsulated PostScript (EPS) is een vector‑gebaseerd grafisch formaat dat veel wordt gebruikt in print‑ en design‑workflows. Het schalen van een EPS‑bestand wijzigt de omhullende box zonder de artwork te rasteren, waardoor de scherpte op elke schaal behouden blijft.

## Waarom EPS‑afbeeldingen schalen?
- **Printkwaliteit behouden:** Vector‑schaling houdt randen scherp.  
- **Aan layoutvereisten voldoen:** Pas afmetingen aan om te passen bij pagina‑ of canvasgroottes.  
- **Batchtaken automatiseren:** Programmeermatig tientallen bestanden in seconden schalen.  

## Voorvereisten

Voordat je in de magie van het schalen duikt, zorg ervoor dat je de volgende zaken klaar hebt staan:

- Aspose.Page voor .NET Library: Zorg ervoor dat je de Aspose.Page voor .NET‑bibliotheek geïnstalleerd hebt. Je kunt deze downloaden van [here](https://releases.aspose.com/page/net/).

- Documentmap: Maak een map aan waarin je je invoer‑EPS‑bestand en de uitgaande geschaalde bestanden opslaat.

Nu alles is ingesteld, gaan we de benodigde namespaces importeren en duiken we in de stap‑voor‑stap‑gids.

## Namespaces importeren

In je .NET‑project begin je met het importeren van de benodigde namespaces om met Aspose.Page te werken. Voeg de volgende code toe aan het begin van je bestand:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Hoe EPS te schalen in punten

Punten zijn een standaard meeteenheid in de drukindustrie. Het voorbeeld hieronder verdubbelt de oorspronkelijke breedte en hoogte.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Hoe EPS te schalen in inches

Inches worden vaak gebruikt door grafisch ontwerpers bij het voorbereiden van assets voor druk.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Hoe EPS te schalen in millimeters

Millimeters zijn gangbaar in regio’s die het metrische stelsel hanteren.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Hoe EPS te schalen met percentages

Schalen op basis van percentages laat je de afbeelding schalen ten opzichte van de oorspronkelijke grootte.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Voel je vrij om deze methoden in je project te integreren, en je zult EPS‑afbeeldingen moeiteloos kunnen schalen. Experimenteer met verschillende eenheden om de gewenste afmetingen te bereiken.

## Veelvoorkomende problemen en oplossingen
- **Bestand niet gevonden:** Controleer of `dataDir` naar de juiste map wijst en of `input.eps` bestaat.  
- **Onverwachte grootte:** Onthoud dat `Units.Percents` waarden verwacht zoals 150 voor 150 % van de oorspronkelijke grootte.  
- **Licentie‑exception:** Als je een licentiefout ziet, zorg dan dat een geldig Aspose.Page‑licentiebestand is geladen voordat je `PsDocument` maakt.

## Conclusie

Gefeliciteerd! Je hebt **hoe EPS‑afbeeldingen te schalen** onder de knie met Aspose.Page voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor het manipuleren van vector‑graphics. Of je nu ontwerpt voor print of digitale media, Aspose.Page stelt je in staat om nauwkeurige en gepersonaliseerde resultaten te behalen.

## Veelgestelde vragen

### Q1: Kan ik meerdere EPS‑afbeeldingen tegelijk schalen?

A1: Ja, je kunt door een collectie EPS‑bestanden itereren en de schaalmethoden toepassen.

### Q2: Is Aspose.Page compatibel met andere afbeeldingsformaten?

A2: Aspose.Page richt zich voornamelijk op PostScript‑ en EPS‑formaten. Voor andere formaten kun je overwegen Aspose.Imaging te gebruiken.

### Q3: Zijn er licentie‑overwegingen voor commerciële projecten?

A3: Ja, zorg voor een geldige licentie. Bezoek [here](https://purchase.aspose.com/buy) voor licentie‑details.

### Q4: Kan ik Aspose.Page eerst uitproberen voordat ik koop?

A4: Absoluut! Je kunt een gratis proefversie krijgen [here](https://releases.aspose.com/).

### Q5: Waar kan ik extra hulp vinden of problemen bespreken?

A5: Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) om contact te leggen met de community en assistentie te krijgen.

## Frequently Asked Questions

**Q: Werkt deze code met .NET Core 6?**  
A: Ja. De API is compatibel met .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ en .NET 6+.

**Q: Hoe kan ik het originele kleurprofiel behouden?**  
A: De `ResizeEps`‑methode wijzigt geen kleurgegevens; ze verandert alleen de omhullende box.

**Q: Is het mogelijk een EPS te schalen zonder het volledige bestand in het geheugen te laden?**  
A: Het gebruik van een stream zoals getoond houdt het geheugenverbruik laag; het document wordt on‑the‑fly verwerkt.

**Q: Kan ik meerdere schaalbewerkingen achter elkaar uitvoeren?**  
A: Absoluut. Roep `ResizeEps` opeenvolgend aan op dezelfde `PsDocument`‑instantie.

**Q: Wat gebeurt er met ingesloten afbeeldingen binnen de EPS?**  
A: Ze worden proportioneel geschaald met de vectorinhoud, waardoor de kwaliteit behouden blijft.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}