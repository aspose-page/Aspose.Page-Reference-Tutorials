---
date: 2026-01-07
description: Naučte se, jak vytvořit XPS dokument, přidat klony glyfů, použít štětec
  s jednolitou barvou a uložit XPS soubor pomocí Aspose.Page pro .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Vytvořte XPS dokument – Přidejte klon glyfy a změňte barvu pomocí Aspose.Page
  pro .NET
url: /cs/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS dokumentu – Přidání klonu glyfu a změna barvy pomocí Aspose.Page pro .NET

## Úvod

Vítejte v tomto krok‑za‑krokem průvodci, který vám ukazuje **jak vytvořit XPS dokument** soubory, klonovat glyfy a měnit jejich barvy pomocí Aspose.Page pro .NET. Ať už vytváříte dynamické zprávy, faktury nebo vlastní grafiku, zvládnutí těchto technik vám umožní vytvářet vizuálně bohatý XPS výstup, aniž byste opustili ekosystém .NET.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Vytvořit XPS dokument, přidat klony glyfů a změnit jejich barvy.  
- **Která knihovna se používá?** Aspose.Page pro .NET.  
- **Potřebuji licenci?** Dočasná licence je k dispozici pro hodnocení; pro produkci je vyžadována plná licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak uložím výsledek?** Použijte metodu `Save` pro zápis XPS souboru na disk.

## Předpoklady

Předtím, než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:

- Základní znalost programovacího jazyka C#.  
- Nainstalovaný Visual Studio nebo jiné preferované vývojové prostředí pro C#.  
- Knihovna Aspose.Page pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).  
- Znalost formátu XPS dokumentu.

## Import jmenných prostorů

Pro začátek zahrňte potřebné jmenné prostory do svého C# projektu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Jak vytvořit XPS dokument a přidat klony glyfů

### Krok 1: Nastavte adresář pro dokumenty

Začněte nastavením adresáře, kde budou vaše dokumenty uloženy:

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte první XPS dokument

Nyní vytvořme první XPS dokument:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Krok 3: Přidejte glyfy do prvního dokumentu

Přidejte glyfy do prvního dokumentu pomocí zadaných parametrů:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Krok 4: Vyplňte glyfy pevnou barvou štětce

Vyplňte glyfy v prvním dokumentu **pevnou barvou štětce**, například zelenou:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Krok 5: Vytvořte druhý XPS dokument

Nyní vytvořte druhý XPS dokument:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Krok 6: Jak přidat klon glyfu do jiného dokumentu

Klonujte glyfy z prvního dokumentu a přidejte je do druhého dokumentu:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Krok 7: Jak změnit barvu klonovaného glyfu

Změňte barvu klonovaných glyfů ve druhém dokumentu, například na červenou. Toto demonstruje **jak změnit barvu** glyfu po klonování:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Krok 8: Uložte XPS soubor – první dokument

Uložte první XPS dokument do složky, kterou jste definovali dříve:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Krok 9: Uložte XPS soubor – druhý dokument

Uložte druhý XPS dokument:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Gratulujeme! Úspěšně jste **vytvořili XPS dokument** soubory, přidali klony glyfů a změnili jejich barvy pomocí Aspose.Page pro .NET.

## Proč používat klonování glyfů a změny barev?

- **Znovupoužitelnost:** Klonujte existující glyfy pro opětovné použití složitých vektorových tvarů bez jejich redefinování.  
- **Výkon:** Snižuje dobu zpracování ve srovnání s opětovným vytvářením glyfů od nuly.  
- **Flexibilita designu:** Použijte různé instance `SolidColorBrush` na stejný glyf pro dosažení různých vizuálních motivů.  
- **Úpravy napříč dokumenty:** Klonujte glyfy mezi více XPS soubory, což umožňuje konzistentní značku napříč zprávami.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Klon vrací null** | Ujistěte se, že zdrojový glyf (`glyphs`) je přidán do prvního dokumentu před klonováním. |
| **Barva se nezmění** | Přetypujte `glyphs.Fill` na `XpsSolidColorBrush` před nastavením vlastnosti `Color` (jak je ukázáno v kroku 7). |
| **Soubor nebyl uložen** | Ověřte, že `dataDir` ukazuje na platnou, zapisovatelnou složku a že máte příslušná oprávnění k souborovému systému. |
| **Neočekávaná velikost glyfu** | Upravte parametr velikosti písma (druhý argument v `AddGlyphs`) pro vhodné škálování glyfu. |

## Často kladené otázky

**Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?**  
A1: Aspose.Page pro .NET je specificky navržen pro práci s XPS dokumenty. Pokud potřebujete manipulovat s jinými formáty, můžete prozkoumat další knihovny Aspose určené pro tyto formáty.

**Q2: Je k dispozici dočasná licence pro Aspose.Page pro .NET?**  
A2: Ano, můžete získat dočasnou licenci pro testovací účely. Navštivte [zde](https://purchase.aspose.com/temporary-license/) pro více informací.

**Q3: Jak mohu získat podporu nebo pomoc při jakýchkoli problémech?**  
A3: Neváhejte navštívit [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde se můžete spojit s komunitou a požádat o pomoc.

**Q4: Existují nějaká omezení u verze zdarma (trial)?**  
A4: Verze zdarma (trial) má některá omezení a doporučuje se před použitím prostudovat dokumentaci pro podrobnosti.

**Q5: Kde najdu komplexní dokumentaci pro Aspose.Page pro .NET?**  
A5: Dokumentaci můžete najít [zde](https://reference.aspose.com/page/net/) s podrobnými informacemi a příklady.

**Q6: Jak změním barvu obrysu glyfu místo výplně?**  
A6: Použijte `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` pro nastavení štětce obrysu.

**Q7: Mohu přidat více klonů glyfů do stejného dokumentu?**  
A7: Ano, opakovaně volejte `doc2.Add(glyphs.Clone());`, přičemž podle potřeby upravujte pozice.

**Poslední aktualizace:** 2026-01-07  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}