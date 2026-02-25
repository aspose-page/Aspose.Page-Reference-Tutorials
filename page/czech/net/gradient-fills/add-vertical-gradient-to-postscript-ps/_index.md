---
date: 2026-02-25
description: Naučte se, jak použít lineární gradientový štětec v C# k přidání gradientu
  do souborů PS a vyplnit obdélník gradientem pomocí Aspose.Page pro .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Lineární gradientová štětka – Přidat vertikální gradient do PostScriptu
  (PS) pomocí Aspose.Page
url: /cs/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Přidání vertikálního gradientu do PostScript (PS) pomocí Aspose.Page

## Úvod

V oblasti manipulace a tvorby dokumentů **Aspose.Page for .NET** vyniká jako výkonný nástroj pro vývojáře. V tomto průvodci se dozvíte, jak **přidat gradient do PS** souborů pomocí **C# linear gradient brush** k **vyplnění obdélníku gradientem**. Na konci tohoto tutoriálu budete mít jasné, krok‑za‑krokem pochopení požadovaného kódu a toho, proč tato technika vytváří plynulý vertikální gradient ve vašem výstupu PostScript.

## Rychlé odpovědi
- **Co dělá C# linear gradient brush?** Vytváří plynulý přechod mezi více barvami napříč tvarem.
- **Lze jej použít s libovolnou verzí .NET?** Ano, Aspose.Page podporuje .NET Framework 4.5+ a .NET Core/5+.
- **Potřebuji licenci pro produkci?** Pro ne‑evaluační sestavení je vyžadována komerční licence.
- **Je gradient skutečně vertikální?** Štětec je otočen o 90°, což zajišťuje vertikální tok.
- **Kam se ukládá výstup?** Do cesty, kterou zadáte v `dataDir` (např. `VerticalGradient_outPS.ps`).

## Co je C# Linear Gradient Brush?
**C# linear gradient brush** je objekt GDI+ (`LinearGradientBrush`), který kreslí lineární přechod barev mezi definovanými body. V kombinaci s kreslícím API Aspose.Page vám umožňuje přímo do dokumentu PostScript (PS) vykreslit propracované gradienty.

## Proč použít Linear Gradient Brush pro PostScript?
- **Vysoce kvalitní výstup:** Gradienty jsou renderovány na úrovni tiskárny, zachovávají věrnost.
- **Plná kontrola:** Můžete nastavit vlastní barevné zastávky, rotaci a škálování.
- **Znovupoužitelný kód:** Stejná logika štětce funguje pro PDF, SVG i další formáty podporované Aspose.Page.

## Požadavky

Než se pustíte do tutoriálu, ujistěte se, že máte následující:

- Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page. Potřebné zdroje a dokumentaci najdete [zde](https://reference.aspose.com/page/net/).
- Vývojové prostředí: Nastavte vhodné vývojové prostředí, včetně integrovaného vývojového prostředí (IDE) pro .NET vývoj.
- Základní znalosti: Seznamte se se základy .NET vývoje, včetně práce se streamy, grafickými cestami a manipulací s barvami.

## Import Namespaces

Ve vašem C# projektu zahrňte požadované jmenné prostory na začátku souboru s kódem:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavení adresáře dokumentu

Určete cestu k adresáři, kde bude váš PS dokument uložen.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvoření výstupního streamu pro PostScript dokument

Vytvořte výstupní stream pro PostScript dokument pomocí třídy `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Krok 3: Vytvoření možností uložení a PS dokumentu

Vytvořte možnosti uložení s velikostí A4 a inicializujte nový jednopage PS dokument.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: Definice rozměrů obdélníku

Zadejte rozměry a pozici obdélníku, kde bude aplikován vertikální gradient.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Krok 5: Vytvoření grafické cesty

Sestavte grafickou cestu z definovaného obdélníku.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Krok 6: Definice interpolačních barev

Stanovte pole interpolačních barev a pozic pro gradient.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Krok 7: Vytvoření Linear Gradient Brush

Vytvořte linear gradient brush s obdélníkem jako ohraničením, počáteční a koncovou barvou.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Krok 8: Nastavení transformace štětce

Nastavte transformaci pro štětec tak, aby komponenty měřítka X a Y odpovídaly šířce a výšce obdélníku.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Krok 9: Nastavení barvy a vyplnění obdélníku

Nastavte barvu pro dokument a **vyplňte obdélník gradientem** pomocí dříve definované cesty.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Krok 10: Uzavření aktuální stránky a uložení dokumentu

Uzavřete aktuální stránku a uložte PostScript dokument.

```csharp
document.ClosePage();
document.Save();
```

Gratulujeme! Úspěšně jste **přidali vertikální gradient do PostScript dokumentu** pomocí **C# linear gradient brush** s Aspose.Page for .NET. Experimentujte s různými parametry a barvami, abyste dosáhli různých vizuálních efektů ve svých dokumentech.

## Časté problémy a řešení

| Problém | Proč se vyskytuje | Jak opravit |
|---------|-------------------|-------------|
| Gradient se zobrazuje horizontálně | Rotace štětce nebyla aplikována | Ujistěte se, že je před přiřazením k `brush.Transform` zavoláno `brushTransform.Rotate(90);`. |
| Barvy vypadají vybledle | Nízké rozlišení výstupního streamu | Použijte vyšší rozlišení `PsSaveOptions` nebo zvětšete velikost dokumentu. |
| Výstupní soubor je prázdný | Stream nebyl vyprázdněn | Ověřte, že je voláno `document.Save();` mimo blok `using`. |

## Často kladené otázky

**Q1: Mohu použít více gradientů v různých oblastech stejného dokumentu?**  
A: Ano. Jednoduše opakujte kroky pro každou oblast s jejími specifickými rozměry a barevným schématem.

**Q2: Jak mohu integrovat tento kód do mého existujícího .NET projektu?**  
A: Zkopírujte a vložte kód do souboru projektu a ujistěte se, že máte odkaz na knihovnu Aspose.Page.

**Q3: Existují i jiné typy gradientů v Aspose.Page pro .NET?**  
A: Aspose.Page podporuje různé typy gradientů, včetně radiálních a cestových gradientů. Podívejte se do dokumentace pro více informací.

**Q4: Mohu používat Aspose.Page v komerčních projektech?**  
A: Ano. Navštivte [zde](https://purchase.aspose.com/buy) a prozkoumejte licenční možnosti.

**Q5: Existuje komunitní fórum pro Aspose.Page, kde mohu získat pomoc?**  
A: Samozřejmě! Přejděte na [Aspose.Page fórum](https://forum.aspose.com/c/page/39) a spojte se s ostatními vývojáři a získejte podporu.

---

**Poslední aktualizace:** 2026-02-25  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}