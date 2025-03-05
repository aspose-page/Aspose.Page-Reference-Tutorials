---
title: Voeg rechthoek toe aan PostScript (PS) met Aspose.Page voor .NET
linktitle: Rechthoek toevoegen aan PostScript (PS)
second_title: Aspose.Page .NET-API
description: Verbeter het maken van documenten in .NET met Aspose.Page. Leer stap voor stap rechthoeken toevoegen aan PostScript-bestanden (PS).
type: docs
weight: 12
url: /nl/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Invoering

Als u uw mogelijkheden voor het maken van documenten in .NET wilt verbeteren, biedt Aspose.Page een krachtige oplossing voor het verwerken van PostScript-documenten. In deze zelfstudie begeleiden we u bij het proces van het toevoegen van rechthoeken aan een PostScript-document met behulp van Aspose.Page voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET-bibliotheek: Download en installeer de Aspose.Page voor .NET-bibliotheek van[hier](https://releases.aspose.com/page/net/).

- Ontwikkelomgeving: Zorg ervoor dat er een .NET-ontwikkelomgeving op uw computer is geïnstalleerd.

## Naamruimten importeren

Voordat u begint met coderen, moet u ervoor zorgen dat u de benodigde naamruimten importeert om toegang te krijgen tot de vereiste klassen en methoden:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we het voorbeeld nu in meerdere stappen opsplitsen:

## Stap 1: Stel uw documentenmap in

```csharp
// ExStart:1
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
```

Vervang in deze stap "Uw documentenmap" door het pad waar u uw PostScript-document wilt opslaan.

## Stap 2: Maak een uitvoerstroom voor een PostScript-document

```csharp
//Maak een uitvoerstroom voor een PostScript-document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Hier maken we een uitvoerstroom voor het PostScript-document en specificeren we de bestandsnaam ("AddRectangle_outPS.ps"). Pas de bestandsnaam en locatie aan volgens uw voorkeuren.

## Stap 3: Stel de opslagopties in en maak een PS-document

```csharp
//Creëer opslagopties met A4-formaat
PsSaveOptions options = new PsSaveOptions();

// Maak een nieuw PS-document met één pagina
PsDocument document = new PsDocument(outPsStream, options, false);
```

Stel de opslagopties in en geef het gewenste paginaformaat op (in dit geval A4). Maak vervolgens een nieuw PostScript-document van één pagina.

## Stap 4: Rechthoek toevoegen en vullen

```csharp
//Maak een grafisch pad vanaf de eerste rechthoek
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Verf instellen
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Vul de rechthoek
document.Fill(path);
```

Hier maken we een grafisch pad dat de eerste rechthoek vertegenwoordigt, stellen we de verfkleur in (in dit geval oranje) en vullen we de rechthoek.

## Stap 5: Voeg nog een rechthoek en lijn toe

```csharp
//Maak een grafisch pad vanuit de tweede rechthoek
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Slag instellen
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Strijk (omtrek) de rechthoek
document.Draw(path);
```

Net als bij de vorige stap maken we een grafisch pad voor de tweede rechthoek, stellen we de streekkleur in (rood met een dikte van 3) en schetsen we de rechthoek.

## Stap 6: Sluit de pagina en sla het document op

```csharp
//Sluit huidige pagina
document.ClosePage();

//Bewaar het document
document.Save();
```

Sluit ten slotte de huidige pagina en sla het hele document op.

## Conclusie

Gefeliciteerd! U hebt met succes rechthoeken aan een PostScript-document toegevoegd met Aspose.Page voor .NET. In deze tutorial werden de essentiële stappen behandeld, van het opzetten van uw ontwikkelomgeving tot het opslaan van het definitieve document.

## Veelgestelde vragen

### Vraag 1: Kan ik de kleuren van de rechthoeken aanpassen?

A1: Ja, u kunt de kleuren aanpassen door de parameters in het bestand aan te passen`SolidBrush` En`Pen` klassen.

### Vraag 2: Is Aspose.Page compatibel met andere documentformaten?

A2: Ja, Aspose.Page ondersteunt verschillende documentformaten, waaronder XPS en PostScript.

### Vraag 3: Hoe kan ik tekst aan het document toevoegen?

 A3: U kunt de`TextFragment` klasse in Aspose.Page om tekst aan uw document toe te voegen.

### V4: Waar kan ik aanvullende voorbeelden en documentatie vinden?

 A4: Bekijk de documentatie[hier](https://reference.aspose.com/page/net/) en bezoek de[Aspose.Page-forum](https://forum.aspose.com/c/page/39) voor gemeenschapssteun.

### Vraag 5: Kan ik Aspose.Page uitproberen voordat ik een aankoop doe?

 A5: Ja, u kunt een gratis proefversie krijgen[hier](https://releases.aspose.com/) , en voor langdurig gebruik, overweeg dan een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).
