---
title: Voeg tekst toe aan een PostScript (PS)-document met Aspose.Page
linktitle: Tekst toevoegen aan PostScript (PS)-document
second_title: Aspose.Page .NET-API
description: Verbeter uw .NET-ontwikkelvaardigheden door te leren tekst toe te voegen aan PostScript (PS)-documenten met behulp van Aspose.Page. Ontdek stapsgewijze voorbeelden en ontketen de kracht van documentmanipulatie.
weight: 10
url: /nl/net/text-manipulation/add-text-to-postscript-ps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg tekst toe aan een PostScript (PS)-document met Aspose.Page

## Invoering

In de dynamische wereld van .NET-ontwikkeling is het manipuleren en verbeteren van PostScript (PS)-documenten een veel voorkomende vereiste. Aspose.Page voor .NET biedt een krachtige set tools waarmee u moeiteloos tekst aan uw PS-documenten kunt toevoegen. Deze tutorial leidt u door het proces en zorgt ervoor dat u deze functionaliteit naadloos in uw projecten kunt integreren.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Page voor .NET: Zorg ervoor dat de Aspose.Page-bibliotheek in uw .NET-project is geïntegreerd. Je kunt het downloaden van de[Aspose.Page .NET-documentatie](https://reference.aspose.com/page/net/).

- Documentmap: stel een map in waarin uw documenten worden opgeslagen. In de voorbeelden wordt dit "Uw documentenmap" genoemd.

- Lettertypenmap: Maak een map om aangepaste lettertypen op te slaan, in de voorbeelden 'Uw documentmap' genoemd.

## Naamruimten importeren

Zorg ervoor dat u, voordat u aan de slag gaat, de benodigde naamruimten in uw project opneemt:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Laten we het voorbeeld nu in meerdere stappen opsplitsen.

## Stap 1: Maak een uitvoerstroom voor PS-document

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Stap 2: tekst vullen met systeemlettertype

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## Stap 3: tekst vullen met aangepast lettertype

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Stap 4: Omlijn tekst met systeemlettertype

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## Stap 5: Omtrektekst met aangepast lettertype

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## Stap 6: Sluiten en opslaan

```csharp
document.ClosePage();
document.Save();
}
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u tekst kunt toevoegen aan een PostScript (PS)-document met behulp van Aspose.Page voor .NET. Ontdek gerust meer functies en verbeter uw mogelijkheden voor documentmanipulatie.

## Veelgestelde vragen

### V1: Kan ik Aspose.Page gebruiken met andere .NET-bibliotheken?

A1: Ja, Aspose.Page kan naadloos worden geïntegreerd met andere .NET-bibliotheken, waardoor een veelzijdige omgeving voor documentmanipulatie ontstaat.

### Vraag 2: Zijn aangepaste lettertypen essentieel voor dit proces?

A2: Hoewel u systeemlettertypen kunt gebruiken, zorgt het opnemen van aangepaste lettertypen voor meer flexibiliteit en ontwerpkeuzes.

### Vraag 3: Is Aspose.Page geschikt voor grootschalige documentverwerking?

A3: Absoluut! Aspose.Page is ontworpen om grootschalige documentverwerking efficiënt en betrouwbaar af te handelen.

### V4: Kan ik de positie van de tekst in het PS-document wijzigen?

A4: Zeker! Pas de coördinaten in de gegeven voorbeelden aan om de positie van de toegevoegde tekst te wijzigen.

### V5: Waar kan ik hulp zoeken voor Aspose.Page-gerelateerde vragen?

 A5: Bezoek de[Aspose.Pagina-forum](https://forum.aspose.com/c/page/39) om verbinding te maken met de gemeenschap en deskundig advies in te winnen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
