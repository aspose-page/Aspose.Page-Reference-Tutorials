---
title: Wijzig de benoemde waarde met Aspose.Page voor .NET
linktitle: Wijzig de benoemde waarde
second_title: Aspose.Page .NET-API
description: Leer hoe u benoemde waarden in EPS-bestanden kunt wijzigen met Aspose.Page voor .NET. Pas XMP-metadata moeiteloos aan voor documentverwerking op maat.
weight: 16
url: /nl/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wijzig de benoemde waarde met Aspose.Page voor .NET

## Invoering

In de wereld van documentverwerking onderscheidt Aspose.Page voor .NET zich als een krachtig hulpmiddel voor het manipuleren van EPS-bestanden. Een van de belangrijkste functionaliteiten die het biedt, is de mogelijkheid om benoemde waarden binnen XMP-metagegevens te wijzigen. Deze tutorial leidt u door het proces van het wijzigen van een benoemde waarde met Aspose.Page voor .NET, waardoor u uw EPS-bestanden kunt aanpassen aan uw specifieke behoeften.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET: Zorg ervoor dat de Aspose.Page voor .NET-bibliotheek is geïnstalleerd. Zo niet, dan kunt u deze downloaden[hier](https://releases.aspose.com/page/net/).

- Documentmap: Zorg voor een aangewezen map voor uw EPS-bestanden waar u de benoemde waardewijzigingen kunt uitvoeren.

## Naamruimten importeren

In uw .NET-project moet u de benodigde naamruimten importeren om toegang te krijgen tot de functionaliteit van Aspose.Page. Voeg de volgende naamruimten toe aan uw code:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Laten we de code nu in meerdere stappen opsplitsen voor een uitgebreid begrip:

## Stap 1: Initialiseer de EPS-bestandsinvoerstroom

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// Verlengen: 1
```

In deze stap stellen we de invoerstroom in voor het EPS-bestand dat u wilt wijzigen. Zorg ervoor dat u "Uw documentenmap" vervangt door het daadwerkelijke pad naar uw documentmap.

## Stap 2: XMP-metagegevens ophalen

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Haal de bestaande XMP-metagegevens op uit het EPS-bestand. Als het EPS-bestand geen XMP-metagegevens bevat, wordt er een nieuw bestand gegenereerd met waarden uit opmerkingen over PS-metagegevens.

## Stap 3: Wijzig XMP-metagegevenswaarden

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Hier demonstreren we het wijzigen van twee benoemde waarden binnen de structuur "xmpTPg:MaxPageSize". U kunt dit aanpassen aan uw specifieke wensen.

## Stap 4: Bewaar het EPS-bestand met gewijzigde XMP-metagegevens

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Sla het gewijzigde EPS-bestand op in de uitvoerstream. Het bestand weerspiegelt nu de wijzigingen die zijn aangebracht in de XMP-metagegevens.

## Conclusie

Met deze zelfstudie hebt u geleerd hoe u Aspose.Page voor .NET kunt gebruiken om benoemde waarden in XMP-metagegevens in EPS-bestanden te wijzigen. Deze functionaliteit opent een wereld aan mogelijkheden voor het aanpassen en afstemmen van uw documenten op specifieke vereisten.

## Veelgestelde vragen

### V1: Kan ik Aspose.Page voor .NET gebruiken met andere documentformaten?

A1: Ja, Aspose.Page ondersteunt verschillende documentformaten, waaronder EPS, XPS en PDF.

### V2: Is er een proefversie beschikbaar voor Aspose.Page voor .NET?

 A2: Ja, u heeft toegang tot een gratis proefperiode[hier](https://releases.aspose.com/).

### V3: Waar kan ik meer documentatie vinden over Aspose.Page voor .NET?

 A3: Raadpleeg de documentatie[hier](https://reference.aspose.com/page/net/).

### V4: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page voor .NET?

 A4: U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).

### V5: Welke ondersteuningsopties zijn beschikbaar voor Aspose.Page voor .NET-gebruikers?

 A5: Bezoek het communityforum[hier](https://forum.aspose.com/c/page/39) voor ondersteuning en discussies.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
