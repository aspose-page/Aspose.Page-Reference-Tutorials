---
title: Přidejte obdélník do dokumentu XPS pomocí Aspose.Page pro .NET
linktitle: Přidat obdélník do dokumentu XPS
second_title: Aspose.Page .NET API
description: Vylepšete vytváření dokumentů pomocí Aspose.Page pro .NET. V tomto podrobném kurzu se dozvíte, jak přidat obdélníky do dokumentů XPS.
type: docs
weight: 13
url: /cs/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Úvod

Aspose.Page for .NET je výkonná knihovna, která poskytuje řadu funkcí pro práci s dokumenty XPS (XML Paper Specification) v aplikacích .NET. V tomto tutoriálu se zaměříme na přidání obdélníku do dokumentu XPS pomocí Aspose.Page for .NET. Postupujte podle tohoto podrobného průvodce, abyste zlepšili proces vytváření dokumentů.

## Předpoklady

Než začnete s tímto výukovým programem, ujistěte se, že máte splněny následující předpoklady:

1.  Knihovna Aspose.Page for .NET: Ujistěte se, že máte ve svém vývojovém prostředí nainstalovanou knihovnu Aspose.Page for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

2. Adresář dokumentů: Nastavte adresář, do kterého chcete ukládat dokumenty XPS.

## Import jmenných prostorů

Ve své aplikaci .NET zahrňte potřebné obory názvů, abyste mohli používat funkce Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Nastavte adresář dokumentů

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

## Krok 3: Přidejte obdélník

```csharp
// Start: 5
// CMYK (modrý) jednobarevný vytažený obdélník vlevo dole
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Rozšíření:5
```

## Krok 4: Uložte dokument

```csharp
// Start: 6
// Uložte výsledný dokument XPS
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Konec:6
```

Gratulujeme! Úspěšně jste přidali obdélník do dokumentu XPS pomocí Aspose.Page for .NET.

## Závěr

Aspose.Page for .NET zjednodušuje úlohy manipulace s dokumenty a umožňuje vývojářům snadno vytvářet a upravovat dokumenty XPS. Tento podrobný průvodce ukazuje, jak do dokumentu XPS přidat obdélník, který poskytuje pevný základ pro další zkoumání.

## FAQ

### Q1: Je Aspose.Page kompatibilní se všemi aplikacemi .NET?

Odpověď 1: Ano, Aspose.Page je navržena tak, aby bezproblémově fungovala se všemi aplikacemi .NET.

### Q2: Kde najdu dokumentaci pro Aspose.Page for .NET?

 A2: Dokumentace je k dispozici[tady](https://reference.aspose.com/page/net/).

### Q3: Mohu si Aspose.Page for .NET vyzkoušet zdarma před nákupem?

 A3: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A4: Návštěva[tento odkaz](https://purchase.aspose.com/temporary-license/) získat dočasnou licenci.

### Q5: Kde mohu vyhledat podporu komunity nebo klást otázky týkající se Aspose.Page for .NET?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.