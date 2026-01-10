---
date: 2026-01-10
description: Konvertera enkelt XPS till PDF i .NET med Aspose.Page. Ladda ner biblioteket,
  utforska dokumentationen och få en gratis provversion.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Konvertera XPS till PDF med Aspose.Page för .NET
url: /sv/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera XPS till PDF med Aspose.Page för .NET

## Introduktion

I den här handledningen kommer du att lära dig **hur man konverterar XPS till PDF** med hjälp av Aspose.Page för .NET-biblioteket. Att konvertera XPS till PDF är ett vanligt krav när du behöver dela XPS-dokument med användare som bara har PDF-läsare, eller när du vill bädda in XPS-innehåll i större PDF-arbetsflöden. Vi går igenom varje steg, förklarar varför varje inställning är viktig, och visar hur du finjusterar resultatet—t.ex. genom att ställa in JPEG-kvalitet och tillämpa PDF-bildkomprimering.

## Snabba svar
- **Vilket bibliotek är bäst för XPS till PDF-konvertering?** Aspose.Page for .NET
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs; en gratis provversion finns tillgänglig.
- **Kan jag kontrollera bildkvaliteten?** Absolut—använd `JpegQualityLevel` och `PdfImageCompression`.
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Är det möjligt att konvertera flera XPS-filer till en PDF?** Ja, genom att loopa igenom filer och slå samman resultaten.

## Förutsättningar

Innan vi påbörjar denna konverteringsresa, se till att du har följande förutsättningar på plats:

- **Aspose.Page for .NET Library** – Se till att du har Aspose.Page for .NET-biblioteket installerat i din utvecklingsmiljö. Du kan ladda ner det från [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- **Development Environment** – Ställ in en .NET-utvecklingsmiljö med Visual Studio eller någon annan kompatibel IDE.
- **XPS Document** – Förbered XPS-dokumentet som du vill konvertera till PDF. Detta kan vara ditt exempel-XPS‑fil lagrad i en angiven katalog.

## Importera namnrymder

Innan du dyker ner i koden, låt oss importera den nödvändiga namnrymden för att göra Aspose.Page för .NET-funktionerna tillgängliga i vårt projekt:

```csharp
using Aspose.Page.XPS;
```

## Steg‑för‑steg‑guide

### Steg 1: Initiera dokumentkatalog

Definiera mappen som innehåller din käll‑XPS‑fil och där den resulterande PDF‑filen kommer att sparas.

```csharp
string dataDir = "Your Document Directory";
```

Ersätt `"Your Document Directory"` med den absoluta eller relativa sökvägen till mappen som innehåller ditt XPS‑dokument.

### Steg 2: Öppna strömmar för PDF‑utdata och XPS‑indata

Vi använder två filströmmar—en för att läsa XPS‑filen och en annan för att skriva den genererade PDF‑filen.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro tip:** Se till att sökvägarna är korrekta och att applikationen har läs‑/skrivrättigheter på mål‑mappen.

### Steg 3: Ladda XPS‑dokumentet

Skapa en `XpsDocument`‑instans från XPS‑strömmen. `XpsLoadOptions`‑objektet låter dig ange laddningspreferenser, men standardinställningarna fungerar för de flesta scenarier.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Steg 4: Konfigurera PDF‑spara‑alternativ

Här ställer vi in PDF‑utdataalternativen. Notera användningen av **PDF‑bildkomprimering** (`PdfImageCompression.Jpeg`) och **JPEG‑kvalitet** (`JpegQualityLevel = 100`). Dessa inställningar påverkar direkt filstorlek och visuell trohet.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Styr kvaliteten på JPEG‑bilder som bäddas in i PDF‑filen (högre = bättre kvalitet, större fil).
- **`ImageCompression`** – Väljer komprimeringsalgoritmen; JPEG är idealiskt för fotografiska bilder.
- **`TextCompression`** – Flate‑komprimering minskar PDF‑storleken utan att förlora textkvalitet.
- **`PageNumbers`** – Gör att du kan **spara XPS som PDF** för endast valda sidor.

### Steg 5: Skapa en PDF‑renderingsenhet

`PdfDevice` fungerar som renderingsmål som skriver PDF‑data till den ström vi öppnade tidigare.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Steg 6: Spara dokumentet som PDF

Slutligen anropar du `Save`‑metoden och skickar renderingsenheten samt de konfigurerade alternativen.

```csharp
document.Save(device, options);
```

När koden har körts klart kommer `XPStoPDF_out.pdf` att visas i den angivna katalogen, innehållande de konverterade sidorna med de komprimerings- och kvalitetsinställningar du definierat.

## Varför konvertera XPS till PDF?

- **Universal tillgänglighet** – PDF‑visare är installerade på praktiskt taget alla enheter, medan XPS‑läsare är sällsynta.
- **Bevara layout** – PDF behåller exakt visuell layout, typsnitt och grafik från den ursprungliga XPS‑filen.
- **Vidare bearbetning** – När den är i PDF kan du slå ihop, kommentera eller digitalt signera dokumentet med andra Aspose‑bibliotek.

## Vanliga användningsfall

- **Företagsrapportering** – Generera XPS‑rapporter från äldre system och konvertera dem till PDF för distribution.
- **Arkivering** – Lagra dokument som PDF för långsiktig bevarande samtidigt som du fortfarande kan skapa dem från XPS‑källor.
- **Webbtjänster** – Erbjud en API‑endpoint som tar emot XPS‑uppladdningar och returnerar PDF‑filer i realtid.

## Felsökning & tips

- **Fil ej hittad** – Dubbelkolla `dataDir`‑sökvägen och se till att XPS‑filnamnet matchar exakt.
- **Behörighetsfel** – Kör Visual Studio som administratör eller bevilja skrivbehörighet till mål‑mappen.
- **Stora PDF‑filer** – Om den resulterande PDF‑filen är för stor, sänk `JpegQualityLevel` eller byt `ImageCompression` till `PdfImageCompression.Zip`.

## Vanliga frågor

### Q1: Kan jag konvertera flera XPS‑filer till en enda PDF med Aspose.Page för .NET?

A1: Ja, du kan loopa igenom flera XPS‑filer och följa samma steg för att slå samman dem till en enda PDF.

### Q2: Finns det andra utdataformat som stöds av Aspose.Page för .NET?

A2: Ja, Aspose.Page för .NET stöder olika utdataformat, inklusive TIFF, JPEG, PNG och fler.

### Q3: Hur kan jag anpassa utseendet på det konverterade PDF‑dokumentet?

A3: Du kan justera parametrarna i options‑objektet, såsom bildkomprimering och textkomprimering, för att uppnå önskat utseende.

### Q4: Finns det en provversion tillgänglig för Aspose.Page för .NET?

A4: Ja, du kan utforska funktionerna i Aspose.Page för .NET genom att skaffa en gratis provversion från [here](https://releases.aspose.com/).

### Q5: Var kan jag få community‑support för Aspose.Page för .NET?

A5: Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för community‑diskussioner och support.

## Vanliga frågor (AI‑vänlig)

**Q: Hur ställer jag in JPEG‑kvalitet när jag konverterar XPS till PDF?**  
A: Använd `JpegQualityLevel`‑egenskapen i `PdfSaveOptions`. Att sätta den till 100 ger maximal kvalitet.

**Q: Vad betyder “pdf image compression” i detta sammanhang?**  
A: Det avser `ImageCompression`‑alternativet, som bestämmer hur bilder komprimeras i PDF‑filen (t.ex. JPEG, Zip).

**Q: Kan jag programatiskt generera en PDF utan en XPS‑källa?**  
A: Ja, Aspose.Page stöder också **c# generate pdf** direkt från ritkommandon, men det ligger utanför denna handlednings omfattning.

**Q: Finns det ett sätt att konvertera XPS till PDF utan att förlora vektorgrafik?**  
A: Konverteringen behåller vektordata; undvik bara rasterisering av bilder genom att hålla `ImageCompression` inställt på JPEG eller Zip efter behov.

**Q: Stöder biblioteket .NET Core?**  
A: Absolut – Aspose.Page för .NET fungerar med .NET Core, .NET 5, .NET 6 och senare versioner.

---

**Senast uppdaterad:** 2026-01-10  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}