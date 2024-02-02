---
title: Přidejte Circle Elipse do PostScriptu (PS) pomocí Aspose.Page
linktitle: Přidat Circle Elipse do PostScriptu (PS)
second_title: Aspose.Page .NET API
description: Naučte se, jak bez námahy přidat elipsy kruhu do dokumentů PostScript (PS) pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 10
url: /cs/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Úvod

Vítejte v tomto komplexním tutoriálu o přidávání elips kruhu do dokumentů PostScript (PS) pomocí Aspose.Page for .NET. Aspose.Page je výkonná knihovna, která umožňuje vývojářům bezproblémově pracovat s PostScriptem a dalšími formáty dokumentů. V této příručce vás provedeme procesem snadného začlenění kruhových elips do dokumentů PS.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

1.  Knihovna Aspose.Page for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Page for .NET z[tady](https://releases.aspose.com/page/net/).

2. Vývojové prostředí: Ujistěte se, že máte na svém počítači nastavené funkční vývojové prostředí .NET.

Nyní začneme s průvodcem krok za krokem.

## Import jmenných prostorů

V prvním kroku musíte importovat potřebné jmenné prostory, aby byla ve vašem kódu dostupná funkce Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní si uvedený příklad rozdělíme do několika kroků, které vás provedou procesem přidávání kruhových elips do dokumentu PostScript.

## Krok 1: Nastavte adresář dokumentů

```csharp
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```

Ujistěte se, že jste nahradili "Your Document Directory" skutečnou cestou k vašemu adresáři dokumentů.

## Krok 2: Vytvořte výstupní proud pro dokument PostScript

```csharp
//Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Zde je vytvořen FileStream pro zápis dokumentu PostScript a režim souboru je nastaven na vytvoření nového souboru.

## Krok 3: Vytvořte možnosti uložení a dokument PS

```csharp
//Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();

// Vytvořte nový 1stránkový dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

Tento krok zahrnuje vytvoření možností uložení s velikostí A4 a inicializaci nového 1stránkového dokumentu PS.

## Krok 4: Vytvořte grafickou cestu pro první elipsu

```csharp
//Vytvořte cestu grafiky z první elipsy
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Pro první elipsu je vytvořena grafická cesta, která určuje její polohu a rozměry.

## Krok 5: Nastavte Malování a Vyplňte elipsu

```csharp
//Nastavte barvu
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Vyplňte elipsu
document.Fill(path);
```

Zde se nastaví barva a první elipsa se vyplní zadanou barvou.

## Krok 6: Vytvořte grafickou cestu pro druhou elipsu

```csharp
//Vytvořte cestu grafiky z druhé elipsy
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Podobně je vytvořena grafická cesta pro druhou elipsu, která definuje její polohu a rozměry.

## Krok 7: Nastavte tah a nakreslete elipsu

```csharp
//Nastavit zdvih
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Vytáhněte (obryste) elipsu
document.Draw(path);
```

V tomto kroku je nastaven tah a druhá elipsa je ohraničena zadanou barvou a tloušťkou čáry.

## Krok 8: Zavřete aktuální stránku a uložte dokument

```csharp
//Zavřít aktuální stránku
document.ClosePage();

//Uložte dokument
document.Save();
```

Nakonec se aktuální stránka zavře a celý dokument se uloží, čímž je proces dokončen.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přidat elipsy kruhu do PostScriptových dokumentů pomocí Aspose.Page for .NET. Tento výukový program poskytuje podrobného průvodce krok za krokem, který vám pomůže bezproblémově integrovat tuto funkci do vašich projektů.

## FAQ

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?

 A1: Aspose.Page se primárně zaměřuje na PostScript, ale Aspose poskytuje další knihovny pro různé formáty dokumentů. Zkontrolovat[Založte dokumentaci](https://reference.aspose.com/page/net/) Více podrobností.

### Q2: Kde najdu další podporu a komunitní diskuse?

 A2: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za komunitní diskuse a podporu.

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

 A3: Ano, máte přístup k[zkušební verze zdarma](https://releases.aspose.com/)prozkoumat funkce Aspose.Page for .NET.

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page?

 A4: Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro účely testování a hodnocení.

### Q5: Kde mohu zakoupit Aspose.Page pro .NET?

 A5: Nákup Aspose.Page pro .NET z[koupit stránku](https://purchase.aspose.com/buy).