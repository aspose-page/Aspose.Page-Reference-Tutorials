---
date: 2026-02-25
description: Naučte se, jak vytvořit XPS dokument a použít lineární gradient s Aspose.Page
  pro .NET. Postupujte podle našeho krok‑za‑krokem průvodce pro uložení XPS souboru.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Vytvořte XPS dokument s vertikálním gradientem pomocí Aspose.Page
url: /cs/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání vertikálního gradientu do XPS pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu **vytvoříte XPS dokument**, který obsahuje hladký vertikální gradient. Přidávání gradientů je běžný způsob, jak učinit XPS soubory profesionálnějšími — ideální pro zprávy, brožury nebo jakoukoliv tisknutelnou grafiku. Provedeme vás každým krokem, od nastavení projektu až po uložení finálního XPS souboru, abyste mohli rychle aplikovat lineární gradient na libovolnou cestu.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání vertikálního lineárního gradientu na cestu v XPS dokumentu.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.  
- **Mohu výsledek uložit jako XPS soubor?** Ano, metoda `Save` zapíše soubor na disk.

## Co je vertikální gradient v XPS?

Vertikální gradient je přechod barev, který probíhá od horní části tvaru k dolní. V XPS se to dosahuje pomocí **linear gradient brush**, který určuje počáteční a koncový bod, a kolekce gradient stopů, které řídí barvu na konkrétních pozicích.

## Proč použít Aspose.Page pro vytvoření XPS dokumentu s gradienty?

- **Plná integrace s .NET** – funguje s .NET Framework, .NET Core a .NET 5/6+.  
- **Žádné externí závislosti** – veškeré vykreslování zajišťuje knihovna.  
- **Vysoká věrnost** – gradienty se vykreslují přesně podle definice, v souladu se specifikací XPS.  
- **Snadná údržba** – přehledný objektový model pro cesty, štětce a barvy.

## Požadavky

- Aspose.Page for .NET Library: Ujistěte se, že máte knihovnu Aspose.Page pro .NET nainstalovanou ve svém vývojovém prostředí. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).
- Vývojové prostředí: Nastavte .NET vývojové prostředí ve svém preferovaném IDE, například Visual Studio.

Nyní, když máme vše připravené, pojďme se ponořit do kódu.

## Importování jmenných prostorů

Ve své .NET aplikaci zahrňte potřebné jmenné prostory pro přístup ke třídám a metodám Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Krok 1: Nastavte adresář dokumentu

Definujte složku, do které bude vygenerovaný XPS soubor uložen.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Krok 2: Vytvořte nový XPS dokument

Vytvořte novou instanci XPS dokumentu, který později naplníme cestou vyplněnou gradientem.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Krok 3: Definujte gradient stopy

Gradient stopy určují barvy a jejich pozice podél gradientové čáry. Zde vytvoříme pět stopů pro plynulý vertikální přechod.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Krok 4: Vytvořte cestu s gradientem

Nakreslíme cestu ve tvaru obdélníku a použijeme **linear gradient brush**, který běží vertikálně od bodu (10, 110) k bodu (10, 200). Štětec získá gradient stopy definované dříve.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Krok 5: Uložte výsledný XPS dokument

Nakonec zapíšeme XPS dokument na disk. Tento krok **save XPS file** vytvoří `AddVerticalGradient_outXPS.xps` ve složce, kterou jste určili.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Tip:** Ověřte výstup otevřením XPS souboru ve Windows XPS Vieweru nebo v jakémkoli jiném prohlížeči, abyste se ujistili, že gradient vypadá podle očekávání.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Gradient se zobrazuje jako jednobarevná plocha | Gradient stopy nebyly přidány do štětce | Ujistěte se, že je provedeno `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`. |
| Soubor nebyl při ukládání nalezen | `dataDir` ukazuje na neexistující složku | Nejprve vytvořte adresář nebo použijte absolutní cestu. |
| Barvy vypadají odlišně | Hodnoty barev používají pořadí ARGB; ověřte pořadí kanálů | Použijte `CreateColor(alpha, red, green, blue)` správně. |

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní s Visual Studio 2019?**  
A: Ano, Aspose.Page je kompatibilní s Visual Studio 2019. Ujistěte se, že máte nainstalovanou správnou verzi knihovny.

**Q: Mohu používat Aspose.Page pro komerční projekty?**  
A: Ano, Aspose.Page lze použít pro komerční projekty. Navštivte [zde](https://purchase.aspose.com/buy) pro prozkoumání licenčních možností.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, bezplatnou zkušební verzi Aspose.Page získáte [zde](https://releases.aspose.com/).

**Q: Kde najdu dokumentaci k Aspose.Page?**  
A: Dokumentace je k dispozici [zde](https://reference.aspose.com/page/net/).

**Q: Jak mohu získat podporu nebo položit otázku?**  
A: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu.

## Závěr

Nyní víte, jak **vytvořit XPS dokument**, **aplikovat lineární gradient** a **uložit XPS soubor** pomocí Aspose.Page pro .NET. Tento přístup vám poskytuje plnou kontrolu nad vizuálním stylem výstupů XPS, což vaše tisknutelné dokumenty učiní výraznějšími.

---  

**Poslední aktualizace:** 2026-02-25  
**Testováno s:** Aspose.Page for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}