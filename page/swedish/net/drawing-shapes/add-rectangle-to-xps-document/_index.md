---
date: 2026-01-20
description: Lär dig hur du skapar ett XPS‑dokument, lägger till en rektangel och
  sparar XPS‑filen med Aspose.Page för .NET i den här steg‑för‑steg‑guiden.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Skapa XPS-dokument: Lägg till rektangel med Aspose.Page för .NET'
url: /sv/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument: Lägg till rektangel med Aspose.Page för .NET

## Introduktion

I den här handledningen kommer du att **skapa XPS-dokument** och rita en rektangelVad kan med finns).  
- **Hur lång tid tar det?** Ungefär 5‑10 minuter att implementera och köra.  
- **Behöver jag en licens?** En tillfällig licens krävs för produktionsanvändning.  
- **Kan jag spara resultatet som en XPS-fil?** Ja – `Save`‑metoden skriver en **spara XPS-fil** till disk.

## Vad betyder “create XPS document”?

Att skapa ett XPS‑dokument innebär att programatiskt bygga en sidbeskrivning i XML Paper Specification‑formatet. Den resulterande filen är uppl – inkluder, pennor och text‑hantering.  
-ningar

Innan du börjar, se till att du har följande:

1. **Aspose.Page för .NET** – ladda ner det [här](https://releases.aspose.com/page/net/).  
2. **En skrivbar mapp** där de genererade XPS‑filerna kommer att lagras.

## Importera namnrymder

I ditt .NET‑projekt, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Ange dokumentkatalogen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Proffstips:** Använd en absolut sökväg eller `Path.Combine` för att undvika problem med sökvägsseparatorer på olika OS.

## Steg 2: Skapa ett nytt XPS-dokument

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

Vid detta tillfälle har du **skapat ett XPS-dokument**‑objekt som kommer att hålla alla rit‑element.

## Steg 3: Lägg till en rektangel (med create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

Anropet `CreatePathGeometry` **skapar path‑geometri** som definierar rektangelns kontur. Du kan ändra den SVG‑liknande kommandosträngen för att rita andra former.

## Steg 4: Spara dokumentet (spara XPS-fil)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Genom att anropa `Save` skrivs **spara XPS-filen** till den plats du angav.

Grattis! Du har framgångsrikt **skapat ett XPS-dokument**, lagt till en rektangel och sparat filen.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| `FileNotFoundException` på `doc.Save` | `dataDir` pekar på en icke‑existerande mapp | Se till att katalogen finns eller skapa den med `Directory.CreateDirectory(dataDir)`. |
| Rektangel syns inte | Stroke‑färgprofil saknas eller path‑geometri felaktig | Verifiera ICC‑filens sökväg och geometristrängen (`M … Z`). |
| Prestandaförsämring i stora dokument | För många enskilda `AddPath`‑anrop | Batcha rit‑operationer eller återanvänd penslar/pen‑objekt. |

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med alla .NET-applikationer?**  
A: Ja, Aspose.Page är designat för att fungera sömlöst med alla .NET‑applikationer.

**Q: Var kan jag hitta dokumentationen för Aspose.Page för .NET?**  
A: Dokumentationen finns [här](https://reference.aspose.com/page/net/).

**Q: Kan jag prova Aspose.Page för .NET gratis innan jag köper?**  
A: Ja, du kan få en gratis provversion [här](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Page för .NET?**  
A: Besök [denna länk](https://purchase.aspose.com/temporary-license/) för att få en tillfällig licens.

**Q: Vart kan jag söka gemenskapsstöd eller ställa frågor om Aspose.Page för .NET?**  
A: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för gemenskapsstöd.

---

**Senast uppdaterad:** 2026-01-20  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}