---
date: 2026-01-20
description: Lägg enkelt till sidnummer i PDF när du sammanslår XPS‑dokument till
  högkvalitativa PDF‑filer med Aspose.Page för .NET. Följ vår steg‑för‑steg‑guide
  för att konvertera XPS till PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Lägg till sidnummer i PDF – Slå ihop XPS till PDF med Aspose.Page
url: /sv/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till sidnummer PDF – Slå ihop XPS till PDF med Aspose.Page

## Introduktion

Om du behöver **lägga till sidnummer i PDF** när du slår ihop XPS‑filer, gör Aspose.Page för .NET processen smärtfri. I den här handledningen går vi igenom ett komplett, produktionsklart exempel som konverterar ett XPS‑dokument till en PDF av hög kvalitet, låter dig styra bildkomprimering och automatiskt infogar sidnummer i den slutgiltiga PDF‑filen. I slutet har du ett återanvändbart kodsnutt som du kan lägga in i vilket C#‑projekt som helst.

## Snabba svar
- **Kan jag lägga till sidnummer när jag slår ihop XPS till PDF?** Ja – egenskapen `PdfSaveOptions.PageNumbers` gör exakt det.  
- **Vilket bibliotek hanterar konverteringen?** Aspose.Page för .NET.  
- **Behöver jag en licens för produktionsbruk?** En giltig Aspose.Page‑licens krävs; en tillfällig licens finns tillgänglig för testning.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+ och .NET 5/6+.  
- **Är högkvalitativ bildutmatning möjlig?** Absolut – sätt `JpegQualityLevel` till 100 och välj `PdfImageCompression.Jpeg`.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:

- Aspose.Page för .NET: Se till att du har Aspose.Page‑biblioteket installerat. Du kan ladda ner det från [here](https://releases.aspose.com/page/net/).
- Dokumentfiler: Ha XPS‑dokumentet (`input.xps`) redo i den angivna katalogen.

## Importera namnrymder

I ditt .NET‑projekt, inkludera de nödvändiga namnrymderna för att arbeta med Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Detta steg säkerställer att du har åtkomst till de klasser och metoder som krävs för dokumentkonverteringen.

## Hur man lägger till sidnummer i PDF när man slår ihop XPS‑dokument

`PdfSaveOptions.PageNumbers`‑samlingen låter dig ange exakt vilka sidor (eller sidintervall) som ska visas i den resulterande PDF‑filen. Genom att fylla den med de sidnummer du vill ha, infogar Aspose.Page automatiskt rätt numrering.

### Steg 1: Initiera strömmar

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Detta steg innebär att konfigurera in‑ och utdata‑strömmarna för XPS‑ och PDF‑filerna. Se till att rätt sökvägar och filnamn används.

### Steg 2: Ladda XPS‑dokument

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Här laddar vi XPS‑dokumentet i `XpsDocument`‑objektet, vilket förbereder det för vidare bearbetning.

### Steg 3: Initiera sparalternativ (slå ihop XPS till PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Anpassa `PdfSaveOptions`‑objektet efter dina preferenser, ange parametrar som bildkomprimering, textkomprimering och de **sidnummer** du vill ha i den slutgiltiga PDF‑filen. Genom att sätta `JpegQualityLevel` till 100 säkerställer du **PDF‑bilder av hög kvalitet**.

### Steg 4: Skapa renderingsenhet

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` är verktyget som ansvarar för att rendera XPS‑dokumentet till PDF‑format.

### Steg 5: Spara dokumentet (c# xps till pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Slutligen sparar du dokumentet med hjälp av renderingsenheten och de angivna alternativen. Den resulterande PDF‑filen kommer att innehålla de valda sidorna med automatiskt tillagda sidnummer.

## Varför använda Aspose.Page för denna konvertering?

- **Tillförlitlighet** – Hanterar komplexa XPS‑funktioner utan förlust av kvalitet.  
- **Prestanda** – Ström‑baserad bearbetning undviker att ladda hela filer i minnet.  
- **Flexibilitet** – Finjusterad kontroll över bildkvalitet, komprimering och sidnumrering.  
- **Plattformsoberoende** – Fungerar på Windows, Linux och macOS med .NET Core.

## Vanliga problem och lösningar

| Problem | Lösning |
|-------|----------|
| **Utdata‑PDF är tom** | Verifiera att XPS‑filens sökväg är korrekt och att filen inte är skadad. |
| **Sidnummer visas inte** | Se till att `PageNumbers` är inställt på rätt noll‑baserade sidindex (t.ex. `new int[] {1,2,6}`). |
| **Bilder med låg kvalitet** | Öka `JpegQualityLevel` och välj `PdfImageCompression.Jpeg`. |
| **Stora XPS‑filer orsakar minnespress** | Bearbeta XPS‑filen i mindre delar eller öka applikationens minnesgräns. |

## Vanliga frågor

### Q1: Kan jag slå ihop flera XPS‑filer till en enda PDF?

Ja, det kan du. Justera helt enkelt `PageNumbers`‑parametern i `PdfSaveOptions` för att inkludera önskade sidor från olika XPS‑filer, eller ladda varje XPS sekventiellt och anropa `document.Save` på samma `PdfDevice`.

### Q2: Finns en tillfällig licens tillgänglig för Aspose.Page för .NET?

Ja, du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/) för teständamål.

### Q3: Finns det några begränsningar för filstorlek när du använder Aspose.Page för dokumentkonvertering?

Aspose.Page för .NET har inga strikta begränsningar för filstorlek, men optimal prestanda uppnås med rimligt stora filer. För mycket stora XPS‑dokument, överväg att bearbeta dem i strömmar för att minska minnesförbrukningen.

### Q4: Kan jag anpassa den resulterande PDF‑filen ytterligare, t.ex. genom att lägga till vattenstämplar eller kommentarer?

Ja, Aspose.Page för .NET erbjuder omfattande funktioner för PDF‑manipulation. Efter konvertering kan du använda Aspose.PDF‑biblioteket för att lägga till vattenstämplar, kommentarer eller andra förbättringar.

### Q5: Stöder Aspose.Page för .NET plattformsoberoende utveckling?

Ja, Aspose.Page för .NET är designat för att fungera sömlöst på olika plattformar, inklusive Windows, Linux och macOS, när det används med .NET Core eller .NET 5/6.

**Senast uppdaterad:** 2026-01-20  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}