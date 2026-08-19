---
date: 2026-03-03
description: Lär dig hur du ställer in anpassad sidstorlek och lägger till en andra
  PS-sida i ett PostScript-dokument med Aspose.Page för .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Ställ in anpassad sidstorlek i PS‑dokument med Aspose.Page
url: /sv/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till sida i PostScript (PS)-dokument med Aspose.Page

## Introduktion

I .NET-utveckling ger möjligheten att **ange anpassad sidstorlek** och **lägga till en andra PS-sida** i ett PostScript (PS)-dokument dig finjusterad kontroll över layouten för genererade utskrifter, rapporter eller grafik. Aspose.Page för .NET gör denna uppgift enkel med ett rent, objektorienterat API. I den här handledningen kommer du att lära dig hur du skapar en flersidig PS-fil, definierar en anpassad storlek för varje sida och sparar resultatet – allt med bara några rader C#-kod.

## Snabba svar
- **Kan jag ange en anpassad sidstorlek?** Ja – skicka bara bredd och höjd när du öppnar en sida.  
- **Hur lägger jag till en andra PS-sida?** Anropa `document.OpenPage(width, height)` en andra gång.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Behöver jag en licens?** En tillfällig licens fungerar för testning; en full licens krävs för produktion.  
- **Var kan jag ladda ner Aspose.Page?** Från den officiella nedladdningssidan som länkas nedan.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

- Kunskap om .NET-utveckling.  
- Visual Studio installerat på din maskin.  
- Aspose.Page för .NET-biblioteket, som du kan ladda ner [här](https://releases.aspose.com/page/net/).  
- Din föredragna dokumentkatalog för testning.

## Importera namnrymder

Se till att du inkluderar de nödvändiga namnrymderna i ditt projekt för att komma åt funktionerna som tillhandahålls av Aspose.Page. I det givna exemplet är namnrymderna implicit inkluderade, men det är viktigt att dubbelkolla och göra justeringar baserat på din projektstruktur.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Steg 1: Ställ in ditt projekt

Skapa ett nytt .NET-projekt i Visual Studio och konfigurera de nödvändiga inställningarna. Se till att referera Aspose.Page‑biblioteket i ditt projekt.

## Ställ in anpassad sidstorlek och lägg till en andra PS-sida

Detta avsnitt visar exakt hur du **anger anpassad sidstorlek** för varje sida och hur du **lägger till en andra ps-sida** i samma dokument.

### Steg 2: Initiera dokumentet

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Steg 3: Lägg till den första sidan (standardstorlek)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Steg 4: Lägg till den andra sidan med en annan (anpassad) storlek

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Steg 5: Spara dokumentet

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Följ dessa steg noggrant, så kommer du att framgångsrikt **ange anpassad sidstorlek** och lägga till en **andra PS-sida** i ett PostScript-dokument med hjälp av Aspose.Page för .NET.

## Varför detta är viktigt

- **Precisionslayout** – Anpassade sidmått låter dig matcha skrivarens specifikationer eller skapa unika broschyrformat.  
- **Flera sidor** – Att lägga till en andra sida (eller fler) möjliggör flersidiga rapporter utan externa sammanslagningsverktyg.  
- **Plattformsoberoende** – Den genererade PS-filen kan renderas på vilken PostScript‑kompatibel enhet som helst eller konverteras till PDF senare.

## Vanliga fallgropar & felsökning

- **Felaktig sökväg** – Se till att `dataDir` slutar med en sökvägsseparator eller använd `Path.Combine`.  
- **Licensproblem** – Utan en giltig licens kan biblioteket lägga till ett vattenmärke eller begränsa antalet sidor.  
- **Enhetsförvirring** – Bredd och höjd mäts i punkter (1 punkt = 1/72 tum). Justera därefter.

## Vanliga frågor

**Q1: Är Aspose.Page kompatibel med olika dokumentformat?**  
A1: Aspose.Page fokuserar främst på manipulation av PostScript-dokument. För andra format kan du utforska Aspose‑bibliotek som är anpassade för specifika behov.

**Q2: Kan jag anpassa sidstorleken i Aspose.Page?**  
A2: Absolut! Som demonstrerat i handledningen kan du ange olika storlekar för varje sida enligt dina krav.

**Q3: Var kan jag hitta fler exempel och dokumentation?**  
A3: Besök [dokumentationen](https://reference.aspose.com/page/net/) för omfattande information och en mängd exempel.

**Q4: Hur får jag en tillfällig licens för Aspose.Page?**  
A4: Gå till [denna länk](https://purchase.aspose.com/temporary-license/) för att skaffa en tillfällig licens för teständamål.

**Q5: Var kan jag få community‑support eller ställa frågor?**  
A5: Gå med i [Aspose.Page community‑forum](https://forum.aspose.com/c/page/39) för att komma i kontakt med andra utvecklare, dela erfarenheter och söka hjälp.

---

**Senast uppdaterad:** 2026-03-03  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}