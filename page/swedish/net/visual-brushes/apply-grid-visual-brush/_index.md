---
date: 2026-04-03
description: Lär dig hur du lägger till en transparent rektangel och använder en Grid
  Visual Brush i .NET med Aspose.Page för fantastiska XPS‑dokument.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Använd rutnätsvisualiseringspensel
second_title: Aspose.Page .NET API
title: Lägg till transparent rektangel med Grid Visual Brush (.NET)
url: /sv/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till transparent rektangel med Grid Visual Brush (.NET)

## Introduktion

Om du vill **lägga till en transparent rektangel** i ett XPS-dokument samtidigt som du använder en stilren Grid Visual Brush, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen som behövs med Aspose.Page för .NET, så att du kan skapa visuellt rika dokument som sticker ut. I slutet har du ett komplett, körbart exempel som demonstrerar båda teknikerna i ett enkelt, lätt‑följt arbetsflöde.

## Snabba svar
- **Vad gör en transparent rektangel?** Den lägger till ett halvgenomskinligt lager som låter bakgrundsinnehållet synas igenom.  
- **Vilket API skapar penseln?** `XpsDocument.CreateVisualBrush` bygger Grid Visual Brush.  
- **Behöver jag en licens?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundexempel.

## Vad är en transparent rektangel i XPS?
En transparent rektangel är helt enkelt en form vars fyllningsfärg innehåller en alfa‑komponent mindre än 1,0, vilket gör att den underliggande grafiken delvis syns. Detta är perfekt för att markera sektioner utan att helt dölja bakgrunden.

## Varför använda en Grid Visual Brush?
En Grid Visual Brush låter dig mosaikera en liten vektorgrafik över ett större område, vilket skapar mönster som rutnät, skraffering eller anpassade texturer. Att kombinera den med en transparent rektangel ger lagerbaserade visuella effekter som både är lätta och upplösningsoberoende.

## Förutsättningar

Innan du dyker ner i koden, se till att du har:

- **Aspose.Page for .NET** – du kan ladda ner den [här](https://releases.aspose.com/page/net/).
- En .NET‑utvecklingsmiljö (Visual Studio, VS Code eller någon IDE du föredrar).
- En mapp där de genererade XPS‑filerna kommer att sparas.

## Importera namnrymder

I din C#‑fil importerar du de nödvändiga namnrymderna:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nu delar vi upp lösningen i tydliga, numrerade steg.

## Steg 1: Initiera XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Vi börjar med att skapa en `XpsDocument`‑instans, som kommer att hålla alla efterföljande ritoperationer.

## Steg 2: Skapa magenta rutnätsgeometri

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Denna geometri definierar konturen av rutnätet som visual brush kommer att fylla.

## Steg 3: Designa magenta rutnäts‑VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Här ritar vi en liten magenta platta som kommer att upprepas över rutnätet.

## Steg 4: Tillämpa VisualBrush på rutnät

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush`‑anropet kopplar den magenta plattan till rutnätsgeometrin och möjliggör mosaikering.

## Steg 5: Lägg till rutnät på Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Vi placerar det mosaikade rutnätet på en canvas och applicerar en translatio‑transform så att det visas på önskad plats.

## Steg 6: Lägg till transparent rektangel

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

I detta steg **lägger vi till en transparent rektangel** (den röda formen med `Opacity = 0.7f`). Justera opacitetsvärdet för att kontrollera hur genomskinlig rektangeln är.

## Steg 7: Spara dokumentet

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

XPS‑filen skrivs till den mapp du angav tidigare.

## Vanliga användningsområden

- **Rapportmarkering:** Överlagra en halvgenomskinlig rektangel för att framhäva ett diagram eller en tabell.  
- **Vattenstämpelseffekter:** Kombinera ett mosaikerat rutnät med ett transparent överlag för subtil varumärkesprofilering.  
- **Interaktiva PDF/XPS:** Använd mönstret som bakgrund för formulärfält samtidigt som UI‑gränssnittet förblir läsbart.

## Felsökningstips

- **Opacitet syns inte?** Se till att din visare stödjer XPS‑transparens; vissa äldre visare kan ignorera `Opacity`‑egenskapen.  
- **Felaktig plattstorlek?** Verifiera att källrektangeln (`new RectangleF(0f, 0f, 10f, 10f)`) matchar dimensionerna på vektortilet.  
- **Filen sparas inte?** Dubbelkolla att `dataDir` pekar på en befintlig, skrivbar katalog.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för .NET i både webb‑ och skrivbordsapplikationer?**  
A: Ja, biblioteket fungerar i alla .NET‑applikationstyper.

**Q: Finns det en provversion tillgänglig innan köp?**  
A: Absolut, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

**Q: Var kan jag hitta ytterligare support eller community‑diskussioner?**  
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för hjälp från communityn och Aspose‑ingenjörer.

**Q: Hur kan jag skaffa en tillfällig licens för utvärdering?**  
A: Du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Vilken annan dokumentation finns tillgänglig för Aspose.Page för .NET?**  
A: Utforska den omfattande dokumentationen [här](https://reference.aspose.com/page/net/).

---

**Senast uppdaterad:** 2026-04-03  
**Testat med:** Aspose.Page 24.12 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}