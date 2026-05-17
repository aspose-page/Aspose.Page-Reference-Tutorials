---
date: 2026-02-25
description: Vylepšete dokumenty PostScript lineárním gradientovým obdélníkem pomocí
  Aspose.Page pro .NET. Postupujte podle našeho krok‑za‑krokem průvodce a naučte se
  gradientní výplň textu i gradient obrysu textu.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Přidat obdélník s lineárním gradientem do PostScriptu (PS) pomocí Aspose.Page
url: /cs/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání lineárního gradientního obdélníku do PostScriptu (PS) pomocí Aspose.Page

## Úvod

Vítejte v tomto komplexním tutoriálu o přidání **lineárního gradientního obdélníku** do dokumentů PostScript (PS) pomocí Aspose.Page pro .NET. Aspose.Page je výkonná knihovna, která vám umožňuje vytvářet, upravovat a renderovat dokumenty v různých formátech, a dnes se zaměříme na to, jak do vašich PS souborů přinést poutavé gradienty.

### Rychlé odpovědi
- **Co dělá lineární gradientní obdélník?** Vyplní obdélníkovou oblast plynulým přechodem barev z jedné strany na druhou.  
- **Které API zpracovává vyplnění textu gradientem?** `LinearGradientBrush` v kombinaci s `SetPaint` a `FillAndStrokeText`.  
- **Mohu obkreslit text gradientem?** Ano — použijte `SetStroke` s gradientním štětcem a zavolejte `OutlineText`.  
- **Potřebuji licenci pro produkci?** Pro ne‑evaluační použití je vyžadována komerční licence Aspose.Page.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Předpoklady

Než se pustíme dál, ujistěte se, že máte:

- Aspose.Page for .NET Library: Ujistěte se, že je knihovna přidána do vašeho projektu. Můžete si ji stáhnout z [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Document Directory: Vytvořte složku na disku, kam bude uložen vygenerovaný PS soubor, a v kódu nahraďte **„Your Document Directory“** touto cestou.

## Importování jmenných prostorů

Pro začátek importujte jmenné prostory, které vám poskytují přístup ke kreslícím a PS‑specifickým třídám:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Co je lineární gradientní obdélník?

**Lineární gradientní obdélník** je jednoduše obdélníkový tvar, jehož vnitřek je natřen lineárním gradientem — barvy přecházejí plynule podél přímky, typicky zleva doprava (horizontální) nebo shora dolů (vertikální). V Aspose.Page to dosáhnete kombinací `GraphicsPath`, který definuje obdélník, a `LinearGradientBrush`, který popisuje přechod barev.

## Proč používat vyplnění textu gradientem a obrysový gradient textu?

- **Vizuální přitažlivost:** Text vyplněný gradientem přidává hloubku a moderní styl do zpráv, faktur nebo propagačních materiálů.  
- **Konzistence značky:** Přizpůsobte firemní barvy pomocí přesných ARGB hodnot.  
- **Všestrannost:** Ten samý štětec lze znovu použít pro vyplnění tvarů, vyplnění textu a obrysové gradienty, čímž se snižuje duplicita kódu.

## Krok 1: Nastavení dokumentu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Definování gradientního obdélníku a barev

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Krok 3: Nastavení transformace pro štětec

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Krok 4: Nastavení barvy a vyplnění obdélníku

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Jak použít vyplnění textu gradientem

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Použití obrysového gradientu pro text

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Krok 7: Uzavření aktuální stránky a uložení dokumentu

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Gratulujeme! Úspěšně jste přidali **lineární gradientní obdélník** do PostScript dokumentu a použili stejný štětec pro **vyplnění textu gradientem** a **obrysový gradient textu**.

## Běžné případy použití a tipy

- **Záhlaví zpráv:** Vyplňte velké bloky textu gradienty pro zvýraznění názvů sekcí.  
- **Loga značek:** Znovu vytvořte tvary loga s gradientním vyplněním pro konzistentní branding.  
- **Profesionální tip:** Znovu použijte stejnou instanci `LinearGradientBrush` pro více kreslících volání, aby byly barvy dokonale zarovnané napříč tvary a textem.

## Často kladené otázky

### Q1: Mohu použít gradienty na jiné tvary než obdélníky?
**A:** Ano, můžete aplikovat gradienty na jakýkoli tvar definovaný pomocí `GraphicsPath`. Jednoduše přidejte kruhy, polygonové tvary nebo vlastní cesty před voláním `document.Fill(path)`.

### Q2: Jak mohu změnit barvy gradientu?
**A:** Upravit hodnoty `Color.FromArgb` při vytváření `LinearGradientBrush`. První barva je počáteční, druhá je koncová barva gradientu.

### Q3: Je Aspose.Page kompatibilní s různými formáty dokumentů?
**A:** Rozhodně. Aspose.Page podporuje XPS, PS, PDF a několik dalších vektorových formátů. Pro úplný seznam zkontrolujte oficiální dokumentaci.

### Q4: Mohu používat Aspose.Page pro komerční projekty?
**A:** Ano, je k dispozici komerční licence. Podrobnosti najdete na stránce nákupu: [here](https://purchase.aspose.com/buy).

### Q5: Kde mohu najít komunitní podporu?
**A:** Připojte se k fóru komunity Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Poslední aktualizace:** 2026-02-25  
**Testováno s:** Aspose.Page 24.10 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}