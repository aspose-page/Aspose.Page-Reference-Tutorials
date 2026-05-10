---
date: 2026-03-03
description: Naučte se nastavit vlastní velikost stránky a přidat druhou PS stránku
  do dokumentu PostScript pomocí Aspose.Page pro .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Nastavte vlastní velikost stránky v PS dokumentu pomocí Aspose.Page
url: /cs/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání stránky do dokumentu PostScript (PS) pomocí Aspose.Page

## Úvod

V .NET vývoji vám možnost **set custom page size** a **add second PS page** do dokumentu PostScript (PS) poskytuje detailní kontrolu nad rozvržením generovaných výtisků, reportů nebo grafiky. Aspose.Page pro .NET tuto úlohu usnadňuje pomocí čistého, objektově orientovaného API. V tomto tutoriálu se naučíte, jak vytvořit více‑stránkový PS soubor, definovat vlastní velikost pro každou stránku a výsledek uložit – vše pomocí několika řádků kódu v C#.

## Rychlé odpovědi
- **Mohu nastavit vlastní velikost stránky?** Ano – stačí při otevírání stránky předat šířku a výšku.  
- **Jak přidám druhou PS stránku?** Zavolejte `document.OpenPage(width, height)` podruhé.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Potřebuji licenci?** Dočasná licence funguje pro testování; plná licence je vyžadována pro produkci.  
- **Kde mohu stáhnout Aspose.Page?** Z oficiální stránky ke stažení uvedené níže.

## Požadavky

Před tím, než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:

- Znalost vývoje v .NET.  
- Nainstalovaný Visual Studio na vašem počítači.  
- Knihovna Aspose.Page pro .NET, kterou můžete stáhnout [zde](https://releases.aspose.com/page/net/).  
- Váš preferovaný adresář pro dokumenty pro testování.

## Importování jmenných prostor

Ujistěte se, že ve svém projektu zahrnete potřebné jmenné prostory pro přístup k funkcionalitám poskytovaným knihovnou Aspose.Page. V daném příkladu jsou jmenné prostory implicitně zahrnuty, ale je důležité je zkontrolovat a případně upravit podle struktury vašeho projektu.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavení projektu

Vytvořte nový .NET projekt ve Visual Studiu a nastavte potřebné konfigurace. Ujistěte se, že ve svém projektu odkazujete na knihovnu Aspose.Page.

## Nastavení vlastní velikosti stránky a přidání druhé PS stránky

Tato sekce přesně ukazuje, jak **set custom page size** pro každou stránku a jak **add second ps page** do stejného dokumentu.

### Krok 2: Inicializace dokumentu

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Krok 3: Přidání první stránky (výchozí velikost)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Krok 4: Přidání druhé stránky s odlišnou (vlastní) velikostí

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Krok 5: Uložení dokumentu

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Postupujte podle těchto kroků pečlivě a úspěšně **set custom page size** a přidáte **second PS page** do dokumentu PostScript pomocí Aspose.Page pro .NET.

## Proč je to důležité

- **Precision Layout** – Vlastní rozměry stránky vám umožní odpovídat specifikacím tiskárny nebo vytvořit jedinečné formáty brožur.  
- **Multiple Pages** – Přidání druhé stránky (nebo více) umožňuje vícestránkové reporty bez externích nástrojů pro sloučení.  
- **Cross‑Platform** – Vygenerovaný PS soubor lze vykreslit na jakémkoli zařízení kompatibilním s PostScriptem nebo později převést do PDF.

## Časté chyby a řešení problémů

- **Incorrect Path** – Ujistěte se, že `dataDir` končí oddělovačem cesty nebo použijte `Path.Combine`.  
- **License Issues** – Bez platné licence může knihovna přidat vodoznak nebo omezit počet stránek.  
- **Unit Confusion** – Šířka a výška jsou měřeny v bodech (1 bod = 1/72 palce). Přizpůsobte podle toho.

## Často kladené otázky

**Q1: Je Aspose.Page kompatibilní s různými formáty dokumentů?**  
A1: Aspose.Page se primárně zaměřuje na manipulaci s dokumenty PostScript. Pro jiné formáty můžete prozkoumat knihovny Aspose určené pro konkrétní potřeby.

**Q2: Mohu v Aspose.Page přizpůsobit velikost stránky?**  
A2: Rozhodně! Jak je ukázáno v tutoriálu, můžete pro každou stránku specifikovat různé velikosti podle vašich požadavků.

**Q3: Kde mohu najít více příkladů a dokumentaci?**  
A3: Navštivte [dokumentaci](https://reference.aspose.com/page/net/) pro komplexní informace a řadu příkladů.

**Q4: Jak získám dočasnou licenci pro Aspose.Page?**  
A4: Přejděte na [tento odkaz](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci pro testovací účely.

**Q5: Kde mohu získat podporu komunity nebo klást otázky?**  
A5: Připojte se k [fóru komunity Aspose.Page](https://forum.aspose.com/c/page/39), kde můžete komunikovat s ostatními vývojáři, sdílet zkušenosti a požádat o pomoc.

---

**Poslední aktualizace:** 2026-03-03  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}