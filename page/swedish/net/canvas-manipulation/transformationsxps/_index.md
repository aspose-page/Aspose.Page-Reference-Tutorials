---
date: 2026-01-05
description: Lär dig hur du enkelt kan omvandla XPS‑dokument med Aspose.Page för .NET.
  Följ vår steg‑för‑steg‑guide för sömlösa transformationer.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Hur man transformerar XPS med Aspose.Page för .NET
url: /sv/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man transformerar XPS med Aspose.Page för .NET

## Introduktion

Välkommen till världen av Aspose.Page för .NET, ett kraftfullt bibliotek som låter dig utföra olika transformationer på XPS-dokument utan ansträngning. **I den här handledningen kommer du att upptäcka hur du transformerar XPS-dokument med Aspose.Page för .NET**, oavsett om du är en erfaren utvecklare eller precis har börjat. Vi går igenom varje steg, förklarar resonemanget bakom varje transformation och ger dig praktiska tips som du kan använda i riktiga projekt.

## Snabba svar
- **Vad kan du uppnå?** Skapa, flytta, skala och rotera XPS‑canvas‑element programatiskt.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (senaste versionen).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Stödda plattformar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för de grundläggande transformationerna som visas här.

## Vad är “how to transform xps”?

Frasen *how to transform xps* avser att programatiskt modifiera layout, storlek och orientering av element i ett XPS (XML Paper Specification)-dokument. Med Aspose.Page kan du applicera matris‑baserade transformationer på canvas‑objekt, vilket ger dig fin‑granulär kontroll över positionering, skalning och rotation utan att manuellt redigera XPS‑XML.

## Varför använda Aspose.Page för XPS‑transformationer?
- **Full .NET‑integration** – fungerar sömlöst med Visual Studio, Rider och andra IDE:er.  
- **Inga externa beroenden** – API:et hanterar alla låg‑nivå XPS‑detaljer åt dig.  
- **Rich transformation support** – flytta, skala, rotera och kombinera flera transformationer i ett enda anrop.  
- **Performance‑optimized** – lämplig för att generera rapporter, fakturor eller annan utskrivbar grafik i realtid.

## Förutsättningar

Innan vi börjar, se till att du har:

- **Aspose.Page for .NET Library** – ladda ner och installera det från den officiella dokumentationen: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio, Visual Studio Code eller någon annan .NET‑kompatibel IDE.  
- **Dokumentkatalog** – en mapp på din maskin där du läser/skriv XPS‑filer. Ersätt platshållaren i koden med den faktiska sökvägen.

Nu när vi har allt på plats, låt oss dyka in i koden.

## Importera namnrymder

Först importerar du namnrymderna som exponerar de Aspose.Page‑klasser du behöver:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hur man transformerar XPS – Steg‑för‑steg‑guide

### Steg 1: Skapa ett nytt XPS‑dokument

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Förklaring*: Vi börjar med att definiera mappen som innehåller våra källa‑ och utdatafiler, och skapar sedan ett tomt `XpsDocument`. Detta objekt blir canvas för alla efterföljande transformationer.

### Steg 2: Skapa en huvud‑canvas

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Varför detta är viktigt*: Huvud‑canvas fungerar som en behållare för alla andra canvas‑objekt. Genom att applicera ett litet offset säkerställer vi att innehållet inte klipps av vid sidans kant.

### Steg 3: Skapa en rektangel‑Path‑Geometry

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tips*: Path‑strängen följer den standard XPS‑path‑syntaxen (`M` för move, `L` för line, `Z` för close). Justera koordinaterna för att ändra rektangelns storlek.

### Steg 4: Lägg till en fyllning för rektanglar

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro‑tips*: Använd `CreateColor` med RGB‑värden för att matcha ditt varumärkespalett.

### Steg 5: Lägg till en ny canvas utan transformationer

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Här placerar vi helt enkelt en rektangel på sidan utan någon extra transformation — användbart som ett grundelement.

### Steg 6: Lägg till en ny canvas med Translate‑transformation

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Vad händer?* Den första matrisen flyttar rektangeln neråt med 200 enheter. Det efterföljande `Translate`‑anropet förflyttar den 500 enheter åt höger, vilket visar hur flera translationer kan kedjas ihop.

### Steg 7: Lägg till en ny canvas med dubbel skalnings‑transformation

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Varför skala?* Skalning med 2 dubblar rektangelns bredd och höjd, vilket låter dig skapa större grafik utan att omdefiniera geometrin.

### Steg 8: Lägg till en ny canvas med Rotation‑runt‑en‑punkt‑transformation

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Viktig insikt*: `RotateAround` roterar canvas‑objektet kring en anpassad punkt (här (100, 50)), vilket ger dig fin kontroll över rotationsankare.

### Steg 9: Spara det resulterande XPS‑dokumentet

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Efter att alla transformationer har applicerats sparas dokumentet till `output1.xps`. Öppna filen i någon XPS‑visare för att se de staplade rektanglarna med sina respektive translationer, skalningar och rotationer.

## Vanliga problem & felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| Tom utdatafil | `dataDir` pekar på en icke‑existerande mapp | Säkerställ att katalogen finns eller använd en absolut sökväg |
| Rektanglar är inte placerade som förväntat | Felaktiga matrisvärden | Dubbelkolla ordningen på `Translate`, `Scale` och `RotateAround`‑anropen |
| Färger visas felaktigt | RGB‑värden utanför intervallet 0‑255 | Använd giltiga byte‑värden för varje kanal |

## Vanliga frågor

**Q: Är Aspose.Page för .NET kompatibel med alla .NET‑utvecklingsmiljöer?**  
A: Ja, den fungerar sömlöst med Visual Studio, Visual Studio Code, Rider och alla IDE:er som stödjer .NET.

**Q: Var kan jag hitta fler exempel och detaljerad API‑dokumentation?**  
A: Besök den officiella dokumentationen på [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: Kan jag prova Aspose.Page innan jag köper en licens?**  
A: Absolut. En gratis provversion finns här: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: Hur får jag en tillfällig licens för testning?**  
A: Du kan begära en via sidan för tillfällig licens: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Var köper jag en full licens?**  
A: Köp direkt från Aspose‑butiken: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-01-05  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}