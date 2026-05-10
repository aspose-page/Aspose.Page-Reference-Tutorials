---
date: 2026-03-26
description: Naučte se, jak vytvořit dokument PostScript v .NET s texturovanými dlaždicovými
  vzory pomocí Aspose.Page. Postupujte podle našeho krok‑za‑krokem průvodce a přidejte
  bohaté textury do svých PS souborů.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Vytvořit dokument PostScript .NET s dlážděním textur
url: /cs/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PostScript .NET dokumentu s texturovaným dlážděním

## Jak vytvořit PostScript dokument .NET s texturovaným dlážděním

V tomto tutoriálu se naučíte, jak **vytvořit PostScript dokument .NET** a obohatit jej o texturovaný dlážděný vzor pomocí knihovny Aspose.Page. Provedeme vás každým krokem, od nastavení projektu až po vyplnění a obkreslení textu texturovaným štětcem, abyste během několika minut mohli vytvářet vizuálně atraktivní PS soubory.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Page for .NET  
- **Mohu použít .NET Core?** Yes, the library supports .NET Core and .NET 5/6  
- **Jaké formáty obrázků fungují pro texturu?** Any format supported by System.Drawing (BMP, PNG, JPEG, etc.)  
- **Jak dlouho trvá implementace?** About 10‑15 minutes for a basic example  
- **Potřebuji licenci?** A free trial works for testing; a license is required for production  

## Požadavky

- [Visual Studio](https://visualstudio.microsoft.com/) nainstalovaný na vašem počítači.  
- Základní znalost programování v C#.  
- Stáhněte a nainstalujte [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- Obrázkový soubor pro texturovaný vzor (např. **TestTexture.bmp**).

## Import jmenných prostorů

Ve vašem C# souboru importujte požadované jmenné prostory, aby kompilátor věděl, kde najít typy, které budeme používat:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavení adresáře dokumentu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Nahraďte **Your Document Directory** složkou, do které chcete uložit vygenerovaný PS soubor.

## Krok 2: Vytvoření výstupního proudu pro PS dokument

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Tento blok otevře souborový stream, nastaví velikost stránky (A4 jako výchozí) a vytvoří novou instanci **PsDocument**, na kterou budeme kreslit.

## Krok 3: Použití texturovaného dlážděného vzoru

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Zde načteme bitmapu, zabalíme ji do **TextureBrush**, volitelně ji roztáhneme horizontálně a řekneme **PsDocument**, aby tento štětec použil pro následující kreslicí operace.

## Krok 4: Vytvoření cesty obdélníku a vyplnění

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Jednoduchý obdélník je definován a vyplněn texturovaným štětcem, který jsme nastavili dříve.

## Krok 5: Nastavení tahu a kreslení

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Získáme aktuální barvu (texturovaný štětec), vytvoříme červené pero pro obrys a nakreslíme okraj obdélníku.

## Krok 6: Vyplnění a obkreslení textu texturovaným vzorem

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Tento krok demonstruje schopnost **fill and stroke text**: znaky „ABC“ jsou vyplněny texturovaným štětcem a poté obkresleny, což vytváří výrazný vizuální efekt.

## Krok 7: Uložení a uzavření dokumentu

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Uzavření stránky dokončí kreslicí příkazy a `Save()` zapíše PostScript soubor na disk.

## Časté problémy a řešení

- **Textura se zobrazuje nesprávně natažená** – upravte hodnoty `Matrix` pro řízení měřítka v osách X/Y.  
- **Obrázek nebyl nalezen** – ověřte, že `dataDir` ukazuje na správnou složku a že název souboru přesně odpovídá, včetně velikosti písmen.  
- **Barvy vypadají špatně** – pamatujte, že PostScript používá zařízení‑nezávislý barevný prostor; ujistěte se, že používáte objekty `Color`, které jsou správně mapovány.

## Často kladené otázky

**Q:** Můžu použít jiné formáty obrázků pro texturovaný vzor?  
**A:** Ano, jakýkoli formát podporovaný `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, atd.) funguje.

**Q:** Je Aspose.Page kompatibilní s .NET Core?  
**A:** Rozhodně. Knihovna běží na .NET Framework, .NET Core a .NET 5/6.

**Q:** Jak změním velikost texturovaného obdélníku?  
**A:** Upravit hodnoty `RectangleF` v kroku vytváření obdélníku (např. `new RectangleF(0, 0, 300, 150)`).

**Q:** Můžu v jednom dokumentu použít více texturovaných vzorů?  
**A:** Ano. Stačí vytvořit nový `TextureBrush` s jiným obrázkem a znovu zavolat `SetPaint` před kreslením dalšího tvaru nebo textu.

**Q:** Kde najdu více příkladů a referenci API?  
**A:** Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro komunitní pomoc a oficiální [documentation](https://reference.aspose.com/page/net/) pro podrobné použití API.

## Závěr

Nyní víte, jak **vytvořit PostScript dokument .NET** a aplikovat texturovaný dlážděný vzor, včetně toho, jak **vyplnit a obkreslit text** touto texturou. Experimentujte s různými obrázky, škálovacími maticemi a kreslicími primitivy, abyste vytvořili vlastní stylizované PS soubory pro zprávy, letáky nebo jakýkoli graficky náročný výstup.

---

**Poslední aktualizace:** 2026-03-26  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}