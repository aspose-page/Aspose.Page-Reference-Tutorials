---
date: 2026-03-21
description: Naučte se, jak vyplnit a přidat text do PS dokumentů pomocí Aspose.Page
  pro .NET. Průvodce krok za krokem s ukázkami kódu.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Jak vyplnit text v dokumentech PostScript (PS) pomocí Aspose.Page
url: /cs/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vyplnit text v dokumentech PostScript (PS) pomocí Aspose.Page

## Úvod

Pokud potřebujete **how to fill text** uvnitř souboru PostScript (PS), Aspose.Page pro .NET to činí jednoduchým. Ať už generujete zprávy, faktury nebo vlastní grafiku, přidávání a stylování textu je základní požadavek. V tomto tutoriálu vás provedeme celým procesem – od nastavení prostředí po uložení finálního PS dokumentu – abyste mohli sebejistě přidávat text do PS souborů ve svých .NET aplikacích.

## Rychlé odpovědi
- **Co znamená „fill text“?** Vykresluje znaky pomocí pevného štětce, maluje glyfy přímo na stránku.  
- **Mohu použít vlastní fonty?** Ano – Aspose.Page podporuje vlastní fonty prostřednictvím funkce `add custom font ps`.  
- **Jak uložit PS dokument?** Zavolejte `document.Save()` po uzavření stránky; tím se soubor zapíše na disk (`save ps document`).  
- **Je podporováno „fill and stroke text“?** Rozhodně; použijte `FillAndStrokeText` pro aplikaci výplně i obrysu.  
- **Jaké verze .NET jsou vyžadovány?** Jakýkoli .NET Framework 4.5+ nebo .NET Core/5/6+ runtime.

## Co je „how to fill text“ v dokumentu PS?

Vyplnění textu znamená malování znaků pevnou barvou (nebo štětcem) bez obrysu. V PostScriptu je to ekvivalent operátoru `fill`. Aspose.Page to abstrahuje do snadno použitelných metod jako `FillText` a `FillAndStrokeText`.

## Proč použít Aspose.Page pro přidání custom font ps?

- **Kompletní podpora fontů** – systémové fonty i externí TrueType/OpenType fonty fungují ihned.  
- **Přesné umístění** – ovládáte souřadnice X/Y, velikost i styl.  
- **Bohaté stylování** – kombinujte výplně, obrysy a pera pro efekty jako „fill and stroke text“.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS se stejným API.

## Požadavky

Než začnete, ujistěte se, že máte:

- **Aspose.Page pro .NET** – stáhněte knihovnu z [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Document Directory** – složka ve vašem počítači, kde budou umístěny vstupní a výstupní PS soubory (v kódu označena jako *Your Document Directory*).  
- **Fonts Folder** – podsložka obsahující všechny vlastní fonty, které plánujete použít.

## Importování jmenných prostorů

Nejprve importujte potřebné jmenné prostory, aby kompilátor věděl, kde najít třídy, které budeme používat:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Postupný průvodce

### Krok 1: Vytvoření výstupního proudu pro PS dokument  

Otevřeme `FileStream`, který bude obsahovat generovaný PS soubor, nastavíme `PsSaveOptions` tak, aby ukazoval na naši složku s vlastními fonty, a vytvoříme instanci `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro tip:** Nechte `using` blok, aby se proud automaticky uzavřel, což také dokončí PS soubor (`save ps document`).

### Krok 2: Vyplnění textu systémovým fontem  

Zde demonstrujeme základní operaci **how to fill text** pomocí vestavěného fontu *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Krok 3: Vyplnění textu vlastním fontem  

Pokud potřebujete specifický vzhled, načtěte vlastní font ze složky s fonty pomocí `ExternalFontCache.FetchDrFont`. Tím splníte požadavek **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Krok 4: Obrys (stroke) textu systémovým fontem  

Obrys vykresluje konturu glyfu. Kombinujte jej s výplní pro efekt „fill and stroke“.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Proč je to důležité:** Volání `FillAndStrokeText` ukazuje, jak **fill and stroke text** provést v jednom kroku, což vám poskytuje bohatší typografickou kontrolu.

### Krok 5: Obrys textu vlastním fontem  

Stejná technika obrysu funguje s jakýmkoli vlastním fontem, který jste načetli.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Krok 6: Zavření stránky a uložení dokumentu  

Dokončení je jednoduché: zavřete aktuální stránku a zavolejte `Save()`, aby se PS soubor zapsal na disk.

```csharp
document.ClosePage();
document.Save();
}
```

> **Výsledek:** V *Your Document Directory* najdete soubor `AddText_outPS.ps`, který obsahuje jak vyplněný, tak obrysný text vykreslený systémovými i vlastními fonty.

## Časté problémy a řešení

| Problém | Řešení |
|---------|--------|
| **Vlastní font nebyl nalezen** | Ověřte, že soubor fontu (.ttf/.otf) existuje ve složce uvedené v `AdditionalFontsFolders`. |
| **Text se zobrazuje na špatné pozici** | Upravte souřadnice X/Y předávané do `FillText`/`OutlineText`. Pamatujte, že PostScript používá body (1/72 palce). |
| **Barvy vypadají odlišně** | Ujistěte se, že používáte `SolidBrush` nebo `Pen` s správnými hodnotami `Color`. |
| **Dokument se neukládá** | Zkontrolujte, že `using` blok skončí bez výjimek a že aplikace má oprávnění zapisovat do cílové složky. |

## Často kladené otázky

**Q: Mohu použít Aspose.Page s jinými .NET knihovnami?**  
A: Ano, Aspose.Page se hladce integruje s dalšími .NET komponentami, což vám umožní kombinovat PDF, obrazové nebo grafické knihovny ve stejném řešení.

**Q: Jsou vlastní fonty pro tento proces nezbytné?**  
A: Zatímco systémové fonty fungují dobře, vlastní fonty vám poskytují plnou tvůrčí svobodu a jsou užitečné, když je vyžadována typografie specifická pro značku.

**Q: Je Aspose.Page vhodný pro zpracování velkého množství dokumentů?**  
A: Rozhodně. Knihovna je optimalizována pro scénáře s vysokou propustností a dokáže efektivně zpracovat tisíce PS souborů.

**Q: Můžu změnit pozici textu v PS dokumentu?**  
A: Samozřejmě – stačí změnit číselné hodnoty X/Y v voláních `FillText` nebo `OutlineText`.

**Q: Kde mohu získat pomoc s dotazy týkajícími se Aspose.Page?**  
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39), kde se můžete spojit s komunitou a získat odbornou pomoc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-03-21  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose