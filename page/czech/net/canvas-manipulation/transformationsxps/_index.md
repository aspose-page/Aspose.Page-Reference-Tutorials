---
date: 2026-06-25
description: Naučte se, jak snadno transformovat XPS dokumenty – definitní průvodce,
  jak transformovat XPS pomocí Aspose.Page pro .NET, s kroky bez kódu a praktickými
  tipy.
keywords:
- how to transform xps
- convert images to xps
- Aspose.Page transformations
linktitle: Transformace XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  headline: How to Transform XPS with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  name: How to Transform XPS with Aspose.Page for .NET
  steps:
  - name: Create a New XPS Document
    text: '`XpsDocument` is the Aspose.Page object that represents an XPS file in
      memory. *Explanation*: We start by defining the folder that holds our source
      and output files, then instantiate an empty `XpsDocument`. This object will
      be the canvas for all subsequent transformations.'
  - name: Create a Main Canvas
    text: '`Canvas` is the drawing surface that groups shapes, text, and other graphical
      elements. *Why this matters*: The main canvas acts as a container for all other
      canvases. By applying a small offset we ensure the content isn’t clipped at
      the page edge.'
  - name: Create a Rectangle Path Geometry
    text: '`PathGeometry` defines vector shapes using XPS path syntax (M = move, L
      = line, Z = close). *Tip*: The path string follows the standard XPS path syntax.
      Adjust the coordinates to change rectangle size.'
  - name: Add a Fill for Rectangles
    text: '`SolidColorBrush` creates a solid‑color fill that can be reused across
      multiple shapes. *Pro tip*: Use `CreateColor` with RGB values to match your
      brand palette.'
  - name: Add a New Canvas Without Transformations
    text: '`Canvas` without a transform serves as a baseline element for comparison.
      Here we simply place a rectangle on the page with no extra transformation—useful
      as a baseline element.'
  - name: Add a New Canvas with Translate Transformation
    text: '`TranslateTransform` moves objects along the X and Y axes. *What’s happening?*
      The first matrix moves the rectangle down by 200 units. The subsequent `Translate`
      call shifts it 500 units to the right, demonstrating how multiple translations
      can be chained.'
  - name: Add a New Canvas with Double Scale Transformation
    text: '`ScaleTransform` multiplies the width and height of the canvas by the supplied
      factors. *Why scale?* Scaling by 2 doubles the rectangle’s width and height,
      letting you create larger graphics without redefining the geometry.'
  - name: Add a New Canvas with Rotation Around a Point Transformation
    text: '`RotateAroundTransform` pivots the canvas around a custom point (here (100,
      50)). *Key insight*: `RotateAround` pivots the canvas around a custom point,
      giving you fine control over rotation anchors.'
  - name: Save Resultant XPS Document
    text: '`Save` persists the in‑memory document to disk in XPS format. After all
      transformations are applied, the document is persisted to `output1.xps`. Open
      the file in any XPS viewer to see the stacked rectangles with their respective
      translations, scaling, and rotation.'
  type: HowTo
- questions:
  - answer: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider,
      and any IDE that supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Is Aspose.Page for .NET compatible with all .NET development environments?
  - answer: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
    question: Where can I find additional examples and detailed API docs?
  - answer: 'Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).'
    question: Can I try Aspose.Page before buying a license?
  - answer: 'Request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for testing?
  - answer: 'Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).'
    question: Where do I purchase a full license?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Jak transformovat XPS pomocí Aspose.Page pro .NET
url: /cs/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak transformovat XPS pomocí Aspose.Page pro .NET

## Úvod

V tomto komplexním průvodci se naučíte **jak transformovat XPS** dokumenty pomocí Aspose.Page pro .NET. Ať už potřebujete posunout, změnit měřítko, otočit nebo zkombinovat více grafiky na jedné stránce, knihovna vám poskytuje řízení založené na maticích, aniž byste museli zasahovat do surového XML. Provedeme vás každým krokem, vysvětlíme, proč je každá transformace důležitá, a podělíme se o praktické tipy, které můžete rovnou použít v produkčním kódu.

## Rychlé odpovědi
- **Co můžete dosáhnout?** Vytvářejte, posouvejte, měřte a otáčejte prvky XPS plátna programově.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (nejnovější verze).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Podporované platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Čas implementace?** Přibližně 10‑15 minut pro základní transformace ukázané níže.

## Co je „jak transformovat xps“?
Fráze *jak transformovat xps* popisuje programatickou změnu rozvržení, velikosti a orientace prvků uvnitř XPS (XML Paper Specification) dokumentu. Pomocí Aspose.Page aplikujete transformace založené na maticích na plátna, což vám poskytuje pixelově přesnou kontrolu nad umístěním, měřítkem a rotací bez ruční úpravy XPS značkování.

## Proč používat Aspose.Page pro XPS transformace?
Načtěte svůj XPS soubor, aplikujte sérii transformací a uložte – vše ve dvou řádcích kódu. Aspose.Page podporuje **50+ vstupních a výstupních formátů**, dokáže zpracovat **200‑stránkové XPS soubory za méně než 2 sekundy** a nevyžaduje **žádné externí závislosti**. To z něj činí ideální řešení pro generování faktur, reportů nebo jakékoli tisknutelné grafiky za běhu.

## Požadavky

Než začneme, ujistěte se, že máte:

- **Aspose.Page for .NET Library** – stáhněte si ji z oficiální dokumentace: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Vývojové prostředí** – Visual Studio, Visual Studio Code, Rider nebo jakékoli IDE cílící na .NET.  
- **Adresář dokumentů** – složka ve vašem počítači, kde budete číst/zapisovat XPS soubory. Nahraďte zástupný znak v kódu skutečnou cestou.

Nyní, když máme vše připravené, pojďme se ponořit do kódu.

## Importovat jmenné prostory

The following namespaces expose the core Aspose.Page types you’ll work with:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Jak transformovat XPS pomocí Aspose.Page?

Načtěte svůj zdrojový XPS (nebo začněte s novým dokumentem) a poté aplikujte sekvenci maticových transformací – posunutí, měřítko a rotaci – přímo na objekty plátna. Každá transformace je aplikována v pořadí, ve kterém ji voláte, což vám umožní vytvořit složité rozvržení pomocí několika volání metod.

## Jak transformovat XPS – Průvodce krok za krokem

V této sekci projdeme kompletním příkladem, který vytvoří XPS soubor, přidá několik pláten a aplikuje sérii transformací jako posunutí, měřítko a rotaci. Každý krok obsahuje stručný úryvek kódu (reprezentovaný zástupnými znaky) a vysvětluje, proč je operace prováděna, abyste ji mohli snadno zopakovat.

### Krok 1: Vytvořit nový XPS dokument

`XpsDocument` je objekt Aspose.Page, který představuje XPS soubor v paměti.  
```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Vysvětlení*: Začínáme definováním složky, která obsahuje naše vstupní a výstupní soubory, a poté vytvoříme prázdný `XpsDocument`. Tento objekt bude plátnem pro všechny následné transformace.

### Krok 2: Vytvořit hlavní plátno

`Canvas` je kreslicí plocha, která seskupuje tvary, text a další grafické prvky.  
```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Proč je to důležité*: Hlavní plátno funguje jako kontejner pro všechna ostatní plátna. Aplikací malého posunu zajistíme, že obsah nebude oříznut na okraji stránky.

### Krok 3: Vytvořit geometrii cesty obdélníku

`PathGeometry` definuje vektorové tvary pomocí XPS syntaxe cesty (M = move, L = line, Z = close).  
```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: Řetězec cesty následuje standardní XPS syntaxi cesty. Upravením souřadnic změníte velikost obdélníku.

### Krok 4: Přidat výplň pro obdélníky

`SolidColorBrush` vytváří výplň jedné barvy, kterou lze znovu použít u více tvarů.  
```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Použijte `CreateColor` s RGB hodnotami, aby odpovídaly vaší firemní paletě.

### Krok 5: Přidat nové plátno bez transformací

`Canvas` bez transformace slouží jako základní prvek pro srovnání.  
```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Zde jednoduše umístíme obdélník na stránku bez další transformace – užitečné jako základní prvek.

### Krok 6: Přidat nové plátno s transformací posunutí

`TranslateTransform` posouvá objekty podél os X a Y.  
```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Co se děje?* První matice posune obdélník dolů o 200 jednotek. Následující volání `Translate` jej posune o 500 jednotek doprava, což ukazuje, jak lze řetězit více posunů.

### Krok 7: Přidat nové plátno s dvojitou transformací měřítka

`ScaleTransform` násobí šířku a výšku plátna zadanými faktory.  
```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Proč měřítko?* Měřítko 2‑násobně zdvojnásobí šířku a výšku obdélníku, což vám umožní vytvořit větší grafiku bez nutnosti redefinovat geometrii.

### Krok 8: Přidat nové plátno s rotací kolem bodu

`RotateAroundTransform` otáčí plátno kolem vlastního bodu (zde (100, 50)).  
```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Klíčový poznatek*: `RotateAround` otáčí plátno kolem vlastního bodu, což vám poskytuje jemnou kontrolu nad kotevními body rotace.

### Krok 9: Uložit výsledný XPS dokument

`Save` uloží dokument z paměti na disk ve formátu XPS.  
```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Po aplikaci všech transformací je dokument uložen jako `output1.xps`. Otevřete soubor v libovolném XPS prohlížeči a uvidíte naskládané obdélníky s jejich příslušnými posuny, měřítky a rotacemi.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Prázdný výstupní soubor | `dataDir` ukazuje na neexistující složku | Zajistěte, aby složka existovala, nebo použijte absolutní cestu |
| Obdélníky nejsou umístěny podle očekávání | Nesprávné hodnoty matice | Zkontrolujte pořadí volání `Translate`, `Scale` a `RotateAround` |
| Barvy jsou špatné | RGB hodnoty mimo rozsah 0‑255 | Použijte platné hodnoty bajtů pro každý kanál |

## Často kladené otázky

**Q: Je Aspose.Page pro .NET kompatibilní se všemi .NET vývojovými prostředími?**  
A: Ano, funguje bez problémů s Visual Studio, Visual Studio Code, Rider a jakýmkoli IDE, které podporuje .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

**Q: Kde mohu najít další příklady a podrobnou dokumentaci API?**  
A: Navštivte oficiální dokumentaci na [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: Můžu si Aspose.Page vyzkoušet před zakoupením licence?**  
A: Rozhodně. Bezplatná zkušební verze je k dispozici zde: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro testování?**  
A: Požádejte o ni na stránce dočasné licence: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Kde si mohu zakoupit plnou licenci?**  
A: Zakupte přímo v obchodě Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-06-25  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit XPS dokument pomocí Aspose.Page pro .NET](/page/net/document-creation/create-xps-document/)
- [Jak oříznout XPS pomocí Aspose.Page pro .NET](/page/net/canvas-manipulation/clippingxps/)
- [Převést XPS na PDF pomocí Aspose.Page pro .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}