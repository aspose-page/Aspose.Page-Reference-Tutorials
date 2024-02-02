---
title: Aplikujte texturu Tiling Pattern na PostScript (PS) pomocí Aspose.Page
linktitle: Použít vzor dlaždic textury na PostScript (PS)
second_title: Aspose.Page .NET API
description: Vylepšete své PostScriptové (PS) dokumenty pomocí texturových vzorů pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro kreativní dotek.
type: docs
weight: 10
url: /cs/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## Úvod

Vítejte v tomto podrobném návodu, jak aplikovat vzor textury na PostScriptový (PS) dokument pomocí Aspose.Page for .NET. Aspose.Page je výkonná knihovna, která vám umožňuje pracovat s různými formáty dokumentů, a v tomto tutoriálu prozkoumáme, jak vylepšit vaše dokumenty PS přidáním vzorů dlaždic textury.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte následující:

- [Vizuální studio](https://visualstudio.microsoft.com/) nainstalovaný na vašem počítači.
- Základní znalost programování v C#.
-  Stáhněte a nainstalujte[Aspose.Page pro knihovnu .NET](https://releases.aspose.com/page/net/).
- Soubor obrázku pro vzorek textury (např. "TestTexture.bmp").

## Import jmenných prostorů

Ujistěte se, že ve svém kódu C# importujete potřebné jmenné prostory:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Pojďme si poskytnutý příklad rozdělit do několika kroků, které vás celým procesem provedou.

## Krok 1: Nastavte adresář dokumentů

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```

Nezapomeňte nahradit „Adresář vašich dokumentů“ cestou, kam chcete uložit dokument PS.

## Krok 2: Vytvořte výstupní stream pro dokument PS

```csharp
// Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Vytvořte možnosti uložení s velikostí A4
    PsSaveOptions options = new PsSaveOptions();

    // Vytvořte nový 1stránkový dokument PS
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Tento krok nastavuje výstupní proud pro dokument PS, včetně definování velikosti dokumentu.

## Krok 3: Aplikujte vzor textury obkladů

```csharp
// Vytvořte objekt Bitmap ze souboru obrázku
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Vytvořte texturový štětec z obrázku
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Přidejte do vzoru změnu měřítka ve směru X
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Nastavte tento štětec textury jako aktuální barvu
    document.SetPaint(brush);
}
```

Tento krok zahrnuje vytvoření texturového štětce z obrázku a jeho nastavení jako aktuální barvy pro dokument.

## Krok 4: Vytvořte obdélníkovou cestu a výplň

```csharp
// Vytvořte obdélníkovou cestu
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Vyplňte obdélník
document.Fill(path);
```

Zde definujeme cestu obdélníku a vyplníme ji dříve nastaveným texturovým štětcem.

## Krok 5: Nastavte Stroke a Draw

```csharp
// Získejte aktuální nátěr
Brush paint = document.GetPaint();

// Nastavit červený tah
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Vytáhněte obdélník
document.Draw(path);
```

Tento krok zahrnuje nastavení vlastností tahu a nakreslení vyznačeného obdélníku.

## Krok 6: Vyplňte a načrtněte text vzorem textury

```csharp
// Vyplňte text vzorem textury
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Obrysový text s texturou
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Nakonec text vyplníme a ohraničíme vzorem textury, čímž zvýšíme vizuální přitažlivost vašeho dokumentu.

## Krok 7: Uložte a zavřete dokument

```csharp
// Zavřít aktuální stránku
document.ClosePage();

// Uložte dokument
document.Save();
```

Chcete-li použít změny, nezapomeňte zavřít aktuální stránku a uložit dokument.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak pomocí Aspose.Page for .NET aplikovat vzor textury na PostScriptový dokument. Experimentujte s různými obrázky a vzory, abyste si své dokumenty PS dále přizpůsobili.

## FAQ

### Q1: Mohu použít jiné formáty obrázků pro vzor textury?

A1: Ano, Aspose.Page podporuje různé formáty obrázků. Zajistěte kompatibilitu s dokumentací knihovny.

### Q2: Je Aspose.Page kompatibilní s .NET Core?

A2: Ano, Aspose.Page je kompatibilní s .NET Framework i .NET Core.

### Q3: Jak mohu upravit velikost texturovaného obdélníku?

 A3: Upravte rozměry v`RectangleF` parametry při vytváření cesty.

### Q4: Mohu do jednoho dokumentu přidat více vzorků textur?

A4: Ano, proces můžete opakovat s různými obrázky a cestami.

### Q5: Kde najdu další zdroje a podporu?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity a prozkoumejte[dokumentace](https://reference.aspose.com/page/net/).
