---
date: 2026-03-29
description: Leer hoe u transparante objecten aan XPS‑documenten kunt toevoegen en
  vervolgens XPS naar PDF kunt exporteren met Aspose.Page voor .NET. Stapsgewijze
  handleiding met praktische tips.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: XPS exporteren naar PDF – Transparant object toevoegen met Aspose.Page
url: /nl/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export XPS naar PDF – Transparant Object Toevoegen met Aspose.Page

## Inleiding

In deze tutorial leer je hoe je transparante objecten aan een XPS-document kunt toevoegen en vervolgens **export XPS to PDF** met Aspose.Page voor .NET. Transparantie kan je documenten er moderner laten uitzien en helpt belangrijke informatie te benadrukken. We lopen elke stap door, leggen de reden achter de code uit, en laten zien hoe je de workflow voltooit door het XPS‑bestand naar een PDF te converteren voor gemakkelijke delen.

## Snelle Antwoorden
- **Wat betekent “export XPS to PDF”?** Een XPS‑bestand omzetten naar een PDF‑bestand terwijl lay-out, kleuren en transparantie behouden blijven.  
- **Waarom eerst transparantie toevoegen?** Transparante objecten laten je gelaagde graphics maken die er geweldig uitzien in de uiteindelijke PDF.  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Page‑licentie is vereist voor productiegebruik.  
- **Kan dit draaien op .NET Core?** Zeker – Aspose.Page ondersteunt .NET Core, .NET 5/6 en het volledige .NET Framework.  
- **Waar kan ik meer voorbeelden vinden?** Bekijk de Aspose.Page‑documentatie en het community‑forum hieronder.

## Voorvereisten

Voordat je aan de tutorial begint, zorg ervoor dat je de volgende voorvereisten hebt:

- Aspose.Page for .NET: Zorg ervoor dat je de Aspose.Page‑bibliotheek voor .NET geïnstalleerd hebt. Je kunt deze downloaden van [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Namespaces Importeren

Om te beginnen, voeg de benodigde namespaces toe aan je project:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Laten we nu verder gaan met de stap‑voor‑stap gids.

## Stap 1: Een nieuw XPS‑document maken

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Deze code initialiseert een nieuw XPS‑document met behulp van Aspose.Page voor .NET.

## Stap 2: Transparantie demonstreren

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Deze regels maken twee grijze paden die dienen als achtergrond voor de transparante vormen die we later zullen toevoegen.

## Stap 3: Een pad maken met een gesloten rechthoekgeometrie

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Hier maken we een blauwe rechthoek. Omdat we later de opacity zullen aanpassen, zal de rechthoek semi‑transparant verschijnen in de uiteindelijke PDF.

## Stap 4: Paden en kleuren manipuleren

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

We klonen de eerste rechthoek, voegen deze toe aan de pagina, en veranderen de vulkleur naar groen. Dit toont hoe eenvoudig het is om bestaande geometrie opnieuw te gebruiken.

## Stap 5: Paden klonen en transformeren

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Het gekloonde pad wordt omlaag verschoven met 300 eenheden en rood gekleurd, waardoor je een gestapeld‑laag effect krijgt.

## Stap 6: Paden herhalen en aanpassen

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

We hergebruiken de geometrie‑data van `path2`, verplaatsen deze naar rechts, en passen opnieuw een blauwe vulling toe.

## Stap 7: Opacity beheren

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Het instellen van de `Opacity`‑eigenschap op 0.8 maakt deze rechthoek 80 % ondoorzichtig, wat illustreert hoe je transparantie per element fijn kunt afstemmen.

## Stap 8: Het XPS‑document opslaan

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Het XPS‑bestand is nu opgeslagen met alle transparante objecten toegepast.  

**Export to PDF:** Om **export XPS to PDF** uit te voeren, roep je eenvoudig `doc.Save` opnieuw aan met een `.pdf` extensie, bijvoorbeeld `doc.Save(dataDir + "TransparentDocument.pdf");`. Dezelfde visuele nauwkeurigheid, inclusief opacity‑instellingen, wordt behouden in de resulterende PDF.

## Waarom XPS naar PDF exporteren na het toevoegen van transparantie?

- **Universele compatibiliteit:** PDF wordt breed ondersteund op verschillende platforms, terwijl XPS meer niche is.  
- **Behoud van visuele effecten:** Aspose.Page behoudt transparantie, verlopen en matrix‑transformaties tijdens de conversie.  
- **Gemakkelijk delen:** PDF's kunnen geopend worden in browsers, mobiele apparaten en vele derde‑partij lezers zonder extra plugins.

## Veelvoorkomende gebruikssituaties

- **Marketingbrochures** waarbij gelaagde graphics een premium gevoel geven.  
- **Technische diagrammen** die gemarkeerde secties nodig hebben zonder de lay-out te rommelig te maken.  
- **Rapportgeneratie** waarbij je watermerken of logo's met gedeeltelijke opacity wilt overleggen.

## Tips & Valstrikken

- **Pro tip:** Stel altijd de `Opacity`‑waarde in tussen 0 en 1. Waarden buiten dit bereik worden afgekapt en kunnen onverwachte resultaten geven.  
- **Performance tip:** Het hergebruiken van geometrie (`path2.Data`) vermindert het geheugenverbruik wanneer je veel gelijkaardige vormen nodig hebt.  
- **Valkuil:** Direct opslaan naar PDF na het toevoegen van transparantie werkt meteen, maar als je later de PDF bewerkt met andere tools, kunnen sommige oudere viewers de opacity niet correct weergeven.

## Conclusie

Het toevoegen van transparante objecten aan XPS‑documenten met Aspose.Page voor .NET biedt een veelzijdige manier om visuele presentaties te verbeteren. Zodra je XPS‑bestand er uitziet zoals je wilt, kun je **export XPS to PDF** in één regel code uitvoeren, waarbij alle transparantie‑effecten behouden blijven voor brede distributie.

## Veelgestelde vragen

### Q1: Kan ik transparantie toepassen op elk object in een XPS‑document?

A1: Ja, transparantie kan worden toegepast op verschillende objecten zoals paden, vormen en afbeeldingen in een XPS‑document.

### Q2: Hoe kan ik de opacity van een specifiek element aanpassen?

A2: Je kunt de opacity‑eigenschap van de Fill of Stroke instellen om de transparantie van een specifiek element aan te passen.

### Q3: Is Aspose.Page compatibel met .NET Core?

A3: Ja, Aspose.Page ondersteunt .NET Core, waardoor cross‑platform ontwikkeling mogelijk is.

### Q4: Kan ik XPS‑documenten exporteren naar andere formaten met Aspose.Page?

A4: Aspose.Page biedt functionaliteit om XPS‑documenten te exporteren naar verschillende formaten, waaronder PDF en afbeeldingen.

### Q5: Waar kan ik extra ondersteuning en community‑discussies vinden?

A5: Voor extra ondersteuning en community‑discussies, bezoek het [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6: Houdt de PDF‑conversie mijn transparantie‑instellingen?

A6: Absoluut. Wanneer je XPS naar PDF exporteert met Aspose.Page, worden alle opacity‑ en blend‑instellingen behouden.

### Q7: Kan ik meerdere XPS‑bestanden in batch verwerken naar PDF?

A7: Ja, je kunt door een collectie XPS‑bestanden itereren en `doc.Save(...".pdf")` voor elk aanroepen, waardoor bulk‑conversies geautomatiseerd worden.

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** Aspose.Page 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}