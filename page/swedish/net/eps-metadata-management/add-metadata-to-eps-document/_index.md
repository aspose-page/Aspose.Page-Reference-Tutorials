---
date: 2026-01-20
description: Lär dig hur du använder Aspose Page EPS‑metadata för att förbättra organiseringen
  av EPS‑dokument med Aspose.Page för .NET. Lägg till metadata enkelt för förbättrad
  tillgänglighet och informationshämtning.
linktitle: Add Metadata to EPS Document
second_title: Aspose.Page .NET API
title: Lägg till EPS-metadata med Aspose.Page för .NET – aspose page eps metadata
url: /sv/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till EPS-metadata med Aspose.Page för .NET – aspose page** Ening; en licens krävs för produktion.  
- **Kan jag bearbeta flera EPS-filer i ett batch?** Ja – loopa helt enkelt igenom dina filer och tillämpa samma steg.  
- **Stödda .NET‑versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är aspose page eps metadata?

`aspose page eps metadata` avser XMP‑paketet (Extensible Metadata Platform) som Aspose.Page bäddar in i ett EPS‑dokument. Detta paket lagrar standard‑Dublin‑Core‑ och XMP‑egenskaper såsom skapare, skapelsedatum, format, titel och anpassade fält som du kan lägga till.

## Varför använda Aspose.Page för EPS-metadata?

- **Sökbarhet:** Metadata möjliggör snabb upptäckt i stora dokumentarkiv.  
- **Efterlevnad:** Spara författar‑ och skapelseinformation för att uppfylla regulatoriska krav.  
- **Automation:** Program kan läsa metadata för att driva efterföljande bearbetning (t.ex. routning, indexering).  

## Förutsättningar

Innan vi dyker ner i koden, se till att du har:

- **Aspose.Page för .NET‑bibliotek:** Ladda ner och installera Aspose.Page för .NET‑biblioteket från [here](https://releases.aspose.com/page/net/).  
- **Dokumentkatalog:** En mapp på din maskin där käll‑EPS‑filerna (`add_input.eps`) finns och där utdata (`add_output.eps`) kommer att sparas.  

## Importera namnrymder

I ditt .NET‑projekt, inkludera de nödvändiga namnrymderna så att du kan arbeta med EPS‑filer och XMP‑metadata.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Steg‑för‑steg‑guide

### Steg 1: Initiera EPS‑filens inmatningsström

Öppna käll‑EPS‑filen som en ström och skapa en `PsDocument`‑instans.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

### Steg 2: Hämta XMP‑metadata

Hämta det befintliga XMP‑paketet (eller ett tomt) från dokumentet.

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Steg 3: Kontrollera och sätt metadata‑värden

Du kan läsa befintliga värden och, om behövs, modifiera eller lägga till nya. Nedan är vanliga egenskaper du kanske vill inspektera.

#### Hämta CreatorTool‑värde

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

#### Hämta CreateDate‑värde

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

#### Hämta Format‑värde

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

#### Hämta Titel‑värde

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

#### Hämta Creator‑värde

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

#### Hämta MetadataDate‑värde

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

> **Proffstips:** För att lägga till en ny egenskap, tilldela den helt enkelt till `xmp`‑dictionaryn, t.ex. `xmp["dc:description"] = new XmpValue("Sample EPS file");`.

### Steg 4: Spara EPS‑fil med ny XMP‑metadata

Efter att ha uppdaterat metadata, skriv dokumentet tillbaka till disk.

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## Vanliga problem & lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Ingen metadata visas efter sparning** | XMP‑paketet modifierades aldrig. | Se till att du tilldelar nya värden till `xmp` innan du anropar `Save`. |
| **Filåtkomst‑undantag** | In‑ eller utdatafilen är låst av en annan process. | Stäng eventuella visare/redigerare som kan ha EPS‑filen öppen. |
| **Metadata‑värden är tomma** | Den ursprungliga EPS‑filen saknar dessa XMP‑taggar. | Lägg till de saknade taggarna manuellt med `xmp["tag"] = new XmpValue("value");`. |

## Vanliga frågor

### Q1: Kan jag lägga till metadata till flera EPS‑dokument samtidigt?

**A:** Ja. Loopa igenom en samling av filsökvägar, tillämpa samma steg på varje `PsDocument` och spara resultaten.

### Q2: Finns det några begränsningar för storleken på EPS‑dokument som Aspose.Page för .NET kan hantera?

**A:** Biblioteket stödjer EPS‑filer av praktiskt taget vilken storlek som helst, men extremt stora filer kan kräva mer minne. Övervaka din applikations minnesanvändning när du bearbetar enorma dokument.

### Q3: Är XMP‑metadata standardiserad för alla EPS‑dokument?

**A:** XMP följer ett standardschema, men de faktiska fälten som finns beror på hur EPS‑filen ursprungligen skapades. Du kan alltid lägga till anpassade egenskaper om det behövs.

### Q4: Kan jag anpassa metadata‑fälten för att passa specifika krav?

**Metadata`‑dictionary andra relevanta01-20  
**Testad med:** Aspose.Page for .NET 24.11 (latest)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}