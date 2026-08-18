---
date: 2026-02-23
description: Naučte se, jak přidat gradient do souborů PostScript, uložit soubor PostScript
  s formátem stránky A4 a vyplnit obdélník gradientem pomocí Aspose.Page pro .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Jak přidat gradient – diagonální gradient v PostScriptu (PS) s Aspose.Page
  .NET
url: /cs/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

 >}}

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat gradient: Diagonální gradient do PostScriptu (PS) s Aspose.Page .NET

## Introduction

Přidání diagonálního gradientu do dokumentu PostScript (PS) může dramaticky zlepšit vizuální přitažlivost, zejména když potřebujete **jak přidat gradient** efekty v technických zprávách, brožurách nebo aplikacích zaměřených na grafiku. V tomto tutoriálu uvidíte přesně, jak přidat gradient do souboru PostScript, nastavit velikost stránky A4 a vyplnit obdélník plynulým přechodem barev pomocí Aspose.Page pro .NET.

## Quick Answers
- **Jaká knihovna je vyžadována?** Aspose.Page for .NET  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Mohu změnit směr gradientu?** Ano – otočte transformaci štětce, jak je ukázáno v kódu  
- **Jak uložím výsledek?** Použijte `PsDocument.Save()`, který zapíše soubor PostScript na disk  
- **Je pro produkci potřeba licence?** Ano, komerční licence odemkne plnou funkčnost  

## What is a diagonal gradient in PostScript?

Co je diagonální gradient v PostScriptu?

Diagonální gradient je lineární přechod barev, který probíhá pod úhlem (typicky 45°) přes tvar. V PostScriptu se to dosahuje použitím `LinearGradientBrush` s vlastním transformačním maticí, která otáčí, škáluje a posouvá gradient tak, aby odpovídal požadovanému obdélníku.

## Why use Aspose.Page for gradient fills?

Proč použít Aspose.Page pro výplně gradientem?

Aspose.Page abstrahuje nízkoúrovňové příkazy PostScriptu, což vám umožňuje pracovat se známými .NET grafickými objekty. Můžete vytvářet složité výplně, nastavit rozměry stránky a exportovat přímo do **uložení souboru PostScript** bez nutnosti pracovat s čistou PS syntaxí.

## Prerequisites

- **Aspose.Page for .NET Library** – stáhněte ji [zde](https://releases.aspose.com/page/net/).  
- **Document Directory** – složka, do které bude zapsán vygenerovaný soubor `*.ps`.

Nyní, když máme základy pokryté, projděme implementaci krok za krokem.

## Import Namespaces

Nejprve importujte jmenné prostory, které vám poskytují přístup k zařízení EPS, nástrojům pro kreslení a třídám I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Vytvořte výstupní stream pro dokument PostScript (Vytvořit dokument PostScript)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Krok 2: Nastavte velikost stránky A4 (Možnosti uložení)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: Vytvořte nový jednopage PS dokument

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: Definujte parametry obdélníku

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Krok 5: Vytvořte grafickou cestu

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Krok 6: Vytvořte lineární gradientový štětec (Vyplnit gradientem obdélník)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Krok 7: Vytvořte transformaci pro štětec

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Krok 8: Aplikujte transformace na štětec (Otočit, škálovat, posunout)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Krok 9: Nastavte transformaci pro štětec

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Krok 10: Nastavte barvu a vyplňte obdélník

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Krok 11: Zavřete aktuální stránku

```csharp
	//Close current page
	document.ClosePage();
```

## Krok 12: Uložte dokument (Uložit soubor PostScript)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Jak uložit soubor PostScript

Volání `PsDocument.Save()` zapíše kompletní obsah PostScriptu do streamu, který jste otevřeli v **kroku 1**. Po dokončení bloku `using` bude soubor `DiagonaGradient_outPS.ps` k dispozici ve složce, kterou jste určili.

## Common Use Cases

Běžné případy použití

- **Technická dokumentace**, která potřebuje jemné pozadí stínování.  
- **Marketingové brožury**, kde diagonální gradient přidává moderní vzhled.  
- **Automatizované generátory zpráv**, které vytvářejí tisknutelné PS soubory za běhu.

## Troubleshooting & Tips

Řešení problémů a tipy

- **Nesprávné barvy** – dvakrát zkontrolujte ARGB hodnoty předané do `LinearGradientBrush`.  
- **Gradient není viditelný** – ujistěte se, že transformační matice správně otáčí a škáluje; volání `Rotate(-45)` nastavuje diagonální úhel.  
- **Soubor nebyl vytvořen** – ověřte, že `dataDir` ukazuje na existující složku a že aplikace má oprávnění k zápisu.

## Frequently Asked Questions

Často kladené otázky

**Q: Je Aspose.Page kompatibilní se všemi .NET frameworky?**  
A: Aspose.Page podporuje širokou škálu verzí .NET, od .NET Framework 4.5+ po .NET 6+, což zajišťuje širokou kompatibilitu.

**Q: Mohu v Aspose.Page přizpůsobit barvy gradientu?**  
A: Ano, můžete při vytváření `LinearGradientBrush` zadat libovolné ARGB barvy, což vám dává plnou kontrolu nad počátečními a koncovými odstíny.

**Q: Je k dispozici zkušební verze Aspose.Page?**  
A: Ano, můžete prozkoumat funkce Aspose.Page stažením zkušební verze [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page?**  
A: Získejte dočasnou licenci pro Aspose.Page [zde](https://purchase.aspose.com/temporary-license/), abyste během hodnocení odemkli další funkce.

**Q: Kde mohu najít komunitní podporu pro Aspose.Page?**  
A: Zapojte se do komunity Aspose.Page na [fóru](https://forum.aspose.com/c/page/39) pro pomoc a diskuse.

---

**Poslední aktualizace:** 2026-02-23  
**Testováno s:** Aspose.Page for .NET (nejnovější stabilní verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}