---
title: Lägg till namngivet värde med Aspose.Page
linktitle: Lägg till namngivet värde
second_title: Aspose.Page .NET API
description: Lär dig hur du lägger till namngivna värden till EPS-filer i .NET med Aspose.Page. Denna omfattande handledning guidar dig genom processen steg för steg.
type: docs
weight: 12
url: /sv/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## Introduktion

När det gäller dokumentbehandling med .NET framstår Aspose.Page som ett kraftfullt verktyg för att hantera EPS-filer. Aspose.Page ger utvecklare möjlighet att manipulera XMP-metadata, vilket underlättar uppgifter som att lägga till namngivna värden. Denna handledning guidar dig genom processen att lägga till namngivna värden till en EPS-fil med hjälp av Aspose.Page på ett steg-för-steg sätt.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

- Grundläggande kunskaper i programmeringsspråket C#.
- En integrerad utvecklingsmiljö (IDE) som Visual Studio installerad.
-  Aspose.Page för .NET-biblioteket. Om den inte är installerad kan du ladda ner den från[här](https://releases.aspose.com/page/net/).

## Importera namnområden

Låt oss först importera de nödvändiga namnrymden till din C#-kod. Dessa namnutrymmen är viktiga för att få tillgång till funktionerna som tillhandahålls av Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Steg 1: Initiera EPS File Input Stream

 Det första steget innebär att initiera ingångsströmmen för EPS-filen. Byta ut`"Your Document Directory"` med sökvägen till din dokumentkatalog:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Steg 2: Hämta XMP-metadata

Hämta XMP-metadata från EPS-filen. Om EPS-filen saknar XMP-metadata kommer en ny att skapas, fylld med värden från PS-metadatakommentarer:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Steg 3: Ändra XMP-metadatavärden

Låt oss nu göra ändringar i XMP-metadata. I det här exemplet lägger vi till ett namngivet värde till "xmpTPg:MaxPageSize"-strukturen:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Steg 4: Spara EPS-fil med ändrad XMP-metadata

Spara EPS-filen med den uppdaterade XMP-metadatan. Skapa en utdataström och spara den modifierade EPS-filen:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Slutsats

Grattis! Du har framgångsrikt lagt till ett namngivet värde till en EPS-fil med Aspose.Page i .NET. Denna handledning har gått igenom de väsentliga stegen och visat upp enkelheten och effektiviteten hos Aspose.Page i dokumentmanipulation.

## FAQ's

### F1: Är Aspose.Page kompatibel med olika EPS-filversioner?

S1: Aspose.Page stöder olika EPS-filversioner, vilket säkerställer kompatibilitet med ett brett utbud av dokument.

### F2: Kan jag använda Aspose.Page för kommersiella projekt?

 S2: Ja, Aspose.Page kommer med en kommersiell licens, och du kan köpa den[här](https://purchase.aspose.com/buy).

### F3: Finns det en gratis testversion tillgänglig för Aspose.Page?

 S3: Ja, du kan utforska Aspose.Page med en gratis provperiod tillgänglig[här](https://releases.aspose.com/).

### F4: Hur kan jag få stöd eller få kontakt med Aspose-communityt?

 A4: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) att få stöd och få kontakt med samhället.

### F5: Vad är en tillfällig licens och hur kan jag få en?

 S5: Om du behöver en tillfällig licens för test- eller utvärderingsändamål kan du skaffa en[här](https://purchase.aspose.com/temporary-license/).