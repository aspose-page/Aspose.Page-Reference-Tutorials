---
title: Přidejte dlaždicový obrázek do dokumentu XPS pomocí Aspose.Page pro .NET
linktitle: Přidejte dlaždicový obrázek do dokumentu XPS
second_title: Aspose.Page .NET API
description: Prozkoumejte snadné přidávání dlaždicových obrázků do dokumentů XPS pomocí Aspose.Page for .NET. Vylepšete vizuální přitažlivost a vytvářejte úžasné dokumenty.
type: docs
weight: 12
url: /cs/net/image-management/add-tiled-image-to-xps-document/
---
## Úvod

Chcete vylepšit své dokumenty XPS přidáním vizuálně přitažlivých dlaždicových obrázků? Aspose.Page for .NET umožňuje vývojářům dosáhnout tohoto hladce. V tomto podrobném průvodci vás provedeme procesem přidání dlaždicového obrázku do dokumentu XPS pomocí Aspose.Page for .NET.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page. Můžete najít podrobnou dokumentaci a stáhnout knihovnu[tady](https://reference.aspose.com/page/net/).
- Vývojové prostředí: Nastavte si preferované vývojové prostředí .NET, jako je Visual Studio.

## Import jmenných prostorů

Chcete-li začít, importujte potřebné jmenné prostory do svého projektu. To zajišťuje, že máte přístup ke třídám a metodám potřebným pro práci s Aspose.Page. Na začátek kódu přidejte následující jmenné prostory:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nyní si příklad rozdělíme do několika kroků.

## Krok 1: Definujte adresář dokumentů

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```

Ujistěte se, že jste nahradili "Your Document Directory" skutečnou cestou, kam chcete uložit dokument XPS.

## Krok 2: Vytvořte nový dokument XPS

```csharp
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```

 Vytvořte instanci nového dokumentu XPS pomocí`XpsDocument` třída.

## Krok 3: Přidejte dlaždicový obrázek

```csharp
// Obrázek dlaždice
// Obdélník vyplněný ImageBrushem vpravo nahoře dole
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Tento krok přidá dlaždicový obrázek do dokumentu XPS. Upravte souřadnice a cestu k souboru obrázku podle svých požadavků.

## Krok 4: Uložte výsledný dokument XPS

```csharp
// Uložte výsledný dokument XPS
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Uložte upravený dokument XPS do určeného adresáře.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přidat dlaždicový obrázek do dokumentu XPS pomocí Aspose.Page for .NET. Tato jednoduchá, ale výkonná funkce vám umožní bez námahy zlepšit vizuální přitažlivost vašich dokumentů.

## FAQ

### Q1: Je Aspose.Page kompatibilní se všemi vývojovými prostředími .NET?

Odpověď 1: Ano, Aspose.Page je navržen tak, aby bezproblémově spolupracoval s různými vývojovými prostředími .NET, včetně sady Visual Studio.

### Q2: Mohu upravit neprůhlednost dlaždicového obrázku?

A2: Jistě, jak je ukázáno v příkladu, můžete nastavit krytí vyplněného obdélníku pomocí`Opacity` vlastnictví.

### Q3: Jsou v Aspose.Page pro .NET k dispozici další režimy dlaždic?

 A3: Ano, Aspose.Page poskytuje různé režimy dlaždic. V tomto tutoriálu jsme použili`XpsTileMode.Tile`, ale další možnosti můžete prozkoumat v dokumentaci.

### Q4: Jak zacházet s dočasnými licencemi pro Aspose.Page?

 A4: Viz[dočasná licence](https://purchase.aspose.com/temporary-license/) na stránce Aspose, kde najdete pokyny k získání a implementaci dočasných licencí.

### Q5: Kde mohu vyhledat pomoc nebo se spojit s komunitou Aspose.Page?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) zapojit se do komunity, klást otázky a hledat řešení.