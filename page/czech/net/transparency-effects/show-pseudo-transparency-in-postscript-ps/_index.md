---
title: Zobrazit pseudoprůhlednost v PostScriptu (PS) pomocí Aspose.Page
linktitle: Zobrazit pseudotransparentnost v PostScriptu (PS)
second_title: Aspose.Page .NET API
description: Prozkoumejte sílu pseudotransparentnosti v PostScriptu s Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro vizuálně úžasné dokumenty.
type: docs
weight: 13
url: /cs/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## Úvod

Chcete zlepšit vizuální přitažlivost vašich dokumentů PostScript (PS) začleněním pseudoprůhlednosti? Aspose.Page for .NET poskytuje výkonné řešení pro dosažení tohoto efektu bez námahy. V tomto tutoriálu krok za krokem vás provedeme procesem zobrazení pseudoprůhlednosti v PostScriptu pomocí Aspose.Page.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page pro .NET. Můžete si jej stáhnout z[Dokumentace Aspose.Page](https://reference.aspose.com/page/net/).

- Adresář dokumentů: Nastavte adresář pro ukládání dokumentů PostScript.

Nyní, když máte ve svém arzenálu potřebné nástroje, pojďme prozkoumat, jak předvést pseudotransparentnost v PostScriptu pomocí Aspose.Page.

## Import jmenných prostorů

Než se ponoříte do příkladu, ujistěte se, že jste importovali požadované jmenné prostory:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Vytvořte výstupní proud pro dokument PostScript

```csharp
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
//Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Vytvořte možnosti uložení s velikostí A4
	PsSaveOptions options = new PsSaveOptions();

	// Vytvořte nový 1stránkový dokument PS
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Vytvořte obdélník s neprůhlednou přechodovou výplní

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Krok 3: Vytvořte obdélník s průsvitnou přechodovou výplní

```csharp
	offsetX = 350;

	//Vytvořte cestu grafiky z prvního obdélníku
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Vytvořte barvy štětce s lineárním přechodem, jejichž průhlednost není 255, ale 150 a 50. Jsou tedy průsvitné.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Krok 4: Zavřete aktuální stránku a uložte dokument

```csharp
	document.ClosePage();
	document.Save();
}
// Rozšíření: 1
```

Dodržováním těchto kroků můžete bez problémů integrovat pseudoprůhlednost do svých dokumentů PostScript pomocí Aspose.Page for .NET.

## Závěr

Na závěr, Aspose.Page for .NET nabízí přímočarý a efektivní způsob, jak vylepšit vizuální prvky vašich dokumentů PostScript. Výše uvedené kroky poskytují jasnou cestu pro začlenění pseudotransparentnosti, což vám umožní vytvářet vizuálně ohromující výstupy.

## FAQ

### Q1: Je Aspose.Page kompatibilní se všemi verzemi .NET?

Odpověď 1: Aspose.Page for .NET je kompatibilní s různými verzemi rozhraní .NET, což zajišťuje flexibilitu a snadnou integraci.

### Q2: Mohu použít pseudoprůhlednost na jiné tvary kromě obdélníků?

Odpověď 2: Ano, stejné principy lze aplikovat na jiné tvary odpovídajícím přizpůsobením GraphicsPath.

### Q3: Kde najdu další příklady a dokumentaci?

 A3: Prozkoumejte[Dokumentace Aspose.Page](https://reference.aspose.com/page/net/) pro komplexní příklady a podrobnou dokumentaci.

### Q4: Je k dispozici bezplatná zkušební verze pro Aspose.Page?

 A4: Ano, máte přístup k bezplatné zkušební verzi Aspose.Page z[tento odkaz](https://releases.aspose.com/).

### Q5: Jak mohu získat dočasnou licenci pro Aspose.Page?

 A5: Návštěva[tento odkaz](https://purchase.aspose.com/temporary-license/) získat dočasnou licenci pro Aspose.Page.