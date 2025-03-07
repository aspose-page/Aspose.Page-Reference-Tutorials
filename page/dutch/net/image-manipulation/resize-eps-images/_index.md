---
title: Wijzig het formaat van EPS-afbeeldingen met Aspose.Page voor .NET
linktitle: Formaat van EPS-afbeeldingen wijzigen
second_title: Aspose.Page .NET-API
description: Ontdek het naadloze proces van het wijzigen van het formaat van EPS-afbeeldingen in .NET met behulp van Aspose.Page. Bereik moeiteloos precisie in punten, inches, millimeters en percentages.
weight: 11
url: /nl/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wijzig het formaat van EPS-afbeeldingen met Aspose.Page voor .NET

## Invoering

Wilt u het formaat van EPS-afbeeldingen naadloos wijzigen met Aspose.Page voor .NET? Deze tutorial is uw uitgebreide gids om moeiteloos de grootte van EPS-afbeeldingen te manipuleren in verschillende eenheden, zoals punten, inches, millimeters en percentages. Aspose.Page voor .NET biedt een krachtige set tools, en in deze zelfstudie leiden we u stap voor stap door het proces.

## Vereisten

Voordat je in de magie van het vergroten/verkleinen duikt, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/page/net/).

- Documentmap: maak een map waarin u uw invoer-EPS-bestand en uitvoerbestanden met gewijzigd formaat opslaat.

Nu je alles hebt ingesteld, gaan we verder met het importeren van de benodigde naamruimten en verdiepen we ons in de stapsgewijze handleiding.

## Naamruimten importeren

Begin in uw .NET-project met het importeren van de benodigde naamruimten om met Aspose.Page te werken. Voeg de volgende code toe aan het begin van uw bestand:

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

## Stap 1: Formaat wijzigen in punten

Laten we beginnen met het in punten vergroten of verkleinen van een EPS-afbeelding. Punten zijn een standaard meeteenheid in de grafische industrie.

```csharp
public static void ResizeInPoints()
{
    // Uw documentenmap
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

## Stap 2: Formaat wijzigen in inches

Laten we nu het formaat van een EPS-afbeelding wijzigen in inches, een gebruikelijke eenheid die wordt gebruikt in grafisch ontwerp.

```csharp
public static void ResizeInInches()
{
    // Uw documentenmap
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

## Stap 3: Formaat wijzigen in millimeters

Laten we nu het formaat van een EPS-afbeelding in millimeters wijzigen, een andere veelgebruikte eenheid bij ontwerp en afdrukken.

```csharp
public static void ResizeInMillimeters()
{
    // Uw documentenmap
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

## Stap 4: Formaat wijzigen in procenten

Laten we ten slotte het formaat van een EPS-afbeelding wijzigen met behulp van percentages, zodat we een flexibele benadering krijgen om de afbeeldingsgrootte aan te passen.

```csharp
public static void ResizeInPercents()
{
    // Uw documentenmap
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

Voel je vrij om deze methoden in je project te integreren, zodat je de grootte van EPS-afbeeldingen moeiteloos kunt aanpassen. Experimenteer met verschillende eenheden om de gewenste afmetingen te bereiken.

## Conclusie

Gefeliciteerd! U beheerst de kunst van het wijzigen van het formaat van EPS-afbeeldingen met Aspose.Page voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor het manipuleren van vectorafbeeldingen. Of u nu ontwerpt voor gedrukte of digitale media, met Aspose.Page kunt u nauwkeurige en op maat gemaakte resultaten bereiken.

## Veelgestelde vragen

### Vraag 1: Kan ik het formaat van meerdere EPS-afbeeldingen tegelijk wijzigen?

A1: Ja, u kunt een verzameling EPS-bestanden doorlopen en de methoden voor het wijzigen van de grootte dienovereenkomstig toepassen.

### V2: Is Aspose.Page compatibel met andere afbeeldingsformaten?

A2: Aspose.Page richt zich voornamelijk op PostScript- en EPS-formaten. Voor andere afbeeldingsformaten kunt u overwegen Aspose.Imaging te gebruiken.

### Vraag 3: Zijn er licentieoverwegingen voor commerciële projecten?

 A3: Ja, zorg ervoor dat u over een geldige licentie beschikt. Bezoek[hier](https://purchase.aspose.com/buy) voor licentiegegevens.

### V4: Kan ik Aspose.Page uitproberen voordat ik een aankoop doe?

 A4: Absoluut! U kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).

### Vraag 5: Waar kan ik aanvullende hulp zoeken of problemen bespreken?

 A5: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) om verbinding te maken met de gemeenschap en hulp te krijgen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
