---
date: 2026-03-21
description: Lär dig hur du skapar PostScript‑dokument i C# med Unicode‑text med hjälp
  av Aspose.Page för .NET – ett snabbt sätt att förbättra dokumenthantering.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Skapa PostScript‑dokument i C# med Unicode‑text – Aspose.Page
url: /sv/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till text med Unicode‑sträng i PostScript (PS) med Aspose.Page

## Introduction

Om du behöver **create a PostScript document C#** och bädda in Unicode‑tecken, gör Aspose.Page for .NET processen enkel. I den här handledningen går vi igenom ett komplett, praktiskt exempel som visar hur du lägger till japansk text (eller någon Unicode‑sträng) i en PS‑fil, väljer ett anpassat teckensnitt och sparar resultatet. I slutet har du ett återanvändbart kodsnutt som du kan lägga in i vilket C#‑projekt som helst.

## Quick Answers
- **What does this tutorial cover?** Adding Unicode text to a PostScript file using Aspose.Page in C#. → **Vad täcker den här handledningen?** Lägga till Unicode‑text i en PostScript‑fil med Aspose.Page i C#.
- **Which library is required?** Aspose.Page for .NET (latest version). → **Vilket bibliotek krävs?** Aspose.Page for .NET (senaste versionen).
- **Do I need a special font?** Any TrueType/OpenType font that supports the desired Unicode range, e.g., *Arial Unicode MS*. → **Behöver jag ett speciellt teckensnitt?** Vilket TrueType/OpenType‑teckensnitt som helst som stödjer det önskade Unicode‑området, t.ex. *Arial Unicode MS*.
- **How many lines of code?** About 30 lines, split into clear steps. → **Hur många kodrader?** Ungefär 30 rader, uppdelade i tydliga steg.
- **Is a license needed?** A temporary license works for evaluation; a full license is required for production. → **Behövs en licens?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.

## What is “create postscript document c#”?

Att skapa ett PostScript‑dokument i C# innebär att programatiskt generera en .ps‑fil som följer PostScript‑språkspecifikationerna. Aspose.Page abstraherar de lågnivå‑detaljerna och låter dig fokusera på innehåll såsom text, grafik och teckensnitt.

## Why use Aspose.Page for Unicode text?

- **Full Unicode support** – rendera tecken från vilket språk som helst utan manuell kodning.
- **Device‑independent** – samma kod fungerar för PS, EPS och PDF‑utdata.
- **No external dependencies** – biblioteket hanterar teckensnittsladdning och glyf‑mappning internt.

## Prerequisites

- Grundläggande kunskap om C# och .NET‑utveckling.
- Aspose.Page for .NET‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- En mapp som innehåller de teckensnitt du planerar att använda (t.ex. *Arial Unicode MS*).

## Import Namespaces

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Document Directory and Fonts Folder

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Step 2: Create Output Stream for PostScript Document

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Step 3: Add Unicode Text with Custom Font

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Step 4: Close the Current Page

```csharp
document.ClosePage();
```

## Step 5: Finalize and Save the Document

```csharp
document.Save();
```

## Common Issues and Solutions

- **Font not found** – Säkerställ att sökvägen `AdditionalFontsFolders` pekar på mappen som innehåller .ttf/.otf‑filerna och att teckensnittsnamnet matchar exakt.
- **Garbage characters** – Verifiera att källsträngen är kodad som UTF‑8 i din C#‑källfil (använd `#pragma warning disable 1591` om det behövs).
- **File not created** – Kontrollera skrivbehörigheter på `dataDir` och att strömmen korrekt frigörs (`using`‑blocket hanterar detta).

## Frequently Asked Questions

**Q: Can I use Aspose.Page for .NET with other programming languages?**  
A: Aspose.Page är främst designat för .NET, men det finns Java‑motsvarigheter tillgängliga.

**Q: How do I obtain a temporary license for Aspose.Page for .NET?**  
A: Besök [Temporary License](https://purchase.aspose.com/temporary-license/) för att skaffa en tillfällig licens.

**Q: Is there a community forum for Aspose.Page discussions?**  
A: Ja, besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för community‑stöd.

**Q: What formats can Aspose.Page for .NET work with?**  
A: Aspose.Page stödjer olika format, inklusive XPS, PS, EPS, PDF och fler.

**Q: Can I customize the appearance of the added text?**  
A: Ja, du kan anpassa teckensnitt, storlek, färg och andra egenskaper för texten i Aspose.Page.

## Conclusion

I den här handledningen har vi demonstrerat hur man **create a PostScript document C#** och bäddar in Unicode‑text med Aspose.Page. Genom att följa stegen ovan kan du snabbt integrera flerspråkig textrendering i vilken .NET‑applikation som helst, vilket ger dig full kontroll över dokumentgenerering och layout.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}