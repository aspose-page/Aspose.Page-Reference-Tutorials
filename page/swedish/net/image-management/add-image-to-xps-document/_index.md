---
title: Lägg till bild till XPS-dokument med Aspose.Page för .NET
linktitle: Lägg till bild till XPS-dokument
second_title: Aspose.Page .NET API
description: Utforska den sömlösa integreringen av bilder i XPS-dokument med Aspose.Page för .NET. Följ vår steg-för-steg-guide för en smidig utvecklingsupplevelse.
weight: 11
url: /sv/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till bild till XPS-dokument med Aspose.Page för .NET

## Introduktion

I en värld av .NET-utveckling är det ett vanligt krav att införliva bilder i XPS-dokument. Aspose.Page för .NET förenklar denna process och erbjuder en kraftfull verktygslåda för att manipulera och förbättra XPS-dokument utan ansträngning. Denna handledning guidar dig genom stegen för att lägga till en bild i ett XPS-dokument med Aspose.Page för .NET.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

1.  Aspose.Page för .NET Library: Ladda ner och installera biblioteket från[Aspose.Page .NET-dokumentation](https://reference.aspose.com/page/net/).

2. Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö, till exempel Visual Studio.

3. Exempelbild: Ha en exempelbildfil (t.ex. "QL_logo_color.tif") som du vill lägga till i XPS-dokumentet.

## Importera namnområden

Börja med att importera de nödvändiga namnområdena till ditt .NET-projekt. Dessa namnutrymmen är viktiga för att använda funktionerna som tillhandahålls av Aspose.Page för .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Ställ in dokumentkatalog

Börja med att ange sökvägen till din dokumentkatalog. Det här steget säkerställer att ditt projekt vet var filerna ska hittas och sparas.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// Exend:1
```

## Steg 2: Skapa XPS-dokument

Skapa ett nytt XPS-dokument med Aspose.Page för .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// Exend:1
```

## Steg 3: Lägg till bild till XPS-dokument

Låt oss nu lägga till bilden i XPS-dokumentet. I det här exemplet använder vi en exempelbild med namnet "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// Exend:1
```

## Steg 4: Spara det resulterande XPS-dokumentet

Spara XPS-dokumentet med den tillagda bilden.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// Exend:1
```

Nu har du framgångsrikt lagt till en bild till ett XPS-dokument med Aspose.Page för .NET!

## Slutsats

I den här handledningen undersökte vi hur man kan utnyttja Aspose.Page för .NET för att sömlöst införliva bilder i XPS-dokument. Denna steg-för-steg-guide säkerställer en smidig integrationsprocess, vilket förbättrar dina .NET-utvecklingsmöjligheter.

## FAQ's

### F1: Är Aspose.Page för .NET kompatibel med de senaste .NET framework-versionerna?

 S1: Aspose.Page för .NET är designad för att vara kompatibel med ett brett utbud av .NET framework-versioner, inklusive de senaste utgåvorna. Referera till[dokumentation](https://reference.aspose.com/page/net/) för specifika detaljer.

### F2: Kan jag använda Aspose.Page för .NET i både Windows- och Linux-miljöer?

S2: Ja, Aspose.Page för .NET är plattformsoberoende, vilket gör den lämplig för användning i både Windows- och Linux-miljöer.

### F3: Finns det några licensalternativ för Aspose.Page för .NET?

 S3: Ja, du kan utforska licensalternativ och göra ett köp[här](https://purchase.aspose.com/buy).

### F4: Finns det en gratis testversion tillgänglig för Aspose.Page för .NET?

 S4: Ja, du kan prova Aspose.Page för .NET gratis genom att gå till[gratis provperiod](https://releases.aspose.com/).

### F5: Var kan jag söka hjälp eller samarbeta med communityn för Aspose.Page för .NET?

 A5: Besök[Aspose.Page för .NET-forum](https://forum.aspose.com/c/page/39) att få kontakt med samhället och få stöd.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
