---
title: Přidejte horizontální přechod do XPS pomocí Aspose.Page pro .NET
linktitle: Přidejte horizontální přechod do XPS
second_title: Aspose.Page .NET API
description: Naučte se, jak přidat úžasné horizontální přechody do dokumentů XPS pomocí Aspose.Page for .NET. Zvyšte vizuální přitažlivost bez námahy.
weight: 13
url: /cs/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte horizontální přechod do XPS pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu prozkoumáme, jak vylepšit dokumenty XPS přidáním horizontálního přechodu pomocí Aspose.Page for .NET. Aspose.Page for .NET je výkonná knihovna, která poskytuje bezproblémovou práci s dokumenty XPS (XML Paper Specification) v aplikacích .NET. Přidání přechodů může vašim dokumentům přinést vizuální přitažlivost a tento průvodce vás provede procesem krok za krokem.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Knihovna Aspose.Page for .NET: Ujistěte se, že máte ve svém vývojovém prostředí nainstalovanou knihovnu Aspose.Page for .NET. Můžete si jej stáhnout z[Aspose.Page pro dokumentaci .NET](https://reference.aspose.com/page/net/).

2. Vývojové prostředí: Nastavte vhodné vývojové prostředí, včetně editoru kódu, jako je Visual Studio.

## Import jmenných prostorů

Začněte importováním potřebných jmenných prostorů do vašeho projektu. Tyto jmenné prostory jsou nezbytné pro práci s Aspose.Page pro .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Nyní si uvedený příklad rozdělíme do několika kroků.

## Krok 1: Nastavte cestu k adresáři dokumentu

```csharp
// Start: 3
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Rozšířit:3
```

## Krok 2: Vytvořte nový dokument XPS

```csharp
// Start: 4
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
// Rozšíření:4
```

## Krok 3: Inicializujte zarážky přechodu

```csharp
// Start: 5
// Inicializovat seznam XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Rozšíření:5
```

## Krok 4: Vytvořte novou cestu

```csharp
// Start: 6
//Vytvořte novou cestu definováním geometrie ve formě zkratky
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Konec:6
```

## Krok 5: Uložte výsledný dokument XPS

```csharp
// Start: 7
// Uložte výsledný dokument XPS
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Konec:7
```

Nyní jste úspěšně přidali horizontální přechod do vašeho dokumentu XPS pomocí Aspose.Page for .NET.

## Závěr

Vylepšení vašich dokumentů XPS pomocí přechodů nejen zlepšuje jejich vizuální přitažlivost, ale také poskytuje poutavější uživatelský zážitek. Aspose.Page for .NET tento proces zjednodušuje a umožňuje vám dosáhnout profesionálních výsledků bez námahy.

## FAQ

### Q1: Kde najdu dokumentaci Aspose.Page pro .NET?

 A1: Můžete najít dokumentaci[tady](https://reference.aspose.com/page/net/).

### Q2: Jak stáhnu Aspose.Page for .NET?

 A2: Knihovnu si můžete stáhnout z[Stránka ke stažení Aspose.Page for .NET](https://releases.aspose.com/page/net/).

### Q3: Kde mohu zakoupit Aspose.Page pro .NET?

 A3: Aspose.Page pro .NET si můžete zakoupit z[nákupní stránku](https://purchase.aspose.com/buy).

### Q4: Je k dispozici bezplatná zkušební verze?

 A4: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q5: Jak získám dočasnou licenci pro Aspose.Page for .NET?

 A5: Můžete získat dočasnou licenci od[tento odkaz](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
