---
date: 2026-06-30
description: Zjistěte, jak vytvořit XPS document .NET a přidat image‑filled glyphs
  nebo foreign images pomocí Aspose.Page pro .NET během několika jednoduchých kroků.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Přidejte Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Vytvořte XPS Document .NET – Add Image Filled Glyph & Foreign Image pomocí
  Aspose.Page
url: /cs/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS dokumentu .NET – Přidání glyphu vyplněného obrázkem a cizího obrázku pomocí Aspose.Page

## Úvod

V .NET vývoji jsou úkoly **create XPS document .NET** běžné, když potřebujete vysoce kvalitní grafiku nezávislou na rozlišení. Aspose.Page pro .NET to usnadňuje a umožňuje obohatit XPS soubory o glyphy vyplněné obrázkem nebo načíst obrázky z jiného XPS dokumentu. Na konci tohoto tutoriálu budete vědět, jak vytvořit dva XPS dokumenty, vyplnit glyphy obrázky a znovu použít tyto obrázky napříč dokumenty – ideální pro generování faktur, certifikátů nebo jakéhokoli vizuálně bohatého výstupu.

## Rychlé odpovědi
- **Co Aspose.Page podporuje?** Více než 25 formátů obrázků a možnost zpracovávat XPS soubory až do 500 MB bez načítání celé paměti.  
- **Kolik řádků kódu je potřeba k přidání glyphu vyplněného obrázkem?** Pouze dva řádky: vytvořit `ImageBrush` a přiřadit jej k `Glyph`.  
- **Potřebuji licenci pro produkci?** Ano, komerční licence odstraňuje vodotisk hodnocení.  
- **Které verze .NET jsou kompatibilní?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Mohu znovu použít písma z jiného XPS?** Naprosto – můžete importovat kolekci písem z prvního dokumentu do druhého.

## Jak vytvořit XPS dokument pomocí Aspose.Page .NET?

Načtěte knihovnu Aspose.Page, vytvořte instanci `XpsDocument`, přidejte stránku a zavolejte `Save` – to je kompletní pracovní postup ve třech stručných příkazech. API automaticky zpracovává velikost stránky, DPI a správu zdrojů, takže nemusíte sami spravovat nízkoúrovňové struktury XPS. Tento přístup škáluje od jednostránkových letáků po katalogy se stovkami stránek.

## Požadavky

- **Aspose.Page for .NET** – stáhněte jej z [here](https://releases.aspose.com/page/net/).  
- **IDE pro .NET** – Visual Studio, Rider nebo VS Code s rozšířením C#.  
- **Složka pro vaše dokumenty** – v ukázkách kódu na ni budeme odkazovat jako **Your Document Directory**.

## Importování jmenných prostorů

`Aspose.Page.XPS` jmenný prostor poskytuje základní třídy XPS dokumentu, zatímco `Aspose.Page.XPS.XpsModel` obsahuje modelové prvky jako glyphy a štětce. Importujte je na začátku souboru:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Co je glyph vyplněný obrázkem?

Glyph je vektorový tvar, který může být vykreslen plnou barvou, gradientem nebo štětcem s obrázkem. Když použijete `ImageBrush`, vnitřek glyphu je natřen dodaným obrázkem, což umožňuje komplexní vizuální efekty bez rasterizace celé stránky.

## Krok 1: Vytvořte první XPS dokument

`XpsDocument` představuje XPS balíček a je vstupním bodem pro vytváření a ukládání XPS souborů. Začněte vytvořením prvního XPS dokumentu, který bude hostit glyphy vyplněné obrázkem.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Krok 2: Přidejte glyphy do prvního dokumentu

`XpsGlyphs` definuje kolekci glyphů (znaků textu), které lze umístit na stránku. Přidejte glyphy do prvního dokumentu a určete písmo, velikost, styl a pozici.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Krok 3: Vyplňte glyphy štětcem s obrázkem

`ImageBrush` maluje oblast obrázkem, což umožňuje vzory nebo obrázky vyplnit tvary. Vyplňte glyphy štětcem s obrázkem, využívajíc obrázek z vašeho datového adresáře.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 4: Vytvořte druhý XPS dokument

`XpsDocument` se používá k vytvoření nového XPS souboru, který může obsahovat stránky, zdroje a obsah. Nyní vytvořte druhý XPS dokument, který bude zahrnovat glyphy z prvního dokumentu.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Krok 5: Přidejte glyphy s písmem z prvního dokumentu

`Font` představuje typ písma používaný k vykreslení textu v XPS dokumentu. Přidejte glyphy do druhého dokumentu a použijte písmo extrahované z prvního dokumentu. Sdílením kolekce písem udržujete velikost souboru nízkou a zajišťujete vizuální konzistenci.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Krok 6: Vytvořte štětec s obrázkem z výplně prvního dokumentu

`ImageBrush` lze vytvořit z existující výplně, aby se stejný obrázek znovu použil napříč dokumenty. Vytvořte štětec s obrázkem z výplně prvního dokumentu a použijte jej k vyplnění glyphů ve druhém dokumentu. Tato technika „cizího obrázku“ vám umožní znovu použít grafiku bez duplikace zdrojového souboru.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 7: Uložte dokumenty

`Save` zapíše XPS balíček do souboru a vloží všechny zdroje. Uložte jak první, tak druhý XPS dokument do výstupní složky. Metoda `Save` zapisuje XPS balíček, vkládá všechny zdroje a zachovává glyphy vyplněné obrázkem.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Časté problémy a řešení

| Problém | Proč se to děje | Řešení |
|---------|----------------|--------|
| **Obrázek se nezobrazuje uvnitř glyphu** | `ImageBrush` byl vytvořen s nesprávným URI nebo velikost obrázku přesahuje hranice glyphu. | Ověřte cestu k obrázku a případně nastavte `ImageBrush.Stretch = Stretch.Uniform`. |
| **Písma chybí ve druhém dokumentu** | Zdroje písem nebyly exportovány z prvního XPS. | Použijte `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` před přidáním glyphů. |
| **Zpomalení výkonu u velkých souborů** | Načítání velkých obrázků do paměti pro každý glyph. | Znovu použijte jedinou instanci `ImageBrush` pro všechny glyphy, nebo před použitím obrázek zmenšete. |

## Často kladené otázky

### Q1: Mohu použít různé formáty obrázků pro vyplňování glyphů?

A1: Ano, Aspose.Page podporuje PNG, JPEG, BMP, GIF, TIFF a další – celkem více než 25 formátů.

### Q2: Jak mohu dále přizpůsobit vzhled glyphů?

A2: Prozkoumejte vlastnosti jako `Glyph.Stroke`, `Glyph.FillOpacity` a `Glyph.Transform`, abyste upravili obrysy, průhlednost a rotaci.

### Q3: Je Aspose.Page vhodný pro zpracování velkých sad dokumentů?

A3: Rozhodně. Knihovna zpracovává XPS soubory se stovkami stránek pomocí streamování, udržuje využití paměti pod 100 MB i u 500‑stránkových dokumentů.

### Q4: Mohu použít různé styly na jednotlivé glyphy?

A4: Ano, každá instance `Glyph` má své vlastní vlastnosti `Fill`, `Stroke` a `Transform`, což umožňuje stylování na úrovni jednotlivých glyphů.

### Q5: Jaké jsou výhody používání Aspose.Page oproti jiným XPS nástrojům?

A5: Aspose.Page podporuje více než 25 formátů obrázků, zpracovává soubory až do 500 MB bez načítání celé paměti a poskytuje 100 % .NET‑native API – eliminuje potřebu COM interop nebo externích nástrojů.

---

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvoření XPS dokumentu – Aspose.Page pro .NET](/page/net/document-creation/)
- [Přidání obrázku do XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/image-management/add-image-to-xps-document/)
- [Přidání klonu glyphu a změna barvy pomocí Aspose.Page pro .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}