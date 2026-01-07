---
date: 2026-01-07
description: Naučte se, jak vytvořit XPS dokument v .NET pomocí Aspose.Page. Tento
  průvodce ukazuje přidávání glyfů vyplněných obrázky a cizích obrázků pro bohatší
  vizuální podobu dokumentu.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Vytvoření XPS dokumentu v .NET s Aspose.Page – Glyf vyplněný obrázkem a cizí
  obrázek
url: /cs/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS document .NET s Aspose.Page – Glyph vyplněný obrázkem a cizí obrázek

## Úvod

Pokud potřebujete **create XPS document .NET** aplikace, které vypadají uhlazeně a profesionálně, Aspose.Page vám poskytuje nástroje pro vložení obrázků přímo do glyphů a opětovné použití grafických zdrojů napříč dokumenty. V tomto tutoriálu vás provedeme tvorbou dvou XPS souborů, vyplněním glyphů pomocí image brush a následným opětovným použitím tohoto brush v druhém dokumentu. Na konci pochopíte, proč tento přístup šetří paměť, zjednodušuje stylování a otevírá kreativní možnosti pro zprávy, faktury nebo jakýkoli tisknutelný obsah.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidávání glyphů vyplněných obrázkem a jejich opětovné použití napříč XPS dokumenty s Aspose.Page pro .NET.  
- **Jaké primární klíčové slovo je cílem?** `create xps document .net`.  
- **Požadavky?** .NET vývojové prostředí, Aspose.Page pro .NET a složka pro vaše XPS soubory.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro funkční prototyp.  
- **Mohu použít jiné formáty obrázků?** Ano – jakýkoli formát podporovaný .NET `System.Drawing.Image`.

## Požadavky

Než se ponoříte do kódu, ujistěte se, že máte připraveno následující:

- **Aspose.Page for .NET** – stáhněte nejnovější knihovnu z [zde](https://releases.aspose.com/page/net/).  
- **Vývojové prostředí** – Visual Studio 2022 (nebo jakékoli IDE podporující .NET 6+).  
- **Adresář dokumentů** – vytvořte složku ve vašem počítači, která bude obsahovat vstupní obrázky a generované XPS soubory; v úryvcích na ni budeme odkazovat jako **Your Document Directory**.

## Importování jmenných prostorů

Začněte načtením jmenných prostorů potřebných pro práci s XPS objekty a nástroji pro kreslení.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Postupný průvodce

### Krok 1: Vytvořte první XPS dokument

Začínáme vytvořením prázdného XPS dokumentu, který bude hostovat glyph vyplněný obrázkem.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Krok 2: Přidejte glyphy do prvního dokumentu

Dále přidejte glyph (znak textu), který později vyplníme image brush.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Krok 3: Vyplňte glyphy pomocí Image Brush

Zde vytvoříme `ImageBrush` z TIFF souboru umístěného v našem datovém adresáři a aplikujeme jej na glyph. Brush je nastavený na režim dlaždicování, takže se obrázek opakuje, pokud oblast glyphu přesahuje velikost obrázku.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Krok 4: Vytvořte druhý XPS dokument

Nyní vytvoříme druhý XPS dokument, který bude opětovně používat styl glyphu a image brush z prvního.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Krok 5: Přidejte glyphy s fontem z prvního dokumentu

Přidáme glyph do druhého dokumentu, opětovně použijeme přesný objekt fontu z prvního dokumentu. To zajišťuje vizuální konzistenci napříč oběma soubory.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Krok 6: Vytvořte Image Brush z výplně prvního dokumentu

Místo opětovného načtení obrázku klonujeme brush z `glyphs1` a přiřadíme jej k `glyphs2`. To ukazuje, jak můžete **create XPS document .NET** workflow, které efektivně sdílejí zdroje.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Krok 7: Uložte dokumenty

Nakonec uložíme oba XPS soubory na disk. Nyní je můžete otevřít v libovolném XPS prohlížeči a vidět efekt glyphu vyplněného obrázkem.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Proč používat glyphy vyplněné obrázkem při tvorbě XPS document .NET?

- **Vizální dopad** – Přeměňte obyčejný text na graficky bohaté prvky bez rasterizace celé stránky.  
- **Opětovné použití zdrojů** – Sdílejte brush a fonty napříč více dokumenty, čímž snižujete paměťovou náročnost.  
- **Flexibilita** – Dlaždicujte, roztáhněte nebo otočte image brush pro vytvoření vlastních vzorů nebo značky.

## Časté problémy a tipy

- **Chyby cesty k souboru** – Ujistěte se, že `dataDir` končí oddělovačem cesty (`\` nebo `/`) vhodným pro váš OS.  
- **Nepodporované formáty obrázků** – Aspose.Page nejlépe funguje s TIFF, PNG a JPEG. Před použitím převádějte jiné formáty.  
- **TileMode se nepoužije** – Ověřte, že před nastavením `TileMode` provedete přetypování na `XpsImageBrush`; jinak je vlastnost ignorována.

## Často kladené otázky

### Q1: Můžu použít různé formáty obrázků pro vyplňování glyphů?

**A:** Ano, Aspose.Page podporuje TIFF, PNG, JPEG, BMP a GIF. Stačí zadat správnou příponu souboru v volání `CreateImageBrush`.

### Q2: Jak mohu dále přizpůsobit vzhled glyphů?

**A:** Prozkoumejte další vlastnosti `XpsGlyphs`, jako jsou `Opacity`, `RenderTransform` a `Stroke`, pro jemné doladění vykreslování.

### Q3: Je Aspose.Page vhodný pro zpracování velkých sad dokumentů?

**A:** Rozhodně. Knihovna je optimalizována pro vysoce výkonné scénáře a dokáže zpracovat tisíce XPS souborů ve dávkových úlohách.

### Q4: Můžu aplikovat různé styly na jednotlivé glyphy?

**A:** Ano. Každá instance `XpsGlyphs` může mít vlastní výplň, obrys a transformaci, což vám poskytuje detailní kontrolu.

### Q5: Jaké jsou výhody používání Aspose.Page oproti jiným nástrojům pro zpracování dokumentů?

**A:** Aspose.Page nabízí kompletní, bezlicenční API pro tvorbu, manipulaci a konverzi XPS, s rozsáhlou dokumentací a 24/7 podporou.

---

**Poslední aktualizace:** 2026-01-07  
**Testováno s:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}