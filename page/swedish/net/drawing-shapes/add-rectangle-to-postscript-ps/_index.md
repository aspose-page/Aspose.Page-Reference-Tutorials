---
date: 2026-06-30
description: Lär dig hur du skapar postscript-dokument .net och lägger till rektanglar
  med Aspose.Page för .NET. Steg‑för‑steg‑guide med kodexempel.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Lägg till rektangel i PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Skapa PostScript-dokument .NET – Lägg till rektangel Aspose.Page
url: /sv/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till rektangel i PostScript (PS) med Aspose.Page för .NET

## Introduktion

Aspose.Page for .NET är ett bibliotek som möjliggör skapande och manipulering av PostScript-, EPS- och XPS-filer programmässigt. Om du vill **skapa postscript-dokument .net**, går den här handledningen igenom hur du lägger till rektanglar i ett PostScript-dokument med Aspose.Page, vilket ger dig en solid grund för rikare grafikgenerering.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Page for .NET.  
- **Kan jag skapa ett PostScript-dokument från början?** Ja – API:et låter dig bygga PS-filer programmässigt.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter för grundläggande former.

## Vad innebär att skapa ett postscript-dokument .net?

Att skapa ett PostScript-dokument i .NET betyder att programmässigt generera en `.ps`-fil som beskriver sidinnehåll—text, grafik eller former—med hjälp av Aspose.Page API. Detta tillvägagångssätt är idealiskt för server‑sidig grafikgenerering, automatiserad rapportskapning eller vilket scenario som helst där du behöver exakt kontroll över utdataformatet.

## Varför använda Aspose.Page för .NET?

Aspose.Page stödjer **30+ grafikprimitiver** och kan generera filer upp till **500 MB** utan att ladda hela dokumentet i minnet, vilket ger högpresterande rendering på Windows, Linux och macOS. Det ger dig full kontroll över former, färger och linjer samtidigt som behovet av att skriva låg‑nivå PostScript‑kod elimineras.

- **Full kontroll över grafik** – rita former, sätt färger och applicera linjer utan att behöva hantera låg‑nivå PS‑syntax.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS‑runtime.  
- **Inga externa beroenden** – biblioteket hanterar all PS‑generering internt.  
- **Rik dokumentation & exempel** – kom snabbt igång.

## Förutsättningar

- **Aspose.Page for .NET Library** – ladda ner och installera från [here](https://releases.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio, VS Code eller någon .NET‑kompatibel IDE.

## Importera namnrymder

`Aspose.Page`-namnrymden exponerar de kärnklasser du behöver, såsom `Document`, `Page`, `SolidBrush` och `Pen`. Importera den innan du börjar koda.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss nu dela upp exemplet i tydliga, numrerade steg.

## Steg 1: Ställ in din dokumentkatalog

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den mapp där du vill spara den resulterande PS-filen.

## Steg 2: Skapa utdataström för PostScript-dokumentet

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Denna ström pekar på **AddRectangle_outPS.ps**. Du kan gärna byta namn på filen eller ändra platsen efter behov.

## Steg 3: Ställ in sparalternativ och skapa PS-dokumentet

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Här instruerar vi Aspose.Page att använda A4-sidstorlek och skapa ett enkelsidigt dokument.

## Steg 4: Lägg till en fylld rektangel

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Vi definierar en rektangel vid (250, 100) med bredd 150 och höjd 100, sätter en orange pensel och fyller formen.

## Steg 5: Lägg till en konturerad rektangel

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

En andra rektangel skapas längre ner på sidan, den här gången med en röd 3‑punkts linje.

## Steg 6: Stäng sidan och spara dokumentet

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Att stänga sidan slutför ritningen, och `Save()` skriver PS-filen till disk.

## Hur skapar man postscript-dokument .net?

`Document` är huvudklassen som representerar en PostScript-fil i Aspose.Page. `SaveOptions` specificerar inställningar såsom sidstorlek och utdataformat för dokumentet. Ladda `Document`‑objektet, konfigurera `SaveOptions` för en A4-sida, rita dina former med `SolidBrush` eller `Pen`, och anropa sedan `document.Save()`—hela arbetsflödet kräver bara några få kodrader och körs på vilken stödjande .NET‑runtime som helst. Detta mönster låter dig generera fullt kompatibla PostScript-filer utan att röra rå PS‑syntax.

## Hur genererar man en postscript-fil

Använd Aspose.Page:s `SaveOptions`-klass för att ange utdataformatet som PostScript (`SaveFormat.PS`). Biblioteket strömmar innehållet direkt till en fil eller minnesström, vilket gör att du kan generera stora dokument effektivt utan onödig minnesanvändning.

## Vanliga problem & tips

- **Felaktig filsökväg** – Säkerställ att `dataDir` slutar med en sökvägsseparator (`\\` eller `/`) eller använd `Path.Combine`.  
- **Saknad licens** – I en produktionsmiljö, applicera din Aspose-licens innan du skapar dokumentet för att undvika utvärderingsvattenmärken.  
- **Färgens synlighet** – Om rektangeln visas tom, kontrollera att pensel- eller linjefärgerna kontrasterar mot sidbakgrunden.

## Vanliga frågor

**Q:** Kan jag anpassa färgerna på rektanglarna?  
**A:** Absolut. Ändra `Color.Orange` eller `Color.Red`-värdena i `SolidBrush`- och `Pen`-konstruktörerna till vilken `System.Drawing.Color` du föredrar.

**Q:** Är Aspose.Page kompatibel med andra dokumentformat?  
**A:** Ja. Förutom PostScript stödjer Aspose.Page även generering av XPS och EPS.

**Q:** Hur kan jag lägga till text i samma dokument?  
**A:** Använd `TextFragment`-klassen för att placera text på önskade koordinater, och anropa sedan `document.Draw(textFragment)`.

**Q:** Var kan jag hitta fler exempel och fullständig API‑referens?  
**A:** Utforska dokumentationen [here](https://reference.aspose.com/page/net/) och gå med i communityn på [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Kan jag prova Aspose.Page innan jag köper?  
**A:** Ja, ladda ner en gratis provversion [here](https://releases.aspose.com/). För förlängd utvärdering, överväg en [temporary license](https://purchase.aspose.com/temporary-license/).

**Senast uppdaterad:** 2026-06-30  
**Testad med:** Aspose.Page 24.12 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man skapar PostScript-dokument med Aspose.Page för .NET](/page/net/document-creation/create-postscript-document/)
- [Lägg till bild i PostScript (PS)-dokument med Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Lägg till text i PostScript (PS)-dokument med Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}