---
date: 2026-03-21
description: Lär dig hur du skapar XPS‑dokument i .NET och lägger till text med Aspose.Page
  för .NET. Steg‑för‑steg‑guide för .NET‑utvecklare.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument i .NET och lägg till text med Aspose.Page
url: /sv/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument .NET och lägg till text med Aspose.Page

## Snabba svar
- **Vad täcker den här handledningen?** Lägga till text i ett nyss skapat XPS-dokument med Aspose.Page för .NET.  
- **Hur lång tid tar det?** Ungefär 5‑10 minuter för en grundläggande implementation.  
- **Vad är förutsättningarna?** .NET-utvecklingsmiljö och Aspose.Page-biblioteket.  
- **Krävs en licens?** Ja, en giltig Aspose.Page-licens behövs för produktionsanvändning.  
- **Kan den köras på .NET Core / .NET 6+?** Absolut – Aspose.Page stödjer alla senaste .NET-versioner.

## Vad innebär att skapa XPS-dokument .NET?

Att skapa ett XPS-dokument i .NET betyder att generera en fast layout‑fil som bevarar exakt hur ditt innehåll ser ut på olika enheter och skrivare. XPS (XML Paper Specification) är Microsofts öppna standard för sidbeskrivning, liknande PDF men helt XML‑baserad.

## Varför använda Aspose.Page för att lägga till text?

Aspose.Page erbjuder ett hög‑nivå, objekt‑orienterat API som döljer den lågnivå XPS‑markupen. Du kan lägga till text, grafik och former utan att behöva hantera rå XML, vilket gör utvecklingsprocessen snabbare och mindre felbenägen.

## Förutsättningar

- Aspose.Page för .NET: Se till att du har Aspose.Page‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page för .NET-dokumentationen](https://reference.aspose.com/page/net/).
- Utvecklingsmiljö: Ställ in din .NET‑utvecklingsmiljö. Om du ännu inte gjort det, följ installationsinstruktionerna i [dokumentationen](https://reference.aspose.com/page/net/).
- Dokumentkatalog: Skapa en katalog där du ska lagra dina dokument. Ersätt "Your Document Directory" i kodexemplet med den faktiska sökvägen.

Nu när vi har gått igenom grunderna, låt oss dyka ner i koden.

## Importera namnrymder

Först importerar du de nödvändiga namnrymderna för att kick‑starta projektet:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Skapa XPS-dokument .NET

Skapa ett nytt XPS-dokument som kommer att fungera som canvas för vår text.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Steg 2: Skapa en pensel för text

Definiera en solid‑färgad pensel som bestämmer textens färg. Här använder vi svart.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Steg 3: Lägg till glyfer (aspose.page add text)

Glyfer är den lågnivårepresentation av tecken i ett XPS-dokument. Detta anrop lägger till texten “Hello World!” på de angivna koordinaterna.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Steg 4: Spara det resulterande XPS-dokumentet

Spara dokumentet till disk så att du kan visa eller skriva ut det senare.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Genom att följa dessa steg har du framgångsrikt **skapat XPS-dokument .NET** och lagt till anpassad text med Aspose.Page.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Fil ej hittad** vid sparning | `dataDir` pekar på en icke‑existerande mapp | Se till att katalogen finns eller använd `Directory.CreateDirectory(dataDir)` innan du sparar. |
| **Text syns inte** | Penselfärgen matchar bakgrunden | Ändra `Color.Black` till en annan kontrasterande färg. |
| **Ej stödd teckensnitt** | Teckensnittet är inte installerat på maskinen | Använd ett teckensnitt som garanterat finns, eller bädda in teckensnittet med Aspose.Page:s funktioner för teckensnitts‑embedning. |

## Vanliga frågor

### Q1: Kan jag anpassa teckensnitt och storlek på den tillagda texten?

A1: Ja, du har full kontroll över teckensnitt och storlek. Justera parametrarna i `AddGlyphs`‑metoden därefter.

### Q2: Är Aspose.Page kompatibel med .NET Core?

A2: Absolut! Aspose.Page stödjer .NET Core, vilket säkerställer kompatibilitet med de senaste .NET-teknologierna.

### Q3: Finns det licenskrav för att använda Aspose.Page?

A3: Ja, du behöver en giltig licens. Utforska licensalternativ [här](https://purchase.aspose.com/buy).

### Q4: Hur kan jag få support eller hjälp?

A4: Besök [Aspose.Page-forumet](https://forum.aspose.com/c/page/39) för att komma i kontakt med communityn och få hjälp.

### Q5: Finns det en gratis provversion tillgänglig?

A5: Självklart! Du kan få en gratis provversion [här](https://releases.aspose.com/).

**Ytterligare frågor & svar**

**Q: Kan jag lägga till flera textblock på samma sida?**  
A: Ja, anropa helt enkelt `doc.AddGlyphs` flera gånger med olika koordinater.

**Q: Tillåter Aspose.Page textrotation?**  
A: Du kan applicera en transformationsmatris på `XpsGlyphs`‑objektet för att rotera eller skeva texten.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---