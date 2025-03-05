---
title: Voeg eenvoudige eigenschappen toe met Aspose.Page voor .NET
linktitle: Voeg eenvoudige eigenschappen toe
second_title: Aspose.Page .NET-API
description: Verbeter EPS-bestanden met Aspose.Page voor .NET. Voeg moeiteloos eenvoudige eigenschappen toe voor aangepaste documentmetagegevens.
type: docs
weight: 14
url: /nl/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Invoering

Op het gebied van documentmanipulatie en -verbetering ontpopt Aspose.Page voor .NET zich als een krachtig hulpmiddel, dat ontwikkelaars de mogelijkheid biedt om naadloos XMP-metagegevens binnen EPS-bestanden toe te voegen en te wijzigen. Deze tutorial begeleidt u bij het toevoegen van eenvoudige eigenschappen aan een EPS-bestand met behulp van Aspose.Page voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Page voor .NET: Zorg ervoor dat Aspose.Page voor .NET in uw ontwikkelomgeving is geïnstalleerd. Zo niet, dan kunt u deze downloaden[hier](https://releases.aspose.com/page/net/).

2.  Documentmap: stel een map in om uw EPS-bestanden op te slaan. Update de`dataDir` variabele in het opgegeven codefragment met het pad naar uw documentmap.

## Naamruimten importeren

Importeer om te beginnen de benodigde naamruimten om communicatie met Aspose.Page voor .NET mogelijk te maken. Voeg de volgende regels toe aan het begin van uw codebestand:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Stap 1: Initialiseer de EPS-bestandsinvoerstroom

```csharp
// ExStart:1
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Initialiseer de invoerstroom van EPS-bestanden
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Maak een PsDocument-instantie vanuit de stream
PsDocument document = new PsDocument(psStream);
```

## Stap 2: XMP-metagegevens ophalen

```csharp
// XMP-metagegevens ophalen. Als het EPS-bestand geen XMP-metagegevens bevat, krijgen we een nieuwe gevuld met waarden uit PS-metagegevensopmerkingen (%%Creator, %%CreateDate, %%Title, enz.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Stap 3: Wijzig XMP-metagegevenswaarden

```csharp
// Wijzig XMP-metagegevenswaarden
DateTime now = DateTime.UtcNow;

// Eigenschap Integer toevoegen
xmp.Add("xmp:Intg1", new XmpValue(111));

// Voeg de DateTime-eigenschap toe
xmp.Add("xmp:Date1", new XmpValue(now));

// Dubbele eigenschap toevoegen
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//String-eigenschap toevoegen
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Stap 4: Bewaar het EPS-bestand met gewijzigde XMP-metagegevens

```csharp
// Sla een EPS-bestand op met gewijzigde XMP-metagegevens

// Maak een uitvoerstroom
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS-bestand opslaan
    document.Save(outPsStream);
}
```

## Stap 5: Sluit FileStream

```csharp
finally
{
    psStream.Close();
}
```

Door deze stappen te volgen, kunt u moeiteloos eenvoudige eigenschappen in uw EPS-bestanden opnemen met behulp van Aspose.Page voor .NET.

## Conclusie

Concluderend blijkt Aspose.Page voor .NET van onschatbare waarde te zijn voor ontwikkelaars die EPS-bestanden willen verbeteren met aangepaste XMP-metagegevens. Door eenvoudige eigenschappen toe te voegen, kunt u uw documenten aanpassen en verrijken om aan specifieke vereisten te voldoen, waardoor er een wereld aan mogelijkheden voor documentmanipulatie opengaat.

## Veelgestelde vragen

### V1: Is Aspose.Page voor .NET compatibel met alle EPS-bestanden?

A1: Aspose.Page voor .NET ondersteunt een breed scala aan EPS-bestanden. De compatibiliteit kan echter variëren, afhankelijk van de complexiteit en structuur van individuele bestanden.

### V2: Kan ik bestaande XMP-metagegevens wijzigen met Aspose.Page voor .NET?

A2: Absoluut! Zoals gedemonstreerd in deze tutorial, kunt u eenvoudig bestaande XMP-metagegevenswaarden wijzigen of nieuwe toevoegen om aan uw behoeften te voldoen.

### V3: Zijn er beperkingen aan de typen eigenschappen die ik kan toevoegen?

A3: Aspose.Page voor .NET ondersteunt verschillende gegevenstypen voor eigenschappen, waaronder gehele getallen, datums, dubbele getallen en tekenreeksen. U heeft flexibiliteit bij het kiezen van het juiste type voor uw metadata.

### V4: Hoe kan ik technische ondersteuning krijgen voor Aspose.Page voor .NET?

 A4: Bezoek voor technische ondersteuning de[Aspose.Pagina-forum](https://forum.aspose.com/c/page/39) of verken de[documentatie](https://reference.aspose.com/page/net/) voor uitgebreide begeleiding.

### V5: Is er een gratis proefversie beschikbaar voor Aspose.Page voor .NET?

 A5: Ja, u heeft toegang tot een gratis proefperiode[hier](https://releases.aspose.com/).