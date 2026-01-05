---
date: 2026-01-05
description: Naučte se, jak přidat ořezovou cestu v PostScriptu pomocí Aspose.Page
  pro .NET – krok za krokem průvodce s technikami nastavení štětce a kreslení čárkovaného
  obdélníku.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Přidat ořezovou cestu do PS pomocí Aspose.Page pro .NET
url: /cs/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání ořezové cesty do PS pomocí Aspose.Page pro .NET

## Úvod

V tomto komplexním tutoriálu se dozvíte, jak **přidat ořezovou cestu** do dokumentu PostScript (PS) pomocí Aspose.Page pro .NET. Provedeme vás každým krokem, ukážeme, jak **nastavit malířskou štětec**, a demonstrujeme, jak **nakreslit čárkovaný obdélník** kolem ořezaného obsahu. Na konci budete mít plně funkční PS soubor, který ilustruje ořez podle tvaru, čímž vaše grafika bude dynamičtější a profesionálnější.

## Rychlé odpovědi
- **Co dělá „přidat ořezovou cestu“?** Omezuje kreslicí operace na definovaný tvar, skrývá vše mimo tento tvar.  
- **Která knihovna v .NET zpracovává ořez?** Aspose.Page pro .NET poskytuje bohaté API pro manipulaci s PS/EPS.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu změnit barvu štětce?** Ano, použijte `SetPaint` s libovolným `SolidBrush` nebo gradientem, který preferujete.  
- **Je možné nakreslit čárkovaný obdélník?** Rozhodně – vytvořte `Pen` s `DashStyle.Dash` a použijte `Draw`.  

## Co je ořezová cesta v PostScriptu?
Ořezová cesta určuje viditelnou oblast následných kreslicích příkazů. Vše, co je nakresleno mimo tuto cestu, je ignorováno, což vám umožní vytvářet složité maskované grafiky bez úpravy původního obsahu.

## Proč použít Aspose.Page pro ořez?
- **Žádné externí závislosti** – čistá .NET knihovna.  
- **Plná kontrola** nad stavem grafiky (save/restore, translate, rotate).  
- **Bohaté kreslicí primitivy** jako `SetPaint`, `Clip` a `Draw` s přizpůsobitelnými pery a štětci.  

## Předpoklady

- Základní znalost programování v C#.  
- Knihovna Aspose.Page pro .NET nainstalována – můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).  
- Visual Studio nebo jakékoli preferované .NET IDE.  

## Import jmenných prostorů

Nejprve importujte jmenné prostory potřebné pro manipulaci s grafikou:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní rozdělíme příklad na přehledné, číslované kroky.

### Krok 1: Nastavení adresáře dokumentu

Definujte složku, kde budou umístěny vaše vstupní a výstupní soubory.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Krok 2: Vytvoření výstupního proudu pro PostScript dokument

Vytvořte zapisovatelný proud, který bude obsahovat vygenerovaný PS soubor.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Krok 3: Vytvoření možností uložení

Instancujte `PsSaveOptions` s výchozími nastaveními. V případě potřeby je můžete později přizpůsobit.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: Vytvoření nového 1‑stránkového PS dokumentu

Inicializujte objekt `PsDocument`, který představuje váš PS soubor.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: Vytvoření grafické cesty z obdélníku

Použijeme obdélník jako základní tvar, který bude později oříznut.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Krok 6: Ořez podle tvaru

Zde **přidáváme ořezovou cestu** pomocí kruhu, **nastavujeme malířský štětec** na modrou a vyplňujeme obdélník v ořezané oblasti.

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

### Krok 7: Posunutí vyšší úrovně grafického stavu a nakreslení čárkovaného obdélníku

Po obnovení předchozího stavu znovu posuneme grafický kurzor, **nakreslíme čárkovaný obdélník** a použijeme modrý tah.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Krok 8: Uzavření a uložení dokumentu

Dokončete stránku a zapište PS soubor na disk.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Nyní jste úspěšně **přidali ořezovou cestu**, nastavili vlastní malířský štětec a nakreslili čárkovaný obdélník kolem vaší grafiky pomocí Aspose.Page pro .NET.

## Časté problémy a řešení

- **Ořez není viditelný:** Ujistěte se, že voláte `WriteGraphicsSave()` před posunutím a `WriteGraphicsRestore()` po vyplnění.  
- **Nesprávné barvy:** Ověřte, že `SetPaint` je voláno po `Clip` a před `Fill`.  
- **Čárkované čáry se zobrazují jako plné:** Ujistěte se, že `Pen` má `DashStyle` nastavený na `DashStyle.Dash` před `SetStroke`.  

## Často kladené otázky

### Q1: Mohu použít Aspose.Page pro .NET s jinými programovacími jazyky?
A: Aspose.Page je primárně navržena pro .NET aplikace. Nicméně Aspose poskytuje podobné knihovny pro jiné programovací jazyky.

### Q2: Kde najdu další příklady a dokumentaci pro Aspose.Page pro .NET?
A: Další příklady a podrobnou dokumentaci můžete prozkoumat na [Aspose.Page documentation](https://reference.aspose.com/page/net/).

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Page pro .NET [zde](https://releases.aspose.com/).

### Q4: Jak získat dočasnou licenci pro Aspose.Page pro .NET?
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Kde získám podporu nebo mohu diskutovat o dotazech týkajících se Aspose.Page?
A: Navštivte [Aspose.Page forums](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuze.

---

**Poslední aktualizace:** 2026-01-05  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}