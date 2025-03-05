---
title: Ändra namngett värde med Aspose.Page för .NET
linktitle: Ändra namngett värde
second_title: Aspose.Page .NET API
description: Lär dig hur du ändrar namngivna värden i EPS-filer med Aspose.Page för .NET. Anpassa XMP-metadata utan ansträngning för skräddarsydd dokumentbehandling.
type: docs
weight: 16
url: /sv/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## Introduktion

en värld av dokumentbehandling framstår Aspose.Page för .NET som ett kraftfullt verktyg för att manipulera EPS-filer. En av nyckelfunktionerna den erbjuder är möjligheten att ändra namngivna värden inom XMP-metadata. Denna handledning guidar dig genom processen att ändra ett namngivet värde med Aspose.Page för .NET, vilket ger dig möjlighet att anpassa dina EPS-filer efter dina specifika behov.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Page for .NET: Se till att du har Aspose.Page for .NET-biblioteket installerat. Om inte kan du ladda ner den[här](https://releases.aspose.com/page/net/).

- Dokumentkatalog: Ha en utsedd katalog för dina EPS-filer där du kan utföra de namngivna värdeändringarna.

## Importera namnområden

I ditt .NET-projekt måste du importera de nödvändiga namnområdena för att komma åt funktionaliteten som tillhandahålls av Aspose.Page. Lägg till följande namnrymder i din kod:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Låt oss nu dela upp koden i flera steg för en heltäckande förståelse:

## Steg 1: Initiera EPS File Input Stream

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// Exend:1
```

det här steget ställer vi in ingångsströmmen för EPS-filen som du vill ändra. Se till att ersätta "Din dokumentkatalog" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Hämta XMP-metadata

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Hämta befintlig XMP-metadata från EPS-filen. Om EPS-filen inte innehåller XMP-metadata kommer en ny att genereras med värden från PS-metadatakommentarer.

## Steg 3: Ändra XMP-metadatavärden

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Här visar vi att två namngivna värden ändras inom strukturen "xmpTPg:MaxPageSize". Du kan anpassa detta efter dina specifika krav.

## Steg 4: Spara EPS-fil med ändrad XMP-metadata

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Spara den modifierade EPS-filen till utdataströmmen. Filen kommer nu att återspegla ändringarna som gjorts i XMP-metadata.

## Slutsats

Med den här handledningen har du lärt dig hur du använder Aspose.Page för .NET för att ändra namngivna värden inom XMP-metadata i EPS-filer. Denna funktion öppnar upp en värld av möjligheter för att skräddarsy och skräddarsy dina dokument för att möta specifika krav.

## FAQ's

### F1: Kan jag använda Aspose.Page för .NET med andra dokumentformat?

S1: Ja, Aspose.Page stöder olika dokumentformat, inklusive EPS, XPS och PDF.

### F2: Finns det en testversion tillgänglig för Aspose.Page för .NET?

 A2: Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/).

### F3: Var kan jag hitta mer dokumentation om Aspose.Page för .NET?

 A3: Se dokumentationen[här](https://reference.aspose.com/page/net/).

### F4: Hur kan jag få en tillfällig licens för Aspose.Page för .NET?

 A4: Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).

### F5: Vilka supportalternativ finns tillgängliga för Aspose.Page för .NET-användare?

 S5: Besök communityforumet[här](https://forum.aspose.com/c/page/39) för stöd och diskussioner.