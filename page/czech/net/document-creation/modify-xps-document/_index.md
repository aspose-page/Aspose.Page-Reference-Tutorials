---
date: 2026-01-12
description: Naučte se, jak upravovat XPS dokument pomocí Aspose.Page pro .NET, a
  zjistěte, jak přidávat text do XPS souborů pomocí jednoduchých ukázek kódu.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Upravit XPS dokument pomocí Aspose.Page pro .NET
url: /cs/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Upravit XPS dokument pomocí Aspose.Page pro .NET

## Úvod

Vítejte v našem podrobném průvodci, jak **modifikovat soubory xps dokumentu** pomocí Aspose.Page pro .NET. Ať už potřebujete vložit podpis, přidat vodoznak nebo jednoduše umístit vlastní text na stránku, tento tutoriál vám ukáže přesně **jak přidat text** do XPS dokumentu během několika minut. Projdeme každý řádek kódu, vysvětlíme, proč je každý krok důležitý, a poskytneme tipy, jak se vyhnout běžným úskalím.

### Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání textu podpisu ("Confirmed") na vybrané stránky XPS souboru.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (nejnovější verze).  
- **Potřebuji licenci?** Dočasná licence funguje pro testování; pro produkci je vyžadována plná licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 10 minut pro základní vložení podpisu.

## Co je úprava XPS dokumentu?

XPS (XML Paper Specification) je formát dokumentu s pevnou rozložením od Microsoftu, podobný PDF. Úprava XPS dokumentu znamená programově měnit jeho vizuální obsah – přidávat text, obrázky nebo tvary – aniž byste soubor převáděli do jiného formátu. Aspose.Page poskytuje bohatý objektový model, který vám umožní upravovat XPS soubory přímo z vašeho .NET kódu.

## Proč použít Aspose.Page k úpravě XPS dokumentů?

* **Plná kontrola** – pracujte se stránkami, glyfy, štětci a transformacemi na nízké úrovni.  
* **Žádné externí závislosti** – čistá .NET knihovna, není potřeba Office ani Adobe komponent.  
* **Cross‑platform** – běží na Windows, Linuxu a macOS přes .NET Core.  
* **Robustní výkon** – efektivně zpracovává velké dokumenty a podporuje pokročilou typografii.

## Předpoklady

Předtím, než začnete, ujistěte se, že máte následující:

- **Aspose.Page pro .NET** – Nainstalujte NuGet balíček nebo stáhněte knihovnu z oficiální dokumentace **[zde](https://reference.aspose.com/page/net/)**.  
- **Vstupní XPS soubor** – Získejte ukázkový XPS dokument (např. `input1.xps`) ze **[stránky vydání Aspose](https://releases.aspose.com/page/net/)**.  
- **Pracovní adresář** – Vytvořte složku na svém počítači pro uložení vstupních a výstupních souborů a poznamenejte si její úplnou cestu; tuto cestu přiřadíte proměnné `dir` v kódu.  
- **Vývojové prostředí** – Visual Studio 2019/2022, .NET Framework 4.7.2 nebo novější, nebo jakýkoli .NET Core/5/6 projekt.

Nyní, když je vše připraveno, ponořme se do kódu.

## Importovat jmenné prostory

Ve vašem .NET projektu začněte importováním požadovaných jmenných prostorů pro Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Krok 1: Otevřít XPS dokument jako stream

Otevřeme zdrojový XPS soubor jako stream a vytvoříme objekt `XpsDocument`, který představuje celý dokument.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Tip:* Zabalte stream do bloku `using`, aby byl souborový handle automaticky uvolněn.

## Krok 2: Vytvořit text podpisu

Dále vytvoříme štětec s plnou barvou, který bude použit k vykreslení glyfů podpisu.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Můžete změnit `Color.BlueViolet` na libovolnou `System.Drawing.Color`, která odpovídá vaší značce.

## Krok 3: Definovat stránky a přidat podpis

Určíme, které stránky mají získat podpis, a poté přidáme glyfy na každou stránku.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Proč tyto souřadnice?* Hodnoty X a Y jsou měřeny v bodech (1/72 palce). Upravit je tak, aby text byl přesně tam, kde jej potřebujete v rozložení stránky.

## Krok 4: Uložit změny do XPS dokumentu

Nakonec zapíšeme upravený dokument zpět na disk.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Nový soubor `input1_out.xps` nyní obsahuje podpis „Confirmed“ na stránkách 1‑3.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **Podpis není viditelný** | Špatné souřadnice nebo nevybraná stránka | Ověřte, že je pro každou stránku voláno `SelectActivePage`, a upravte hodnoty X/Y. |
| **Výjimka při `AddGlyphs`** | Písmo není nainstalováno na serveru | Zajistěte, aby požadované písmo (např. Arial) bylo dostupné, nebo vložte vlastní písmo pomocí `document.AddFont`. |
| **Výstupní soubor je poškozen** | Stream nebyl řádně uzavřen | Použijte `using` bloky pro všechny streamy a v případě potřeby zavolejte `document.Dispose()`. |
| **Zpomalení výkonu u velkých souborů** | Načítání celého dokumentu do paměti | Zpracovávejte stránky po dávkách nebo použijte `XpsLoadOptions` s možnostmi streamování (pokud jsou k dispozici v novějších verzích). |

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní s nejnovějšími .NET frameworky?**  
A: Ano, Aspose.Page je pravidelně aktualizována, aby podporovala .NET Framework 4.5+, .NET Core 3.1+, .NET 5 a .NET 6.

**Q: Mohu přizpůsobit písmo a styl přidaného textu?**  
A: Samozřejmě. Změňte parametry `AddGlyphs` (název písma, velikost, `FontStyle`) podle vašeho návrhu.

**Q: Existují nějaká omezení velikosti pro XPS soubory?**  
A: Aspose.Page dokáže zpracovat velké dokumenty, ale spotřeba paměti roste s velikostí souboru. U velmi velkých souborů zvažte zpracování stránek jednotlivě.

**Q: Jak získám dočasnou licenci pro Aspose.Page?**  
A: Dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde mohu získat pomoc nebo se spojit s komunitou Aspose?**  
A: Navštivte **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, kde můžete klást otázky a sdílet zkušenosti.

## Závěr

V tomto tutoriálu jsme ukázali, jak **modifikovat xps dokument** soubory přidáním vlastního textu podpisu pomocí Aspose.Page pro .NET. Nyní máte pevný základ pro vložení libovolného textu, vodoznaku nebo anotace na konkrétní stránky XPS souboru. Experimentujte s různými písmy, barvami a pozicemi, aby vyhovovaly požadavkům značky vaší aplikace, a prozkoumejte širší API Aspose.Page pro pokročilou grafiku a možnosti rozvržení.

---

**Last Updated:** 2026-01-12  
**Testováno s:** Aspose.Page 24.11 pro .NET (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}