---
date: 2026-03-03
description: Leer hoe u Aspose.Page voor .NET kunt gebruiken om afbeeldingen in XPS‑documenten
  te tegelen. Deze stapsgewijze handleiding laat zien hoe u afbeeldingen efficiënt
  kunt tegelen en de visuele aantrekkingskracht kunt verbeteren.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Hoe Aspose.Page te gebruiken om een getegelde afbeelding aan een XPS‑document
  toe te voegen
url: /nl/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Aspose.Page te gebruiken om een getegelde afbeelding toe te voegen aan een XPS-document

## Inleiding

Als je je afvraagt **hoe je Aspose** kunt gebruiken om je XPS‑bestanden een rijkere visuele stijl te geven, ben je hier aan het juiste adres. In deze tutorial lopen we de exacte stappen door die nodig zijn om **een afbeelding te tegelen** binnen een XPS‑document met Aspose.Page voor .NET. Aan het einde heb je een herbruikbare code‑fragment dat je in elk .NET‑project kunt plaatsen om dynamisch getegelde‑afbeeldingsgrafieken te maken.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for .NET  
- **Welke methode maakt de getegelde brush?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Kan ik de opacity regelen?** Ja – stel `path.Fill.Opacity` in (bijv. 0.5f)  
- **Heb ik een licentie nodig voor testen?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Wat is Aspose.Page en waarom afbeeldingen tegelen?

Aspose.Page is een krachtige API die ontwikkelaars in staat stelt XPS-, PDF- en andere paginagebaseerde formaten te genereren, bewerken en renderen zonder afhankelijk te zijn van Microsoft Office. Het tegelen van een afbeelding—het herhalen van een bitmap over een vorm—helpt je grote gebieden te vullen met patronen, watermerken of achtergrondtexturen, terwijl de bestandsgrootte laag blijft.

## Hoe Aspose.Page te gebruiken om afbeeldingen te tegelen in XPS‑documenten

Hieronder vind je een compleet, kant‑klaar voorbeeld. Elke stap wordt in eenvoudige taal uitgelegd vóór het bijbehorende code‑blok, zodat je **waarom** elke regel belangrijk is kunt zien.

### Vereisten

- **Aspose.Page for .NET** – download en verwijs naar de bibliotheek vanaf de officiële site [here](https://reference.aspose.com/page/net/).  
- **Ontwikkelomgeving** – Visual Studio (elke editie) of een andere .NET‑IDE die je verkiest.

### Namespaces importeren

Breng eerst de benodigde namespaces in scope zodat de compiler weet waar de XPS‑klassen te vinden zijn.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Stap 1: Definieer de documentmap

Geef op waar het gegenereerde XPS‑bestand en de bronafbeelding worden opgeslagen. Vervang de tijdelijke aanduiding door een daadwerkelijke map op je computer.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Stap 2: Maak een nieuw XPS‑document

Instantieer een leeg XPS‑document dat de getegelde grafiek zal bevatten.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Stap 3: Voeg een getegelde afbeelding toe

Hier maken we een rechthoekig pad, vullen het met een `ImageBrush` en stellen de brush in op tegelmodus. De eigenschap `TileMode` vertelt de engine om de afbeelding zowel horizontaal als verticaal te herhalen. Pas de coördinaten van de rechthoek of de bronafbeelding aan naar behoefte voor jouw scenario.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Stap 4: Sla het resulterende XPS‑document op

Schrijf tenslotte het document naar schijf. Het uitvoerbestand kan worden geopend met elke XPS‑viewer of verder worden verwerkt met Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Veelvoorkomende problemen & tips

- **Pad‑fouten** – Zorg ervoor dat `dataDir` eindigt met een slash of gebruik `Path.Combine` om ontbrekende scheidingsteken‑problemen te voorkomen.  
- **Afbeeldings‑grootte mismatch** – De bronafbeelding moet groot genoeg zijn voor het tegelgebied; anders kan het patroon uitgerekt lijken.  
- **Opacity niet zichtbaar** – Sommige viewers negeren opacity in XPS; test met een viewer die XPS‑rendering volledig ondersteunt (bijv. XPS Viewer op Windows).

## Veelgestelde vragen

### Q1: Is Aspose.Page compatibel met alle .NET‑ontwikkelomgevingen?
A: Ja, Aspose.Page werkt met Visual Studio, Rider, VS Code en elke IDE die .NET ondersteunt.

### Q2: Kan ik de opacity van de getegelde afbeelding aanpassen?
A: Absoluut. Het voorbeeld stelt `path.Fill.Opacity = 0.5f;` in—je kunt de float‑waarde wijzigen tussen 0 (transparant) en 1 (ondoorzichtig).

### Q3: Zijn er andere tegel‑modi beschikbaar in Aspose.Page voor .NET?
A: Ja. Naast `XpsTileMode.Tile` kun je `FlipX`, `FlipY` en `FlipXY` gebruiken om gespiegelde patronen te maken.

### Q4: Hoe ga ik om met tijdelijke licenties voor Aspose.Page?
A: Raadpleeg de pagina [temporary license](https://purchase.aspose.com/temporary-license/) op de Aspose‑website voor details over het verkrijgen en toepassen van een proeflicentie.

### Q5: Waar kan ik hulp zoeken of contact maken met de Aspose.Page‑gemeenschap?
A: Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) om vragen te stellen, fragmenten te delen en te leren van andere ontwikkelaars.

### Q6: Kan ik deze aanpak gebruiken om een watermerk‑effect te creëren?
A: Ja. Door de opacity te verlagen en een semi‑transparante afbeelding te kiezen, werkt de getegelde brush perfect als een herhalend watermerk.

## Conclusie

Je weet nu **hoe je Aspose** kunt gebruiken om een getegelde afbeelding toe te voegen aan een XPS‑document, de opacity te regelen en het resultaat op te slaan voor later gebruik. Deze techniek is ideaal voor achtergrondpatronen, watermerken of elke situatie waarin een herhalende grafiek visuele interesse toevoegt zonder de bestandsgrootte op te blazen. Voel je vrij om te experimenteren met verschillende vormen, afbeeldingen en tegel‑modi om aan de behoeften van je project te voldoen.

---

**Laatst bijgewerkt:** 2026-03-03  
**Getest met:** Aspose.Page for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}