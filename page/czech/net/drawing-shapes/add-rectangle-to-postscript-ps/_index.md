---
date: 2026-01-18
description: Naučte se, jak vytvořit PostScript dokument v .NET a přidávat obdélníky
  pomocí Aspose.Page pro .NET. Podrobný návod krok za krokem s ukázkami kódu.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Vytvořte PostScript dokument v .NET – Přidejte obdélník pomocí Aspose.Page
url: /cs/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání obdélníku do PostScriptu (PS) pomocí Aspose.Page pro .NET

## Úvod

Pokud hledáte **create postscript document .net**, Aspose.Page poskytuje výkonné řešení pro práci se soubory PostScript. V tomto tutoriálu vás provedeme přidáním obdélníků do dokumentu PostScript pomocí Aspose.Page pro .NET, což vám poskytne pevný základ pro tvorbu bohatší grafiky.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.Page for .NET.
- **Mohu vytvořit dokument PostScript od nuly?** Ano – API vám umožní programově vytvářet PS soubory.
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci.
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní tvary.

## Co je vytváření dokumentu PostScript v .NET?
Vytváření dokumentu PostScript v .NET znamená programově generovat soubor .ps, který popisuje obsah stránky — text, grafiku nebo tvary — pomocí API Aspose.Page. Tento přístup je ideální pro generování grafiky na serveru, automatizované vytváření reportů nebo jakýkoli scénář, kde potřebujete přesnou kontrolu nad výstupním formátem.

## Proč používat Aspose.Page pro .NET?
- **Plná kontrola nad grafikou** — kreslete tvary, nastavujte barvy a aplikujte tahy bez nutnosti pracovat s nízkoúrovňovou PS syntaxí.
- **Cross‑platform** — funguje na Windows, Linux a macOS runtimech.
- **Žádné externí závislosti** — knihovna interně zajišťuje veškerou generaci PS.
- **Bohatá dokumentace a příklady** — rychle se rozjedete.

## Požadavky

- **Aspose.Page for .NET Library** — stáhněte a nainstalujte z [here](https://releases.aspose.com/page/net/).
- **Vývojové prostředí** — Visual Studio, VS Code nebo jakékoli IDE kompatibilní s .NET.

## Importování jmenných prostorů

Před zahájením kódování importujte jmenné prostory, které poskytují požadované třídy:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní rozdělíme příklad do jasných, číslovaných kroků.

## Krok 1: Nastavte adresář dokumentu

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` složkou, kam chcete uložit výsledný PS soubor.

## Krok 2: Vytvořte výstupní stream pro dokument PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Tento stream ukazuje na **AddRectangle_outPS.ps**. Klidně soubor přejmenujte nebo změňte umístění podle potřeby.

## Krok 3: Nastavte možnosti uložení a vytvořte PS dokument

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Zde říkáme Aspose.Page, aby použil velikost stránky A4 a vytvořil jednosloučkový dokument.

## Krok 4: Přidejte vyplněný obdélník

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definujeme obdélník v (250, 100) s šířkou 150 a výškou 100, nastavíme oranžový štětec a vyplníme tvar.

## Krok 5: Přidejte obdélník s obrysem

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Druhý obdélník je vytvořen níže na stránce, tentokrát s červeným tahovým štětcem o tloušťce 3 bodů.

## Krok 6: Zavřete stránku a uložte dokument

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Zavřením stránky dokončíte kresbu a `Save()` zapíše PS soubor na disk.

## Časté problémy a tipy

- **Nesprávná cesta k souboru** — Ujistěte se, že `dataDir` končí oddělovačem cesty (`\\` nebo `/`) nebo použijte `Path.Combine`.
- **Chybějící licence** — V produkčním prostředí aplikujte svou Aspose licenci před vytvořením dokumentu, aby se předešlo vodoznakům z hodnocení.
- **Viditelnost barvy** — Pokud se obdélník zobrazuje prázdně, ověřte, že barvy štětce nebo pera kontrastují s pozadím stránky.

## Často kladené otázky

**Q:** Mohu přizpůsobit barvy obdélníků?  
**A:** Rozhodně. Změňte hodnoty `Color.Orange` nebo `Color.Red` v konstruktorech `SolidBrush` a `Pen` na libovolnou `System.Drawing.Color`, kterou preferujete.

**Q:** Je Aspose.Page kompatibilní s jinými formáty dokumentů?  
**A:** Ano. Kromě PostScriptu Aspose.Page také podporuje generování XPS a EPS.

**Q:** Jak mohu do stejného dokumentu přidat text?  
**A:** Použijte třídu `TextFragment` k umístění textu na požadované souřadnice a poté zavolejte `document.Draw(textFragment)`.

**Q:** Kde najdu další příklady a kompletní referenci API?  
**A:** Prozkoumejte dokumentaci [here](https://reference.aspose.com/page/net/) a připojte se ke komunitě na [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Můžu si Aspose.Page vyzkoušet před zakoupením?  
**A:** Ano, stáhněte si bezplatnou zkušební verzi [here](https://releases.aspose.com/). Pro rozšířené hodnocení zvažte [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-01-18  
**Testováno s:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}