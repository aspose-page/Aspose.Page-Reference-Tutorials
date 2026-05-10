---
date: 2026-03-21
description: Naučte se, jak přidat Unicode text do XPS dokumentu pomocí Aspose.Page
  pro .NET. Tento průvodce vám ukáže, jak vytvořit XPS dokument v C# a přidat text
  s Unicode řetězci pomocí Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Jak přidat Unicode text do XPS dokumentu pomocí Aspose.Page
url: /cs/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat Unicode text do XPS dokumentu pomocí Aspose.Page

## Úvod

Pokud potřebujete **how to add unicode** znaky do XPS souboru, jste na správném místě. V tomto tutoriálu vás provedeme přesnými kroky potřebnými k **create XPS document C#**‑style pomocí Aspose.Page pro .NET a ukážeme schopnost **aspose page add text** s Unicode řetězcem. Na konci budete mít plně funkční XPS dokument, který správně zobrazuje text z prava do leva (RTL) v Unicode.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Přidání Unicode textu do XPS dokumentu pomocí Aspose.Page pro .NET.  
- **Jaký jazyk je použit?** C# (kompatibilní s .NET Framework a .NET Core).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu změnit písmo nebo velikost?** Ano – příklad používá Arial 20 pt, ale funguje jakékoli nainstalované písmo.  
- **Je podpora RTL zahrnuta?** Nastavení `BidiLevel = 1` umožňuje renderování zprava doleva pro Unicode řetězce.

## Co znamená “how to add unicode” v XPS?

Přidání Unicode textu znamená vložení znaků z libovolného jazyka – arabštiny, hebrejštiny, čínštiny atd. – do XPS dokumentu. Třída `XpsGlyphs` v Aspose.Page zajišťuje nízkoúrovňové umístění glyfů, zatímco vlastnost `BidiLevel` řídí směr textu pro RTL skripty.

## Proč použít Aspose.Page k přidání textu?

- **Plná integrace s .NET** – funguje s .NET Framework, .NET Core, .NET 5/6+.  
- **Žádné externí závislosti** – čistý spravovaný kód, žádný COM interop.  
- **Bohatá podpora typografie** – písma, styly, barvy a obousměrný text.  
- **Vysoký výkon** – rychle vytváří a ukládá XPS soubory, ideální pro generování na serveru.

## Požadavky

- Základní znalosti C# a vývoje v .NET.  
- Visual Studio (libovolná recentní verze).  
- Knihovna Aspose.Page pro .NET – stáhněte ji z [here](https://releases.aspose.com/page/net/).

## Importujte jmenné prostory

Nejprve importujte jmenné prostory, které vám umožní přístup k modelu XPS a nástrojům pro kreslení.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Nastavte dokument – vytvořte XPS dokument C#

Vytvořte nový XPS dokument, který bude hostit Unicode text.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Krok 2: Přidejte Unicode text – aspose page add text

Nyní přidáme skutečný Unicode řetězec. V tomto příkladu používáme písmo Arial, velikost 20, a umístíme text na (400 f, 200 f). `BidiLevel` nastavený na 1 říká rendereru, aby řetězec zpracoval jako zprava doleva.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Krok 3: Uložte dokument

Nakonec uložte XPS soubor na disk.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gratulujeme! Úspěšně jste přidali **how to add unicode** text do XPS dokumentu pomocí Aspose.Page pro .NET.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Text se zobrazuje poškozeně | Písmo nepodporuje Unicode rozsah | Použijte písmo, které obsahuje požadované glyfy (např. Arial Unicode MS). |
| RTL text je stále zleva doprava | `BidiLevel` není nastaven nebo je nastaven na 0 | Ujistěte se, že `glyphs.BidiLevel = 1;` pro RTL skripty. |
| Soubor nebyl uložen | Neplatná cesta `dataDir` | Ověřte, že adresář existuje a aplikace má oprávnění k zápisu. |

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní s nejnovějšími .NET frameworky?**  
A: Ano, Aspose.Page je pravidelně aktualizován tak, aby podporoval .NET Framework, .NET Core a .NET 5/6+.

**Q: Mohu přizpůsobit styl a velikost písma při přidávání textu?**  
A: Rozhodně! Metoda `AddGlyphs` vám umožní zadat libovolnou rodinu písma, velikost a `FontStyle`, který potřebujete.

**Q: Kde najdu další dokumentaci k Aspose.Page?**  
A: Dokumentaci můžete najít [here](https://reference.aspose.com/page/net/) pro podrobné informace o API.

**Q: Existují nějaké bezplatné zdroje pro zahájení práce s Aspose.Page?**  
A: Ano, prozkoumejte komunitní fórum na [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro tipy, příklady a podporu od ostatních.

**Q: Je k dispozici zkušební verze před zakoupením?**  
A: Samozřejmě! Stáhněte si bezplatnou zkušební verzi [here](https://releases.aspose.com/) pro vyzkoušení knihovny.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}