---
date: 2026-03-21
description: Lär dig hur du lägger till Unicode‑text i ett XPS‑dokument med Aspose.Page
  för .NET. Den här guiden visar hur du skapar ett XPS‑dokument i C# och lägger till
  text med Unicode‑strängar med Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Hur man lägger till Unicode‑text i XPS‑dokument med Aspose.Page
url: /sv/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till Unicode‑text i XPS‑dokument med Aspose.Page

## Introduktion

Om du behöver **how to add unicode** tecken i en XPS‑fil, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen som krävs för att **create XPS document C#**‑stil med Aspose.Page för .NET och demonstrerar **aspose page add text**‑funktionen med en Unicode‑sträng. I slutet har du ett fullt funktionellt XPS‑dokument som korrekt visar Unicode‑text från höger till vänster (RTL).

## Snabba svar
- **Vad täcker handledningen?** Lägga till Unicode‑text i ett XPS‑dokument med Aspose.Page för .NET.  
- **Vilket språk används?** C# (compatible with .NET Framework and .NET Core).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag ändra teckensnitt eller storlek?** Ja – exemplet använder Arial 20 pt, men vilket installerat teckensnitt som helst fungerar.  
- **Ingår RTL‑stöd?** Setting `BidiLevel = 1` enables right‑to‑left rendering for Unicode strings.

## Vad är “how to add unicode” i XPS?

Att lägga till Unicode‑text innebär att infoga tecken från vilket språk som helst—arabiska, hebreiska, kinesiska osv.—i ett XPS‑dokument. Aspose.Page:s `XpsGlyphs`‑klass hanterar den lågnivå‑glyph‑placeringen, medan egenskapen `BidiLevel` styr textriktningen för RTL‑skript.

## Varför använda Aspose.Page för att lägga till text?

- **Full .NET‑integration** – fungerar med .NET Framework, .NET Core, .NET 5/6+.  
- **Inga externa beroenden** – ren hanterad kod, ingen COM‑interop.  
- **Rik typografistöd** – teckensnitt, stilar, färger och bidi‑text.  
- **Hög prestanda** – skapar och sparar XPS‑filer snabbt, idealiskt för server‑sidig generering.

## Förutsättningar

- Grundläggande kunskap om C# och .NET‑utveckling.  
- Visual Studio (valfri nyare version).  
- Aspose.Page för .NET‑biblioteket – ladda ner det från [here](https://releases.aspose.com/page/net/).

## Importera namnrymder

Först, importera namnrymderna som ger dig åtkomst till XPS‑modellen och ritverktygen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Ställ in dokumentet – create XPS document C#

Skapa ett nytt XPS‑dokument som kommer att innehålla Unicode‑texten.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Steg 2: Lägg till Unicode‑text – aspose page add text

Nu lägger vi till den faktiska Unicode‑strängen. I det här exemplet använder vi teckensnittet Arial, storlek 20, och placerar texten vid (400 f, 200 f). `BidiLevel` = 1 talar om för renderaren att behandla strängen som höger‑till‑vänster.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Steg 3: Spara dokumentet

Slutligen, skriv XPS‑filen till disk.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Grattis! Du har framgångsrikt lagt till **how to add unicode**‑text i ett XPS‑dokument med Aspose.Page för .NET.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| Text visas förvrängd | Teckensnittet stödjer inte Unicode‑intervallet | Använd ett teckensnitt som innehåller de nödvändiga glyph‑tecknen (t.ex. Arial Unicode MS). |
| RTL‑text är fortfarande vänster‑till‑höger | `BidiLevel` är inte satt eller är 0 | Se till att `glyphs.BidiLevel = 1;` för RTL‑skript. |
| Filen sparas inte | Ogiltig `dataDir`‑sökväg | Verifiera att katalogen finns och att programmet har skrivbehörighet. |

## Vanliga frågor och svar

**Q: Är Aspose.Page kompatibel med de senaste .NET‑ramverken?**  
A: Ja, Aspose.Page uppdateras regelbundet för att stödja .NET Framework, .NET Core och .NET 5/6+.

**Q: Kan jag anpassa teckensnittsstil och storlek när jag lägger till text?**  
A: Absolut! Metoden `AddGlyphs` låter dig ange vilken teckensnittsfamilj, storlek och `FontStyle` du behöver.

**Q: Var kan jag hitta ytterligare dokumentation för Aspose.Page?**  
A: Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/page/net/) för omfattande API‑detaljer.

**Q: Finns det några gratisresurser för att komma igång med Aspose.Page?**  
A: Ja, utforska community‑forumet på [Aspose.Page forum](https://forum.aspose.com/c/page/39) för tips, exempel och stöd från andra.

**Q: Finns det en provversion tillgänglig innan köp?**  
A: Självklart! Ladda ner den kostnadsfria provversionen från [here](https://releases.aspose.com/) för att utvärdera biblioteket.

---

**Senast uppdaterad:** 2026-03-21  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}