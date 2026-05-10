---
date: 2026-03-21
description: Naučte se, jak vytvořit PostScript dokument v C# s Unicode textem pomocí
  Aspose.Page pro .NET – rychlý způsob, jak vylepšit manipulaci s dokumenty.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Vytvořit dokument PostScript v C# s Unicode textem – Aspose.Page
url: /cs/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání textu s Unicode řetězcem do PostScriptu (PS) pomocí Aspose.Page

## Úvod

Pokud potřebujete **vytvořit PostScript dokument v C#** a vložit Unicode znaky, Aspose.Page pro .NET proces značně usnadňuje. V tomto tutoriálu projdeme kompletní, praktický příklad, který ukazuje, jak přidat japonský text (nebo libovolný Unicode řetězec) do souboru PS, zvolit vlastní písmo a výsledek uložit. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do libovolného C# projektu.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání Unicode textu do PostScript souboru pomocí Aspose.Page v C#.
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (nejnovější verze).
- **Potřebuji speciální písmo?** Jakékoli TrueType/OpenType písmo, které podporuje požadovaný Unicode rozsah, např. *Arial Unicode MS*.
- **Kolik řádků kódu?** Přibližně 30 řádků, rozdělených do přehledných kroků.
- **Je potřeba licence?** Pro hodnocení stačí dočasná licence; pro produkční nasazení je vyžadována plná licence.

## Co znamená „create postscript document c#“?
Vytvoření PostScript dokumentu v C# znamená programově generovat soubor .ps, který splňuje specifikace jazyka PostScript. Aspose.Page abstrahuje nízkoúrovňové detaily a umožňuje soustředit se na obsah, jako je text, grafika a písma.

## Proč použít Aspose.Page pro Unicode text?
- **Plná podpora Unicode** – vykreslí znaky z libovolného jazyka bez nutnosti ručního kódování.
- **Zařízení‑nezávislé** – stejný kód funguje pro výstupy PS, EPS i PDF.
- **Žádné externí závislosti** – knihovna interně zajišťuje načítání písem a mapování glifů.

## Předpoklady

- Základní znalost C# a vývoje v .NET.
- Knihovna Aspose.Page pro .NET nainstalovaná. Můžete si ji stáhnout z [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Složka obsahující písma, která hodláte použít (např. *Arial Unicode MS*).

## Import Namespaces

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavení adresáře dokumentu a složky s písmy

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Krok 2: Vytvoření výstupního proudu pro PostScript dokument

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Krok 3: Přidání Unicode textu s vlastním písmem

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Krok 4: Uzavření aktuální stránky

```csharp
document.ClosePage();
```

## Krok 5: Dokončení a uložení dokumentu

```csharp
document.Save();
```

## Časté problémy a řešení

- **Písmo nebylo nalezeno** – Ujistěte se, že cesta `AdditionalFontsFolders` ukazuje na složku obsahující soubory .ttf/.otf a že název písma je zadán přesně.
- **Zobrazení nesprávných znaků** – Ověřte, že zdrojový řetězec je v souboru C# kódován jako UTF‑8 (případně použijte `#pragma warning disable 1591`).
- **Soubor nebyl vytvořen** – Zkontrolujte oprávnění zápisu do `dataDir` a že proud je řádně uvolněn (blok `using` se o to postará).

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro .NET i s jinými programovacími jazyky?**  
A: Aspose.Page je primárně určen pro .NET, ale existují ekvivalenty pro Javu.

**Q: Jak získám dočasnou licenci pro Aspose.Page pro .NET?**  
A: Navštivte [Temporary License](https://purchase.aspose.com/temporary-license/) pro získání dočasné licence.

**Q: Existuje komunitní fórum pro diskuze o Aspose.Page?**  
A: Ano, navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro podporu komunity.

**Q: S jakými formáty může Aspose.Page pro .NET pracovat?**  
A: Aspose.Page podporuje různé formáty, včetně XPS, PS, EPS, PDF a dalších.

**Q: Mohu přizpůsobit vzhled přidaného textu?**  
A: Ano, můžete upravit písmo, velikost, barvu a další vlastnosti textu v Aspose.Page.

## Závěr

V tomto tutoriálu jsme ukázali, jak **vytvořit PostScript dokument v C#** a vložit Unicode text pomocí Aspose.Page. Dodržením výše uvedených kroků můžete rychle integrovat vícejazyčné vykreslování textu do libovolné .NET aplikace a získat tak plnou kontrolu nad generováním a rozvržením dokumentu.

---

**Poslední aktualizace:** 2026-03-21  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}