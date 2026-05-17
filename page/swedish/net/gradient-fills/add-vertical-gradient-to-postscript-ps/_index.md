---
date: 2026-02-25
description: Lär dig hur du använder en C#‑linjärgradientpensel för att lägga till
  gradient i PS‑filer och fylla en rektangel med gradient med Aspose.Page för .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Linjär gradientpensel – Lägg till vertikal gradient i PostScript (PS) med
  Aspose.Page
url: /sv/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Lägg till vertikal gradient i PostScript (PS) med Aspose.Page

## Introduktion

I området för dokumentmanipulering och -skapande utmärker sig **Aspose.Page for .NET** som ett kraftfullt verktyg för utvecklare. I den här guiden kommer du att upptäcka hur du **lägger till gradient i PS**-filer genom att använda en **C# linear gradient brush** för att **fylla en rektangel med gradient**. I slutet av den här handledningen har du en tydlig, steg‑för‑steg‑förståelse av den nödvändiga koden och varför denna teknik ger en jämn vertikal gradient i ditt PostScript‑utdata.

## Snabba svar
- **Vad gör en C# linear gradient brush?** Den skapar en mjuk övergång mellan flera färger över en form.
- **Kan jag använda detta med någon .NET-version?** Ja, Aspose.Page stöder .NET Framework 4.5+ och .NET Core/5+.
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för icke‑utvärderingsbyggen.
- **Är gradienten verkligen vertikal?** Penseln roteras 90°, vilket säkerställer ett vertikalt flöde.
- **Var sparas utdata?** Till den sökväg du anger i `dataDir` (t.ex. `VerticalGradient_outPS.ps`).

## Vad är en C# Linear Gradient Brush?
En **C# linear gradient brush** är ett GDI+-objekt (`LinearGradientBrush`) som målar en linjär färgövergång mellan definierade punkter. När det kombineras med Aspose.Page:s rit‑API kan du rendera sofistikerade gradienter direkt i ett PostScript (PS)-dokument.

## Varför använda en Linear Gradient Brush för PostScript?
- **Högkvalitativt utdata:** Gradienter renderas på skrivarnivå, vilket bevarar noggrannheten.
- **Full kontroll:** Du kan ange anpassade färgstopp, rotation och skalning.
- **Återanvändbar kod:** Samma pensellogik fungerar för PDF, SVG och andra format som stöds av Aspose.Page.

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande på plats:

- Aspose.Page for .NET: Se till att du har Aspose.Page‑biblioteket installerat. Du kan hitta nödvändiga resurser och dokumentation [here](https://reference.aspose.com/page/net/).
- Utvecklingsmiljö: Ställ in en lämplig utvecklingsmiljö, inklusive en Integrated Development Environment (IDE) för .NET‑utveckling.
- Grundläggande förståelse: Bekanta dig med grunderna i .NET‑utveckling, inklusive arbete med strömmar, grafikvägar och färgmanipulation.

## Importera namnrymder

I ditt C#‑projekt, inkludera de nödvändiga namnrymderna i början av din kodfil:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Steg 1: Ställ in dokumentkatalogen

Börja med att ange sökvägen till din dokumentkatalog. Detta är platsen där ditt PS‑dokument kommer att sparas.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Skapa utdata‑ström för PostScript‑dokument

Generera en utdata‑ström för PostScript‑dokumentet med hjälp av `FileStream`‑klassen.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Steg 3: Skapa spara‑alternativ och PS‑dokument

Skapa spara‑alternativ med A4‑storlek och initiera ett nytt 1‑sidigt PS‑dokument.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Steg 4: Definiera rektangelns dimensioner

Ange dimensionerna och positionen för rektangeln där den vertikala gradienten kommer att tillämpas.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Steg 5: Skapa grafikväg

Bygg en grafikväg från den definierade rektangeln.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Steg 6: Definiera interpolationsfärger

Skapa en array med interpolationsfärger och positioner för gradienten.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Steg 7: Skapa Linear Gradient Brush

Skapa en linear gradient brush med rektangeln som gränser, start‑ och slutfärger.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Steg 8: Ställ in penseltransform

Skapa en transform för penseln, så att X‑ och Y‑skalningskomponenterna matchar rektangelns bredd och höjd.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Steg 9: Ställ in målning och fyll rektangeln

Ställ in målning för dokumentet, och **fyll rektangel med gradient** med den tidigare definierade vägen.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Steg 10: Stäng den aktuella sidan och spara dokumentet

Stäng den aktuella sidan och spara PostScript‑dokumentet.

```csharp
document.ClosePage();
document.Save();
```

Grattis! Du har framgångsrikt **lagt till en vertikal gradient i ett PostScript‑dokument** med en **C# linear gradient brush** med Aspose.Page for .NET. Experimentera med olika parametrar och färger för att uppnå olika visuella effekter i dina dokument.

## Vanliga problem och lösningar

| Problem | Varför det händer | Hur man åtgärdar |
|---------|-------------------|------------------|
| Gradienten visas horisontellt | Penselrotation har inte tillämpats | Se till att `brushTransform.Rotate(90);` anropas innan den tilldelas `brush.Transform`. |
| Färgerna ser urvattnade ut | Utdata‑ström med låg upplösning | Använd en `PsSaveOptions` med högre upplösning eller öka dokumentets storlek. |
| Utdatafilen är tom | Strömmen har inte spolas | Verifiera att `document.Save();` anropas utanför `using`‑blocket. |

## Vanliga frågor

**Q1: Kan jag applicera flera gradienter på olika områden i samma dokument?**  
A: Ja, det kan du. Upprepa helt enkelt stegen för varje område med dess specifika dimensioner och färgschema.

**Q2: Hur kan jag integrera denna kod i mitt befintliga .NET‑projekt?**  
A: Kopiera och klistra in koden i din projektfil och se till att du har Aspose.Page‑biblioteket refererat.

**Q3: Finns det andra gradienttyper tillgängliga i Aspose.Page för .NET?**  
A: Aspose.Page stöder olika gradienttyper, inklusive radial‑ och path‑gradienter. Se dokumentationen för mer information.

**Q4: Kan jag använda Aspose.Page för kommersiella projekt?**  
A: Ja, det kan du. Besök [here](https://purchase.aspose.com/buy) för att utforska licensalternativ.

**Q5: Finns det ett community‑forum för Aspose.Page där jag kan få hjälp?**  
A: Absolut! Gå till [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att ansluta med andra utvecklare och få hjälp.

---

**Senast uppdaterad:** 2026-02-25  
**Testat med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}