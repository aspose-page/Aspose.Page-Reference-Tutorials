---
title: Voeg afbeelding toe aan XPS-document met Aspose.Page voor .NET
linktitle: Afbeelding toevoegen aan XPS-document
second_title: Aspose.Page .NET-API
description: Ontdek de naadloze integratie van afbeeldingen in XPS-documenten met Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor een soepele ontwikkelingservaring.
weight: 11
url: /nl/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg afbeelding toe aan XPS-document met Aspose.Page voor .NET

## Invoering

In de wereld van .NET-ontwikkeling is het opnemen van afbeeldingen in XPS-documenten een veel voorkomende vereiste. Aspose.Page voor .NET vereenvoudigt dit proces en biedt een krachtige toolkit om XPS-documenten moeiteloos te manipuleren en te verbeteren. In deze zelfstudie wordt u door de stappen geleid voor het toevoegen van een afbeelding aan een XPS-document met behulp van Aspose.Page voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Page voor .NET Library: Download en installeer de bibliotheek van[Aspose.Page .NET-documentatie](https://reference.aspose.com/page/net/).

2. Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op, zoals Visual Studio.

3. Voorbeeldafbeelding: zorg dat u een voorbeeldafbeeldingsbestand hebt (bijvoorbeeld "QL_logo_color.tif") dat u aan het XPS-document wilt toevoegen.

## Naamruimten importeren

Begin met het importeren van de benodigde naamruimten in uw .NET-project. Deze naamruimten zijn essentieel voor het gebruik van de functies van Aspose.Page voor .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Stap 1: Documentmap instellen

Begin met het opgeven van het pad naar uw documentmap. Deze stap zorgt ervoor dat uw project weet waar bestanden moeten worden gevonden en opgeslagen.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// Verlengen: 1
```

## Stap 2: Maak een XPS-document

Maak een nieuw XPS-document met Aspose.Page voor .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// Verlengen: 1
```

## Stap 3: Afbeelding toevoegen aan XPS-document

Laten we nu de afbeelding toevoegen aan het XPS-document. In dit voorbeeld gebruiken we een voorbeeldafbeelding met de naam "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// Verlengen: 1
```

## Stap 4: Bewaar het resulterende XPS-document

Sla het XPS-document op met de toegevoegde afbeelding.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// Verlengen: 1
```

Nu hebt u met succes een afbeelding aan een XPS-document toegevoegd met Aspose.Page voor .NET!

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u Aspose.Page voor .NET kunt gebruiken om afbeeldingen naadloos in XPS-documenten op te nemen. Deze stapsgewijze handleiding zorgt voor een soepel integratieproces, waardoor uw .NET-ontwikkelingsmogelijkheden worden vergroot.

## Veelgestelde vragen

### V1: Is Aspose.Page voor .NET compatibel met de nieuwste .NET-frameworkversies?

 A1: Aspose.Page voor .NET is ontworpen om compatibel te zijn met een breed scala aan .NET-frameworkversies, inclusief de nieuwste releases. Verwijs naar de[documentatie](https://reference.aspose.com/page/net/) voor specifieke details.

### V2: Kan ik Aspose.Page voor .NET gebruiken in zowel Windows- als Linux-omgevingen?

A2: Ja, Aspose.Page voor .NET is platformonafhankelijk, waardoor het geschikt is voor gebruik in zowel Windows- als Linux-omgevingen.

### V3: Zijn er licentieopties voor Aspose.Page voor .NET?

 A3: Ja, u kunt licentieopties verkennen en een aankoop doen[hier](https://purchase.aspose.com/buy).

### V4: Is er een gratis proefversie beschikbaar voor Aspose.Page voor .NET?

 A4: Ja, u kunt Aspose.Page voor .NET gratis uitproberen door naar de[gratis proefperiode](https://releases.aspose.com/).

### V5: Waar kan ik hulp zoeken of contact opnemen met de community voor Aspose.Page voor .NET?

 A5: Bezoek de[Aspose.Page voor .NET-forum](https://forum.aspose.com/c/page/39) om verbinding te maken met de gemeenschap en steun te krijgen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
