---
date: 2026-01-12
description: Lär dig hur du skapar XPS-dokument med Aspose.Page för .NET – en steg‑för‑steg‑guide
  för att generera högkvalitativa elektroniska dokument.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument med Aspose.Page för .NET
url: /sv/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument med Aspose.Page för .NET

## Introduktion

Välkommen till vår steg‑för‑steg‑guide om **hur man skapar XPS-dokument** med Aspose.Page för .NET. I den här handledningen kommer vi att utforska processen för att generera XPS‑filer, ett allmänt använt format för elektroniska dokument. Oavsett om du är en erfaren utvecklare eller precis har börjat med Aspose.Page, är den här guiden utformad för att hjälpa dig att smidigt skapa XPS-dokument med tydliga exempel och detaljerade förklaringar.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Page for .NET  
- **Kan jag köra detta på .NET Core?** Ja, biblioteket stödjer fullt ut .NET Core och .NET 5/6  
- **Hur många kodrader?** Mindre än 20 rader för att producera en grundläggande XPS‑fil  
- **Behöver jag en licens för testning?** En gratis provversion finns tillgänglig; en licens krävs för produktion  
- **Vilket format har utdata?** XPS (XML Paper Specification)  

## Så skapar du XPS-dokument med Aspose.Page för .NET

Nedan hittar du allt du behöver innan du börjar koda, följt av en kortfattad, numrerad genomgång.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

1. Aspose.Page för .NET-biblioteket: Ladda ner och installera Aspose.Page‑biblioteket från [nedladdningslänken](https://releases.aspose.com/page/net/).

2. Din dokumentkatalog: Välj eller skapa en katalog på ditt system där du vill spara de genererade XPS‑filerna.

Nu, låt oss hoppa in i handledningen!

## Importera namnrymder

För att använda Aspose.Page för .NET måste du importera de nödvändiga namnrymderna i ditt projekt. Följ dessa steg:

### Steg 1: Lägg till referens till Aspose.Page

I ditt projekt, lägg till en referens till Aspose.Page för .NET‑biblioteket. Du kan hitta den nödvändiga DLL‑filen i det nedladdade paketet.

### Steg 2: Importera namnrymder

Inkludera följande namnrymder i din kodfil:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nu när vi har ställt in förutsättningarna och importerat de nödvändiga namnrymderna, låt oss dela upp processen för att skapa ett XPS‑dokument i flera steg.

## Steg 1: Ange dokumentkatalog

```csharp
string dir = "Your Document Directory";
```

Se till att ersätta `"Your Document Directory"` med den faktiska sökvägen där du vill spara den genererade XPS‑filen.

## Steg 2: Skapa XPS-dokument

```csharp
XpsDocument xDocs = new XpsDocument();
```

Initiera ett nytt XPS‑dokument med `XpsDocument`‑klassen.

## Steg 3: Lägg till glyfer i dokumentet

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Använd `AddGlyphs`‑metoden för att lägga till glyfer (text) i dokumentet. Anpassa teckensnitt, storlek, stil och position efter behov.

## Steg 4: Ange fyllnadsfärg för glyfer

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Ange fyllnadsfärgen för de tillagda glyferna. I detta exempel använder vi svart, men du kan välja vilken färg som helst.

## Steg 5: Spara resultatet

```csharp
xDocs.Save(dir + "output.xps");
```

Spara slutligen XPS‑dokumentet till den angivna katalogen med önskat filnamn. Den resulterande XPS‑filen kommer att innehålla texten "Hello World!".

Grattis! Du har framgångsrikt skapat ett XPS‑dokument med Aspose.Page för .NET.

## Vanliga tips & fallgropar

- **Katalogsökväg** – Använd `Path.Combine(dir, "output.xps")` för att undvika saknade sökvägsavgränsare på olika operativsystem.  
- **Tillgänglighet för teckensnitt** – Det teckensnitt du anger måste vara installerat på maskinen där koden körs; annars kommer Aspose att ersätta det med ett standardteckensnitt.  
- **Flera sidor** – För att skapa flersidiga XPS‑filer, skapa ytterligare `XpsPage`‑objekt och lägg till innehåll på varje sida innan du sparar.

## Slutsats

I den här handledningen gick vi igenom processen för att skapa XPS‑dokument med Aspose.Page för .NET. Detta kraftfulla bibliotek erbjuder ett smidigt sätt att generera elektroniska dokument med lätthet. Experimentera med olika teckensnitt, stilar och innehåll för att anpassa dina XPS‑filer efter dina specifika behov.

## Vanliga frågor

### Q1: Kan jag använda anpassade teckensnitt i mitt XPS‑dokument?

A1: Ja, du kan ange teckensnittsfamilj och storlek när du lägger till glyfer i ditt XPS‑dokument.

### Q2: Är Aspose.Page kompatibel med .NET Core?

A2: Ja, Aspose.Page stödjer .NET Core, vilket gör att du kan använda det i plattformsoberoende applikationer.

### Q3: Hur kan jag lägga till bilder i ett XPS‑dokument?

A3: Aspose.Page tillhandahåller metoder för att lägga till bilder i ditt XPS‑dokument. Se dokumentationen för detaljerade exempel.

### Q4: Kan jag skapa flersidiga XPS‑dokument?

A4: Absolut! Du kan lägga till flera sidor i ett XPS‑dokument med hjälp av Aspose.Page‑biblioteket.

### Q5: Finns det en provversion tillgänglig?

A5: Ja, du kan utforska funktionerna i Aspose.Page genom att ladda ner [gratis provversion](https://releases.aspose.com/).

---

**Senast uppdaterad:** 2026-01-12  
**Testat med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}