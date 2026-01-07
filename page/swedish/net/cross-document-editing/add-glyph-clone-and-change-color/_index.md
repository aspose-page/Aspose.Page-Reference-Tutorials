---
date: 2026-01-07
description: Lär dig hur du skapar XPS-dokument, lägger till glyfkloner, använder
  en solid färgborste och sparar XPS-filen med Aspose.Page för .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument – Lägg till glyphklon och ändra färg med Aspose.Page för
  .NET
url: /sv/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument – Lägg till glyph-klon och ändra färg med Aspose.Page för .NET

## Introduktion

Välkommen till den här steg‑för‑steg‑guiden som visar dig **hur du skapar XPS‑dokument**‑filer, klonar glyphs och ändrar deras färger med Aspose.Page för .NET. Oavsett om du bygger dynamiska rapporter, fakturor eller anpassad grafik, ger dig behärskning av dessa tekniker möjlighet att producera visuellt rika XPS‑utdata utan att lämna .NET‑ekosystemet.

## Snabba svar
- **Vad är huvudmålet?** Skapa ett XPS‑dokument, lägga till glyph‑kloner och ändra deras färger.  
- **Vilket bibliotek används?** Aspose.Page för .NET.  
- **Behöver jag en licens?** En tillfällig licens finns tillgänglig för utvärdering; en fullständig licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur sparar jag resultatet?** Använd `Save`‑metoden för att skriva XPS‑filen till disk.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar:

- Grundläggande kunskap i C#‑programmeringsspråket.  
- Visual Studio eller någon annan föredragen C#‑utvecklingsmiljö installerad.  
- Aspose.Page för .NET‑biblioteket. Du kan ladda ner det [here](https://releases.aspose.com/page/net/).  
- Bekantskap med XPS‑dokumentformatet.

## Importera namnrymder

För att komma igång, inkludera de nödvändiga namnrymderna i ditt C#‑projekt:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hur man skapar XPS-dokument och lägger till glyph-kloner

### Steg 1: Ställ in din dokumentkatalog

Börja med att konfigurera katalogen där dina dokument ska lagras:

```csharp
string dataDir = "Your Document Directory";
```

### Steg 2: Skapa det första XPS-dokumentet

Låt oss nu skapa det första XPS‑dokumentet:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Steg 3: Lägg till glyphs i det första dokumentet

Lägg till glyphs i det första dokumentet med de angivna parametrarna:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Steg 4: Fyll glyphs med en solid färgpensel

Fyll glyphs i det första dokumentet med en **solid color brush**, till exempel grön:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Steg 5: Skapa det andra XPS-dokumentet

Skapa nu det andra XPS‑dokumentet:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Steg 6: Hur man lägger till glyph-klon i ett annat dokument

Klona glyphs från det första dokumentet och lägg till dem i det andra dokumentet:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Steg 7: Hur man ändrar färg på den klonade glyphen

Ändra färgen på de klonade glyphs i det andra dokumentet, till exempel till röd. Detta demonstrerar **hur man ändrar färg** på en glyph efter kloning:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Steg 8: Spara XPS-fil – Första dokumentet

Spara det första XPS‑dokumentet till den mapp du definierade tidigare:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Steg 9: Spara XPS-fil – Andra dokumentet

Spara det andra XPS‑dokumentet:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Grattis! Du har framgångsrikt **skapat XPS‑dokument**‑filer, lagt till glyph‑kloner och ändrat deras färger med Aspose.Page för .NET.

## Varför använda glyph-kloning och färgändringar?

- **Återanvändning:** Klona befintliga glyphs för att återanvända komplexa vektorformer utan att definiera om dem.  
- **Prestanda:** Minskar bearbetningstid jämfört med att återskapa glyphs från början.  
- **Designflexibilitet:** Använd olika `SolidColorBrush`‑instanser på samma glyph för att uppnå varierande visuella teman.  
- **Redigering över dokument:** Klona glyphs över flera XPS‑filer, vilket möjliggör konsekvent varumärkesprofil i rapporter.

## Vanliga problem & felsökning

| Problem | Lösning |
|-------|----------|
| **Clone returns null** | Ensure the source glyph (`glyphs`) is added to the first document before cloning. |
| **Color does not change** | Cast `glyphs.Fill` to `XpsSolidColorBrush` before setting the `Color` property (as shown in Step 7). |
| **File not saved** | Verify that `dataDir` points to a valid, writable folder and that you have appropriate file‑system permissions. |
| **Unexpected glyph size** | Adjust the font size parameter (second argument in `AddGlyphs`) to scale the glyph appropriately. |

## Vanliga frågor

**Q1: Kan jag använda Aspose.Page för .NET med andra dokumentformat?**  
A1: Aspose.Page för .NET är specifikt utformat för att arbeta med XPS‑dokument. Om du behöver manipulera andra format kan du utforska andra Aspose‑bibliotek som är anpassade för dessa format.

**Q2: Finns en tillfällig licens tillgänglig för Aspose.Page för .NET?**  
A2: Ja, du kan skaffa en tillfällig licens för teständamål. Besök [here](https://purchase.aspose.com/temporary-license/) för mer information.

**Q3: Hur kan jag få support eller söka hjälp för eventuella problem?**  
A3: Besök gärna [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att komma i kontakt med communityn och söka hjälp.

**Q4: Finns det några begränsningar i gratisprovversionen?**  
A4: Gratisprovversionen har vissa begränsningar, och det rekommenderas att granska dokumentationen för detaljer innan användning.

**Q5: Var kan jag hitta omfattande dokumentation för Aspose.Page för .NET?**  
A5: Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/page/net/) för detaljerad information och exempel.

**Q6: Hur ändrar jag linjefärgen på en glyph istället för fyllningsfärgen?**  
A6: Använd `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` för att sätta en linjepensel.

**Q7: Kan jag lägga till flera glyph‑kloner i samma dokument?**  
A7: Ja, anropa `doc2.Add(glyphs.Clone());` upprepade gånger och justera positionerna efter behov.

**Senast uppdaterad:** 2026-01-07  
**Testat med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}