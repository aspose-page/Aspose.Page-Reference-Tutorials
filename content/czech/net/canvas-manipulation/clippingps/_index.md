---
title: Oříznutí PS pomocí Aspose.Page pro .NET
linktitle: Výstřižek PS
second_title: Aspose.Page .NET API
description: Prozkoumejte sílu Aspose.Page for .NET v tomto podrobném tutoriálu o ořezávání PostScriptových dokumentů. Naučte se bez námahy vylepšit své možnosti zpracování dokumentů.
type: docs
weight: 10
url: /cs/net/canvas-manipulation/clippingps/
---
## Úvod

Vítejte v obsáhlém tutoriálu o využití Aspose.Page pro .NET k implementaci ořezávání v dokumentech PostScript (PS). Tento tutoriál vás provede procesem ořezávání dokumentů PS pomocí Aspose.Page, výkonné knihovny pro práci s různými formáty dokumentů v aplikacích .NET.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Pracovní znalost programovacího jazyka C#.
-  Nainstalovaná knihovna Aspose.Page for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).
- Integrované vývojové prostředí (IDE), jako je Visual Studio.

## Import jmenných prostorů

Začněte importováním potřebných jmenných prostorů do kódu C#:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní si příklad rozdělíme do několika kroků:

## Krok 1: Nastavte adresář dokumentů

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte výstupní proud pro dokument PostScript

```csharp
// Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## Krok 3: Vytvořte možnosti uložení

```csharp
// Vytvořte možnosti uložení s výchozími hodnotami
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Vytvořte nový 1stránkový dokument PS

```csharp
// Vytvořte nový 1stránkový dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: Vytvořte grafickou cestu z obdélníku

```csharp
// Vytvořte cestu grafiky z obdélníku
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## Krok 6: Oříznutí podle tvaru

```csharp
// Uložte stav grafiky, abyste se po transformaci vrátili zpět do tohoto stavu
document.WriteGraphicsSave();

//Přemístit aktuální stav grafiky o 100 bodů doprava a 100 bodů dolů.
document.Translate(100, 100);

// Vytvořte grafickou cestu z kruhu
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Přidejte do aktuálního grafického stavu oříznutí podle kruhu
document.Clip(circlePath);

// Nastavit malování v aktuálním stavu grafiky
document.SetPaint(new SolidBrush(Color.Blue));

// Vyplňte obdélník v aktuálním grafickém stavu (s oříznutím)
document.Fill(rectanglePath);

// Obnovte stav grafiky na předchozí (vyšší) úroveň
document.WriteGraphicsRestore();
```

## Krok 7: Přemístění stavu grafiky horní úrovně

```csharp
// Přemístit stav grafiky horní úrovně o 100 bodů doprava a 100 bodů dolů.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Nakreslete obdélník v aktuálním grafickém stavu (nemá žádné oříznutí) nad oříznutým obdélníkem
document.Draw(rectanglePath);
```

## Krok 8: Zavřete a uložte dokument

```csharp
// Zavřít aktuální stránku
document.ClosePage();

// Uložte dokument
document.Save();
```

Nyní jste úspěšně implementovali oříznutí v dokumentu PostScript pomocí Aspose.Page for .NET.

## Závěr

V tomto kurzu jste se naučili, jak využít Aspose.Page for .NET k implementaci ořezávání v PostScriptových dokumentech. Tato výkonná knihovna poskytuje bezproblémový a efektivní způsob zpracování různých formátů dokumentů ve vašich aplikacích .NET.

## FAQ

### Q1: Mohu používat Aspose.Page pro .NET s jinými programovacími jazyky?

A1: Aspose.Page je primárně určen pro aplikace .NET. Aspose však poskytuje podobné knihovny pro jiné programovací jazyky.

### Q2: Kde najdu další příklady a dokumentaci pro Aspose.Page for .NET?

 A2: Můžete prozkoumat další příklady a podrobnou dokumentaci na[Dokumentace Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

 A3: Ano, máte přístup k bezplatné zkušební verzi Aspose.Page pro .NET[tady](https://releases.aspose.com/).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A4: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Kde mohu získat podporu nebo diskutovat o dotazech souvisejících s Aspose.Page?

 A5: Navštivte[Aspose.Page fóra](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.