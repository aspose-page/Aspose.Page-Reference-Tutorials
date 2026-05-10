---
date: 2026-03-26
description: Leer hoe u een opaciteitsmasker instelt en meerdere opaciteitsmaskers
  toepast in XPS‑documenten met Aspose.Page voor .NET.
linktitle: Set Opacity Mask in XPS Document
second_title: Aspose.Page .NET API
title: Meerdere doorzichtigheidsmaskers instellen in XPS-document met Aspose.Page
  voor .NET
url: /nl/net/transparency-effects/set-opacity-mask-in-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel Meerdere Opaciteitsmaskers in XPS‑document met Aspose.Page voor .NET

## Inleiding

Opaciteitsmaskers laten u de transparantie van elk visueel element regelen, en met **meerdere opaciteitsmaskers** kunt u verfijnde laageffecten bereiken die uw XPS‑documenten laten opvallen. In deze tutorial laten we u zien **hoe u een opaciteitsmasker** op vormen instelt en demonstreren we hoe u verschillende maskers kunt combineren voor rijkere visuele resultaten. Aan het einde kunt u één of meer opaciteitsmaskers toevoegen aan elk XPS‑element met slechts een paar regels C#‑code.

## Snelle Antwoorden
- **Wat is een opaciteitsmasker?** Een bitmap, verloop of effen‑kleur penseel dat per‑pixel transparantie voor een vorm definieert.  
- **Waarom meerdere opaciteitsmaskers gebruiken?** Het stapelen van maskers creëert complexe transparantiepatronen die een enkel masker niet kan bereiken.  
- **Welke bibliotheek ondersteunt dit?** Aspose.Page for .NET biedt volledige ondersteuning voor opaciteitsmaskers op XPS‑graphics.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat zijn “meerdere opaciteitsmaskers”?
Meerdere opaciteitsmaskers verwijzen naar de techniek waarbij meer dan één masker wordt toegepast — ofwel opeenvolgend of gelaagd — zodat elk masker bijdraagt aan de uiteindelijke transparantiemap. Deze aanpak is nuttig voor het creëren van verlopen, texturen of patroon‑transparantie zonder complexe beeldbewerking.

## Waarom Aspose.Page voor .NET gebruiken om opaciteitsmaskers in te stellen?
- **Volledige XPS‑functieset** – Alle XPS‑graphicsmogelijkheden worden beschikbaar gesteld via een nette .NET‑API.  
- **Geen externe afhankelijkheden** – Werk direct met XPS‑objecten; er is geen extra beeldverwerkingsbibliotheek nodig.  
- **Prestatie‑geoptimaliseerd** – Verwerkt grote documenten en masks met hoge resolutie efficiënt.  

## Voorvereisten

Voordat u aan de tutorial begint, zorg ervoor dat u de volgende voorvereisten heeft:

- Aspose.Page for .NET: Zorg ervoor dat de bibliotheek geïnstalleerd is. Zo niet, download deze van de [website](https://releases.aspose.com/page/net/).
- Documentmap: Maak een map aan om uw XPS‑documenten op te slaan.

## Namespaces importeren

In uw .NET‑project begint u met het importeren van de benodigde namespaces:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Stap 1: Maak een nieuw XPS‑document

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Begin met het maken van een nieuw XPS‑document met behulp van Aspose.Page for .NET.

## Stap 2: Voeg een canvas toe aan XpsDocument‑instantie

```csharp
// Add Canvas to XpsDocument instance
XpsCanvas canvas = doc.AddCanvas();
```

Voeg nu een canvas toe aan het XPS‑document. Het canvas dient als container voor verschillende grafische elementen.

## Stap 3: Voeg een rechthoek toe met een opaciteitsmasker

```csharp
// Rectangle with opacity masked by ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

Voeg een rechthoek toe aan het canvas en stel de transparantie in met de eigenschap `OpacityMask`. In dit voorbeeld gebruiken we een afbeelding als opaciteitsmasker. U kunt deze stap herhalen met een andere brush om **meerdere opaciteitsmaskers** op dezelfde vorm toe te passen, waardoor gelaagde transparantie‑effecten ontstaan.

## Stap 4: Sla het resulterende XPS‑document op

```csharp
// Save resultant XPS document
doc.Save(dataDir + "OpacityMask_out.xps");
```

Tot slot slaat u het aangepaste XPS‑document op met het toegepaste opaciteitsmasker.

## Veelvoorkomende gebruikssituaties voor meerdere opaciteitsmaskers
- **Watermerken** – Combineer een tekstmasker met een patroonmasker om half‑transparante watermerken te creëren.  
- **Thematische kaarten** – Leg een verloopmasker over een rasterafbeelding om specifieke regio's te accentueren.  
- **Branding** – Gebruik een logo‑afbeeldingsmasker samen met een kleurverloopmasker voor verfijnde merkelementen.

## Probleemoplossing & Tips
- **Maskeralignering** – Zorg ervoor dat de afmetingen van de bronrechthoek overeenkomen met de doelvorm om uitrekken te voorkomen.  
- **TileMode** – Experimenteer met `XpsTileMode.Tile` of `XpsTileMode.None` om te bepalen hoe het masker zich herhaalt.  
- **Prestaties** – Hergebruik `XpsImageBrush`‑instanties bij het toepassen van hetzelfde masker op meerdere elementen.

## FAQ's

### Q1: Kan ik opaciteitsmaskers toepassen op andere vormen dan rechthoeken?
A1: Ja, Aspose.Page for .NET stelt u in staat opaciteitsmaskers toe te passen op diverse vormen, waaronder cirkels, polygonen en aangepaste paden.

### Q2: Is het opaciteitsmasker beperkt tot afbeeldingen?
A2: Nee, hoewel deze tutorial een afbeelding als opaciteitsmasker gebruikte, kunt u effen kleuren, verlopen of zelfs patronen gebruiken.

### Q3: Zijn er geavanceerde opties voor het fijn afstellen van opaciteitsniveaus?
A3: Absoluut, Aspose.Page for .NET biedt gedetailleerde controle over opaciteitsinstellingen, zodat u precieze transparantie‑effecten kunt bereiken.

### Q4: Kan ik meerdere opaciteitsmaskers toepassen op één element?
A4: Ja, u kunt meerdere opaciteitsmaskers stapelen om ingewikkelde transparantie‑effecten te creëren.

### Q5: Is Aspose.Page compatibel met andere documentformaten?
A5: Aspose.Page richt zich voornamelijk op XPS‑documenten, maar Aspose biedt een reeks producten voor het verwerken van verschillende formaten.

**Aanvullende Vragen**

**Q: Hoe combineer ik twee verschillende maskers op dezelfde vorm?**  
A: Maak twee `XpsImageBrush` (of verloop‑brush) objecten, wijs één toe aan `OpacityMask`, wikkel vervolgens de vorm in een `XpsCanvas` en pas het tweede masker toe op het canvas zelf.

**Q: Ondersteunt de API geanimeerde opaciteitsveranderingen?**  
A: Hoewel XPS zelf geen animatie ondersteunt, kunt u een reeks XPS‑pagina's genereren met variërende maskerovertransparantie om animatie te simuleren.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}