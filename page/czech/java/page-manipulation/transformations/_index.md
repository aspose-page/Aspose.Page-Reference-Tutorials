---
date: 2026-10-20
description: Zjistěte, jak škálovat obdélník pomocí Aspose.Page pro Java, jak posunout
  tvar a aplikovat afinní transformaci pro vytvoření PostScript dokumentů.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformace při manipulaci se stránkami v Java
og_description: Zjistěte, jak škálovat obdélník, posunout tvar a aplikovat afinní
  transformaci pomocí Aspose.Page pro Java pro efektivní generování PostScript souborů.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Jak škálovat obdélník pomocí Aspose.Page pro Java – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Jak škálovat obdélník pomocí Aspose.Page pro Java
url: /cs/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak škálovat obdélník pomocí Aspose.Page pro Java

## Úvod
V tomto průvodci se dozvíte, **jak škálovat obdélník** pomocí Aspose.Page pro Java, a také se naučíte, jak posunout (přeložit) pozice tvarů, otáčet grafiku a použít afinní transformace k vytvoření vysoce kvalitního výstupu PostScript. Tyto techniky vám umožní vytvářet sofistikovanou, zařízení‑nezávislou grafiku bez psaní nízkoúrovňového vykreslovacího kódu, což učiní vaše Java aplikace výkonnějšími a udržovatelnějšími.

## Rychlé odpovědi
`scale(sx, sy)` scales the graphics context by the given horizontal and vertical factors.  

- **Jak mohu v Javě se Aspose.Page škálovat obdélník?** Call the `scale(sx, sy)` method on the graphics context before drawing the rectangle.  
- **Mohu přesunout (přeložit) tvar, aniž by to ovlivnilo ostatní grafiku?** Yes—wrap the translation between `writeGraphicsSave()` and `writeGraphicsRestore()` calls.  
- **Která třída vytváří soubor PostScript?** Use `PsDocument` together with `PsSaveOptions`.  
- **Potřebuji licenci pro produkční použití?** A valid Aspose.Page license is required for commercial deployments.  
- **Která verze Javy je podporována?** Aspose.Page works with Java 8 and later.

## Předpoklady
Before you start, verify that you have:

- Solidní znalost základní syntaxe Javy a objektově orientovaných konceptů.  
- Knihovna Aspose.Page pro Java nainstalována. Můžete ji stáhnout z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- IDE pro Javu (IntelliJ IDEA, Eclipse nebo VS Code) nakonfigurované s JAR soubory knihovny na classpath.

## Import balíčků
`PsDocument` is the main class used to create a PostScript document, and `PsSaveOptions` configures how the document is saved.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Co je „jak škálovat obdélník“ v Aspose.Page?
The `scale(float sx, float sy)` method applies an affine scaling transform to the current graphics state, resizing subsequent drawings by the factors `sx` (horizontal) and `sy` (vertical). This is the core operation behind the **how to scale rectangle** keyword. By applying this transform before drawing, any subsequent shapes such as rectangles will be rendered with the new dimensions while preserving their proportions.

## Jak přeložit (posunout) tvar pomocí Aspose.Page
`writeGraphicsSave()` saves the current graphics state and `writeGraphicsRestore()` restores it, ensuring transformations affect only the intended shape. Translation repositions the origin of the coordinate system without altering object dimensions. By surrounding `translate(dx, dy)` with `writeGraphicsSave()` / `writeGraphicsRestore()`, you ensure that only the intended shape moves while other graphics remain unchanged, providing precise control over individual elements.

## Příklad 1: bez transformací
The first example draws a rectangle without any transformation, establishing a baseline for visual comparison with later examples.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Příklad 2: translace
In this sample we move the graphics context 250 units to the right before drawing a second rectangle, illustrating **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Příklad 3: škálování
Here we answer the primary question **how to scale rectangle**. The rectangle is reduced to 50 % of its original width and 75 % of its original height using the `scale(0.5f, 0.75f)` call.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Jak otáčet tvar v Javě (rotate shape java)
`rotate(angle)` rotates the coordinate system by the specified angle in degrees. Load your `PsDocument`, call `rotate(angle)` on the graphics state, draw the shape, then restore the previous state. This pattern implements **rotate shape java** and **how to rotate rectangle** in a single, reusable block, allowing you to pivot graphics around any point you choose.

## Proč je to důležité – reálné výhody
- **Výstup nezávislý na zařízení** – Aspose.Page může generovat soubory PostScript a XPS, které se zobrazují identicky na jakémkoli tiskárně nebo prohlížeči, čímž eliminuje platform‑specifické úpravy.  
- **Detailní kontrola** – Kombinujte translaci, škálování, zkosení a rotaci pro splnění přesných specifikací rozvržení; API podporuje více než 20 kombinací transformací na stránku.  
- **Výkonnostně orientované zpracování** – Knihovna zpracovává dokumenty s paměťovou stopou pod 10 MB pro typické 100‑stránkové zprávy, což umožňuje rychlé a škálovatelné dávkové úlohy.

## Běžné případy použití
- **Tisknutelné faktury** – Přesně umístěte loga, čárové kódy a tabulky pomocí škálování a translace podle firemních směrnic.  
- **Technické diagramy** – Generujte schémata, kde každý komponent musí být proporcionálně změněn a umístěn.  
- **Automatizované vícestránkové zprávy** – Vytvářejte PostScript zprávy, které vyžadují konzistentní škálování napříč stránkami, např. technické specifikace.

## Běžné problémy a řešení
- **Transformace se neresetuje** – Vždy párujte `writeGraphicsSave()` s `writeGraphicsRestore()`; jinak následné kresby zdědí nechtěné transformace.  
- **Neočekávané barvy** – Nastavte barvu (paint) po každé transformaci, protože stav grafiky neuchovává informaci o barvě po obnovení.  
- **Velikost souboru je příliš velká** – Povolením komprese v `PsSaveOptions` a omezením rozlišení vložených rastrových obrázků udržte finální soubor pod 5 MB pro typické 50‑stránkové dokumenty.

## Často kladené otázky
### Mohu použít Aspose.Page pro Java i pro jiné formáty dokumentů?
Aspose.Page primarily focuses on page manipulation for PostScript and XPS formats, but it also offers limited PDF export capabilities.

### Kde najdu více příkladů a dokumentaci pro Aspose.Page pro Java?
Visit the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) for comprehensive guides, API references, and sample projects.

### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
Yes, you can access a free trial via the **Aspose free trial download** page: [Aspose free trial download](https://releases.aspose.com/).

### Jak získám dočasnou licenci pro Aspose.Page pro Java?
Obtain a temporary license through the **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Kde mohu získat komunitní podporu nebo položit otázky ohledně Aspose.Page pro Java?
Visit the [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) for community discussions, code snippets, and troubleshooting tips.

## Často kladené otázky

**Q: Jaký je rozdíl mezi `translate` a `scale`?**  
A: `translate` moves the origin of the coordinate system, while `scale` changes the size of drawn objects along the X and/or Y axes.

**Q: Mohu kombinovat více transformací v jednom grafickém stavu?**  
A: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially before drawing, you create a combined affine transformation.

**Q: Jak resetuji transformace po nakreslení tvaru?**  
A: Use `writeGraphicsRestore()` to revert to the previously saved graphics state.

**Q: Je možné otočit obdélník kolem jeho středu?**  
A: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`, then translate it back before drawing.

**Q: Podporuje Aspose.Page anti‑aliasing pro hladší grafiku?**  
A: Yes—set the appropriate rendering options in `PsSaveOptions` to enable anti‑aliasing.

---

**Last Updated:** 2026-10-20  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose

## Související tutoriály

- [Jak nakreslit obdélník v Java PostScript pomocí Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Vytvořit radiální gradient v PostScript pomocí Aspose.Page pro Java](/page/java/postscript-gradient-addition/)
- [Manipulace se stránkou PostScript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}