---
date: 2026-01-23
description: Leer hoe u een namespace aan EPS‑bestanden toevoegt met Aspose.Page voor
  .NET. Deze gids laat stap voor stap zien hoe u een namespace toevoegt, XMP‑metadata
  wijzigt en uw .NET‑workflow stroomlijnt.
linktitle: Add Namespace
second_title: Aspose.Page .NET API
title: Hoe een namespace toevoegen met Aspose.Page voor .NET
url: /nl/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Namespace toe te voegen met Aspose.Page voorontwikkeling is **hoe een namespace toe te voegen** aan een EPS‑bestand een veelvoorkomende behoefte wanneer je XMP‑metadata wilt verrijken. Aspose.Page voor .NET maakt deze taak eenvoudig, zodat je aangepaste XML‑namespaces kunt registreren en extra eigenschappen kunt opslaan zonder je code‑editor te verlaten. In deze tutorial zie je precies hoe je een namespace toevoegt, waarom dat belangrijk is en hoe je het bijgewerkte EPS‑bestand opslaat — alles met duidelijke, gesprekachtige uitleg.

## Snelle antwoorden
- **Wat betekent “namespace toevoegen”?** Het registreert een aangepast XML‑prefix dat je kunt gebruiken voor nieuwe XMP‑eigenschappen.  
- **Welke bibliotheek is vereist?** Aspose.Page voor .NET (download van de officiële documentatie).  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Kan ik dit draaien op .NET Core / .NET 6+?** Ja, de bibliotheek ondersteunt alle recente .NET‑versies.  
- **Hoe lang duurt de implementatie?** Meestal minder dan 10 minuten zodra de bibliotheek is toegevoegd.

## Wat is een Namespace toevoegen?
Een namespace toevoegen betekent het creëren van een unieke identifier (een URI) die gerelateerde metadata‑velden groepeert onder een gemeenschappelijk prefix. Dit houdt je metadata georganiseerd en voorkomt conflicten met bestaande standaarden.

## Waarom Aspose.Page gebruiken voor Namespace‑beheer?
- **Volledige controle** over XMP‑metadata zonder handmatige XML‑parsing.  
- **Cross‑platform** ondersteuning voor .NET Framework, .NET Core en .NET 5/6+.  
- **Zero‑dependency** — de API regelt stream‑beheer en bestandssaving voor je.  

## Voorvereisten

1. **Aspose.Page voor .NET** — download en installeer via de [Aspose.Page‑documentatie](https://reference.aspose.com/page/net/).  
2. **Een .NET‑ontwikkelomgeving** — Visual Studio, VS Code of een andere IDE naar keuze.  

Nu de basis is behandeld, duiken we in de code.

## Namespaces importeren

Breng eerst de benodigde Aspose.Page‑namespaces in scope:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Stap 1: Initialiseer je project

Stel het pad in naar de map die je EPS‑bestanden bevat:

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Stap 2: Open EPS‑bestand

Open het EPS‑bestand met een `FileStream` en maak een `PsDocument`‑instantie:

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## Stap 3: Haal XMP‑metadata op

Verkrijg bestaande XMP‑metadata (of maak een nieuwe aan als er geen bestaat):

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## Stap 4: Wijzig XMP‑metadata

Hier komt **hoe een namespace toe te voegen** in de praktijk. Registreer een nieuwe namespace‑URI en voeg een eigenschap toe die het nieuwe prefix gebruikt:

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

*Pro tip:* Kies een kort, betekenisvol prefix (bijv. `tmp`) en een wereldwijd unieke URI om conflicten met andere metadata‑standaarden te vermijden.

## Stap 5: Sla EPS‑bestand op

Schrijf het gewijzig```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

Na het uitvoeren van de code bevat het bestand `add_namespace_output.eps` de nieuwe `tmp:newKey`‑eigenschap binnen de aangepaste namespace die je hebt geregistreerd.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Namespace verschijnt niet** | Vergeten `RegisterNamespaceUri` aan te roepen vóór het toevoegen van de eigenschap. | Zorg dat de `RegisterNamespaceUri`‑regel wordt uitgevoerd vóór `xmp.Add`. |
| **Bestands‑toegangs­fouten** | Het EPS‑bestand staat open in een ander programma. | Sluit alle toepassingen die het bestand mogelijk vergrendelen of gebruik een ander uitvoerpad. |
| **Metadata verloren na opslaan** | Een verouderde versie van Aspose.Page wordt gebruikt. | Update naar de nieuwste Aspose.Page‑release voor .NET. |

## FAQ's

### Q1: Is Aspose.Page compatibel met alle versies van .NET?

A1: Aspose.Page voor .NET is compatibel met diverse versies van het .NET‑framework, waardoor ontwikkelaars flexibel blijven.

### Q2: Kan ik Aspose.Page gebruiken om metadata uit EPS‑bestanden te extraheren?

A2: Absoluut! Aspose.Page stelt je in staat om XMP‑metadata uit EPS‑bestanden moeiteloos te extraheren en te wijzigen.

### Q3: Waar vind ik extra ondersteuning of hulp?

A3: Bezoek het [Aspose.Page‑forum](https://forum.aspose.com/c/page/39) voor community‑ondersteuning en discussies.

### Q4: Is er een gratis proefversie beschikbaar voor Aspose.Page?

A4: Ja, je kunt een gratis proefversie van Aspose.Page [hier](https://releases.aspose.com/) verkennen.

### Q5: Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?

A5: Verkrijg een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) voor testdoeleinden.

## Veelgestelde vragen

**V: Kan ik meerdere namespaces in één sessie toevoegen?**  
A: Ja, roep simpelweg `RegisterNamespaceUri` aan voor elk prefix dat je nodig hebt voordat je eigenschappen toevoegt.

**V: Ondersteunt de bibliotheek Unicode‑tekens in eigenschapswaarden?**  
A: Ja. XMP‑waarden worden opgeslagen als UTF‑8, dus je kunt veilig internationale tekens gebruiken.

**V: Hoe verifieer ik dat de namespace correct is toegevoegd?**  
A: Open het resulterende EPS‑bestand in een XMP‑viewer of gebruik `document.GetXmpMetadata().ToString()` om de ruwe XML te inspecteren.

**V: Verhoogt het toevoegen van een namespace de bestandsgrootte merkbaar?**  
A: Alleen marginaal — XMP‑metadata is lichtgewicht en de toegevoegde XML bestaat meestal uit enkele bytes.

## Conclusie

Je weet nu **hoe een namespace toe te voegen** aan een EPS‑bestand met Aspose.Page voor .NET, van het opzetten van het project tot het opslaan van de wijzigingen. Deze mogelijkheid opent de deur naar rijkere, aangepaste metadata die kan worden benut door downstream‑applicaties, digitale asset‑management‑systemen of elke workflow die afhankelijk is van XMP. Experimenteer gerust met extra eigenschappen, verschillende namespaces en integreer dit patroon in grotere document‑verwerkings‑pijplijnen.

---

**Laatst bijgewerkt:** 2026-01-23  
**Getest met:** Aspose.Page 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}