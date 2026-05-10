---
date: 2026-02-23
description: Leer hoe u diagonale gradient‑XPS‑documenten maakt met Aspose.Page voor
  .NET en til uw visuele presentaties moeiteloos naar een hoger niveau.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Diagonale gradient XPS maken met Aspose.Page voor .NET
url: /nl/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Diagonale Gradient XPS met Aspose.Page voor .NET

## Inleiding

Als je **diagonale gradient XPS**‑bestanden wilt maken die de aandacht trekken, maakt Aspose.Page voor .NET het eenvoudig. In deze tutorial leer je stap voor stap hoe je een diagonale gradient toevoegt aan een XPS‑document met behulp van de Aspose.Page API. Aan het einde heb je een herbruikbaar patroon dat je kunt aanpassen aan elke vorm of kleurenpalet.

## Snelle Antwoorden
- **Wat doet de API‑methode?** Het maakt een lineaire gradient‑kwast die diagonaal over een pad loopt.  
- **Welke klasse vertegenwoordigt het XPS‑document?** `XpsDocument`.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Kan ik de gradientrichting wijzigen?** Ja—pas de start‑ en eind‑`PointF`‑waarden aan.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is **create diagonal gradient xps**?
Een diagonale gradient is een vloeiende kleurovergang die van de ene hoek van een vorm naar de tegenoverliggende hoek loopt. In XPS wordt dit effect bereikt door een `LinearGradientBrush` toe te passen op de vul‑eigenschap van een pad. De Aspose.Page‑bibliotheek abstraheert de low‑level XPS‑markup, zodat je je kunt concentreren op kleuren en geometrie.

## Waarom Aspose.Page gebruiken voor diagonale gradients?
- **High‑fidelity rendering** – de output komt exact overeen met de XPS‑specificatie.  
- **Volledige .NET‑integratie** – werkt met C#, VB.NET en elke .NET‑taal.  
- **Geen externe afhankelijkheden** – alles wordt in‑process afgehandeld, geen COM of Office nodig.  
- **Schaalbaar naar complexe documenten** – je kunt meerdere gradients, afbeeldingen en tekst op dezelfde pagina combineren.

## Voorvereisten

1. **Aspose.Page for .NET Library** – download het [hier](https://releases.aspose.com/page/net/).  
2. **Ontwikkelomgeving** – Visual Studio, Rider of elke editor die .NET‑projecten ondersteunt.  

Laten we nu in de code duiken.

## Namespaces Importeren

In je .NET‑project moet je de benodigde namespaces van de Aspose.Page‑bibliotheek opnemen om toegang te krijgen tot de vereiste klassen en methoden. Voeg de volgende namespaces toe aan het begin van je code:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Stap 1: Documentmap Instellen

Begin met het specificeren van het pad naar je documentmap. Dit is waar het resulterende XPS‑document met de diagonale gradient wordt opgeslagen.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Stap 2: Een Nieuw XPS‑Document Maken

Initialiseer een nieuw `XpsDocument` met behulp van de Aspose.Page‑bibliotheek.

```csharp
XpsDocument doc = new XpsDocument();
```

## Stap 3: Gradientkleuren Definiëren

Maak een lijst van `XpsGradientStop`‑objecten, elk representerend een kleur in de diagonale gradient.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Stap 4: Een Diagonale Gradient Aan Een Pad Toevoegen

Maak een nieuw pad met een gedefinieerde geometrie en pas de diagonale gradient erop toe. Pas de rendering‑transformatie en vul‑eigenschappen naar behoefte aan.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Stap 5: Het Resulterende XPS‑Document Opslaan

Sla tenslotte het gewijzigde XPS‑document op in de opgegeven map.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Je hebt nu succesvol een **diagonale gradient XPS**‑bestand gemaakt. Voel je vrij om te experimenteren met verschillende kleurstops, geometrie‑strings of transformaties om een verscheidenheid aan visuele effecten te produceren.

## Veelvoorkomende Problemen en Oplossingen
- **Gradient niet zichtbaar** – Controleer of de padgeometrie gesloten is en of de start‑/eindpunten van de kwast binnen de padgrenzen liggen.  
- **Onjuiste kleuren** – Zorg ervoor dat je `CreateColor` gebruikt met de juiste ARGB‑waarden; de methode verwacht waarden in het bereik 0‑255.  
- **Bestand niet opgeslagen** – Controleer of `dataDir` naar een bestaande map wijst en of de applicatie schrijfrechten heeft.

## Veelgestelde Vragen

**Q: Kan ik meerdere gradients toepassen op verschillende delen van het document?**  
A: Ja, je kunt meerdere paden maken en voor elk een aparte gradient toepassen.

**Q: Zijn er vooraf gedefinieerde gradient‑stijlen beschikbaar?**  
A: Aspose.Page staat aangepaste gradients toe, waardoor je volledige controle hebt over kleurovergangen.

**Q: Kan ik Aspose.Page voor .NET gebruiken met andere documentformaten?**  
A: Aspose.Page richt zich voornamelijk op XPS‑documentmanipulatie.

**Q: Hoe kan ik fouten met betrekking tot documentverwerking afhandelen?**  
A: Raadpleeg de [documentatie](https://reference.aspose.com/page/net/) voor best practices omtrent foutafhandeling.

**Q: Is er een proefversie beschikbaar voordat ik koop?**  
A: Ja, je kunt de [gratis proefversie](https://releases.aspose.com/) verkennen om Aspose.Page voor .NET te ervaren.

**Q: Hoe wijzig ik de gradientrichting naar verticaal of horizontaal?**  
A: Pas de `PointF`‑argumenten in `CreateLinearGradientBrush` aan om nieuwe start‑ en eindpunten in te stellen.

**Q: Ondersteunt de bibliotheek transparantie in gradients?**  
A: Ja—voeg een alfa‑waarde toe bij het maken van kleuren met `CreateColor`.

## Conclusie

Aspose.Page voor .NET vereenvoudigt het proces van het verrijken van XPS‑documenten met diagonale gradients. Deze gids heeft je stap voor stap begeleid van het instellen van de vereisten tot het opslaan van het uiteindelijke bestand. Blijf experimenteren met verschillende vormen en kleurenpaletten om je XPS‑rapporten, brochures of facturen echt te laten opvallen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---