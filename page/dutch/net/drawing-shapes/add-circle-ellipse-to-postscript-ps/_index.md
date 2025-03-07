---
title: Voeg Circle Ellipse toe aan PostScript (PS) met Aspose.Page
linktitle: Cirkel-ellips toevoegen aan PostScript (PS)
second_title: Aspose.Page .NET-API
description: Leer hoe u moeiteloos cirkel-ellipsen kunt toevoegen aan PostScript-documenten (PS) met behulp van Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor een naadloze integratie.
weight: 10
url: /nl/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg Circle Ellipse toe aan PostScript (PS) met Aspose.Page

## Invoering

Welkom bij deze uitgebreide tutorial over het toevoegen van cirkel-ellipsen aan PostScript (PS)-documenten met behulp van Aspose.Page voor .NET. Aspose.Page is een krachtige bibliotheek waarmee ontwikkelaars naadloos met PostScript en andere documentformaten kunnen werken. In deze handleiding begeleiden we u eenvoudig door het proces van het opnemen van cirkel-ellipsen in uw PS-documenten.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:

1.  Aspose.Page voor .NET-bibliotheek: Download en installeer de Aspose.Page voor .NET-bibliotheek van[hier](https://releases.aspose.com/page/net/).

2. Ontwikkelomgeving: Zorg ervoor dat er een werkende .NET-ontwikkelomgeving op uw computer is geïnstalleerd.

Laten we nu aan de slag gaan met de stapsgewijze handleiding.

## Naamruimten importeren

In de eerste stap moet u de benodigde naamruimten importeren om de Aspose.Page-functionaliteit beschikbaar te maken in uw code.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we het gegeven voorbeeld nu in meerdere stappen opsplitsen om u door het proces van het toevoegen van cirkel-ellipsen aan een PostScript-document te leiden.

## Stap 1: Stel de documentmap in

```csharp
// ExStart:1
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
```

Zorg ervoor dat u "Uw documentenmap" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Maak een uitvoerstroom voor een PostScript-document

```csharp
//Maak een uitvoerstroom voor een PostScript-document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Hier wordt een FileStream gemaakt om het PostScript-document te schrijven en wordt de bestandsmodus ingesteld om een nieuw bestand te maken.

## Stap 3: Creëer opslagopties en PS-document

```csharp
//Creëer opslagopties met A4-formaat
PsSaveOptions options = new PsSaveOptions();

// Maak een nieuw PS-document met één pagina
PsDocument document = new PsDocument(outPsStream, options, false);
```

Deze stap omvat het maken van opslagopties met A4-formaat en het initialiseren van een nieuw PS-document met één pagina.

## Stap 4: Maak een grafisch pad voor de eerste ellips

```csharp
//Maak een grafisch pad vanaf de eerste ellips
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Er wordt een grafisch pad gemaakt voor de eerste ellips, waarin de positie en afmetingen ervan worden gespecificeerd.

## Stap 5: Stel Paint in en vul de ellips

```csharp
//Verf instellen
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Vul de ellips
document.Fill(path);
```

Hier wordt de verf ingesteld en wordt de eerste ellips gevuld met de opgegeven kleur.

## Stap 6: Maak een grafisch pad voor de tweede ellips

```csharp
//Maak een grafisch pad vanaf de tweede ellips
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Op dezelfde manier wordt er een grafisch pad gemaakt voor de tweede ellips, waarin de positie en afmetingen ervan worden gedefinieerd.

## Stap 7: Stel de lijn in en teken de ellips

```csharp
//Slag instellen
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Strijk (omtrek) de ellips
document.Draw(path);
```

In deze stap wordt de lijn ingesteld en wordt de tweede ellips omlijnd met de opgegeven kleur en lijndikte.

## Stap 8: Sluit de huidige pagina en sla het document op

```csharp
//Sluit huidige pagina
document.ClosePage();

//Bewaar het document
document.Save();
```

Ten slotte wordt de huidige pagina gesloten en wordt het hele document opgeslagen, waarmee het proces is voltooid.

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u cirkel-ellipsen kunt toevoegen aan PostScript-documenten met behulp van Aspose.Page voor .NET. Deze tutorial biedt een gedetailleerde, stapsgewijze handleiding waarmee u deze functionaliteit naadloos in uw projecten kunt integreren.

## Veelgestelde vragen

### V1: Kan ik Aspose.Page voor .NET gebruiken met andere documentformaten?

 A1: Aspose.Page richt zich primair op PostScript, maar Aspose biedt andere bibliotheken voor verschillende documentformaten. Controleer de[Documentatie aanvragen](https://reference.aspose.com/page/net/) voor meer details.

### Vraag 2: Waar kan ik aanvullende ondersteuning en communitydiscussies vinden?

 A2: Bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapsdiscussies en ondersteuning.

### V3: Is er een gratis proefversie beschikbaar voor Aspose.Page voor .NET?

 A3: Ja, u heeft toegang tot de[gratis proefperiode](https://releases.aspose.com/)om de functies van Aspose.Page voor .NET te verkennen.

### V4: Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?

 A4: Verkrijg een tijdelijke licentie[hier](https://purchase.aspose.com/temporary-license/) voor test- en evaluatiedoeleinden.

### V5: Waar kan ik Aspose.Page voor .NET kopen?

 A5: Koop Aspose.Page voor .NET bij de[pagina kopen](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
