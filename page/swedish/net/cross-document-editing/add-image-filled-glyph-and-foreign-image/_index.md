---
title: Lägg till bildfylld glyph & utländsk bild med Aspose.Page .NET
linktitle: Lägg till bildfylld glyph & främmande bild
second_title: Aspose.Page .NET API
description: Lås upp kraften i dokumentbehandling i .NET med Aspose.Page. Lägg till bildfyllda glyfer utan ansträngning. Förbättra bilder och effektivisera ditt arbetsflöde.
type: docs
weight: 11
url: /sv/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---
## Introduktion

en värld av .NET-utveckling framstår Aspose.Page som en kraftfull verktygslåda för att hantera dokumentbearbetningsuppgifter. Denna handledning guidar dig genom processen att lägga till bildfyllda glyfer och införliva främmande bilder med Aspose.Page för .NET. I slutet av den här guiden har du en gedigen förståelse för hur du kan förbättra dina dokumentbehandlingsmöjligheter.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Page för .NET: Se till att du har Aspose.Page-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/page/net/).

- Utvecklingsmiljö: Konfigurera en fungerande .NET-utvecklingsmiljö med Visual Studio eller någon annan föredragen IDE.

- Dokumentkatalog: Skapa en katalog där du ska lagra dina dokument. Detta kommer att kallas "Din dokumentkatalog" i kodexemplen.

## Importera namnområden

I din .NET-applikation börjar du med att importera de nödvändiga namnområdena för att komma åt klasserna och metoderna som tillhandahålls av Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Skapa det första XPS-dokumentet

Börja med att skapa det första XPS-dokumentet med Aspose.Page. Detta dokument kommer att fungera som grunden för att lägga till bildfyllda glyfer.

```csharp
// ExStart:1
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";

// Skapa det första XPS-dokumentet
XpsDocument doc1 = new XpsDocument();
```

## Steg 2: Lägg till tecken i det första dokumentet

Lägg till glyfer i det första dokumentet och ange teckensnitt, storlek, stil och position.

```csharp
// Lägg till glyfer i det första dokumentet
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Steg 3: Fyll glyfer med en bildpensel

Fyll glyferna med en bildpensel och använd en bild från din datakatalog.

```csharp
// Fyll glyferna med en bildpensel
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Steg 4: Skapa det andra XPS-dokumentet

Skapa nu det andra XPS-dokumentet som kommer att innehålla glyfer från det första dokumentet.

```csharp
// Skapa det andra XPS-dokumentet
XpsDocument doc2 = new XpsDocument();
```

## Steg 5: Lägg till tecken med teckensnittet från det första dokumentet

Lägg till glyfer i det andra dokumentet med teckensnittet från det första dokumentet.

```csharp
// Lägg till glyfer med teckensnittet från det första dokumentet till det andra dokumentet
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Steg 6: Skapa en bildpensel från fyllningen av det första dokumentet

Skapa en bildpensel från fyllningen av det första dokumentet och använd den för att fylla glyferna i det andra dokumentet.

```csharp
// Skapa en bildpensel från fyllningen av det första dokumentet och fyll glyfer i det andra dokumentet
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Steg 7: Spara dokumenten

Spara både det första och andra XPS-dokumentet.

```csharp
// Spara det första XPS-dokumentet
doc1.Save(dataDir + "out1.xps");

// Spara det andra XPS-dokumentet
doc2.Save(dataDir + "out2.xps");
// Exend:1
```

## Slutsats

Grattis! Du har framgångsrikt lagt till bildfyllda glyfer och införlivat främmande bilder med Aspose.Page för .NET. Den här handledningen ger en grund för att förbättra dina dokumentbehandlingsmöjligheter, vilket öppnar upp för nya möjligheter för kreativa och visuellt tilltalande dokument.

## FAQ's

### F1: Kan jag använda olika bildformat för att fylla glyfer?

S1: Ja, Aspose.Page stöder olika bildformat. Säkerställ kompatibilitet med det valda bildformatet.

### F2: Hur kan jag anpassa utseendet på glyfer ytterligare?

S2: Utforska Aspose.Page-dokumentationen för ytterligare egenskaper och metoder för att finjustera glyfernas utseende.

### F3: Är Aspose.Page lämplig för att hantera stora dokumentuppsättningar?

A3: Aspose.Page är utformad för att hantera både små och stora dokumentuppsättningar effektivt.

### F4: Kan jag använda olika stilar på enskilda glyfer?

S4: Ja, du kan anpassa stilar för varje glyf oberoende, vilket ger en hög nivå av flexibilitet.

### F5: Vilka är fördelarna med att använda Aspose.Page framför andra dokumentbearbetningsverktyg?

A5: Aspose.Page erbjuder en omfattande uppsättning funktioner, utmärkt prestanda och omfattande dokumentation, vilket gör det till ett föredraget val för många utvecklare.