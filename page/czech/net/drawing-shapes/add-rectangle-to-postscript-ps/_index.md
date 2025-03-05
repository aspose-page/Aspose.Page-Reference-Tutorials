---
title: Přidejte obdélník do PostScriptu (PS) pomocí Aspose.Page pro .NET
linktitle: Přidat obdélník do PostScriptu (PS)
second_title: Aspose.Page .NET API
description: Vylepšete vytváření dokumentů v .NET pomocí Aspose.Page. Naučte se přidávat obdélníky do souborů PostScript (PS) krok za krokem.
type: docs
weight: 12
url: /cs/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Úvod

Pokud chcete zlepšit své možnosti vytváření dokumentů v .NET, Aspose.Page poskytuje výkonné řešení pro práci s dokumenty PostScript. V tomto tutoriálu vás provedeme procesem přidávání obdélníků do dokumentu PostScript pomocí Aspose.Page for .NET.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Page for .NET z[tady](https://releases.aspose.com/page/net/).

- Vývojové prostředí: Ujistěte se, že máte na svém počítači nastavené vývojové prostředí .NET.

## Import jmenných prostorů

Než začnete kódovat, nezapomeňte naimportovat potřebné jmenné prostory pro přístup k požadovaným třídám a metodám:

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
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
```

V tomto kroku nahraďte "Your Document Directory" cestou, kam chcete uložit svůj PostScriptový dokument.

## Krok 2: Vytvořte výstupní proud pro dokument PostScript

```csharp
//Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Zde vytvoříme výstupní proud pro PostScriptový dokument a určíme název souboru ("AddRectangle_outPS.ps"). Upravte název a umístění souboru podle svých preferencí.

## Krok 3: Nastavte možnosti uložení a vytvořte dokument PS

```csharp
//Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();

// Vytvořte nový 1stránkový dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

Nastavte možnosti uložení a určete požadovanou velikost stránky (v tomto případě A4). Potom vytvořte nový jednostránkový dokument PostScript.

## Krok 4: Přidejte obdélník a výplň

```csharp
//Vytvořte cestu grafiky z prvního obdélníku
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Nastavte barvu
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Vyplňte obdélník
document.Fill(path);
```

Zde vytvoříme grafickou cestu představující první obdélník, nastavíme barvu nátěru (v tomto případě oranžovou) a vyplníme obdélník.

## Krok 5: Přidejte další obdélník a tah

```csharp
//Vytvořte cestu grafiky z druhého obdélníku
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Nastavit zdvih
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Vytáhněte (obkreslete) obdélník
document.Draw(path);
```

Podobně jako v předchozím kroku vytvoříme grafickou cestu pro druhý obdélník, nastavíme barvu tahu (červená s tloušťkou 3) a obdélník obkreslíme.

## Krok 6: Zavřete stránku a uložte dokument

```csharp
//Zavřít aktuální stránku
document.ClosePage();

//Uložte dokument
document.Save();
```

Nakonec zavřete aktuální stránku a uložte celý dokument.

## Závěr

Gratulujeme! Úspěšně jste přidali obdélníky do dokumentu PostScript pomocí Aspose.Page for .NET. Tento tutoriál se zabýval základními kroky, od nastavení vývojového prostředí až po uložení finálního dokumentu.

## FAQ

### Q1: Mohu přizpůsobit barvy obdélníků?

A1: Ano, můžete přizpůsobit barvy úpravou parametrů v`SolidBrush` a`Pen` třídy.

### Q2: Je Aspose.Page kompatibilní s jinými formáty dokumentů?

A2: Ano, Aspose.Page podporuje různé formáty dokumentů, včetně XPS a PostScript.

### Q3: Jak mohu přidat text do dokumentu?

 A3: Můžete použít`TextFragment` třídy v Aspose.Page přidat text do dokumentu.

### Q4: Kde najdu další příklady a dokumentaci?

 A4: Prozkoumejte dokumentaci[tady](https://reference.aspose.com/page/net/) a navštívit[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.

### Q5: Mohu vyzkoušet Aspose.Page před nákupem?

 A5: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/) a pro rozšířené použití zvažte a[dočasná licence](https://purchase.aspose.com/temporary-license/).
