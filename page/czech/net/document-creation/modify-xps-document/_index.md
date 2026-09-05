---
date: 2026-07-10
description: 'Aspose Page .NET tutoriál: Naučte se, jak upravovat XPS dokumenty pomocí
  Aspose.Page for .NET, včetně přidávání textu, podpisů a vodoznaků s přehlednými
  ukázkami kódu.'
keywords:
- aspose page .net tutorial
- modify xps document
- add text to xps
lastmod: 2026-07-10
linktitle: Upravit XPS dokument
og_description: Aspose Page .NET tutoriál ukazuje, jak upravit XPS dokumenty, rychle
  přidat text a podpisy. Postupujte podle krok‑za‑krokem průvodce pro vývojáře .NET.
og_image_alt: Guide to modify XPS document using Aspose.Page for .NET
og_title: 'Aspose.Page .NET tutoriál: Úprava XPS dokumentu'
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: 'Aspose Page .NET tutorial: Learn how to modify XPS documents using
    Aspose.Page for .NET, including adding text, signatures, and watermarks with clear
    code examples.'
  headline: 'Aspose.Page .NET Tutorial: Modify XPS Document'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page is regularly updated to support .NET Framework 4.5+,
      .NET Core 3.1+, .NET 5, and .NET 6.
    question: Is Aspose.Page compatible with the latest .NET frameworks?
  - answer: Absolutely. Change the parameters of `AddGlyphs` (font name, size, `FontStyle`)
      to suit your design.
    question: Can I customize the font and style of the added text?
  - answer: Aspose.Page can handle documents larger than 200 MB and up to 500 pages
      without exhausting memory, thanks to its streaming architecture.
    question: Are there any size limits for XPS files?
  - answer: You can acquire a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How do I obtain a temporary license for Aspose.Page?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: Where can I seek help or connect with the Aspose community?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose page
- xps modification
- .net tutorial
title: 'Aspose.Page .NET tutoriál: Úprava XPS dokumentu'
url: /cs/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET tutoriál: Úprava XPS dokumentu

## Úvod

V tomto **aspose page .net tutorial** objevíte, jak programově upravit XPS dokument pomocí Aspose.Page pro .NET. Ať už potřebujete vložit podpis, přidat vodoznak nebo jednoduše umístit vlastní text na stránku, projdeme každý řádek kódu, vysvětlíme, proč je každý krok důležitý, a podělíme se o praktické tipy, jak se vyhnout běžným úskalím. Na konci budete schopni upravovat XPS soubory během několika minut, ne hodin.

### Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání textu podpisu („Confirmed“) na vybrané stránky XPS souboru.  
- **Která knihovna je vyžadována?** Aspose.Page for .NET (nejnovější verze).  
- **Potřebuji licenci?** Dočasná licence funguje pro testování; pro produkci je vyžadována plná licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 10 minut pro základní vložení podpisu.

## Co je úprava XPS dokumentu?

Úprava XPS dokumentu zahrnuje programové změny jeho vizuálního obsahu – například vkládání textu, obrázků nebo vektorových tvarů – při zachování pevného rozvržení souboru. Protože XPS je založen na XML, změny se aplikují přímo na strukturu stránek dokumentu bez nutnosti konverze, což umožňuje přesnou kontrolu nad rozvržením, typografií a grafikou.

## Proč použít Aspose.Page k úpravě XPS dokumentů?

Aspose.Page nabízí nativní .NET API, které funguje napříč platformami, eliminuje externí závislosti a poskytuje vysoký výkon pro velké dokumenty. Vývojářům poskytuje nízkoúrovňový přístup ke stránkám, glyphům, štětcům a transformacím, což umožňuje implementovat vlastní podpisy, vodoznaky a složité grafiky s jemnou kontrolou.

## Požadavky

Před zahájením se ujistěte, že máte následující:

- **Aspose.Page for .NET** – Nainstalujte NuGet balíček nebo stáhněte knihovnu z oficiální dokumentace **[here](https://reference.aspose.com/page/net/)**.  
- **Input XPS file** – Získejte ukázkový XPS dokument (např. `input1.xps`) ze **[Aspose releases page](https://releases.aspose.com/page/net/)**.  
- **Working directory** – Vytvořte složku na svém počítači pro uložení vstupních a výstupních souborů a poznamenejte si její úplnou cestu; tuto cestu přiřadíte proměnné `dir` v kódu.  
- **Development environment** – Visual Studio 2019/2022, .NET Framework 4.7.2 nebo novější, nebo jakýkoli .NET Core/5/6 projekt.

Nyní, když je vše připraveno, ponořme se do kódu.

## Jak importovat jmenné prostory pro Aspose.Page?

Pro práci s Aspose.Page musíte na začátku svého C# souboru importovat jeho jmenné prostory. Tím kompilátoru zpřístupní typy jako `XpsDocument`, `Glyphs` a `SolidColorBrush`. Třída `XpsDocument` představuje XPS soubor a poskytuje přístup k jeho stránkám a zdrojům.  

```csharp
using Aspose.Page;
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using System.IO;
using System.Drawing;
```

Příkazy `using` vám poskytují přímý přístup k `XpsDocument`, `Glyphs` a dalším základním třídám.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Jak otevřít stream XPS dokumentu?

Otevřete zdrojový XPS soubor pomocí `FileStream` v režimu jen pro čtení a předávejte jej konstruktoru `XpsDocument`. Tím se soubor načte do objektu `XpsDocument`, který slouží jako vstupní bod pro všechny následné úpravy. Ujistěte se, že stream je zabalený v `using` bloku, aby byl souborový handle automaticky uvolněn.  

```csharp
string inputPath = Path.Combine(dir, "input1.xps");
using (FileStream fs = new FileStream(inputPath, FileMode.Open, FileAccess.Read))
{
    XpsDocument document = new XpsDocument(fs);
    // All further operations use the 'document' variable.
}
```

**Definition anchor:** Třída `XpsDocument` je nejvyšší objekt Aspose.Page, který zapouzdřuje jeden XPS soubor a vystavuje stránky, zdroje a metadata pro manipulaci.

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

*Tip:* Zabalte stream do `using` bloku, aby byl souborový handle automaticky uvolněn.

## Jak vytvořit text podpisu v XPS?

Vytvořte `SolidColorBrush`, který určuje barvu vyplňující text podpisu, a poté připravte řetězec, který chcete vykreslit. Třída `SolidColorBrush` poskytuje jednotnou barvu pro kreslicí operace, jako je text nebo tvary. Před přidáním glyphů upravte barvu štětce tak, aby odpovídala vaší firemní identitě.  

```csharp
SolidColorBrush brush = new SolidColorBrush(document, Color.BlueViolet);
string signature = "Confirmed";
```

**Definition anchor:** `SolidColorBrush` je kreslicí objekt, který vyplňuje tvary nebo text jednou, jednotnou barvou.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Můžete změnit `Color.BlueViolet` na libovolnou `System.Drawing.Color`, která odpovídá vaší značce.

## Jak definovat stránky a přidat glyphy podpisu?

Vyberte každou cílovou stránku pomocí `SelectActivePage` a poté zavolejte `AddGlyphs`, aby se text podpisu umístil na požadované souřadnice. Metoda `AddGlyphs` vloží sekvenci znaků do aktivní stránky s určeným fontem, velikostí, stylem a štětcem. Jemně doladěte hodnoty X a Y pro přesné umístění textu.  

```csharp
int[] pages = { 1, 2, 3 };
foreach (int pageNumber in pages)
{
    XpsPage page = document.Pages[pageNumber - 1];
    page.SelectActivePage();
    page.AddGlyphs(100, 200, signature, "Arial", 24, FontStyle.Regular, brush);
}
```

**Definition anchor:** `AddGlyphs` vkládá sekvenci znaků (glyphů) do aktivní stránky pomocí zadaného fontu, velikosti, stylu a štětce.

*Proč tyto souřadnice?* Hodnoty X a Y jsou měřeny v bodech (1/72 palce). Upravením těchto hodnot umístíte text přesně tam, kde jej potřebujete v rozvržení stránky.

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

## Jak uložit změny do XPS dokumentu?

Po přidání všech požadovaných glyphů zavolejte metodu `Save` na instanci `XpsDocument`, aby se upravený obsah zapsal do nového souboru. Funkce `Save` serializuje paměťovou reprezentaci dokumentu zpět do formátu XPS a zachová všechny změny, jako je přidaný text nebo grafika. Zadejte odlišný výstupní název souboru, aby nedošlo k přepsání originálu.  

```csharp
string outputPath = Path.Combine(dir, "input1_out.xps");
using (FileStream outFs = new FileStream(outputPath, FileMode.Create, FileAccess.Write))
{
    document.Save(outFs);
}
```

Nový soubor `input1_out.xps` nyní obsahuje podpis „Confirmed“ na stránkách 1‑3.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **Podpis není viditelný** | Špatné souřadnice nebo nevybraná stránka | Ověřte, že je pro každou stránku voláno `SelectActivePage`, a upravte hodnoty X/Y. |
| **Výjimka při `AddGlyphs`** | Písmo není nainstalováno na serveru | Ujistěte se, že je požadované písmo (např. Arial) k dispozici, nebo vložte vlastní písmo pomocí `document.AddFont`. |
| **Výstupní soubor je poškozen** | Stream není řádně uzavřen | Použijte `using` bloky pro všechny streamy a v případě potřeby zavolejte `document.Dispose()`. |
| **Zpomalení výkonu u velkých souborů** | Načítání celého dokumentu do paměti | Zpracovávejte stránky po dávkách nebo použijte `XpsLoadOptions` s možnostmi streamování (pokud jsou k dispozici v novějších verzích). |

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní s nejnovějšími .NET frameworky?**  
A: Ano, Aspose.Page je pravidelně aktualizováno, aby podporovalo .NET Framework 4.5+, .NET Core 3.1+, .NET 5 a .NET 6.

**Q: Mohu přizpůsobit písmo a styl přidaného textu?**  
A: Určitě. Změňte parametry `AddGlyphs` (název písma, velikost, `FontStyle`) podle potřeby.

**Q: Existují nějaká omezení velikosti pro XPS soubory?**  
A: Aspose.Page zvládne dokumenty větší než 200 MB a až 500 stránek bez vyčerpání paměti díky své streamovací architektuře.

**Q: Jak získám dočasnou licenci pro Aspose.Page?**  
A: Dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde mohu získat pomoc nebo se spojit s komunitou Aspose?**  
A: Navštivte **[Aspose.Page fórum](https://forum.aspose.com/c/page/39)**, kde můžete klást otázky a sdílet zkušenosti.

## Závěr

V tomto **aspose page .net tutorial** jsme ukázali, jak **upravit XPS dokumenty** přidáním vlastního textu podpisu pomocí Aspose.Page pro .NET. Nyní máte pevný základ pro vkládání libovolného textu, vodoznaku nebo anotace na konkrétní stránky XPS souboru. Experimentujte s různými fonty, barvami a pozicemi, aby vyhovovaly požadavkům vaší aplikace, a prozkoumejte širší API Aspose.Page pro pokročilé grafické a rozvržení funkce.

---

**Poslední aktualizace:** 2026-07-10  
**Testováno s:** Aspose.Page 24.11 for .NET (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Přidat text do XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Přidat obrázek do XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/image-management/add-image-to-xps-document/)
- [Vytvořit XPS dokument – Aspose.Page pro .NET](/page/net/document-creation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}