---
date: 2026-06-30
description: Lär dig hur du skapar XPS-dokument .NET och lägger till bildfyllda glyfer
  eller främmande bilder med Aspose.Page för .NET på några enkla steg.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Lägg till bildfylld glyf och främmande bild
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument .NET – Lägg till bildfylld glyf och främmande bild med Aspose.Page
url: /sv/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument .NET – Lägg till bildfylld glyf & främmande bild med Aspose.Page

## Introduktion

I .NET‑utveckling är **create XPS document .NET**‑uppgifter vanliga när du behöver högkvalitativ, upplösningsoberoende grafik. Aspose.Page för .NET gör detta enkelt och låter dig berika XPS‑filer med bildfyllda glyfer eller hämta bilder från ett annat XPS‑dokument. I slutet av den här handledningen kommer du att veta hur du skapar två XPS‑dokument, fyller glyfer med bilder och återanvänder dessa bilder i flera dokument – perfekt för att generera fakturor, certifikat eller annat visuellt rikt innehåll.

## Snabba svar
- **Vad stödjer Aspose.Page?** Över 25 bildformat och möjlighet att bearbeta XPS‑filer upp till 500 MB utan full minnesladdning.  
- **Hur många kodrader behövs för att lägga till en bildfylld glyf?** Endast två rader: skapa en `ImageBrush` och tilldela den till en `Glyph`.  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens tar bort utvärderingsvattenstämplar.  
- **Vilka .NET‑versioner är kompatibla?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan jag återanvända teckensnitt från ett annat XPS?** Absolut – du kan importera teckensnittssamlingen från det första dokumentet till det andra.

## Hur skapar du ett XPS‑dokument med Aspose.Page .NET?

Läs in Aspose.Page‑biblioteket, skapa en `XpsDocument`, lägg till en sida och anropa `Save` – det är hela arbetsflödet i tre koncisa satser. API‑et hanterar automatiskt sidstorlek, DPI och resurshantering, så du behöver inte hantera lågnivå‑XPS‑strukturer själv. Detta tillvägagångssätt skalar från en enkelsidig flyer till kataloger med flera hundra sidor.

## Förutsättningar

Innan du börjar, se till att du har:

- **Aspose.Page for .NET** – ladda ner det från [here](https://releases.aspose.com/page/net/).  
- **A .NET IDE** – Visual Studio, Rider eller VS Code med C#‑tillägget.  
- **A folder for your documents** – vi kommer att referera till den som **Your Document Directory** i kodsnuttarna.

## Importera namnrymder

`Aspose.Page.XPS`‑namnrymden tillhandahåller kärnklasser för XPS‑dokument, medan `Aspose.Page.XPS.XpsModel` innehåller modelelement såsom glyfer och penslar. Importera dem högst upp i din fil:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Vad är en bildfylld glyf?

En glyf är en vektorform som kan renderas med en solid färg, gradient eller en bildpensel. När du applicerar en `ImageBrush` målas glyfens inre med den angivna bilden, vilket möjliggör komplexa visuella effekter utan att rasterisera hela sidan.

## Steg 1: Skapa det första XPS‑dokumentet

`XpsDocument` representerar ett XPS‑paket och är startpunkten för att skapa och spara XPS‑filer. Börja med att skapa det första XPS‑dokumentet som ska innehålla de bildfyllda glyferna.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Steg 2: Lägg till glyfer i det första dokumentet

`XpsGlyphs` definierar en samling glyfer (texttecken) som kan placeras på en sida. Lägg till glyfer i det första dokumentet och ange teckensnitt, storlek, stil och position.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Steg 3: Fyll glyfer med en bildpensel

`ImageBrush` målar ett område med en bild, vilket möjliggör mönster eller bilder att fylla former. Fyll glyferna med en bildpensel och använd en bild från din datamapp.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Steg 4: Skapa det andra XPS‑dokumentet

`XpsDocument` används för att skapa en ny XPS‑fil som kan innehålla sidor, resurser och innehåll. Skapa nu det andra XPS‑dokumentet som ska inkorporera glyfer från det första dokumentet.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Steg 5: Lägg till glyfer med teckensnittet från det första dokumentet

`Font` representerar ett teckensnitt som används för att rendera text i ett XPS‑dokument. Lägg till glyfer i det andra dokumentet med teckensnittet som extraherats från det första dokumentet. Genom att dela teckensnittssamlingen håller du filstorleken låg och säkerställer visuell konsistens.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Steg 6: Skapa en bildpensel från fyllningen i det första dokumentet

`ImageBrush` kan skapas från en befintlig fyllning för att återanvända samma bild i flera dokument. Skapa en bildpensel från fyllningen i det första dokumentet och använd den för att fylla glyferna i det andra dokumentet. Denna “främmande bild”-teknik låter dig återanvända grafik utan att duplicera källfilen.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Steg 7: Spara dokumenten

`Save` skriver XPS‑paketet till en fil och bäddar in alla resurser. Spara både det första och det andra XPS‑dokumentet i utdata‑mappen. `Save`‑metoden skriver XPS‑paketet, bäddar in alla resurser och bevarar de bildfyllda glyferna.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Vanliga problem och lösningar

| Problem | Varför det händer | Lösning |
|---------|-------------------|--------|
| **Bild visas inte inuti glyf** | `ImageBrush` skapades med en felaktig URI eller bildens storlek överstiger glyfens gränser. | Verifiera bildens sökväg och eventuellt sätt `ImageBrush.Stretch = Stretch.Uniform`. |
| **Teckensnitt saknas i det andra dokumentet** | Teckensnittresurser exporterades inte från den första XPS‑filen. | Använd `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` innan du lägger till glyfer. |
| **Prestandaförsämring vid stora filer** | Stora bilder laddas in i minnet för varje glyf. | Återanvänd en enda `ImageBrush`‑instans för alla glyfer, eller minska bildens upplösning innan användning. |

## Vanliga frågor

### Q1: Kan jag använda olika bildformat för att fylla glyfer?

A1: Ja, Aspose.Page stödjer PNG, JPEG, BMP, GIF, TIFF och fler – över 25 format totalt.

### Q2: Hur kan jag anpassa glyfernas utseende ytterligare?

A2: Utforska egenskaper som `Glyph.Stroke`, `Glyph.FillOpacity` och `Glyph.Transform` för att justera konturer, transparens och rotation.

### Q3: Är Aspose.Page lämplig för att hantera stora dokumentuppsättningar?

A3: Absolut. Biblioteket bearbetar XPS‑filer med flera hundra sidor med hjälp av streaming, vilket håller minnesanvändningen under 100 MB även för 500‑sidiga dokument.

### Q4: Kan jag tillämpa olika stilar på enskilda glyfer?

A4: Ja, varje `Glyph`‑instans har sina egna `Fill`, `Stroke` och `Transform`‑egenskaper, vilket möjliggör styling per glyf.

### Q5: Vilka är fördelarna med att använda Aspose.Page jämfört med andra XPS‑verktyg?

A5: Aspose.Page stödjer 25+ bildformat, bearbetar filer upp till 500 MB utan full minnesladdning och erbjuder ett 100 % .NET‑native API – vilket eliminerar behovet av COM‑interop eller externa verktyg.

---

**Senast uppdaterad:** 2026-06-30  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa XPS-dokument – Aspose.Page för .NET](/page/net/document-creation/)
- [Lägg till bild i XPS-dokument med Aspose.Page för .NET](/page/net/image-management/add-image-to-xps-document/)
- [Lägg till glyfklon och ändra färg med Aspose.Page för .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}