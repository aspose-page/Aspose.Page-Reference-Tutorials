---
date: 2026-09-09
description: Naučte se, jak vytvořit radiální gradient v Java PostScript pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce vám ukáže, jak přidat color stops gradient, nastavit
  radii a rychle vygenerovat PS file.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Mistrovství radial gradients v Java
og_description: Naučte se, jak vytvořit radiální gradient v Java PostScript pomocí
  Aspose.Page. Tento průvodce vysvětluje, jak přidat color stops gradient, nastavit
  radii a během několika minut vygenerovat PS file.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Jak vytvořit radiální gradient v Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Jak vytvořit radiální gradient v Java PostScript
url: /cs/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit radiální gradient v Java PostScript pomocí Aspose.Page

## Úvod
Pokud potřebujete **vytvořit radiální gradient** uvnitř souboru PostScript, jste na správném místě. V tomto tutoriálu projdeme každý krok potřebný k vygenerování dokumentu PostScript, který obsahuje plynulý radiální gradient, pomocí **Aspose.Page for Java**. Na konci pochopíte API, uvidíte kompletní spustitelný příklad a budete vědět, jak upravit barvy, pozice a poloměry pro jakýkoli designový scénář.

## Rychlé odpovědi
- **Která knihovna vytváří radiální gradienty v PostScriptu?** Aspose.Page for Java.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší.  
- **Mohu změnit tvar gradientu?** Ano – upravte poloměr a středový bod v konstruktoru `RadialGradientPaint`.

## Jak vytvořit radiální gradient v Javě
Načtěte svůj Java projekt, importujte požadované třídy a postupujte podle níže uvedeného krok‑za‑krokem průvodce. Hlavní odpovědí je, že vytvoříte instanci `RadialGradientPaint` s vašimi barevnými zastávkami a poté ji použijete na obdélník nakreslený na `PsDocument`. Tento dvou‑objektový přístup zpracuje všechny nízkoúrovňové příkazy PostScript za vás.

## Co je radiální gradient?
`RadialGradientPaint` je třída Java AWT, která definuje kruhový přechod barev od centrálního bodu směrem ven. Vytváří plynulé spojení několika barevných zastávek, což je ideální pro reflektory, jemná pozadí nebo jakýkoli efekt, kde barvy vyzařují z ohniskového bodu.

## Proč použít Aspose.Page pro radiální gradienty?
Aspose.Page vám poskytuje úplnou programovou kontrolu nad výstupem PostScriptu a zároveň se stará o těžkou práci s nízkoúrovňovou syntaxí PS. Podporuje **50+ vstupních a výstupních formátů**, dokáže renderovat dokumenty o stovkách stránek bez načítání celého souboru do paměti a běží na jakémkoli operačním systému, který podporuje Java 8+. Tato kvantifikovaná schopnost z něj činí spolehlivou volbu pro generování grafiky podnikové úrovně.

## Požadavky
- **Java Development Kit (JDK) 8+** – ověřte pomocí `java -version`.  
- **Aspose.Page for Java** – stáhněte nejnovější JAR z oficiální [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE dle vašeho výběru** – Eclipse, IntelliJ IDEA nebo VS Code s rozšířeními pro Javu.  
- **Zapisovatelná složka** – kam bude uložen vygenerovaný soubor `.ps`.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat. Balíček `java.awt` poskytuje objekty pro gradientní barvy, zatímco `com.aspose.eps` obsahuje třídy pro práci s dokumenty PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Průvodce krok za krokem

### Krok 1: vytvořit obdélník a otevřít PS dokument
`PsDocument` je třída Aspose.Page, která představuje dokument PostScript a poskytuje metody pro kreslení tvarů, textu a obrázků. Začneme vytvořením výstupního proudu, nastavením velikosti stránky (A4 jako výchozí) a definováním obdélníku, který bude hostit gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Tip:** Upravte souřadnice obdélníku (`200, 100, 200, 200`), abyste gradient umístili kamkoli na stránce.

### Krok 2: definovat barvy a frakce
Radiální gradient je vytvořen z *barevných zastávek* (barvy) a *frakcí* (relativní pozice těchto zastávek). Zde vytvoříme pole šesti barev a jejich odpovídajících frakcí.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Proč je to důležité:** Úpravou `fractions` řídíte rychlost přechodu barev, což umožňuje jemné nebo dramatické efekty.

### Krok 3: vytvořit radiální gradient paint
`RadialGradientPaint` je hlavní třída, která popisuje radiální barevný gradient, včetně středového bodu, poloměru, ohniskového bodu, frakcí, barev, metody cyklu a barevného prostoru. Nyní vytvoříme objekt `RadialGradientPaint` pomocí výše definovaných polí.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Poznámka:** `transform` může být `null`, pokud nepotřebujete další škálování nebo rotaci. Klidně experimentujte s `AffineTransform` pro zkosené gradienty.

### Krok 4: nastavit paint a vyplnit obdélník
Jakmile je paint připraven, řekneme `PsDocument`, aby jej použil, a poté vyplníme obdélník, který jsme dříve definovali.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

V tomto okamžiku stránka PostScript obsahuje obdélník hladce vyplněný radiálním gradientem, který jsme nakonfigurovali.

### Krok 5: zavřít a uložit dokument
Nakonec zavřete aktuální stránku a zapíšete soubor na disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Otevřete `RadialGradient1_outPS.ps` v libovolném prohlížeči PostScript (např. Ghostscript) a uvidíte gradient vykreslený přesně tak, jak byl definován.

## Časté problémy a řešení
| Problém | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Gradient se zobrazuje jako jednobarevná plocha | pole `fractions` nezačíná na `0.0f` nebo nekončí na `1.0f` | Ujistěte se, že první frakce je `0.0f` a poslední je `1.0f`. |
| Barvy vypadají vybledlé | Použití nesprávného `ColorSpaceType` | Přepněte na `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` pro živější výstup. |
| Nebyl vygenerován žádný výstupní soubor | cesta `FileOutputStream` je neplatná nebo není zapisovatelná | Ověřte, že `dataDir` existuje a aplikace má oprávnění k zápisu. |

## Často kladené otázky

**Q: Mohu používat Aspose.Page pro Java v komerčních projektech?**  
A: Ano. Pro produkční použití je vyžadována komerční licence. Můžete ji zakoupit na [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Kde najdu oficiální referenci API?**  
A: Kompletní dokumentace je k dispozici na [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Je k dispozici bezplatná zkušební verze pro testování?**  
A: Rozhodně. Stáhněte si zkušební verzi ze [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro hodnocení?**  
A: Dočasnou licenci lze požádat na [temporary license request page](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu získat podporu komunity?**  
A: Připojte se k fóru komunity Aspose.Page na [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Závěr
Nyní víte **jak vytvořit radiální gradient** v Java PostScript dokumentu pomocí Aspose.Page. Úpravou velikosti obdélníku, barevných zastávek a poloměru gradientu můžete vytvořit nespočet vizuálních efektů – od jemných výplní pozadí po výrazné grafiky se světelnými efekty. Klidně experimentujte s různými hodnotami `AffineTransform` pro otáčení nebo zkosení gradientu a kombinujte tuto techniku s textem a obrázky pro bohatší výstupy PDF nebo EPS.

---

**Poslední aktualizace:** 2026-09-09  
**Testováno s:** Aspose.Page for Java latest (as of writing)  
**Autor:** Aspose

## Související tutoriály

- [Vyplnit tvar gradientem: Java PostScript Radiální příklad](/page/java/postscript-gradient-addition/radial2/)
- [Vytvořit PostScript gradient v Javě – Přidat vertikální gradient](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Transparentnost tutoriál – Přidat transparentnost v Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}