---
title: Přidejte Circle Elipse do dokumentu XPS pomocí Aspose.Page pro .NET
linktitle: Přidejte kruhovou elipsu do dokumentu XPS
second_title: Aspose.Page .NET API
description: Vylepšete dokumenty XPS pomocí zářivých radiálních přechodů pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro úžasné vizuální efekty.
weight: 11
url: /cs/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte Circle Elipse do dokumentu XPS pomocí Aspose.Page pro .NET

## Úvod

Vytváření vizuálně atraktivních dokumentů XPS je běžným požadavkem v různých aplikacích. Aspose.Page for .NET poskytuje výkonnou sadu funkcí pro efektivní manipulaci s dokumenty XPS. V tomto tutoriálu se zaměříme na přidání kruhové elipsy do dokumentu XPS pomocí Aspose.Page for .NET. Chcete-li své dokumenty XPS vylepšit zářivými radiálními přechody, postupujte podle níže uvedených kroků.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Nainstalovaná knihovna Aspose.Page for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).
- Vývojové prostředí, nejlépe Visual Studio nebo jakýkoli jiný vývojový nástroj .NET.
- Základní znalost programování v C#.

## Import jmenných prostorů

Chcete-li začít, zahrňte do kódu C# potřebné jmenné prostory:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Nyní si příklad rozdělíme do několika kroků:

## Krok 1: Nastavte dokument

```csharp
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```

Zde inicializujeme nový dokument XPS pomocí Aspose.Page for .NET.

## Krok 2: Definujte elipsu radiálního gradientu

```csharp
// Vytažená elipsa s radiálním přechodem vlevo dole
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Tento krok zahrnuje definování radiální přechodové elipsy s různými barvami.

## Krok 3: Nastavte Radial Gradient Brush

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Zde nastavíme tah elipsy na radiální gradientní štětec, který mu poskytne potřebné parametry.

## Krok 4: Upravte tloušťku tahu

```csharp
path.StrokeThickness = 12f;
```

Tento krok zahrnuje úpravu tloušťky tahu pro lepší vizualizaci.

## Krok 5: Uložte výsledný dokument XPS

```csharp
// Uložte výsledný dokument XPS
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// Rozšíření: 1
```

Nakonec uložte upravený dokument XPS na požadované místo.

## Závěr

Gratulujeme! Pomocí Aspose.Page for .NET jste do dokumentu XPS úspěšně přidali kruhovou elipsu s radiálními přechody. Experimentujte s různými parametry a barvami, abyste dosáhli požadovaných vizuálních efektů ve svých dokumentech.

## FAQ

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?

A1: Aspose.Page for .NET se konkrétně zabývá manipulací s dokumenty XPS. U jiných formátů zvažte použití souvisejících knihoven Aspose.

### Q2: Je k dispozici dočasná licence pro testovací účely?

 A2: Ano, můžete získat dočasnou licenci pro testování návštěvou[tento odkaz](https://purchase.aspose.com/temporary-license/).

### Q3: Kde najdu další pomoc a diskuze?

 A3: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.

### Q4: Jsou k dispozici nějaké vzorové dokumenty pro referenci?

 A4: Prozkoumejte[dokumentace](https://reference.aspose.com/page/net/) pro komplexní příklady a pokyny.

### Q5: Mohu zakoupit Aspose.Page pro .NET?

 A5: Ano, můžete si koupit knihovnu[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
