---
date: 2026-03-29
description: Naučte se, jak v C# použít štětec s lineárním přechodem k vytvoření pseudo‑průhlednosti
  v PostScriptu pomocí Aspose.Page pro .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Lineární gradientová štětka C# pro pseudo‑průhlednost v PS
url: /cs/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lineární štětec s gradientem C# pro pseudo‑průhlednost v PostScriptu (PS)

## Úvod

Pokud potřebujete přidat jemný efekt průhlednosti do svých souborů PostScript (PS), **linear gradient brush C#** je ideální nástroj. Aspose.Page pro .NET usnadňuje malování obdélníků s neprůhlednými i průhlednými výplněmi gradientu, což vašim dokumentům dodává moderní, vrstvený vzhled. V tomto tutoriálu vás provedeme přesnými kroky potřebnými k vytvoření pseudo‑průhlednosti pomocí lineárního štětce s gradientem v C#.

## Rychlé odpovědi
- **Která knihovna poskytuje lineární štětec s gradientem?** Aspose.Page for .NET
- **Která grafická třída vytváří gradient?** `LinearGradientBrush`
- **Mohu řídit neprůhlednost pro každou barvu?** Yes, using `Color.FromArgb(alpha, …)`
- **Potřebuji licenci pro produkci?** A valid Aspose.Page license is required
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Co je lineární štětec s gradientem C#?

`LinearGradientBrush` je objekt GDI+, který vykresluje plynulý přechod mezi dvěma barvami podél přímky. Když pro každou barvu určíte alfa kanál (0‑255), můžete vytvořit průhledné gradienty – přesně to, co potřebujeme pro pseudo‑průhlednost v PostScriptu.

## Proč použít lineární štětec s gradientem C# pro pseudo‑průhlednost?

- **Detailní řízení neprůhlednosti:** Nastavte alfa každé barvy, aby dosáhla požadované úrovně průhlednosti.  
- **Zařízení‑nezávislé vykreslování:** Štětec funguje stejně na obrazovce, PDF, EPS i PS výstupech.  
- **Jednoduché API:** Několik řádků C# kódu vytvoří profesionální vizuální efekty.

## Prerequisites

Před tím, než se ponoříte do kódu, ujistěte se, že máte:

- Aspose.Page pro .NET nainstalovaný. Můžete jej stáhnout z [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- Zapisovatelnou složku, kam bude uložen vygenerovaný PostScript dokument.

Nyní, když máte potřebné nástroje, začněme vytvářet pseudo‑průhledné obdélníky.

## Importovat jmenné prostory

Před začátkem importujte jmenné prostory, které obsahují třídy, jež budeme používat:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Vytvořit výstupní proud pro dokument PostScript

Začneme vytvořením souborového proudu, který bude obsahovat výsledný soubor PS, a poté inicializujeme `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Vytvořit obdélník s **neprůhlednou** výplní gradientu

Zde vytvoříme `LinearGradientBrush`, jehož barvy jsou zcela neprůhledné (alpha = 255). Tento obdélník bude sloužit jako vrstva pozadí.

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

## Krok 3: Vytvořit obdélník s **průhlednou** výplní gradientu

Nyní použijeme **linear gradient brush C#**, kde jsou hodnoty alfa menší než 255 (např. 150 a 50). To způsobí, že obdélník bude částečně průhledný, čímž dosáhneme efektu pseudo‑průhlednosti.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Krok 4: Zavřít stránku a uložit dokument

Nakonec dokončíme stránku a zapíšeme soubor PS na disk.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Dodržením těchto čtyř kroků můžete plynule kombinovat neprůhledné a průhledné obdélníky, čímž vytvoříte přesvědčivý pseudo‑průhledný efekt v jakémkoli výstupu PostScriptu.

## Časté problémy a řešení

| Problém | Proč se to stane | Řešení |
|-------|----------------|-----|
| Barvy se jeví jako plně neprůhledné | Hodnota alfa byla omylem nastavena na 255 | Use `Color.FromArgb(alpha, …)` with `alpha` < 255 |
| Gradient je nesprávně roztáhnut | Nesprávná transformační matice | Verify the matrix parameters match the rectangle dimensions |
| Výstupní soubor je prázdný | Proud není uzavřen nebo nebyla zavolána metoda `Save()` | Ensure `document.ClosePage()` and `document.Save()` are executed inside the `using` block |

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní se všemi verzemi .NET?**  
A: Aspose.Page pro .NET je kompatibilní s různými verzemi .NET frameworku, což zajišťuje flexibilitu a snadnou integraci.

**Q: Mohu použít pseudo‑průhlednost i na jiné tvary než obdélníky?**  
A: Ano, stejná principy lze použít na jakýkoli tvar úpravou `GraphicsPath` podle potřeby.

**Q: Kde mohu najít další příklady a dokumentaci?**  
A: Prozkoumejte [Aspose.Page documentation](https://reference.aspose.com/page/net/) pro komplexní příklady a podrobné reference API.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Page na [this link](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page?**  
A: Navštivte [this link](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci pro Aspose.Page.

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}