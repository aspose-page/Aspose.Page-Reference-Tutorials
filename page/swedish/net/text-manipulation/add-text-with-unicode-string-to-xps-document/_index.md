---
title: Lägg till text med Unicode-sträng till XPS-dokument med Aspose.Page
linktitle: Lägg till text med Unicode-sträng till XPS-dokument
second_title: Aspose.Page .NET API
description: Utforska kraften i Aspose.Page för .NET med vår steg-för-steg-guide för att lägga till Unicode-text till XPS-dokument.
type: docs
weight: 12
url: /sv/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Introduktion

I det ständigt föränderliga landskapet för .NET-utveckling framstår Aspose.Page som ett kraftfullt verktyg för att hantera XPS-dokument. Bland dess många funktioner är möjligheten att lägga till text med Unicode-strängar till ett XPS-dokument en värdefull funktionalitet. Den här steg-för-steg-guiden leder dig genom processen och säkerställer att du utnyttjar denna förmåga effektivt.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

- En grundläggande förståelse för .NET-utveckling.
- Visual Studio installerat på din dator.
-  Aspose.Page för .NET-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/page/net/).

## Importera namnområden

Till att börja med, se till att du importerar de nödvändiga namnrymden till ditt projekt. Detta kommer att tillhandahålla de klasser och funktioner som krävs för att arbeta med Aspose.Page. Här är de viktigaste namnområdena:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Konfigurera dokumentet

Skapa först ett nytt XPS-dokument där du lägger till Unicode-texten. Följ kodavsnittet nedan:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
// Skapa nytt XPS-dokument
XpsDocument doc = new XpsDocument();
```

## Steg 2: Lägg till Unicode-text

Låt oss nu lägga till Unicode-text till XPS-dokumentet. Det här exemplet använder typsnittet Arial, ställer in teckensnittsstorleken till 20 och placerar texten vid koordinater (400f, 200f). Unicode-strängen i detta fall är "TEN. rof SPX.esopsA". Kolla in kodavsnittet nedan:

```csharp
// Lägg till text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Steg 3: Spara dokumentet

När Unicode-texten har lagts till sparar du det resulterande XPS-dokumentet. Här är det sista steget:

```csharp
// Spara resulterande XPS-dokument
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Grattis! Du har framgångsrikt lagt till Unicode-text till ett XPS-dokument med Aspose.Page för .NET.

## Slutsats

I den här handledningen utforskade vi processen att lägga till Unicode-text till XPS-dokument med Aspose.Page för .NET. Denna funktion öppnar dörrar till mångsidigt och dynamiskt dokumentskapande inom .NET-miljön.

## FAQ's

### F1: Är Aspose.Page kompatibel med de senaste .NET-ramverken?

S1: Ja, Aspose.Page uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET-ramverken.

### F2: Kan jag anpassa teckensnittsstilen och storleken när jag lägger till text?

A2: Absolut! Exempelkoden som tillhandahålls gör att du enkelt kan anpassa teckensnittsstil, storlek och andra attribut.

### F3: Var kan jag hitta ytterligare dokumentation för Aspose.Page?

 S3: Du kan hänvisa till dokumentationen[här](https://reference.aspose.com/page/net/) för omfattande information och exempel.

### F4: Finns det några gratisresurser för att komma igång med Aspose.Page?

 A4: Ja, du kan utforska[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd och diskussioner.

### F5: Finns det en testversion innan du gör ett köp?

 A5: Visst! Du kan komma åt den kostnadsfria testversionen[här](https://releases.aspose.com/) innan du gör ett köp.