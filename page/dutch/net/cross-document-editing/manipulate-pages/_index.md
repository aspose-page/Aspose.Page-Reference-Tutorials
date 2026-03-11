---
date: 2026-01-10
description: Leer hoe u XPS‑documenten kunt samenvoegen met Aspose.Page voor .NET.
  Deze stapsgewijze gids toont paginamanipulatietechnieken voor efficiënte resultaten.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: XPS-documenten samenvoegen met Aspose.Page voor .NET
url: /nl/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-documenten samenvoegen met Aspose.Page voor .NET

## Inleiding

In deze tutorial ontdek je hoe je **XPS-documenten kunt samenvoegen** en hun pagina's kunt manipuleren met de Aspose.Page-bibliotheek in een .NET-omgeving. Of je nu meerdere rapporten wilt combineren tot één XPS-bestand of pagina's wilt herschikken voor een gepolijste output, deze gids leidt je stap voor stap door het proces, met duidelijke uitleg en kant‑klaar code.

## Snelle antwoorden
- **Wat kan ik doen met Aspose.Page?** XPS-documenten samenvoegen, pagina's invoegen, toevoegen of verwijderen, en het resultaat opslaan.  
- **Heb ik een licentie nodig voor testen?** Er is een tijdelijke licentie beschikbaar voor evaluatie.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is Visual Studio vereist?** Nee, elke IDE die C# ondersteunt werkt, maar Visual Studio wordt aanbevolen.  
- **Hoe lang duurt het samenvoegen?** Meestal een paar seconden voor standaard‑grootte XPS-bestanden.

## Wat is het samenvoegen van XPS-documenten?
Het samenvoegen van XPS-documenten betekent dat je pagina's van twee of meer bestaande XPS‑bestanden neemt en combineert tot één XPS‑document. Dit is handig voor het maken van geconsolideerde rapporten, het samenstellen van meerpagina‑handleidingen, of het voorbereiden van print‑klare pakketten zonder te converteren naar een ander formaat.

## Waarom Aspose.Page voor .NET gebruiken?
Aspose.Page biedt een **pure .NET API** die direct met XPS‑bestanden werkt—geen externe tools of componenten van derden nodig. Het geeft je fijnmazige controle over paginavolgorde, invoerpunt(en) en behoud van inhoud, waardoor het samenvoegproces betrouwbaar en snel is.

## Vereisten

- **Aspose.Page for .NET** – download van de [Aspose.Page for .NET-documentatie](https://reference.aspose.com/page/net/).  
- **Ontwikkelomgeving** – Visual Studio, Rider, of elke IDE die C# ondersteunt.  
- **Invoergegevens XPS‑bestanden** – drie voorbeeldbestanden (`input1.xps`, `input2.xps`, `input3.xps`) geplaatst in een bekende map.

## Namespaces importeren

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Deze namespaces geven je toegang tot de kern‑XPS‑documentklassen, paginamodellen en basis‑tekenhulpmiddelen.

## Stap 1: Stel de documentdirectory in

```csharp
string dataDir = "Your Document Directory";
```

Vervang **Your Document Directory** door het volledige pad waar je XPS‑bestanden zijn opgeslagen, bijv. `C:\\Docs\\XpsFiles\\`.

## Stap 2: Maak XPS‑documentinstanties

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` en `doc3` vertegenwoordigen de bron‑documenten die je wilt samenvoegen.  
- `doc4` is een leeg XPS‑document dat het samengevoegde resultaat zal bevatten.

## Stap 3: Pagina's invoegen, toevoegen en verwijderen

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Dit is wat elke regel doet:

1. **InsertPage(1, doc2.Page, false)** – plaatst de eerste pagina van `doc2` op positie 1 in `doc4`.  
2. **AddPage(doc3.Page, false)** – voegt de eerste pagina van `doc3` toe aan het einde van `doc4`.  
3. **RemovePageAt(2)** – verwijdert de pagina die nu op index 2 staat (handig om ongewenste pagina's te verwijderen).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – voegt de derde pagina van `doc1` in op positie 2, waardoor het samenvoegen voltooid wordt.

Deze bewerkingen illustreren hoe je **XPS-documenten kunt samenvoegen** terwijl je pagina's herschikt of verwijdert indien nodig.

## Stap 4: Sla het samengevoegde document op

```csharp
doc4.Save(dataDir + "out.xps");
```

Het uiteindelijke samengevoegde XPS‑bestand (`out.xps`) wordt weggeschreven naar dezelfde map. Je kunt het nu openen in elke XPS‑viewer of verder verwerken met Aspose.Page.

## Veelvoorkomende problemen en oplossingen
- **Bestand niet gevonden** – controleer het `dataDir`‑pad en zorg ervoor dat de invoerbestanden bestaan.  
- **Ongeldige paginanaam** – paginanummers beginnen bij 1; proberen een niet‑bestaande pagina in te voegen veroorzaakt een uitzondering.  
- **Licentiefouten** – gebruik een tijdelijke of volledige licentie voordat je naar productie gaat.

## Veelgestelde vragen

### Q1: Kan ik pagina's van verschillende XPS‑documenten manipuleren?
A1: Ja, zoals in de tutorial getoond, kun je pagina's van meerdere XPS‑documenten invoegen in een nieuw document.

### Q2: Hoe kan ik een specifieke pagina uit een document verwijderen?
A2: Gebruik de `RemovePageAt`‑methode en geef de index van de pagina die je wilt verwijderen op.

### Q3: Is Aspose.Page compatibel met Visual Studio?
A3: Ja, Aspose.Page is volledig compatibel met Visual Studio, waardoor het eenvoudig te integreren is in je .NET‑projecten.

### Q4: Zijn er licentieopties beschikbaar?
A4: Ja, je kunt licentieopties verkennen en een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### Q5: Waar kan ik ondersteuning krijgen of vragen stellen?
A5: Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor ondersteuning en om deel te nemen aan de community.

## Veelgestelde vragen

**Q: Kan ik meer dan drie XPS‑bestanden samenvoegen?**  
A: Absoluut. Maak extra `XpsDocument`‑instanties aan en gebruik herhaaldelijk `InsertPage` of `AddPage` om een groter samengevoegd document te bouwen.

**Q: Behoudt het samenvoegen de oorspronkelijke opmaak en grafische elementen?**  
A: Ja. Aspose.Page kopieert de paginainhoud byte‑voor‑byte, zodat tekst, afbeeldingen en vector‑graphics ongewijzigd blijven.

**Q: Hoe voeg ik een pagina toe aan het einde zonder een index op te geven?**  
A: Gebruik `AddPage(sourcePage, false)` dat de pagina aan het einde van het document toevoegt.

**Q: Is het mogelijk om XPS‑documenten op een server samen te voegen zonder UI?**  
A: De API is volledig headless; je kunt dezelfde code uitvoeren in ASP.NET, Azure Functions of elke server‑side .NET‑omgeving.

**Q: Wat als mijn XPS‑bestanden met een wachtwoord beveiligd zijn?**  
A: Aspose.Page ondersteunt momenteel geen versleutelde XPS‑bestanden; je moet ze eerst ontcijferen voordat je ze samenvoegt.

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.Page for .NET 24.10  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}