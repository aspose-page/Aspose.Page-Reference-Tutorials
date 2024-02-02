---
title: Přidejte vertikální přechod do XPS pomocí Aspose.Page pro .NET
linktitle: Přidejte vertikální přechod do XPS
second_title: Aspose.Page .NET API
description: Naučte se, jak vylepšit dokumenty XPS pomocí vertikálních přechodů pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 15
url: /cs/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Úvod

Vítejte v tomto podrobném návodu, jak přidat vertikální přechod do dokumentu XPS pomocí Aspose.Page for .NET. Aspose.Page je výkonné API, které vám umožňuje pracovat se soubory XPS (XML Paper Specification) ve vašich aplikacích .NET. V tomto tutoriálu vás provedeme procesem vytvoření nového dokumentu XPS, přidání vertikálního přechodu k cestě a uložení výsledku.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:

-  Knihovna Aspose.Page for .NET: Ujistěte se, že máte ve svém vývojovém prostředí nainstalovanou knihovnu Aspose.Page for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

- Vývojové prostředí: Nastavte vývojové prostředí .NET s preferovaným IDE, jako je Visual Studio.

Nyní začněme s přidáním vertikálního přechodu do dokumentu XPS pomocí Aspose.Page for .NET.

## Import jmenných prostorů

Ve své aplikaci .NET zahrňte potřebné jmenné prostory pro přístup ke třídám a metodám Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Krok 1: Nastavte adresář dokumentů

Než začnete, nastavte cestu k adresáři dokumentů, kam chcete uložit výsledný dokument XPS.

```csharp
// Start: 3
string dataDir = "Your Document Directory";
// Rozšířit:3
```

## Krok 2: Vytvořte nový dokument XPS

Inicializujte nový dokument XPS pomocí následujícího kódu:

```csharp
// Start: 4
XpsDocument doc = new XpsDocument();
// Rozšíření:4
```

## Krok 3: Definujte zarážky přechodu

Vytvořte seznam zarážek přechodu a určete barvu a polohu každé zarážky. V tomto příkladu definujeme vertikální gradient s pěti zastávkami.

```csharp
// Start: 5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Rozšíření:5
```

## Krok 4: Vytvořte cestu s přechodem

Definujte cestu určením její geometrie a aplikujte na ni štětec s lineárním přechodem.

```csharp
// Start: 6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Konec:6
```

## Krok 5: Uložte výsledný dokument XPS

Uložte upravený dokument XPS do určeného adresáře.

```csharp
// Start: 7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Konec:7
```

Gratulujeme! Úspěšně jste přidali vertikální přechod do dokumentu XPS pomocí Aspose.Page for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak využít Aspose.Page pro .NET k vylepšení dokumentů XPS pomocí vertikálních přechodů. Aspose.Page zjednodušuje složité úkoly a poskytuje vývojářům bezproblémový způsob manipulace se soubory XPS v jejich aplikacích .NET.

## FAQ

### Q1: Je Aspose.Page kompatibilní se sadou Visual Studio 2019?

Odpověď 1: Ano, Aspose.Page je kompatibilní se sadou Visual Studio 2019. Ujistěte se, že máte nainstalovanou správnou verzi knihovny.

### Q2: Mohu použít Aspose.Page pro komerční projekty?

 A2: Ano, Aspose.Page lze použít pro komerční projekty. Návštěva[tady](https://purchase.aspose.com/buy) prozkoumat možnosti licencování.

### Q3: Je k dispozici bezplatná zkušební verze?

 A3: Ano, můžete získat bezplatnou zkušební verzi Aspose.Page[tady](https://releases.aspose.com/).

### Q4: Kde najdu dokumentaci Aspose.Page?

 A4: Dokumentace je k dispozici[tady](https://reference.aspose.com/page/net/).

### Q5: Jak mohu získat podporu nebo klást otázky?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.