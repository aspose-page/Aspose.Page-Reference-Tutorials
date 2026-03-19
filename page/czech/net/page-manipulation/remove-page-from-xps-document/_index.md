---
date: 2026-03-19
description: Naučte se, jak **odstranit stránku XPS** z dokumentů a **smazat stránku
  na indexu** pomocí Aspose.Page pro .NET – kompletní krok‑za‑krokem průvodce s předpoklady,
  ukázkami kódu a častými dotazy.
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: Odstranit stránku z XPS dokumentu pomocí Aspose.Page pro .NET
url: /cs/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odebrat stránku z XPS dokumentu pomocí Aspose.Page pro .NET

## Úvod

Pokud potřebujete **odstranit stránku xps** souborů programově, Aspose.Page pro .NET vám poskytuje čistý a spolehlivý způsob, jak to provést. V tomto tutoriálu projdeme přesně kroky potřebné k smazání konkrétní stránky z XPS dokumentu, vysvětlíme, proč je tato operace důležitá, a ukážeme vám, jak uložit aktualizovaný soubor zpět na disk.

## Rychlé odpovědi
- **Co znamená „remove page xps“?** Jedná se o smazání jedné stránky z XPS (XML Paper Specification) dokumentu.  
- **Která metoda maže stránku?** Použijte `RemovePageAt(index)`, kde index je nulový‑založený.  
- **Mohu smazat stránku na libovolné pozici?** Ano – můžete **smazat stránku na indexu** 0, 1, 2 atd., podle potřeby.  
- **Potřebuji licenci pro Aspose.Page?** Pro testování je vyžadována dočasná licence; pro produkci je nutná plná licence.  
- **Je kód kompatibilní s .NET 6?** Rozhodně – Aspose.Page podporuje .NET Framework, .NET Core i .NET 5/6.

## Co je „remove page xps“?
Odstranění stránky z XPS dokumentu znamená vyjmout jednu ze stran dokumentu při zachování zbytku obsahu, rozvržení a metadat. Tato operace je užitečná, když potřebujete zkrátit PDF, generovat vlastní zprávy nebo splnit omezení velikosti dokumentu.

## Proč použít Aspose.Page pro .NET?
- **Žádné externí závislosti** – čistá .NET knihovna.  
- **Vysoká věrnost** – zachovává vektorovou grafiku a přesnost rozvržení.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS.  
- **Jednoduché API** – jediný volání metody (`RemovePageAt`) provede těžkou práci.

## Požadavky

Než se ponoříte do kódu, ujistěte se, že máte:

- **Aspose.Page pro .NET** – stáhněte si ji z [dokumentace Aspose.Page pro .NET](https://reference.aspose.com/page/net/).  
- **Vývojové prostředí .NET** (Visual Studio, VS Code nebo jakékoli IDE podle vašeho výběru).  
- **Ukázkový XPS dokument** (např. `Sample.xps`) umístěný ve složce, na kterou můžete odkazovat z projektu.

## Import jmenných prostorů

Přidejte požadované jmenné prostory na začátek vašeho C# souboru, aby kompilátor věděl, kde najít třídy XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Nastavte adresář dokumentu

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Tip:** Použijte `Path.Combine` pro tvorbu cest nezávislých na platformě.

## Krok 2: Vytvořte nový XPS dokument

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

Tento řádek načte existující XPS soubor (`Sample.xps`) do objektu `XpsDocument`, připraveného k úpravám.

## Krok 3: Smažte stránku na indexu

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

Metoda `RemovePageAt` **smaže stránku na zadaném indexu**. Pamatujte, že indexování začíná od 0, takže `1` odstraní druhou stránku. Upravit index podle toho, kterou stránku potřebujete smazat.

## Krok 4: Uložte výsledný XPS dokument

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

Po odebrání je dokument uložen jako `Sample_out.xps`. Nyní můžete tento soubor otevřít a ověřit, že nežádoucí stránka zmizela.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Index mimo rozsah** | Pokus o smazání stránky, která neexistuje. | Ověřte počet stránek pomocí `doc.Pages.Count` před voláním `RemovePageAt`. |
| **Soubor uzamčen** | XPS soubor je otevřen v jiném programu. | Zavřete všechny prohlížeče nebo zajistěte, aby soubor nebyl používán před spuštěním kódu. |
| **Licence není použita** | Používání knihovny bez platné licence v produkci. | Aplikujte dočasnou nebo trvalou licenci pomocí `License license = new License(); license.SetLicense("Aspose.Page.lic");` |

## Často kladené otázky

**Q1: Mohu odstranit více stránek najednou pomocí Aspose.Page pro .NET?**  
A1: Ano, stačí volat `RemovePageAt` opakovaně nebo projít seznam indexů (pamatovat si, že odstraňujete od nejvyššího k nejnižšímu indexu, aby zůstaly ostatní indexy platné).

**Q2: Je Aspose.Page kompatibilní s nejnovější verzí .NET frameworku?**  
A2: Aspose.Page je pravidelně aktualizována, aby podporovala nejnovější verze .NET, včetně .NET 6 a .NET 7.

**Q3: Mohu používat Aspose.Page v komerčních aplikacích?**  
A3: Rozhodně. Podrobnosti o licencování najdete na stránce [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q4: Kde najdu další podporu a diskuze o Aspose.Page?**  
A4: Připojte se ke komunitě na [fóru Aspose.Page](https://forum.aspose.com/c/page/39), kde najdete tipy, příklady a pomoc při řešení problémů.

**Q5: Potřebuji dočasnou licenci pro testování Aspose.Page?**  
A5: Ano, můžete získat [dočasnou licenci](https://purchase.aspose.com/temporary-license/) pro vyhodnocení knihovny před zakoupením.

**Q6: Jak zachovat metadata dokumentu po odebrání stránky?**  
A6: Metoda `RemovePageAt` automaticky zachovává původní metadata. Pokud je potřebujete upravit, použijte kolekci `doc.DocumentProperties`.

## Závěr

Nyní jste se naučili, jak **odstranit stránku xps** a **smazat stránku na indexu** pomocí Aspose.Page pro .NET. Tento stručný přístup vám umožní integrovat logiku odstraňování stránek přímo do vašich .NET aplikací a mít plnou kontrolu nad obsahem XPS dokumentů.

---

**Poslední aktualizace:** 2026-03-19  
**Testováno s:** Aspose.Page 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}