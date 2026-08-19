---
date: 2026-03-03
description: Lär dig hur du använder Aspose.Page för .NET för att mosaiklägga bilder
  i XPS‑dokument. Denna steg‑för‑steg‑guide visar hur du mosaiklägger bilder effektivt
  och förbättrar den visuella attraktionskraften.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Hur du använder Aspose.Page för att lägga till en kakelbild i ett XPS-dokument
url: /sv/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du använder Aspose.Page för att lägga till en mosaikbild i ett XPS‑dokument

## Introduktion

Om du undrar **hur du använder Aspose** för att ge dina XPS‑filer en rikare visuell stil, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen som krävs för att **mosaikera en bild** i ett XPS‑dokument med Aspose.Page för .NET. I slutet har du ett återanvändbart kodsnutt som du kan klistra in i vilket .NET‑projekt som helst för att skapa mosaik‑bildgrafik i farten.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page för .NET  
- **Vilken metod skapar den mosaikade penseln?** `CreateImageBrush` med `TileMode = XpsTileMode.Tile`  
- **Kan jag kontrollera opaciteten?** Ja – sätt `path.Fill.Opacity` (t.ex. 0.5f)  
- **Behöver jag en licens för testning?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Vad är Aspose.Page och varför mosaikera bilder?

Aspose.Page är ett kraftfullt API som låter utvecklare generera, redigera och rendera XPS, PDF och andra sidbaserade format utan att förlita sig på Microsoft Office. Att mosaikera en bild—att upprepa en bitmap över en form—hjälper dig att fylla stora områden med mönster, vattenstämplar eller bakgrundstexturer samtidigt som filstorleken hålls låg.

## Hur du använder Aspose.Page för att mosaikera bilder i XPS‑dokument

Nedan hittar du ett komplett, färdigt‑att‑köra exempel. Varje steg förklaras med enkel svenska innan motsvarande kodblock, så du kan se **varför** varje rad är viktig.

### Förutsättningar

- **Aspose.Page för .NET** – ladda ner och referera biblioteket från den officiella sidan [here](https://reference.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio (valfri edition) eller någon annan .NET‑IDE du föredrar.

### Importera namnrymder

Först importerar vi de nödvändiga namnrymderna så att kompilatorn vet var XPS‑klasserna finns.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Steg 1: Definiera dokumentkatalogen

Ange var den genererade XPS‑filen och källbilden ska lagras. Ersätt platshållaren med en faktisk mapp på din dator.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Steg 2: Skapa ett nytt XPS‑dokument

Instansiera ett tomt XPS‑dokument som kommer att hålla den mosaikade grafiken.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Steg 3: Lägg till en mosaikbild

Här skapar vi en rektangulär bana, fyller den med en `ImageBrush` och sätter penseln till mosaikläge. `TileMode`‑egenskapen instruerar motorn att upprepa bilden både horisontellt och vertikalt. Justera rektangelkoordinaterna eller källbilden efter behov för ditt scenario.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Steg 4: Spara det resulterande XPS‑dokumentet

Till sist skriver vi dokumentet till disk. Utdatafilen kan öppnas med vilken XPS‑visare som helst eller vidarebearbetas med Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Vanliga problem & tips

- **Sökvägsfel** – Se till att `dataDir` slutar med ett snedstreck eller använd `Path.Combine` för att undvika problem med saknade separatorer.  
- **Bildstorleksavvikelser** – Källbilden bör vara tillräckligt stor för mosaikområdet; annars kan mönstret se utdraget ut.  
- **Opacitet syns inte** – Vissa visare ignorerar opacitet i XPS; testa med en visare som fullt stödjer XPS‑rendering (t.ex. XPS Viewer på Windows).

## Vanliga frågor

### Q1: Är Aspose.Page kompatibel med alla .NET‑utvecklingsmiljöer?
**A:** Ja, Aspose.Page fungerar med Visual Studio, Rider, VS Code och alla IDE som stödjer .NET.

### Q2: Kan jag justera opaciteten för den mosaikade bilden?
**A:** Absolut. Exemplet sätter `path.Fill.Opacity = 0.5f;`—du kan ändra flyttalet mellan 0 (genomskinlig) och 1 (opak).

### Q3: Finns det andra mosaiklägen tillgängliga i Aspose.Page för .NET?
**A:** Ja. Förutom `XpsTileMode.Tile` kan du använda `FlipX`, `FlipY` och `FlipXY` för att skapa speglade mönster.

### Q4: Hur hanterar jag tillfälliga licenser för Aspose.Page?
**A:** Se sidan för [temporary license](https://purchase.aspose.com/temporary-license/) på Aspose‑webbplatsen för detaljer om hur du får och använder en provlicens.

### Q5: Var kan jag få hjälp eller ansluta till Aspose.Page‑gemenskapen?
**A:** Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att ställa frågor, dela kodsnuttar och lära dig av andra utvecklare.

### Q6: Kan jag använda detta tillvägagångssätt för att skapa en vattenstämpelseffekt?
**A:** Ja. Genom att sänka opaciteten och välja en halvtransparent bild fungerar den mosaikade penseln perfekt som en upprepande vattenstämpel.

## Slutsats

Du vet nu **hur du använder Aspose** för att lägga till en mosaikbild i ett XPS‑dokument, kontrollera dess opacitet och spara resultatet för vidare användning. Denna teknik är idealisk för bakgrundsmönster, vattenstämplar eller alla situationer där en upprepande grafik ger visuell intresse utan att öka filstorleken. Känn dig fri att experimentera med olika former, bilder och mosaiklägen för att passa ditt projekts behov.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}