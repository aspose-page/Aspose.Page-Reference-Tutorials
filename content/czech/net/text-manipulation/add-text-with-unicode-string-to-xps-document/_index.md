---
title: Přidejte text s řetězcem Unicode do dokumentu XPS pomocí Aspose.Page
linktitle: Přidejte text s řetězcem Unicode do dokumentu XPS
second_title: Aspose.Page .NET API
description: Prozkoumejte sílu Aspose.Page for .NET pomocí našeho podrobného průvodce přidáváním textu Unicode do dokumentů XPS.
type: docs
weight: 12
url: /cs/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Úvod

V neustále se vyvíjejícím prostředí vývoje .NET vyniká Aspose.Page jako výkonný nástroj pro práci s dokumenty XPS. Mezi jeho mnoha funkcemi je cennou funkcí možnost přidat text s řetězci Unicode do dokumentu XPS. Tento průvodce vás krok za krokem provede celým procesem a zajistí, že tuto schopnost využijete efektivně.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Základní pochopení vývoje .NET.
- Visual Studio nainstalované na vašem počítači.
-  Aspose.Page pro knihovnu .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).

## Import jmenných prostorů

Nejprve se ujistěte, že jste do projektu importovali potřebné jmenné prostory. To poskytne požadované třídy a funkce pro práci s Aspose.Page. Zde jsou základní jmenné prostory:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Nastavte dokument

Nejprve vytvořte nový dokument XPS, do kterého přidáte text Unicode. Postupujte podle fragmentu kódu níže:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```

## Krok 2: Přidejte text Unicode

Nyní do dokumentu XPS přidáme text Unicode. Tento příklad používá písmo Arial, nastaví velikost písma na 20 a umístí text na souřadnice (400f, 200f). Řetězec Unicode je v tomto případě "TEN. rof SPX.esopsA". Podívejte se na fragment kódu níže:

```csharp
// Přidej text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Krok 3: Uložte dokument

Po přidání textu Unicode uložte výsledný dokument XPS. Zde je poslední krok:

```csharp
// Uložte výsledný dokument XPS
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gratulujeme! Úspěšně jste přidali text Unicode do dokumentu XPS pomocí Aspose.Page for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali proces přidávání textu Unicode do dokumentů XPS pomocí Aspose.Page for .NET. Tato funkce otevírá dveře k rozmanité a dynamické tvorbě dokumentů v prostředí .NET.

## FAQ

### Q1: Je Aspose.Page kompatibilní s nejnovějšími frameworky .NET?

A1: Ano, Aspose.Page je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími frameworky .NET.

### Q2: Mohu přizpůsobit styl a velikost písma při přidávání textu?

A2: Rozhodně! Poskytnutý vzorový kód vám umožňuje snadno přizpůsobit styl písma, velikost a další atributy.

### Q3: Kde najdu další dokumentaci pro Aspose.Page?

 A3: Můžete nahlédnout do dokumentace[tady](https://reference.aspose.com/page/net/) pro vyčerpávající informace a příklady.

### Q4: Existují nějaké bezplatné zdroje, jak začít s Aspose.Page?

 A4: Ano, můžete prozkoumat[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.

### Otázka 5: Je před nákupem k dispozici zkušební verze?

 A5: Určitě! Máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/) před nákupem.