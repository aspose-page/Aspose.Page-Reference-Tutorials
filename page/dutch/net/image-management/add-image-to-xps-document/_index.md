---
date: 2026-02-28
description: Leer hoe u een XPS‑document maakt in .NET en een afbeelding toevoegt
  met Aspose.Page voor .NET. Volg deze stapsgewijze handleiding voor een soepele ontwikkelervaring.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: XPS-document maken met .NET – Afbeelding toevoegen met Aspose.Page
url: /nl/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Afbeelding toevoegen aan XPS-document met Aspose.Page voor .NET

In deze tutorial leer je hoe je **create XPS document .NET** maakt en een afbeelding insluit met de krachtige Aspose.Page bibliotheek. Of je nu rapporten, facturen of aangepaste grafieken genereert, het toevoegen van visuele elementen aan XPS‑bestanden is een veelvoorkomende vereiste voor .NET‑ontwikkelaars.

## Introductie

In de wereld van .NET‑ontwikkeling is het opnemen van afbeeldingen in XPS‑documenten een veelvoorkomende vereiste. Aspose.Page voor .NET vereenvoudigt dit proces en biedt een krachtig gereedschap om XPS‑documenten moeiteloos te manipuleren en te verbeteren. Deze tutorial leidt je door de stappen om een afbeelding toe te voegen aan een XPS‑document met Aspose.Page voor .NET.

## Snelle antwoorden
- **Wat behandelt deze tutorial?** Een afbeelding toevoegen aan een XPS‑document met Aspose.Page voor .NET.  
- **Welk primair zoekwoord wordt getarget?** *create xps document .net*  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar; een licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** Werkt met .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een eenvoudige afbeeldinginvoeging.

## Wat is “create XPS document .NET”?

Een XPS‑document maken in .NET betekent het programmatisch genereren van een XML Paper Specification (XPS)‑bestand — een vast‑indelingsdocumentformaat — met C# of VB.NET. Aspose.Page biedt een vloeiende API die de low‑level details abstraheert, zodat je je kunt concentreren op inhoud zoals tekst, vormen en afbeeldingen.

## Waarom Aspose.Page gebruiken om een afbeelding toe te voegen?

- **Volledige controle** over positionering, schaalvergroting en bijsnijden van afbeeldingen.  
- **Geen externe afhankelijkheden** – de bibliotheek verwerkt afbeeldingsdecodering intern.  
- **Cross‑platform** ondersteuning voor Windows- en Linux‑omgevingen.  
- **Hoge getrouwheid** rendering die de beeldkwaliteit behoudt in het uiteindelijke XPS‑bestand.

## Voorvereisten

Voordat je aan de tutorial begint, zorg ervoor dat je de volgende voorvereisten hebt:

1. Aspose.Page for .NET Library: Download en installeer de bibliotheek vanaf [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).

2. Ontwikkelomgeving: Stel een .NET‑ontwikkelomgeving in, zoals Visual Studio.

3. Voorbeeldafbeelding: Zorg voor een voorbeeldafbeeldingsbestand (bijv. "QL_logo_color.tif") dat je aan het XPS‑document wilt toevoegen.

## Namespaces importeren

Begin met het importeren van de benodigde namespaces in je .NET‑project. Deze namespaces zijn essentieel om de functies van Aspose.Page voor .NET te gebruiken.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page afbeelding toevoegen aan XPS-document

Hieronder lopen we stap voor stap door elke stap die nodig is om **create XPS document .NET** te maken en een afbeelding in te sluiten.

### Stap 1: Documentmap instellen

Begin met het opgeven van het pad naar je documentmap. Deze stap zorgt ervoor dat je project weet waar bestanden te vinden en op te slaan.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Stap 2: XPS-document maken

Maak een nieuw XPS‑document met Aspose.Page voor .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Stap 3: Afbeelding toevoegen aan XPS-document

Laten we nu de afbeelding toevoegen aan het XPS‑document. In dit voorbeeld gebruiken we een voorbeeldafbeelding met de naam "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Stap 4: Resulterend XPS-document opslaan

Sla het XPS‑document op met de toegevoegde afbeelding.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Nu heb je met succes een afbeelding toegevoegd aan een XPS‑document met Aspose.Page voor .NET!

## Veelvoorkomende problemen en oplossingen

- **File not found error** – Controleer of `dataDir` naar de juiste map wijst en of de bestandsnaam van de afbeelding exact overeenkomt, inclusief hoofdlettergevoeligheid op Linux.  
- **Image appears distorted** – Pas de schaalfactoren van `CreateMatrix` of de parameters van `RectangleF` aan om grootte en beeldverhouding te regelen.  
- **Unsupported image format** – Aspose.Page ondersteunt gangbare rasterformaten (PNG, JPEG, TIFF). Converteer niet‑ondersteunde formaten voordat je `CreateImageBrush` gebruikt.

## Veelgestelde vragen

### Q1: Is Aspose.Page for .NET compatibel met de nieuwste .NET‑frameworkversies?

A1: Aspose.Page for .NET is ontworpen om compatibel te zijn met een breed scala aan .NET‑frameworkversies, inclusief de nieuwste releases. Raadpleeg de [documentation](https://reference.aspose.com/page/net/) voor specifieke details.

### Q2: Kan ik Aspose.Page for .NET gebruiken in zowel Windows- als Linux-omgevingen?

A2: Ja, Aspose.Page for .NET is platform‑independent, waardoor het geschikt is voor gebruik in zowel Windows- als Linux‑omgevingen.

### Q3: Zijn er licentieopties voor Aspose.Page for .NET?

A3: Ja, je kunt licentieopties verkennen en een aankoop doen [hier](https://purchase.aspose.com/buy).

### Q4: Is er een gratis proefversie beschikbaar voor Aspose.Page for .NET?

A4: Ja, je kunt Aspose.Page for .NET gratis uitproberen door de [free trial](https://releases.aspose.com/) te bezoeken.

### Q5: Waar kan ik hulp zoeken of contact opnemen met de community voor Aspose.Page for .NET?

A5: Bezoek het [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) om contact te maken met de community en ondersteuning te krijgen.

## Conclusie

In deze tutorial hebben we onderzocht hoe je Aspose.Page voor .NET kunt benutten om naadloos afbeeldingen in XPS‑documenten te integreren. Deze stap‑voor‑stap‑gids zorgt voor een soepel integratieproces, verbetert je .NET‑ontwikkelcapaciteiten en helpt je **create XPS document .NET**‑oplossingen te realiseren met visuele rijkdom.

---

**Laatst bijgewerkt:** 2026-02-28  
**Getest met:** Aspose.Page for .NET 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}