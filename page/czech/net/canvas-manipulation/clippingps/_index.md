---
date: 2026-06-25
description: Naučte se, jak přidat ořezovou cestu v PostScriptu pomocí Aspose.Page
  pro .NET – podrobný návod s technikami štětce a čárkovaného obdélníku.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: Ořez PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Jak přidat ořezovou cestu do PostScriptu pomocí Aspose.Page pro .NET
url: /cs/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat ořezovou cestu do PostScriptu pomocí Aspose.Page pro .NET

## Úvod

V tomto komplexním tutoriálu se naučíte **jak přidat ořezovou cestu** do dokumentu PostScript (PS) pomocí Aspose.Page pro .NET. Provedeme vás každým krokem, ukážeme vám, jak **nastavit štětec**, a demonstrujeme, jak **nakreslit přerušovaný obdélník** kolem ořezaného obsahu. Na konci budete mít plně funkční PS soubor, který ilustruje ořezávání tvarem a dodá vašim grafikám dynamičtější a profesionálnější vzhled.

## Rychlé odpovědi
- **Co dělá „přidat ořezovou cestu“?** Omezuje kreslicí operace na definovaný tvar a skrývá vše, co je mimo tento tvar.  
- **Která knihovna v .NET provádí ořezávání?** Aspose.Page pro .NET poskytuje bohaté API pro manipulaci s PS/EPS.  
- **Potřebuji licenci?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Mohu změnit barvu štětce?** Ano, použijte `SetPaint` s libovolným `SolidBrush` nebo gradientem podle potřeby.  
- **Je možné nakreslit přerušovaný obdélník?** Rozhodně – vytvořte `Pen` s `DashStyle.Dash` a použijte `Draw`.  

## Co je ořezová cesta v PostScriptu?

Ořezová cesta určuje viditelnou oblast následných kreslicích příkazů a zahazuje vše, co je vykresleno mimo její hranice. Prakticky vám umožňuje maskovat grafiku tak, aby byl zobrazen pouze část uvnitř cesty, což je nezbytné pro tvorbu složitých kompozic bez trvalé změny původních objektů.

## Jak přidat ořezovou cestu do dokumentu PostScript pomocí Aspose.Page?

Načtěte `PsDocument`, definujte grafickou cestu (například kruh), použijte `Clip()` k omezení kreslicí oblasti, poté použijte `SetPaint` a `Fill` k vykreslení obsahu uvnitř ořezané oblasti. Po obnovení grafického stavu můžete kreslit další tvary – například přerušovaný obdélník – aniž byste ovlivnili ořezanou oblast. Tento postup provádí ořezávání pomocí několika stručných volání API.

`PsDocument` představuje objekt dokumentu PostScript.  
`GraphicsPath` je vektorový kontejner pro geometrické tvary.  
`Clip()` nastaví ořezovou oblast pro následné kreslení.  
`SetPaint` přiřadí štětec používaný k vyplňování tvarů.  
`Fill` vykreslí aktuální cestu pomocí aktuálního štětce.

## Proč použít Aspose.Page pro ořezávání?

Aspose.Page podporuje **více než 50 vstupních a výstupních formátů**, včetně PS, EPS, PDF, SVG a typů obrázků, a dokáže zpracovávat dokumenty o stovkách stránek, aniž by načítal celý soubor do paměti. Knihovna má **žádné externí závislosti**, běží na **.NET Framework 4.5+**, **.NET Core 3.1+** a **.NET 6+** a nabízí plnou kontrolu nad grafickým stavem (uložení/obnovení, posunutí, rotace). Tyto kvantifikovatelné výhody z ní činí spolehlivou volbu pro server‑side generování grafiky.

## Předpoklady

- Základní znalost programování v C#.  
- Knihovna Aspose.Page pro .NET nainstalována – můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).  
- Visual Studio nebo jakékoli preferované .NET IDE.  

## Importovat jmenné prostory

Následující jmenné prostory vám poskytují přístup k základním grafickým objektům a PS‑specifickým možnostem uložení.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní rozdělíme příklad na přehledné, číslované kroky.

### Krok 1: Nastavit adresář dokumentu

Definujte složku, kde budou umístěny vaše vstupní a výstupní soubory. To usnadní pozdější vyhledání vygenerovaného PS souboru.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvořit výstupní stream pro dokument PostScript

Vytvořte zapisovatelný stream, který bude obsahovat vygenerovaný PS soubor. Použití `FileStream` zajistí, že soubor bude zapisován přímo na disk.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Krok 3: Vytvořit možnosti uložení

`PsSaveOptions` je konfigurační objekt Aspose.Page pro výstup PS. Umožňuje vám řídit kompresi, verzi a další podrobnosti vykreslování.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: Vytvořit nový jednoprvkový PS dokument

`PsDocument` představuje objekt dokumentu PostScript. Instancujete jej s výstupním streamem a možnostmi uložení, které jste právě nakonfigurovali.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: Vytvořit grafickou cestu z obdélníku

`GraphicsPath` je vektorový kontejner pro geometrické tvary. Zde začínáme s jednoduchým obdélníkem, který bude později oříznut.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Krok 6: Ořezávání pomocí tvaru

Přidáme ořezovou cestu pomocí kruhu, nastavíme štětec na modrou barvu a vyplníme obdélník uvnitř ořezané oblasti. Tím demonstrujeme, jak ořez omezuje kreslení na vnitřek kruhu.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Krok 7: Posunout stav grafiky vyšší úrovně a nakreslit přerušovaný obdélník

Po obnovení předchozího grafického stavu posuneme kurzor, vytvoříme `Pen` s `DashStyle.Dash` a nakreslíme přerušovaný obdélník kolem ořezaného obsahu. Modrá čára zvýrazní hranici ořezu.

`Pen` definuje atributy tahu, jako je barva a styl čáry.  
`DashStyle.Dash` určuje vzor přerušované čáry.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Krok 8: Zavřít a uložit dokument

Dokončete stránku, vyprázdněte stream a uvolněte prostředky. PS soubor je nyní zapsán na disk a připraven k prohlížení v libovolném PostScript prohlížeči.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Úspěšně jste **přidali ořezovou cestu**, nastavili vlastní štětec a nakreslili přerušovaný obdélník kolem vaší grafiky pomocí Aspose.Page pro .NET.

## Časté problémy a řešení

- **Ořez není viditelný:** Ujistěte se, že voláte `WriteGraphicsSave()` před posunutím a `WriteGraphicsRestore()` po vyplnění.  
- **Nesprávné barvy:** Ověřte, že `SetPaint` je voláno po `Clip` a před `Fill`.  
- **Přerušované čáry se zobrazují jako plné:** Zkontrolujte, že `Pen` má nastavený `DashStyle` na `DashStyle.Dash` před `SetStroke`.  

## Často kladené otázky

### Q1: Můžu použít Aspose.Page pro .NET s jinými programovacími jazyky?
**A:** Aspose.Page je primárně navržen pro .NET aplikace, ale Aspose nabízí ekvivalentní knihovny pro Javu, C++ a další platformy.

### Q2: Kde najdu další příklady a dokumentaci pro Aspose.Page pro .NET?
**A:** Další příklady a podrobnou dokumentaci můžete prozkoumat na [dokumentaci Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Je k dispozici bezplatná zkušební verze Aspose.Page pro .NET?
**A:** Ano, bezplatnou zkušební verzi Aspose.Page pro .NET získáte [zde](https://releases.aspose.com/).

### Q4: Jak získat dočasnou licenci pro Aspose.Page pro .NET?
**A:** Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Kde mohu získat podporu nebo diskutovat o dotazech týkajících se Aspose.Page?
**A:** Navštivte [fóra Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

**Poslední aktualizace:** 2026-06-25  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit PostScript dokument pomocí Aspose.Page pro .NET](/page/net/document-creation/create-postscript-document/)
- [Uložit PostScript soubor s transformacemi Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [Vytvořit PostScript dokument .NET – Přidat obdélník s Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}