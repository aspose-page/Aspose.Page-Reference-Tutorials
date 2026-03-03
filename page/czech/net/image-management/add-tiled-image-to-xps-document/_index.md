---
date: 2026-03-03
description: Naučte se, jak používat Aspose.Page pro .NET k dlaždicování obrázků v
  dokumentech XPS. Tento krok‑za‑krokem průvodce ukazuje, jak efektivně dlaždicovat
  obrázek a zvýšit vizuální přitažlivost.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Jak použít Aspose.Page k přidání dlaždicového obrázku do XPS dokumentu
url: /cs/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít Aspose.Page k přidání dlaždicového obrázku do XPS dokumentu

## Úvod

Pokud se ptáte, **jak použít Aspose**, abyste svým XPS souborům dodali bohatší vizuální styl, jste na správném místě. V tomto tutoriálu projdeme přesně kroky potřebné k **dlaždicování obrázku** uvnitř XPS dokumentu pomocí Aspose.Page pro .NET. Na konci budete mít znovupoužitelný úryvek, který můžete vložit do libovolného .NET projektu a vytvořit tak grafiku s dlaždicovým obrázkem za běhu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for .NET  
- **Která metoda vytváří dlaždicový štětec?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Mohu řídit průhlednost?** Ano – nastavte `path.Fill.Opacity` (např. 0.5f)  
- **Potřebuji licenci pro testování?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6!

## Co je Aspose.Page a proč dlaždicovat obrázky?

Aspose.Page je výkonné API, které umožňuje vývojářům generovat, upravovat a renderovat XPS, PDF a další formáty založené na stránkách, aniž by bylo nutné spoléhat na Microsoft Office. Dlaždicování obrázku – opakování bitmapy přes tvar – vám pomůže vyplnit velké oblasti vzory, vodoznaky nebo texturami pozadí při zachování malé velikosti souboru.

## Jak použít Aspose.Page k dlaždicování obrázků v XPS dokumentech

Níže najdete kompletní, připravený příklad. Každý krok je vysvětlen srozumitelně před odpovídajícím blokem kódu, takže můžete vidět **proč** je každý řádek důležitý.

### Požadavky

- **Aspose.Page pro .NET** – stáhněte a odkažte knihovnu z oficiální stránky [here](https://reference.aspose.com/page/net/).  
- **Vývojové prostředí** – Visual Studio (libovolná edice) nebo jiné .NET IDE, které preferujete.

### Importujte jmenné prostory

Nejprve přidejte požadované jmenné prostory do rozsahu, aby kompilátor věděl, kde najít třídy XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Krok 1: Definujte adresář dokumentu

Určete, kde bude uložen vygenerovaný XPS soubor a zdrojový obrázek. Nahraďte zástupný znak skutečnou složkou na vašem počítači.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte nový XPS dokument

Vytvořte prázdný XPS dokument, který bude obsahovat dlaždicovou grafiku.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Krok 3: Přidejte dlaždicový obrázek

Zde vytvoříme obdélníkovou cestu, vyplníme ji `ImageBrush` a nastavíme štětec do režimu dlaždicování. Vlastnost `TileMode` říká enginu, aby opakoval obrázek jak horizontálně, tak vertikálně. Podle potřeby upravte souřadnice obdélníku nebo zdrojový obrázek pro váš scénář.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Krok 4: Uložte výsledný XPS dokument

Nakonec zapíšete dokument na disk. Výstupní soubor lze otevřít v libovolném XPS prohlížeči nebo dále zpracovat pomocí Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Časté problémy a tipy

- **Chyby cesty** – Ujistěte se, že `dataDir` končí lomítkem, nebo použijte `Path.Combine`, aby se předešlo problémům s chybějícím oddělovačem.  
- **Nesoulad velikosti obrázku** – Zdrojový obrázek by měl být dostatečně velký pro oblast dlaždicování; jinak se vzor může zdát roztažený.  
- **Průhlednost není viditelná** – Některé prohlížeče ignorují průhlednost v XPS; otestujte s prohlížečem, který plně podporuje renderování XPS (např. XPS Viewer ve Windows).

## Často kladené otázky

### Q1: Je Aspose.Page kompatibilní se všemi .NET vývojovými prostředími?
A: Ano, Aspose.Page funguje s Visual Studio, Rider, VS Code a jakýmkoli IDE, které podporuje .NET.

### Q2: Mohu upravit průhlednost dlaždicového obrázku?
A: Rozhodně. Příklad nastavuje `path.Fill.Opacity = 0.5f;` – můžete změnit hodnotu float mezi 0 (průhledný) a 1 (neprůhledný).

### Q3: Existují v Aspose.Page pro .NET i jiné režimy dlaždicování?
A: Ano. Kromě `XpsTileMode.Tile` můžete použít `FlipX`, `FlipY` a `FlipXY` k vytvoření zrcadlových vzorů.

### Q4: Jak zacházet s dočasnými licencemi pro Aspose.Page?
A: Odkazujte se na stránku [temporary license](https://purchase.aspose.com/temporary-license/) na webu Aspose pro podrobnosti o získání a použití zkušební licence.

### Q5: Kde mohu získat pomoc nebo se spojit s komunitou Aspose.Page?
A: Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39), kde můžete klást otázky, sdílet úryvky a učit se od ostatních vývojářů.

### Q6: Mohu tento přístup použít k vytvoření efektu vodoznaku?
A: Ano. Snížením průhlednosti a výběrem poloprůhledného obrázku funguje dlaždicový štětec perfektně jako opakující se vodoznak.

## Závěr

Nyní víte **jak použít Aspose** k přidání dlaždicového obrázku do XPS dokumentu, řízení jeho průhlednosti a uložení výsledku pro další použití. Tato technika je ideální pro vzory pozadí, vodoznaky nebo jakoukoli situaci, kde opakující se grafika přidává vizuální zajímavost bez zvětšování velikosti souboru. Nebojte se experimentovat s různými tvary, obrázky a režimy dlaždicování, aby vyhovovaly potřebám vašeho projektu.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}