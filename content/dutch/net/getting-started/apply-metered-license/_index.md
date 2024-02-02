---
title: Pas een gemeten licentie toe met Aspose.Page voor .NET
linktitle: Pas een gemeten licentie toe
second_title: Aspose.Page .NET-API
description: Ontdek de naadloze integratie van Aspose.Page voor .NET met deze stapsgewijze handleiding voor het toepassen van een gemeten licentie. Optimaliseer documentverwerking moeiteloos.
type: docs
weight: 10
url: /nl/net/getting-started/apply-metered-license/
---
## Invoering

Ontgrendel het volledige potentieel van Aspose.Page voor .NET door een gemeten licentie toe te passen. Deze tutorial leidt u door het proces van het instellen en toepassen van de gemeten licentie, waardoor een soepel en geoptimaliseerd gebruik van deze krachtige .NET-bibliotheek wordt gegarandeerd.

## Vereisten

Voordat u in de stappen duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Een geldige Aspose.Page voor .NET-licentie: u kunt deze verkrijgen via[aankoop.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page-bibliotheek geïnstalleerd: Raadpleeg de[documentatie](https://reference.aspose.com/page/net/) voor installatie-instructies.
- .NET-ontwikkelomgeving: Zorg ervoor dat er een werkende .NET-omgeving op uw computer is geïnstalleerd.

## Naamruimten importeren

Importeer in uw .NET-project de benodigde naamruimten om toegang te krijgen tot de Aspose.Page-functionaliteiten:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Stap 1: Stel gemeten openbare en privésleutels in

 Initialiseer de`Aspose.Page.Metered` class en stel de gemeten publieke en private sleutels in. Vervangen`<type public key here>` En`<type private key here>` met uw echte sleutels.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Stap 2: Laad het EPS-bestand en maak een document

 Geef het pad naar uw EPS-bestand op en maak een stream om de inhoud ervan te lezen. Maak vervolgens een exemplaar van de`PsDocument` klasse uit de stroom.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Stap 3: Converteer EPS naar PNG-afbeelding

 Creëer een`ImageDevice` voor het converteren van het EPS-bestand naar een PNG-afbeelding. Sla het EPS-bestand op als afbeelding met behulp van de`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Stap 4: Afbeeldingsbytes ophalen

Haal de afbeeldingsbytes op, waarbij elke byte-array één pagina vertegenwoordigt. In dit geval hebben we één pagina.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Stap 5: Afbeeldingsbytes opslaan in bestand

Sla de afbeeldingsbytes op in een bestand, zodat u verzekerd bent van een succesvolle conversie van EPS naar PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Stap 6: Controleer de gemeten licentie

Controleer visueel of de gemeten licentie succesvol is toegepast. Als de resulterende afbeelding het rode evaluatiebericht niet bevat, geeft dit aan dat de gemeten licentie zonder problemen wordt toegepast.

Nu bent u klaar om de volledige mogelijkheden van Aspose.Page voor .NET te benutten met een gemeten licentie!

## Conclusie

Met deze stapsgewijze handleiding beschikt u over de kennis om naadloos een gemeten licentie toe te passen met Aspose.Page voor .NET. Verbeter uw documentverwerkingsmogelijkheden en ontdek de uitgebreide functies die deze krachtige bibliotheek biedt.

## Veelgestelde vragen

### V1: Hoe verkrijg ik een gemeten licentie voor Aspose.Page voor .NET?

 A1: Bezoek[aankoop.aspose.com](https://purchase.aspose.com/buy) om een geldige licentie te verkrijgen.

### V2: Waar kan ik de documentatie voor Aspose.Page voor .NET vinden?

 A2: Raadpleeg[Aspose.Pagina .NET](https://reference.aspose.com/page/net/) voor uitgebreide documentatie.

### V3: Is er een forum voor Aspose.Page-discussies en ondersteuning?

 A3: Ja, bezoek[forum](https://forum.aspose.com/c/page/39) om met de gemeenschap in contact te komen en hulp te zoeken.

### V4: Kan ik Aspose.Page voor .NET uitproberen voordat ik een aankoop doe?

 A4: Absoluut! Ga naar de gratis proefperiode op[hier](https://releases.aspose.com/).

### V5: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor .NET?

 A5: Bezoek[tijdelijke licentie/](https://purchase.aspose.com/temporary-license/) om een tijdelijke vergunning te verkrijgen.