---
title: Přidejte diagonální přechod do PostScriptu (PS) pomocí Aspose.Page .NET
linktitle: Přidat diagonální přechod do PostScriptu (PS)
second_title: Aspose.Page .NET API
description: Prozkoumejte jednoduchost přidávání diagonálních přechodů do PostScriptových dokumentů v .NET pomocí Aspose.Page. Pozvedněte své projekty pomocí dynamických vizuálních prvků.
weight: 10
url: /cs/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte diagonální přechod do PostScriptu (PS) pomocí Aspose.Page .NET

## Úvod

Přidání diagonálního přechodu do dokumentu PostScript (PS) může vašim projektům přinést vizuální přitažlivost a kreativitu. Aspose.Page for .NET poskytuje bezproblémové řešení pro integraci této funkce do vašich aplikací. V tomto tutoriálu vás krok za krokem provedeme procesem přidání diagonálního přechodu do dokumentu PS pomocí Aspose.Page.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

- Adresář dokumentů: Nastavte adresář pro vaše dokumenty, kam bude uložen výstupní soubor PS.

Nyní přejdeme k podrobnému průvodci.

## Import jmenných prostorů

Nejprve se ujistěte, že jste do projektu importovali potřebné jmenné prostory. Tyto jmenné prostory jsou klíčové pro práci s funkcemi Aspose.Page.

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Krok 2: Vytvořte možnosti uložení s velikostí A4

```csharp
	//Vytvořte možnosti uložení s velikostí A4
	PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: Vytvořte nový 1stránkový dokument PS

```csharp
	// Vytvořte nový 1stránkový dokument PS
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: Definujte parametry obdélníku

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Krok 5: Vytvořte grafickou cestu

```csharp
	//Vytvořte cestu grafiky z prvního obdélníku
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Krok 6: Vytvořte štětec s lineárním přechodem

```csharp
	//Vytvořte štětec s lineárním přechodem s obdélníkem jako hranice, počáteční a koncové barvy
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Krok 7: Vytvořte Transform for Brush

```csharp
	//Vytvořte transformaci pro štětec. Složka měřítka X a Y se musí rovnat šířce a výšce obdélníku.
	// Komponenty překladu jsou posuny obdélníku
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Krok 8: Aplikujte transformace na štětec

```csharp
	//Otočte přechod, poté škálujte a překládejte, abyste získali viditelný barevný přechod v požadovaném obdélníku
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Krok 9: Nastavte Transform na Brush

```csharp
	//Nastavit transformaci
	brush.Transform = brushTransform;
```

## Krok 10: Nastavte barvu a vyplňte obdélník

```csharp
	//Nastavte barvu
	document.SetPaint(brush);

	//Vyplňte obdélník
	document.Fill(path);
```

## Krok 11: Zavřete aktuální stránku

```csharp
	//Zavřít aktuální stránku
	document.ClosePage();
```

## Krok 12: Uložte dokument

```csharp
	//Uložte dokument
	document.Save();
}
// Rozšíření: 1
```

Pomocí těchto kroků úspěšně přidáte diagonální přechod do dokumentu PostScript pomocí Aspose.Page for .NET.

## Závěr

Vylepšení dokumentů PS pomocí diagonálních přechodů může učinit vaše projekty vizuálně přitažlivými a dynamickými. Aspose.Page for .NET tento proces zjednodušuje a umožňuje vývojářům bez námahy integrovat tuto funkci do svých aplikací.

## FAQ

### Q1: Je Aspose.Page kompatibilní se všemi .NET frameworky?

Odpověď 1: Aspose.Page podporuje různé rámce .NET, což zajišťuje kompatibilitu s celou řadou vývojových prostředí.

### Q2: Mohu přizpůsobit barvy přechodu v Aspose.Page?

Odpověď 2: Ano, Aspose.Page poskytuje flexibilitu při výběru a přizpůsobení barev přechodu podle požadavků vašeho projektu.

### Q3: Je k dispozici zkušební verze pro Aspose.Page?

 A3: Ano, můžete prozkoumat funkce Aspose.Page stažením zkušební verze[tady](https://releases.aspose.com/).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page?

 A4: Získejte dočasnou licenci pro Aspose.Page[tady](https://purchase.aspose.com/temporary-license/) pro odemknutí dalších funkcí.

### Q5: Kde najdu podporu komunity pro Aspose.Page?

 A5: Zapojte se do komunity Aspose.Page na[Fórum](https://forum.aspose.com/c/page/39) za pomoc a diskuze.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
