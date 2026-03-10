---
date: 2026-02-28
description: Lär dig hur du skapar XPS‑dokument i .NET och lägger till en bild med
  Aspose.Page för .NET. Följ den här steg‑för‑steg‑guiden för en smidig utvecklingsupplevelse.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument .NET – Lägg till bild med Aspose.Page
url: /sv/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till bild i XPS-dokument med Aspose.Page för .NET

I den här handledningen lär du dig hur du **skapar XPS-dokument .NET** och bäddar in en bild med det kraftfulla Aspose.Page‑biblioteket. Oavsett om du genererar rapporter, fakturor eller anpassad grafik är det en vanlig uppgift för .NET‑utvecklare att lägga till visuella element i XPS‑filer.

## Introduktion

I .NET‑utveckling är det vanligt att infoga bilder i XPS‑dokument. Aspose.Page för .NET förenklar processen och erbjuder ett kraftfullt verktyg för att manipulera och förbättra XPS‑dokument utan ansträngning. Denna handledning guidar dig genom stegen för att lägga till en bild i ett XPS‑dokument med Aspose.Page för .NET.

## Snabba svar
- **Vad täcker den här handledningen?** Att lägga till en bild i ett XPS‑dokument med Aspose.Page för .NET.  
- **Vilket primärt nyckelord är målet?** *create xps document .net*  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** Fungerar med .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hur lång tid tar implementeringen?** Cirka 5‑10 minuter för en grundläggande bildinfogning.

## Vad betyder “create XPS document .NET”?
Att skapa ett XPS‑dokument i .NET innebär att programatiskt generera en XML Paper Specification (XPS)‑fil – ett fast‑layoutformat – med C# eller VB.NET. Aspose.Page tillhandahåller ett flytande API som döljer låg‑nivå‑detaljer, så att du kan fokusera på innehåll som text, former och bilder.

## Varför använda Aspose.Page för att lägga till en bild?
- **Full kontroll** över positionering, skalning och beskärning av bilder.  
- **Inga externa beroenden** – biblioteket hanterar bildavkodning internt.  
- **Plattformsoberoende** stöd för Windows‑ och Linux‑miljöer.  
- **Hög återgivningskvalitet** som bevarar bildens skärpa i den slutliga XPS‑filen.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:

1. Aspose.Page för .NET‑bibliotek: Ladda ner och installera biblioteket från [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).

2. Utvecklingsmiljö: Ställ in en .NET‑utvecklingsmiljö, exempelvis Visual Studio.

3. Exempelbild: Ha en bildfil (t.ex. "QL_logo_color.tif") som du vill lägga till i XPS‑dokumentet.

## Importera namnrymder

Börja med att importera de nödvändiga namnrymderna i ditt .NET‑projekt. Dessa namnrymder är avgörande för att utnyttja funktionerna som Aspose.Page för .NET erbjuder.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page lägger till bild i XPS-dokument

Nedan går vi igenom varje steg som krävs för att **skapa XPS-dokument .NET** och bädda in en bild.

### Steg 1: Ange dokumentkatalog

Börja med att specificera sökvägen till din dokumentkatalog. Detta steg säkerställer att projektet vet var filer ska hämtas och sparas.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Steg 2: Skapa XPS-dokument

Skapa ett nytt XPS-dokument med Aspose.Page för .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Steg 3: Lägg till bild i XPS-dokument

Nu lägger vi till bilden i XPS-dokumentet. I detta exempel använder vi en bild med namnet "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Steg 4: Spara resulterande XPS-dokument

Spara XPS-dokumentet med den tillagda bilden.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Nu har du framgångsrikt lagt till en bild i ett XPS-dokument med Aspose.Page för .NET!

## Vanliga problem och lösningar

- **Fil‑ej‑hittad‑fel** – Kontrollera att `dataDir` pekar på rätt mapp och att bildfilens namn matchar exakt, inklusive skiftlägeskänslighet på Linux.  
- **Bilden ser förvrängd ut** – Justera skalningsfaktorerna i `CreateMatrix` eller parametrarna i `RectangleF` för att kontrollera storlek och bildförhållande.  
- **Ej‑stödd bildformat** – Aspose.Page stöder vanliga rasterformat (PNG, JPEG, TIFF). Konvertera ej‑stödda format innan du använder `CreateImageBrush`.

## Vanliga frågor

### Q1: Är Aspose.Page för .NET kompatibel med de senaste .NET‑ramverken?

A1: Aspose.Page för .NET är designad för att vara kompatibel med ett brett spektrum av .NET‑ramverksversioner, inklusive de senaste utgåvorna. Se [dokumentationen](https://reference.aspose.com/page/net/) för specifika detaljer.

### Q2: Kan jag använda Aspose.Page för .NET både i Windows‑ och Linux‑miljöer?

A2: Ja, Aspose.Page för .NET är plattformsoberoende och lämpar sig för både Windows‑ och Linux‑miljöer.

### Q3: Finns det licensalternativ för Aspose.Page för .NET?

A3: Ja, du kan utforska licensalternativ och göra ett köp [här](https://purchase.aspose.com/buy).

### Q4: Finns det en gratis provversion av Aspose.Page för .NET?

A4: Ja, du kan prova Aspose.Page för .NET gratis genom att besöka [gratis provversion](https://releases.aspose.com/).

### Q5: Var kan jag få hjälp eller engagera mig i communityn för Aspose.Page för .NET?

A5: Besök [Aspose.Page för .NET‑forumet](https://forum.aspose.com/c/page/39) för att ansluta till communityn och få support.

## Slutsats

I den här handledningen har vi gått igenom hur du med Aspose.Page för .NET enkelt kan infoga bilder i XPS-dokument. Denna steg‑för‑steg‑guide säkerställer en smidig integrationsprocess, förbättrar dina .NET‑utvecklingsmöjligheter och hjälper dig att **skapa XPS-dokument .NET** med visuell rikedom.

---

**Senast uppdaterad:** 2026-02-28  
**Testat med:** Aspose.Page för .NET 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}