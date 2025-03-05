---
title: Přidejte text do dokumentu PostScript (PS) pomocí Aspose.Page
linktitle: Přidat text do dokumentu PostScript (PS).
second_title: Aspose.Page .NET API
description: Vylepšete své vývojové dovednosti .NET tím, že se naučíte přidávat text do dokumentů PostScript (PS) pomocí Aspose.Page. Prozkoumejte příklady krok za krokem a uvolněte sílu manipulace s dokumenty.
type: docs
weight: 10
url: /cs/net/text-manipulation/add-text-to-postscript-ps-document/
---
## Úvod

V dynamickém světě vývoje .NET je manipulace a vylepšování PostScriptových (PS) dokumentů běžným požadavkem. Aspose.Page for .NET poskytuje výkonnou sadu nástrojů pro snadné přidávání textu do vašich dokumentů PS. Tento tutoriál vás provede celým procesem a zajistí, že můžete tuto funkci bez problémů integrovat do svých projektů.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte knihovnu Aspose.Page integrovanou do vašeho projektu .NET. Můžete si jej stáhnout z[Dokumentace Aspose.Page .NET](https://reference.aspose.com/page/net/).

- Adresář dokumentů: Nastavte adresář, kde budou uloženy vaše dokumenty. Toto bude v příkladech označováno jako „Adresář vašich dokumentů“.

- Složka písem: Vytvořte složku pro ukládání vlastních písem, v příkladech označovanou jako „Adresář vašich dokumentů“.

## Import jmenných prostorů

Než začnete, nezapomeňte do projektu zahrnout potřebné jmenné prostory:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní si příklad rozdělíme do několika kroků.

## Krok 1: Vytvořte výstupní stream pro dokument PS

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Vyplňte text systémovým písmem

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## Krok 3: Vyplňte text vlastním písmem

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Krok 4: Osnova textu pomocí systémového písma

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## Krok 5: Obrysový text pomocí vlastního písma

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## Krok 6: Zavřete a uložte

```csharp
document.ClosePage();
document.Save();
}
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přidat text do dokumentu PostScript (PS) pomocí Aspose.Page for .NET. Neváhejte prozkoumat další funkce a vylepšit své možnosti manipulace s dokumenty.

## FAQ

### Q1: Mohu používat Aspose.Page s jinými knihovnami .NET?

Odpověď 1: Ano, Aspose.Page se hladce integruje s ostatními knihovnami .NET a poskytuje všestranné prostředí pro manipulaci s dokumenty.

### Q2: Jsou pro tento proces nezbytná vlastní písma?

A2: I když můžete používat systémová písma, začlenění vlastních písem umožňuje větší flexibilitu a možnosti návrhu.

### Q3: Je Aspose.Page vhodný pro zpracování dokumentů ve velkém měřítku?

A3: Rozhodně! Aspose.Page je navržena tak, aby efektivně a spolehlivě zvládla zpracování rozsáhlých dokumentů.

### Q4: Mohu upravit pozici textu v dokumentu PS?

A4: Určitě! Upravte souřadnice v poskytnutých příkladech, abyste změnili polohu přidaného textu.

### Q5: Kde mohu požádat o pomoc s dotazy souvisejícími s Aspose.Page?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) spojit se s komunitou a vyhledat odbornou radu.