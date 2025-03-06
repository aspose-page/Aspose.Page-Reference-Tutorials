---
title: Přidejte horizontální přechod do PostScriptu (PS) pomocí Aspose.Page
linktitle: Přidat horizontální přechod do PostScriptu (PS)
second_title: Aspose.Page .NET API
description: Vylepšete PostScriptové dokumenty s úžasnými horizontálními přechody pomocí Aspose.Page pro .NET. Pro bezproblémovou implementaci postupujte podle našeho podrobného návodu.
weight: 12
url: /cs/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte horizontální přechod do PostScriptu (PS) pomocí Aspose.Page

## Úvod

Vítejte v tomto komplexním kurzu o přidávání horizontálních přechodů do dokumentů PostScript (PS) pomocí Aspose.Page for .NET. Aspose.Page je výkonná knihovna, která usnadňuje manipulaci s dokumenty v různých formátech a poskytuje vývojářům nástroje, které potřebují k bezproblémovému vytváření, úpravám a vykreslování dokumentů.

tomto tutoriálu se zaměříme na vylepšení vašich PostScriptových dokumentů začleněním poutavých horizontálních přechodů. Provedeme vás každým krokem procesu a zajistíme, že získáte důkladné pochopení implementace.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Ujistěte se, že máte knihovnu Aspose.Page for .NET integrovanou do vašeho vývojového prostředí. Můžete si jej stáhnout z[Aspose.Page pro dokumentaci .NET](https://reference.aspose.com/page/net/).

- Adresář dokumentů: Nastavte adresář pro ukládání dokumentů a nahraďte "Váš adresář dokumentů" v poskytnutém kódu skutečnou cestou.

Nyní se podívejme, jak přidat vodorovný přechod do dokumentu PostScript krok za krokem.

## Import jmenných prostorů

Než začnete, je nezbytné importovat potřebné jmenné prostory pro přístup k funkcím poskytovaným Aspose.Page. Na začátek kódu přidejte následující jmenné prostory:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavte dokument

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

// Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Vytvořte možnosti uložení s velikostí A4
    PsSaveOptions options = new PsSaveOptions();

    // Vytvořte nový 1stránkový dokument PS
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Definujte přechodový obdélník a barvy

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Vytvořte cestu grafiky z prvního obdélníku
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Vytvořte štětec s lineárním přechodem s obdélníkem jako hranice, počáteční a koncové barvy
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Krok 3: Nastavte Transform pro štětec

```csharp
    // Vytvořte transformaci pro štětec. Složka měřítka X a Y se musí rovnat šířce a výšce obdélníku.
    // Komponenty překladu jsou posuny obdélníku
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Nastavit transformaci
    brush.Transform = brushTransform;
```

## Krok 4: Nastavte Malování a Vyplňte obdélník

```csharp
    // Nastavte barvu
    document.SetPaint(brush);

    // Vyplňte obdélník
    document.Fill(path);
```

## Krok 5: Vyplňte text přechodem

```csharp
    // Vyplňte text přechodem
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Krok 6: Nastavte tah a obrysový text

```csharp
    // Nastavte aktuální zdvih
    document.SetStroke(new Pen(brush, 5));
    // Obrysový text s přechodem
    document.OutlineText("ABC", font, 200, 400);
```

## Krok 7: Zavřete aktuální stránku a uložte dokument

```csharp
    // Zavřít aktuální stránku
    document.ClosePage();

    // Uložte dokument
    document.Save();
}
```

Gratulujeme! Úspěšně jste přidali horizontální přechod do dokumentu PostScript pomocí Aspose.Page for .NET.

## Závěr

V tomto tutoriálu jsme se zabývali procesem vylepšování vašich PostScriptových dokumentů s horizontálními přechody pomocí knihovny Aspose.Page for .NET. Sledováním tohoto podrobného průvodce jste získali cenné poznatky o využití tohoto mocného nástroje pro manipulaci s dokumenty.

## FAQ

### Q1: Mohu použít přechody na jiné tvary kromě obdélníků?

 Odpověď 1: Ano, pomocí Aspose.Page můžete použít přechody na různé tvary. Upravte`GraphicsPath` vytvoření podle vašeho konkrétního tvaru.

### Q2: Jak mohu změnit barvy přechodu?

 A2: Upravte`Color.FromArgb` hodnoty v`LinearGradientBrush` instanciací k dosažení požadovaných barev přechodu.

### Q3: Je Aspose.Page kompatibilní s různými formáty dokumentů?

A3: Aspose.Page podporuje různé formáty dokumentů, včetně XPS, PS, PDF a dalších. Úplný seznam naleznete v dokumentaci.

### Q4: Mohu použít Aspose.Page pro komerční projekty?

 A4: Ano, Aspose.Page je dodáván s možnostmi komerčních licencí. Návštěva[tady](https://purchase.aspose.com/buy) pro detaily.

### Q5: Existuje komunitní fórum pro uživatele Aspose.Page?

 A5: Ano, připojte se ke komunitě Aspose.Page na[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) spojit se s ostatními uživateli a vyhledat pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
