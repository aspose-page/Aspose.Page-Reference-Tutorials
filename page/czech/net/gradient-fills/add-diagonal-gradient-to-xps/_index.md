---
date: 2026-02-23
description: Naučte se, jak pomocí Aspose.Page pro .NET vytvářet XPS dokumenty s diagonálním
  gradientem a bez námahy vylepšete své vizuální prezentace.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Vytvořte úhlopříčkový gradient XPS pomocí Aspose.Page pro .NET
url: /cs/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

 Ensure we kept all shortcodes, code block placeholders, links unchanged.

Now output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte diagonální gradient XPS pomocí Aspose.Page pro .NET

## Úvod

Pokud potřebujete **vytvořit diagonální gradient XPS** soubory, které upoutají pozornost, Aspose.Page pro .NET to usnadňuje. V tomto tutoriálu se naučíte, jak přidat diagonální gradient do XPS dokumentu krok za krokem pomocí Aspose.Page API. Na konci budete mít znovupoužitelný vzor, který můžete přizpůsobit jakémukoli tvaru nebo barevnému schématu.

## Rychlé odpovědi
- **Co dělá metoda API?** Vytváří lineární gradientový štětec, který se rozprostírá diagonálně přes cestu.  
- **Která třída představuje XPS dokument?** `XpsDocument`.  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze funguje pro vývoj; licence je vyžadována pro produkci.  
- **Mohu změnit směr gradientu?** Ano – upravte počáteční a koncové hodnoty `PointF`.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je **create diagonal gradient xps**?
Diagonální gradient je plynulý přechod barev, který probíhá od jednoho rohu tvaru k protilehlému rohu. V XPS se tento efekt dosahuje aplikací `LinearGradientBrush` na vlastnost výplně cesty. Knihovna Aspose.Page abstrahuje nízkoúrovňové XPS značkování, což vám umožňuje soustředit se na barvy a geometrie.

## Proč použít Aspose.Page pro diagonální gradienty?
- **Vysoká věrnost vykreslování** – výstup přesně odpovídá specifikaci XPS.  
- **Plná integrace s .NET** – funguje s C#, VB.NET a jakýmkoli .NET jazykem.  
- **Žádné externí závislosti** – vše je zpracováno v procesu, není potřeba COM ani Office.  
- **Škálovatelnost pro komplexní dokumenty** – můžete kombinovat více gradientů, obrázků a textu na stejné stránce.

## Předpoklady

1. **Knihovna Aspose.Page pro .NET** – stáhněte ji [zde](https://releases.aspose.com/page/net/).  
2. **Vývojové prostředí** – Visual Studio, Rider nebo jakýkoli editor, který podporuje .NET projekty.  

Nyní se ponořme do kódu.

## Importujte jmenné prostory

Ve vašem .NET projektu zahrňte potřebné jmenné prostory z knihovny Aspose.Page, abyste získali přístup k požadovaným třídám a metodám. Přidejte následující jmenné prostory na začátek vašeho kódu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Krok 1: Nastavte adresář dokumentu

Začněte určením cesty k vašemu adresáři dokumentů. Zde bude uložen výsledný XPS dokument s diagonálním gradientem.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte nový XPS dokument

Inicializujte nový `XpsDocument` pomocí knihovny Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Krok 3: Definujte barvy gradientu

Vytvořte seznam objektů `XpsGradientStop`, z nichž každý představuje barvu v diagonálním gradientu.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Krok 4: Přidejte diagonální gradient k cestě

Vytvořte novou cestu s definovanou geometrií a aplikujte na ni diagonální gradient. Podle potřeby upravte transformaci vykreslování a vlastnosti výplně.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Krok 5: Uložte výsledný XPS dokument

Nakonec uložte upravený XPS dokument do určeného adresáře.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Úspěšně jste **vytvořili XPS soubor s diagonálním gradientem**. Klidně experimentujte s různými barevnými zastávkami, řetězci geometrie nebo transformačními maticemi, abyste vytvořili různé vizuální efekty.

## Časté problémy a řešení
- **Gradient není viditelný** – Ověřte, že geometrie cesty je uzavřená a že počáteční/konečné body štětce jsou v mezích cesty.  
- **Nesprávné barvy** – Ujistěte se, že používáte `CreateColor` se správnými ARGB hodnotami; metoda očekává hodnoty v rozsahu 0‑255.  
- **Soubor nebyl uložen** – Zkontrolujte, že `dataDir` ukazuje na existující složku a že aplikace má oprávnění k zápisu.

## Často kladené otázky

**Q: Mohu použít více gradientů na různé části dokumentu?**  
A: Ano, můžete vytvořit více cest a aplikovat na každou odlišný gradient.

**Q: Existují předdefinované styly gradientů?**  
A: Aspose.Page umožňuje vlastní gradienty, což vám dává plnou kontrolu nad barevnými přechody.

**Q: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?**  
A: Aspose.Page se primárně zaměřuje na manipulaci s XPS dokumenty.

**Q: Jak mohu řešit chyby související se zpracováním dokumentu?**  
A: Podívejte se na [dokumentaci](https://reference.aspose.com/page/net/) pro osvědčené postupy při zpracování chyb.

**Q: Je k dispozici zkušební verze před zakoupením?**  
A: Ano, můžete vyzkoušet [bezplatnou zkušební verzi](https://releases.aspose.com/), abyste si vyzkoušeli Aspose.Page pro .NET.

**Q: Jak změním směr gradientu na vertikální nebo horizontální?**  
A: Upravit argumenty `PointF` v `CreateLinearGradientBrush`, aby nastavil nové počáteční a koncové body.

**Q: Podporuje knihovna průhlednost v gradientu?**  
A: Ano – zahrňte alfa hodnotu při vytváření barev pomocí `CreateColor`.

## Závěr

Aspose.Page pro .NET zjednodušuje proces vylepšování XPS dokumentů pomocí diagonálních gradientů. Tento průvodce vás provede všemi kroky od nastavení předpokladů až po uložení finálního souboru. Pokračujte v experimentování s různými tvary a barevnými paletami, aby vaše XPS zprávy, brožury nebo faktury skutečně vynikly.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-02-23  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose