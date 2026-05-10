---
date: 2026-02-28
description: Naučte se, jak vytvořit XPS dokument v .NET a přidat obrázek pomocí Aspose.Page
  pro .NET. Postupujte podle tohoto krok‑za‑krokem průvodce pro plynulý vývojový zážitek.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: Vytvoření XPS dokumentu v .NET – Přidání obrázku pomocí Aspose.Page
url: /cs/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání obrázku do XPS dokumentu pomocí Aspose.Page pro .NET

V tomto tutoriálu se naučíte, jak **create XPS document .NET** a vložit obrázek pomocí výkonné knihovny Aspose.Page. Ať už generujete zprávy, faktury nebo vlastní grafiku, přidávání vizuálních prvků do XPS souborů je častý požadavek pro .NET vývojáře.

## Úvod

Ve světě .NET vývoje je začlenění obrázků do XPS dokumentů běžným požadavkem. Aspose.Page pro .NET tento proces zjednodušuje a nabízí výkonný nástrojový set pro snadnou manipulaci a vylepšování XPS dokumentů. Tento tutoriál vás provede kroky, jak přidat obrázek do XPS dokumentu pomocí Aspose.Page pro .NET.

## Rychlé odpovědi
- **What does this tutorial cover?** Přidání obrázku do XPS dokumentu s Aspose.Page pro .NET.  
- **Which primary keyword is targeted?** *create xps document .net*  
- **Do I need a license?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Which .NET versions are supported?** Funguje s .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does implementation take?** Přibližně 5‑10 minut pro základní vložení obrázku.

## Co je “create XPS document .NET”?
Vytvoření XPS dokumentu v .NET znamená programově generovat soubor XML Paper Specification (XPS) – formát s pevně daným rozložením – pomocí C# nebo VB.NET. Aspose.Page poskytuje plynulé API, které abstrahuje nízkoúrovňové detaily a umožňuje vám soustředit se na obsah, jako je text, tvary a obrázky.

## Proč použít Aspose.Page k přidání obrázku?
- **Full control** nad umístěním, měřítkem a ořezáváním obrázků.  
- **No external dependencies** – knihovna interně zpracovává dekódování obrázků.  
- **Cross‑platform** podpora pro Windows i Linux prostředí.  
- **High fidelity** vykreslování, které zachovává kvalitu obrázku ve výsledném XPS souboru.

## Požadavky

Před zahájením tutoriálu se ujistěte, že máte splněny následující požadavky:

1. Aspose.Page for .NET Library: Stáhněte a nainstalujte knihovnu z [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).

2. Development Environment: Nastavte .NET vývojové prostředí, například Visual Studio.

3. Sample Image: Mějte připravený ukázkový soubor obrázku (např. "QL_logo_color.tif"), který chcete přidat do XPS dokumentu.

## Importování jmenných prostorů

Začněte importováním potřebných jmenných prostorů do vašeho .NET projektu. Tyto jmenné prostory jsou nezbytné pro využití funkcí poskytovaných knihovnou Aspose.Page pro .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page Přidání obrázku do XPS dokumentu

Níže projdeme každý krok potřebný k **create XPS document .NET** a vložení obrázku.

### Krok 1: Nastavení adresáře dokumentu

Nejprve určete cestu k adresáři, kde budou soubory dokumentu uloženy. Tento krok zajistí, že projekt bude vědět, kde hledat a kam ukládat soubory.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Krok 2: Vytvoření XPS dokumentu

Vytvořte nový XPS dokument pomocí Aspose.Page pro .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Krok 3: Přidání obrázku do XPS dokumentu

Nyní přidáme obrázek do XPS dokumentu. V tomto příkladu použijeme ukázkový obrázek s názvem "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Krok 4: Uložení výsledného XPS dokumentu

Uložte XPS dokument s přidaným obrázkem.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Nyní jste úspěšně přidali obrázek do XPS dokumentu pomocí Aspose.Page pro .NET!

## Časté problémy a řešení

- **File not found error** – Ověřte, že `dataDir` ukazuje na správnou složku a že název souboru obrázku přesně odpovídá, včetně citlivosti na velikost písmen v Linuxu.  
- **Image appears distorted** – Upravit škálovací faktory `CreateMatrix` nebo parametry `RectangleF` pro kontrolu velikosti a poměru stran.  
- **Unsupported image format** – Aspose.Page podporuje běžné rastrové formáty (PNG, JPEG, TIFF). Před použitím `CreateImageBrush` převěďte nepodporované formáty.

## Často kladené otázky

### Q1: Je Aspose.Page pro .NET kompatibilní s nejnovějšími verzemi .NET frameworku?

A1: Aspose.Page pro .NET je navržen tak, aby byl kompatibilní s širokou škálou verzí .NET frameworku, včetně nejnovějších vydání. Podrobnosti najdete v [documentation](https://reference.aspose.com/page/net/).

### Q2: Mohu použít Aspose.Page pro .NET jak ve Windows, tak v Linux prostředí?

A2: Ano, Aspose.Page pro .NET je platformně nezávislý, což ho činí vhodným pro použití jak ve Windows, tak v Linux prostředí.

### Q3: Jaké jsou licenční možnosti pro Aspose.Page pro .NET?

A3: Ano, můžete prozkoumat licenční možnosti a provést nákup [here](https://purchase.aspose.com/buy).

### Q4: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

A4: Ano, můžete si vyzkoušet Aspose.Page pro .NET zdarma prostřednictvím [free trial](https://releases.aspose.com/).

### Q5: Kde mohu získat podporu nebo se zapojit do komunity pro Aspose.Page pro .NET?

A5: Navštivte [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39), kde se můžete spojit s komunitou a získat podporu.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak využít Aspose.Page pro .NET k bezproblémovému začlenění obrázků do XPS dokumentů. Tento krok‑za‑krokem průvodce zajišťuje hladký integrační proces, rozšiřuje vaše .NET vývojářské schopnosti a pomáhá vám **create XPS document .NET** řešení s vizuální bohatostí.

---

**Poslední aktualizace:** 2026-02-28  
**Testováno s:** Aspose.Page for .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}