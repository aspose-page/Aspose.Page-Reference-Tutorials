---
title: Použijte Grid Visual Brush s Aspose.Page pro .NET
linktitle: Naneste mřížkový vizuální štětec
second_title: Aspose.Page .NET API
description: Prozkoumejte dynamický svět zpracování dokumentů v .NET s Aspose.Page. Naučte se používat mřížkový vizuální štětec pro vizuálně úžasné dokumenty.
weight: 10
url: /cs/net/visual-brushes/apply-grid-visual-brush/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Použijte Grid Visual Brush s Aspose.Page pro .NET

## Úvod

Ve světě vývoje .NET vyniká Aspose.Page jako výkonný nástroj pro zpracování úloh zpracování dokumentů. Jednou z fascinujících funkcí, které nabízí, je možnost použít mřížkový vizuální štětec, který vašim dokumentům přináší nový rozměr. Tento tutoriál vás provede procesem implementace vizuálního štětce Magenta Grid krok za krokem pomocí Aspose.Page for .NET.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte knihovnu nainstalovanou a nastavenou ve vašem prostředí .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

- Vývojové prostředí: Mějte připravené funkční vývojové prostředí .NET a základní znalost programování v C#.

- Adresář dokumentů: Vytvořte adresář pro vaše dokumenty, kam se budou ukládat zpracované soubory.

## Import jmenných prostorů

Chcete-li efektivně využívat funkce Aspose.Page, musíte do svého kódu C# importovat potřebné jmenné prostory:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nyní si příklad rozdělíme do několika kroků.

## Krok 1: Inicializujte XpsDocument

```csharp
// Start: 3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// Rozšířit:3
```

 Zde vytvoříme instanci`XpsDocument` pro práci s dokumenty XPS.

## Krok 2: Vytvořte geometrii purpurové mřížky

```csharp
// Start: 4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// Rozšíření:4
```

Tento krok zahrnuje vytvoření geometrie cesty pro purpurovou mřížku.

## Krok 3: Navrhněte VisualBrush Magenta Grid

```csharp
// Start: 5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// Rozšíření:5
```

Zde navrhujeme vizuální stránku purpurové mřížky pomocí vektorové grafiky.

## Krok 4: Použijte VisualBrush na mřížku

```csharp
// Start: 6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// Konec:6
```

Naneste vizuální štětec na dráhu mřížky a ujistěte se, že je správně dlaždice.

## Krok 5: Přidejte mřížku na plátno

```csharp
// Start: 7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// Konec:7
```

Přidejte mřížku na plátno a zadejte potřebné transformace.

## Krok 6: Vylepšení pomocí červeného obdélníku

```csharp
// Start: 8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// Konec:8
```

Vylepšete vizuální přitažlivost přidáním červeného průhledného obdélníku.

## Krok 7: Uložte dokument

```csharp
// Start: 9
doc.Save(dataDir + "AddGrid_out.xps");
// Konec:9
```

Uložte výsledný dokument XPS do určeného adresáře.

## Závěr

Gratulujeme! Úspěšně jste na svůj dokument použili mřížkový vizuální štětec pomocí Aspose.Page for .NET. Tato technika může výrazně vylepšit vizuální prvky vašich dokumentů a poskytnout dynamické a poutavé uživatelské prostředí.

## FAQ

### Q1: Mohu používat Aspose.Page for .NET ve webových i desktopových aplikacích?

A1: Ano, Aspose.Page for .NET je univerzální a lze jej použít v různých typech aplikací.

### Q2: Je před zakoupením k dispozici zkušební verze?

 A2: Rozhodně máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).

### Q3: Kde najdu další podporu nebo komunitní diskuse?

 A3: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za diskusi a podporu.

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A4: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Jaká další dokumentace je k dispozici pro Aspose.Page for .NET?

 A5: Prozkoumejte komplexní dokumentaci[tady](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
