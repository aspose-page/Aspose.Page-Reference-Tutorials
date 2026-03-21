---
date: 2026-03-21
description: Naučte se, jak vytvořit XPS dokument v .NET a přidat text pomocí Aspose.Page
  pro .NET. Krok za krokem průvodce pro vývojáře .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Vytvořte XPS dokument v .NET a přidejte text pomocí Aspose.Page
url: /cs/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS dokumentu .NET a přidání textu pomocí Aspose.Page

V moderním vývoji .NET je schopnost **create XPS document .NET** souborů programově cennou dovedností, zejména když potřebujete generovat tisknutelné zprávy, faktury nebo vlastní grafiku. Tento tutoriál vás provede používáním Aspose.Page k **aspose.page add text** do XPS dokumentu, což vám poskytne plnou kontrolu nad rozvržením a stylem – vše z vaší .NET aplikace.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání textu do nově vytvořeného XPS dokumentu pomocí Aspose.Page pro .NET.  
- **Jak dlouho to trvá?** Přibližně 5‑10 minut pro základní implementaci.  
- **Jaké jsou předpoklady?** Vývojové prostředí .NET a knihovna Aspose.Page.  
- **Je licence vyžadována?** Ano, pro produkční použití je potřeba platná licence Aspose.Page.  
- **Lze to spustit na .NET Core / .NET 6+?** Rozhodně – Aspose.Page podporuje všechny aktuální verze .NET.

## Co je create xps document .net?

Vytvoření XPS dokumentu v .NET znamená generování souboru s pevně daným rozvržením, který zachovává přesný vzhled vašeho obsahu napříč zařízeními a tiskárnami. XPS (XML Paper Specification) je otevřený standard Microsoftu pro popis stránky, podobný PDF, ale zcela založený na XML.

## Proč použít Aspose.Page k přidání textu?

Aspose.Page nabízí vysoce úrovňové, objektově orientované API, které abstrahuje nízkoúrovňové XPS značkování. Můžete přidávat text, grafiku a tvary, aniž byste se museli zabývat surovým XML, což urychluje vývoj a snižuje chybovost.

## Prerequisites

- Aspose.Page pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page. Můžete si ji stáhnout z [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Vývojové prostředí: Nastavte své .NET vývojové prostředí. Pokud jste tak ještě neučinili, postupujte podle instalačních pokynů uvedených v [documentation](https://reference.aspose.com/page/net/).
- Adresář dokumentů: Vytvořte adresář, kde budete ukládat své dokumenty. Nahraďte „Your Document Directory“ v poskytnutém úryvku kódu skutečnou cestou.

Nyní, když jsme pokryli základy, pojďme se ponořit do kódu.

## Importování jmenných prostorů

Nejprve importujte potřebné jmenné prostory pro zahájení projektu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Vytvoření XPS dokumentu .NET

Vytvořte nový XPS dokument, který bude sloužit jako plátno pro náš text.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Krok 2: Vytvoření štětce pro text

Definujte jednobarevný štětec, který určuje barvu textu. Zde používáme černou.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Krok 3: Přidání glyphů (aspose.page add text)

Glyphy jsou nízkoúrovňová reprezentace znaků v XPS dokumentu. Tento volání přidá text „Hello World!“ na zadané souřadnice.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Krok 4: Uložení výsledného XPS dokumentu

Uložte dokument na disk, abyste jej mohli později zobrazit nebo vytisknout.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Po provedení těchto kroků jste úspěšně **create XPS document .NET** a přidali vlastní text pomocí Aspose.Page.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Soubor nenalezen** při ukládání | `dataDir` ukazuje na neexistující složku | Zajistěte, aby adresář existoval, nebo před uložením použijte `Directory.CreateDirectory(dataDir)`. |
| **Text není viditelný** | Barva štětce se shoduje s pozadím | Změňte `Color.Black` na jinou kontrastní barvu. |
| **Není podporováno písmo** | Písmo není nainstalováno na počítači | Použijte písmo, které je jistě dostupné, nebo vložte písmo pomocí funkcí pro vkládání písem v Aspose.Page. |

## Často kladené otázky

### Q1: Mohu přizpůsobit písmo a velikost přidaného textu?

A1: Ano, máte plnou kontrolu nad písmem a velikostí. Podle potřeby upravte parametry v metodě `AddGlyphs`.

### Q2: Je Aspose.Page kompatibilní s .NET Core?

A2: Rozhodně! Aspose.Page podporuje .NET Core, což zajišťuje kompatibilitu s nejnovějšími .NET technologiemi.

### Q3: Existují licenční požadavky pro používání Aspose.Page?

A3: Ano, potřebujete platnou licenci. Prozkoumejte možnosti licencování [here](https://purchase.aspose.com/buy).

### Q4: Jak mohu získat podporu nebo pomoc?

A4: Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39), kde se můžete spojit s komunitou a získat pomoc.

### Q5: Je k dispozici bezplatná zkušební verze?

A5: Samozřejmě! Bezplatnou zkušební verzi získáte [here](https://releases.aspose.com/).

**Additional Q&A**

**Q: Mohu přidat více textových bloků na stejnou stránku?**  
A: Ano, stačí volat `doc.AddGlyphs` vícekrát s různými souřadnicemi.

**Q: Umožňuje Aspose.Page otáčení textu?**  
A: Můžete použít transformační matici na objekt `XpsGlyphs` pro otáčení nebo sklonování textu.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Poslední aktualizace:** 2026-03-21  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

---