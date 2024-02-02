---
title: Toon pseudo-transparantie in PostScript (PS) met Aspose.Page
linktitle: Pseudo-transparantie tonen in PostScript (PS)
second_title: Aspose.Page .NET-API
description: Ontdek de kracht van pseudo-transparantie in PostScript met Aspose.Page voor .NET. Volg onze stapsgewijze handleiding voor visueel verbluffende documenten.
type: docs
weight: 13
url: /nl/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## Invoering

Wilt u de visuele aantrekkingskracht van uw PostScript (PS)-documenten vergroten door pseudo-transparantie op te nemen? Aspose.Page voor .NET biedt een krachtige oplossing om dit effect moeiteloos te bereiken. In deze stapsgewijze zelfstudie begeleiden we u door het proces van het tonen van pseudo-transparantie in PostScript met behulp van Aspose.Page.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Aspose.Page voor .NET: Zorg ervoor dat de Aspose.Page-bibliotheek voor .NET is geïnstalleerd. Je kunt het downloaden van de[Aspose.Page-documentatie](https://reference.aspose.com/page/net/).

- Documentmap: Stel een map in om uw PostScript-documenten op te slaan.

Nu u over de nodige hulpmiddelen beschikt, gaan we eens kijken hoe u pseudo-transparantie in PostScript kunt laten zien met behulp van Aspose.Page.

## Naamruimten importeren

Voordat u zich in het voorbeeld verdiept, moet u ervoor zorgen dat u de vereiste naamruimten importeert:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Stap 1: Maak een uitvoerstroom voor een PostScript-document

```csharp
// ExStart:1
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
//Maak een uitvoerstroom voor een PostScript-document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Creëer opslagopties met A4-formaat
	PsSaveOptions options = new PsSaveOptions();

	// Maak een nieuw PS-document met één pagina
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 2: Creëer een rechthoek met ondoorzichtige verloopvulling

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Stap 3: Creëer een rechthoek met doorschijnende verloopvulling

```csharp
	offsetX = 350;

	//Maak een grafisch pad vanaf de eerste rechthoek
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Creëer lineaire verlooppenseelkleuren waarvan de transparantie niet 255 is, maar 150 en 50. Het is dus doorschijnend.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Stap 4: Sluit de huidige pagina en sla het document op

```csharp
	document.ClosePage();
	document.Save();
}
// Verlengen: 1
```

Door deze stappen te volgen, kunt u pseudo-transparantie naadloos integreren in uw PostScript-documenten met behulp van Aspose.Page voor .NET.

## Conclusie

Concluderend biedt Aspose.Page voor .NET een eenvoudige en efficiënte manier om de visuele elementen van uw PostScript-documenten te verbeteren. De hierboven beschreven stappen bieden een duidelijk pad voor het opnemen van pseudo-transparantie, waardoor u visueel verbluffende resultaten kunt creëren.

## Veelgestelde vragen

### Vraag 1: Is Aspose.Page compatibel met alle versies van .NET?

A1: Aspose.Page voor .NET is compatibel met verschillende versies van het .NET-framework, wat flexibiliteit en integratiegemak garandeert.

### Vraag 2: Kan ik pseudo-transparantie toepassen op andere vormen dan rechthoeken?

A2: Ja, dezelfde principes kunnen op andere vormen worden toegepast door het GraphicsPath dienovereenkomstig aan te passen.

### V3: Waar kan ik aanvullende voorbeelden en documentatie vinden?

 A3: Ontdek de[Aspose.Page-documentatie](https://reference.aspose.com/page/net/) voor uitgebreide voorbeelden en gedetailleerde documentatie.

### V4: Is er een gratis proefversie beschikbaar voor Aspose.Page?

 A4: Ja, u heeft toegang tot een gratis proefversie van Aspose.Page vanaf[deze link](https://releases.aspose.com/).

### V5: Hoe kan ik een tijdelijke licentie voor Aspose.Page verkrijgen?

 A5: Bezoek[deze link](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor Aspose.Page te verkrijgen.