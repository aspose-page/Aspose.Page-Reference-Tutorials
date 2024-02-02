---
title: Wijzig waarden met Aspose.Page voor .NET
linktitle: Verander waarden
second_title: Aspose.Page .NET-API
description: Beheers de manipulatie van EPS-bestanden met Aspose.Page voor .NET. Wijzig moeiteloos de waarden van XMP-metagegevens.
type: docs
weight: 17
url: /nl/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## Invoering

In de dynamische wereld van documentverwerking onderscheidt Aspose.Page voor .NET zich als een krachtig hulpmiddel, dat ontwikkelaars de mogelijkheid biedt om moeiteloos EPS-bestanden te manipuleren. In deze zelfstudie gaan we dieper in op het proces van het wijzigen van waarden in EPS-bestanden met behulp van Aspose.Page voor .NET. Of u nu een doorgewinterde ontwikkelaar of een nieuwsgierige beginner bent, deze stapsgewijze handleiding zal u voorzien van de vaardigheden die nodig zijn om XMP-metagegevens efficiënt aan te passen in uw EPS-bestanden.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:

### 1. Aspose.Page voor .NET-bibliotheek

Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek in uw ontwikkelomgeving is geïnstalleerd. Zo niet, dan kunt u deze downloaden[hier](https://releases.aspose.com/page/net/).

### 2. Documentmap

Stel een map in voor uw documenten. Dit is de locatie waar uw EPS-bestanden worden opgeslagen.

Nu we onze vereisten op orde hebben, gaan we verder met de volgende cruciale stappen.

## Naamruimten importeren

In elk .NET-project is het essentieel om de benodigde naamruimten te importeren om de functionaliteiten van Aspose.Page te kunnen gebruiken. Hier ziet u hoe u het kunt doen:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Stap 1: Initialiseer de invoerstroom van het EPS-bestand

```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Initialiseer de invoerstroom van EPS-bestanden
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Stap 2: Maak een PsDocument-instantie uit de stream

```csharp
//Maak een PsDocument-instantie vanuit de stream
PsDocument document = new PsDocument(psStream);
```

Nu we de basis hebben gelegd, gaan we verder met de kern van onze tutorial: het wijzigen van XMP-metagegevenswaarden in het EPS-bestand.

## Stap 3: Verkrijg XMP-metagegevens

```csharp
// XMP-metagegevens ophalen. Als het EPS-bestand geen XMP-metagegevens bevat, krijgen we een nieuwe gevuld met waarden uit PS-metagegevensopmerkingen (%%Creator, %%CreateDate, %%Title, enz.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Stap 4: Wijzig de XMP-metagegevenswaarden

Laten we nu enkele sleutelwaarden in de XMP-metagegevens wijzigen:

### Stap 4.1: Wijzig de ModifyDate-waarde

```csharp
// Wijzig de ModifyDate-waarde
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Stap 4.2: Wijzig de Creator-waarde

```csharp
// Wijzig de Creator-waarde
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Stap 4.3: Titelwaarde wijzigen

```csharp
// Titelwaarde wijzigen
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Nu deze wijzigingen zijn aangebracht, gaan we verder met de laatste stap: het gewijzigde EPS-bestand opslaan.

## Stap 5: Sla het EPS-bestand op met gewijzigde XMP-metagegevens

### Stap 5.1: Maak een uitvoerstroom

```csharp
// Maak een uitvoerstroom
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Stap 5.2: EPS-bestand opslaan

```csharp
// EPS-bestand opslaan
document.Save(outPsStream);
```

Sluit ten slotte de invoerstroom:

```csharp
finally
{
    psStream.Close();
}
```

Gefeliciteerd! U hebt met succes XMP-metagegevenswaarden in een EPS-bestand gewijzigd met Aspose.Page voor .NET.

## Conclusie

In deze zelfstudie hebben we het naadloze proces van het wijzigen van waarden in EPS-bestanden onderzocht met behulp van Aspose.Page voor .NET. Als ontwikkelaar beschikt u nu over een krachtig hulpmiddel voor efficiënte documentmanipulatie.

## Veelgestelde vragen

### V1: Kan ik Aspose.Page voor .NET gebruiken met andere bestandsindelingen?

A1: Aspose.Page richt zich voornamelijk op het manipuleren van EPS-bestanden. Voor andere formaten kunt u het gevarieerde productassortiment van Aspose verkennen.

### Vraag 2: Is er een proefversie beschikbaar?

 A2: Ja, u kunt Aspose.Page voor .NET uitproberen met de gratis proefversie die beschikbaar is[hier](https://releases.aspose.com/).

### Vraag 3: Waar kan ik gedetailleerde documentatie vinden?

 A3: De uitgebreide documentatie is te vinden[hier](https://reference.aspose.com/page/net/).

### Vraag 4: Hoe verkrijg ik een tijdelijke licentie?

 A4: U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).

### V5: Kan ik Aspose.Page voor .NET kopen?

 A5: Absoluut! Bezoek de aankooppagina[hier](https://purchase.aspose.com/buy) voor licentiemogelijkheden.