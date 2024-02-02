---
title: Přidejte text s řetězcem Unicode do PostScriptu (PS) pomocí Aspose.Page
linktitle: Přidání textu s řetězcem Unicode do PostScriptu (PS)
second_title: Aspose.Page .NET API
description: Naučte se, jak přidat text Unicode do PostScriptových souborů pomocí Aspose.Page for .NET. Vylepšete snadnou manipulaci s dokumenty.
type: docs
weight: 11
url: /cs/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---
## Úvod

V oblasti manipulace s dokumenty vyniká Aspose.Page for .NET jako robustní knihovna, která umožňuje vývojářům vytvářet, upravovat a převádět různé formáty dokumentů. Jednou z jeho výkonných funkcí je možnost přidávat text pomocí řetězců Unicode do souborů PostScript (PS). V tomto tutoriálu prozkoumáme podrobného průvodce splněním tohoto úkolu, který poskytuje bezproblémové prostředí pro vývojáře pracující s Aspose.Page.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:

- Pracovní znalost programovacího jazyka C#.
-  Nainstalovaná knihovna Aspose.Page for .NET. Můžete si jej stáhnout z[Aspose.Page pro dokumentaci .NET](https://reference.aspose.com/page/net/).
- Vývojové prostředí nastavené s nezbytnými konfiguracemi.

## Import jmenných prostorů

Do svého kódu C# importujte požadované jmenné prostory pro používání funkcí Aspose.Page for .NET:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavte adresář dokumentů a složku písem

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Krok 2: Vytvořte výstupní proud pro dokument PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Vytvořte možnosti uložení s velikostí A4
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (zde lze nastavit další možnosti)
    
    // Vytvořte nový 1stránkový dokument PS
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Další kroky budou vysvětleny níže)
    
    // Uložte dokument
    document.Save();
}
```

## Krok 3: Přidejte text Unicode s vlastním písmem

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Použití vlastního písma pro vyplnění textu
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Krok 4: Zavřete aktuální stránku

```csharp
document.ClosePage();
```

## Krok 5: Dokončete a uložte dokument

```csharp
document.Save();
```

## Závěr

V tomto tutoriálu jsme prošli procesem přidávání textu Unicode do dokumentu PostScript pomocí Aspose.Page for .NET. Využitím jeho výkonných schopností mohou vývojáři vylepšit své pracovní postupy při manipulaci s dokumenty a zajistit flexibilitu a přesnost.

## FAQ

### Q1: Mohu používat Aspose.Page pro .NET s jinými programovacími jazyky?

A1: Aspose.Page je primárně navržen pro .NET, ale jsou k dispozici i další verze pro Javu.

### Q2: Jak získám dočasnou licenci pro Aspose.Page for .NET?

 A2: Návštěva[Dočasná licence](https://purchase.aspose.com/temporary-license/) pro získání dočasné licence.

### Q3: Existuje komunitní fórum pro diskuse Aspose.Page?

 A3: Ano, navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.

### Q4: S jakými formáty může Aspose.Page for .NET pracovat?

A4: Aspose.Page podporuje různé formáty, včetně XPS, PS, EPS, PDF a dalších.

### Q5: Mohu přizpůsobit vzhled přidaného textu?

A5: Ano, můžete přizpůsobit písmo, velikost, barvu a další vlastnosti textu v Aspose.Page.