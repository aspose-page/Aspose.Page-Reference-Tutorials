---
date: 2026-01-12
description: Lär dig hur du modifierar XPS-dokument med Aspose.Page för .NET och upptäck
  hur du lägger till text i XPS-filer med enkla kodexempel.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Ändra XPS-dokument med Aspose.Page för .NET
url: /sv/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifiera XPS-dokument med Aspose.Page för .NET

## Introduktion

Välkommen till vår steg‑för‑steg‑guide om **hur man modifierar xps‑dokument** med Aspose.Page för .NET. Oavsett om du behöver infoga en signatur, lägga till ett vattenmärke eller helt enkelt placera anpassad text på en sida, visar den här handledningen exakt **hur man lägger till text** i ett XPS‑dokument på några minuter. Vi går igenom varje kodrad, förklarar varför varje steg är viktigt och ger dig tips för att undvika vanliga fallgropar.

### Snabba svar
- **Vad täcker den här handledningen?** Lägga till signaturtexten ("Confirmed") på valda sidor i en XPS‑fil.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (senaste versionen).  
- **Behöver jag en licens?** En tillfällig licens fungerar för testning; en fullständig licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Ungefär 10 minuter för en grundläggande signaturinsättning.

## Vad innebär att modifiera ett XPS-dokument?

XPS (XML Paper Specification) är Microsofts fast‑layout‑dokumentformat, liknande PDF. Att modifiera ett XPS‑dokument betyder att programatiskt ändra dess visuella innehåll – lägga till text, bilder eller former – utan att konvertera filen till ett annat format. Aspose.Page erbjuder en rik objektmodell som låter dig redigera XPS‑filer direkt från din .NET‑kod.

## Varför använda Aspose.Page för att modifiera XPS-dokument?

* **Full kontroll** – arbeta med sidor, glyfer, penslar och transformationer på låg nivå.  
* **Inga externa beroenden** – ren .NET‑bibliotek, ingen Office‑ eller Adobe‑komponent behövs.  
* **Plattformsoberoende** – körs på Windows, Linux och macOS via .NET Core.  
* **Robust prestanda** – hanterar stora dokument effektivt och stödjer avancerad typografi.

## Förutsättningar

Innan du börjar, se till att du har följande:

- **Aspose.Page för .NET** – Installera NuGet‑paketet eller ladda ner biblioteket från den officiella dokumentationen **[here](https://reference.aspose.com/page/net/)**.  
- **Input XPS file** – Skaffa ett exempel‑XPS‑dokument (t.ex. `input1.xps`) från **[Aspose releases page](https://releases.aspose.com/page/net/)**.  
- **Working directory** – Skapa en mapp på din maskin för att lagra in‑ och utdatafiler och notera dess fullständiga sökväg; du kommer att tilldela denna sökväg till variabeln `dir` i koden.  
- **Development environment** – Visual Studio 2019/2022, .NET Framework 4.7.2 eller senare, eller något .NET Core/5/6‑projekt.

Nu när allt är klart, låt oss dyka ner i koden.

## Importera namnrymder

I ditt .NET‑projekt, börja med att importera de nödvändiga namnrymderna för Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Steg 1: Öppna XPS-dokumentström

Vi öppnar käll‑XPS‑filen som en ström och skapar ett `XpsDocument`‑objekt som representerar hela dokumentet.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Proffstips:* Wrappa strömmen i ett `using`‑block för att säkerställa att filhandtaget frigörs automatiskt.

## Steg 2: Skapa signaturtext

Därefter skapar vi en solid‑färgsborste som kommer att användas för att måla signatur‑glyphs.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Du kan ändra `Color.BlueViolet` till vilken `System.Drawing.Color` som helst som matchar ditt varumärke.

## Steg 3: Definiera sidor och lägg till signatur

Vi specificerar vilka sidor som ska få signaturen och lägger sedan till glyphs på varje sida.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Varför dessa koordinater?* X‑ och Y‑värdena mäts i punkter (1/72 tum). Justera dem för att placera texten exakt där du vill ha den i sidlayouten.

## Steg 4: Spara ändringar till XPS-dokument

Sist, skriv tillbaka det modifierade dokumentet till disk.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Den nya filen `input1_out.xps` innehåller nu “Confirmed”-signaturen på sidor 1‑3.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|----------|
| **Signaturen syns inte** | Fel koordinater eller sidan är inte vald | Verifiera att `SelectActivePage` anropas för varje sida och justera X/Y‑värdena. |
| **Undantag på `AddGlyphs`** | Typsnittet är inte installerat på servern | Se till att det angivna typsnittet (t.ex. Arial) finns tillgängligt, eller bädda in ett eget typsnitt med `document.AddFont`. |
| **Utdatafilen är korrupt** | Strömmen stängdes inte korrekt | Använd `using`‑satser för alla strömmar och anropa `document.Dispose()` om det behövs. |
| **Prestandaförsämring på stora filer** | Laddar hela dokumentet i minnet | Bearbeta sidor i batcher eller använd `XpsLoadOptions` med strömalternativ (om tillgängligt i nyare versioner). |

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med de senaste .NET‑ramverken?**  
A: Ja, Aspose.Page uppdateras regelbundet för att stödja .NET Framework 4.5+, .NET Core 3.1+, .NET 5 och .NET 6.

**Q: Kan jag anpassa typsnittet och stilen på den tillagda texten?**  
A: Absolut. Ändra parametrarna för `AddGlyphs` (typsnittsnamn, storlek, `FontStyle`) för att passa din design.

**Q: Finns det några storleksgränser för XPS‑filer?**  
A: Aspose.Page kan hantera stora dokument, men minnesanvändningen ökar med filstorleken. För mycket stora filer, överväg att bearbeta sidor individuellt.

**Q: Hur får jag en tillfällig licens för Aspose.Page?**  
A: Du kan skaffa en tillfällig licens **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Var kan jag få hjälp eller ansluta till Aspose‑gemenskapen?**  
A: Besök **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** för att ställa frågor och dela erfarenheter.

## Slutsats

I den här handledningen har vi demonstrerat hur man **modifierar xps‑dokument** genom att lägga till anpassad signaturtext med Aspose.Page för .NET. Du har nu en solid grund för att infoga vilken text, vattenmärke eller annotation som helst på specifika sidor i ett XPS‑dokument. Experimentera med olika typsnitt, färger och positioner för att uppfylla ditt programs varumärkeskrav, och utforska det bredare Aspose.Page‑API‑et för avancerad grafik och layoutfunktionalitet.

---

**Senast uppdaterad:** 2026-01-12  
**Testat med:** Aspose.Page 24.11 för .NET (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}