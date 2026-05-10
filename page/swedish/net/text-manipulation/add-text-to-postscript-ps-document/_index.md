---
date: 2026-03-21
description: Lär dig hur du fyller i text och lägger till text i PS‑dokument med Aspose.Page
  för .NET. Steg‑för‑steg‑guide med kodexempel.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Hur man fyller i text i PostScript (PS)-dokument med Aspose.Page
url: /sv/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man fyller text i PostScript (PS) dokument med Aspose.Page

## Introduktion

Om du behöver **how to fill text** i en PostScript (PS)-fil, gör Aspose.Page för .NET det enkelt. Oavsett om du genererar rapporter, fakturor eller anpassad grafik, är tillägg och formatering av text ett grundläggande krav. I den här handledningen går vi igenom hela processen—från att konfigurera miljön till att spara det slutliga PS-dokumentet—så att du tryggt kan lägga till text i PS-filer i dina .NET-applikationer.

## Snabba svar
- **Vad betyder “fill text”?** Det renderar tecken med en solid pensel och målar glyferna direkt på sidan.  
- **Kan jag använda anpassade typsnitt?** Ja—Aspose.Page stöder anpassade typsnitt via funktionen `add custom font ps`.  
- **Hur sparar jag PS-dokumentet?** Anropa `document.Save()` efter att ha stängt sidan; detta skriver filen till disk (`save ps document`).  
- **Stöds “fill and stroke text”?** Absolut; använd `FillAndStrokeText` för att applicera både fyllning och kontur.  
- **Vilka .NET-versioner krävs?** Alla .NET Framework 4.5+ eller .NET Core/5/6+ runtime.

## Vad är “how to fill text” i ett PS-dokument?

Att fylla text betyder att måla tecknen med en solid färg (eller pensel) utan kontur. I PostScript motsvaras detta av `fill`‑operatorn. Aspose.Page abstraherar detta till enkla metoder som `FillText` och `FillAndStrokeText`.

## Varför använda Aspose.Page för att lägga till anpassade font ps?

- **Full font support** – systemtypsnitt och externa TrueType/OpenType‑typsnitt fungerar direkt.  
- **Precise positioning** – du styr X/Y‑koordinater, storlek och stil.  
- **Rich styling** – kombinera fyllningar, konturer och pennor för effekter som “fill and stroke text”.  
- **Cross‑platform** – fungerar på Windows, Linux och macOS med samma API.

## Förutsättningar

Innan du börjar, se till att du har:

- **Aspose.Page for .NET** – ladda ner biblioteket från [Aspose.Page .NET-dokumentationen](https://reference.aspose.com/page/net/).  
- **Document Directory** – en mapp på din maskin där käll- och utdata‑PS‑filerna kommer att ligga (refereras till som *Your Document Directory* i koden).  
- **Fonts Folder** – en undermapp som innehåller eventuella anpassade typsnitt du planerar att använda.

## Importera namnrymder

First, import the required namespaces so the compiler knows where to find the classes we’ll use:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Steg‑för‑steg‑guide

### Steg 1: Skapa utdata‑ström för PS‑dokument  

Vi öppnar en `FileStream` som kommer att innehålla den genererade PS‑filen, konfigurerar `PsSaveOptions` för att peka på vår anpassade typsnittsmapp och skapar en `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Proffstips:** Behåll `using`‑blocket för att säkerställa att strömmen stängs automatiskt, vilket också avslutar PS‑filen (`save ps document`).

### Steg 2: Fyll text med ett systemtypsnitt  

Här demonstrerar vi den grundläggande **how to fill text**‑operationen med det inbyggda *Times New Roman*-typsnittet.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Steg 3: Fyll text med ett anpassat typsnitt  

Om du behöver ett specifikt utseende, ladda ett anpassat typsnitt från typsnittsmappen med `ExternalFontCache.FetchDrFont`. Detta uppfyller kravet **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Steg 4: Kontur (Stroke) text med ett systemtypsnitt  

Konturering ritar glyfens kontur. Kombinera den med en fyllning för en “fill and stroke”-effekt.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Varför detta är viktigt:** `FillAndStrokeText`‑anropet visar hur man **fill and stroke text** i ett enda steg, vilket ger dig rikare typografisk kontroll.

### Steg 5: Konturera text med ett anpassat typsnitt  

Samma kontureringsteknik fungerar med vilket anpassat typsnitt du har laddat.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Steg 6: Stäng sidan och spara dokumentet  

Avslutningen är enkel: stäng den aktuella sidan och anropa `Save()` för att skriva PS‑filen till disk.

```csharp
document.ClosePage();
document.Save();
}
```

> **Resultat:** Du hittar `AddText_outPS.ps` i *Your Document Directory*, som innehåller både fylld och konturerad text renderad med system‑ och anpassade typsnitt.

## Vanliga problem och lösningar

| Problem | Lösning |
|-------|----------|
| **Custom font not found** | Verifiera att typsnittsfilen (.ttf/.otf) finns i mappen som refereras av `AdditionalFontsFolders`. |
| **Text appears at wrong position** | Justera X/Y‑koordinaterna som skickas till `FillText`/`OutlineText`. Kom ihåg att PostScript använder punkter (1/72 tum). |
| **Colors look different** | Säkerställ att du använder `SolidBrush` eller `Pen` med korrekta `Color`‑värden. |
| **Document not saving** | Bekräfta att `using`‑blocket avslutas utan undantag och att applikationen har skrivbehörighet till mål‑mappen. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Page med andra .NET‑bibliotek?**  
A: Ja, Aspose.Page integreras smidigt med andra .NET‑komponenter, vilket gör att du kan kombinera PDF-, bild‑ eller diagram‑bibliotek i samma lösning.

**Q: Är anpassade typsnitt nödvändiga för denna process?**  
A: Även om systemtypsnitt fungerar bra, ger anpassade typsnitt dig full designfrihet och är användbara när varumärkes‑specifik typografi krävs.

**Q: Är Aspose.Page lämplig för storskalig dokumentbehandling?**  
A: Absolut. Biblioteket är optimerat för hög genomströmning och kan hantera tusentals PS‑filer effektivt.

**Q: Kan jag ändra positionen för texten i PS‑dokumentet?**  
A: Självklart—ändra helt enkelt de numeriska X/Y‑värdena i anropen till `FillText` eller `OutlineText`.

**Q: Var kan jag söka hjälp för frågor relaterade till Aspose.Page?**  
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för att ansluta till communityn och få experthjälp.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-03-21  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose