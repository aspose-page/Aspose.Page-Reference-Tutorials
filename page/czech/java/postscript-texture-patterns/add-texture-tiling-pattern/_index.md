---
date: 2026-09-14
description: Naučte se, jak použít texture paint java k přidání tiling patterns v
  PostScriptu s Aspose.Page. Tento tutoriál podrobně pokrývá texture fills, shape
  rendering a text styling.
keywords:
- texture paint java
- fill shape with texture
- apply texture to text
- fill rectangle with texture
- texture tiling tutorial
lastmod: 2026-09-14
linktitle: Přidat Texture Tiling Pattern v Java PostScript
og_description: Objevte, jak použít texture paint java k přidání tiling patterns v
  dokumentech PostScriptu s Aspose.Page. Postupujte podle krok‑za‑krokem instrukcí
  a osvědčených postupů.
og_image_alt: Guide showing texture paint java usage in a Java PostScript example
og_title: Jak použít texture paint java pro dlaždicování v PostScriptu
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to use texture paint java to add tiling patterns in PostScript
    with Aspose.Page. This tutorial covers texture fills, shape rendering, and text
    styling in detail.
  headline: How to use texture paint java for tiling in PostScript
  type: TechArticle
- description: Learn how to use texture paint java to add tiling patterns in PostScript
    with Aspose.Page. This tutorial covers texture fills, shape rendering, and text
    styling in detail.
  name: How to use texture paint java for tiling in PostScript
  steps:
  - name: create a PostScript document
    text: First, instantiate a `Document` object that represents the output file.
      This object is the entry point for all drawing operations. `Document` is Aspose.Page's
      top‑level object that models a single PostScript file in memory. After creation,
      you can add pages, set page size, and control output options
  - name: set up the graphics environment
    text: Translate the coordinate system to a convenient origin and load the bitmap
      that will serve as the tile. The bitmap is read into a `BufferedImage`, which
      Aspose.Page can use directly.
  - name: create texture brush
    text: Define a `TexturePaint` that repeats the bitmap across the shape’s area.
      `TexturePaint` is the class that implements the tiling logic; it takes the bitmap
      and a rectangle that defines the tile size. Adjust the rectangle if you want
      the texture to appear larger or smaller.
  - name: draw and fill shapes
    text: Create a rectangle (or any other shape) and call `document.fill(shape)`
      while the `TexturePaint` is active. Then optionally stroke the shape to give
      it a clear outline.
  - name: add text with texture pattern
    text: You can also apply the same `TexturePaint` to text glyphs. This demonstrates
      **how to fill texture** on characters while still being able to stroke them
      for a crisp appearance.
  - name: save and close
    text: Finally, close the page, write the document to disk, and release any resources.
      The resulting `.ps` file contains a fully tiled texture that can be viewed in
      any PostScript‑compatible viewer.
  type: HowTo
- questions:
  - answer: Absolutely. The library provides clear documentation and intuitive APIs,
      making it easy for developers of any experience level to generate PostScript
      content.
    question: Is Aspose.Page for Java suitable for beginners?
  - answer: Yes. Add the Maven/Gradle dependency, import the required namespaces,
      and start using the API. Detailed integration steps are available **[Aspose.Page
      Java API reference](https://reference.aspose.com/page/java/)**.
    question: Can I integrate Aspose.Page for Java into an existing project?
  - answer: Join the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** to
      ask questions, share examples, and get help from both Aspose engineers and other
      developers.
    question: Where can I find community support?
  - answer: Yes, you can download a trial version **[Aspose trial download](https://releases.aspose.com/)**
      to evaluate all features before purchasing.
    question: Is a free trial available?
  - answer: Visit **[temporary license request](https://purchase.aspose.com/temporary-license/)**
      to request a time‑limited license that removes evaluation restrictions.
    question: How do I obtain a temporary license for testing?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- texture paint
- Aspose.Page
- Java graphics
- PostScript
title: Jak použít texture paint java pro dlaždicování v PostScriptu
url: /cs/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak používat texture paint java pro dlaždicování v PostScriptu

## Úvod
Pokud potřebujete obohatit soubor PostScript o opakující se bitmapové textury, **texture paint java** je nejpohodlnější způsob, jak to provést. Aspose.Page pro Java abstrahuje nízkoúrovňové příkazy PostScript, což vám umožní soustředit se na návrh místo ručního kreslení. V tomto průvodci se naučíte, jak vytvořit dlaždicový vzor, vyplnit tvary a použít stejnou texturu na text – vše pomocí několika jednoduchých volání API.

## Rychlé odpovědi
- **Jaká knihovna poskytuje podporu texture paint?** Aspose.Page for Java.  
- **Na které primární klíčové slovo je tento tutoriál zaměřen?** *texture paint java*.  
- **Potřebuji licenci pro produkční použití?** Ano – je k dispozici bezplatná zkušební verze pro hodnocení, ale pro komerční nasazení je vyžadována licencovaná verze.  
- **Jaké Java runtime je vyžadováno?** Java 8 nebo novější.  
- **Lze stejný texturový štětec znovu použít?** Rozhodně – vytvořte `TexturePaint` jednou a znovu jej použijte pro libovolný počet tvarů nebo textových objektů.  
- **Jak vyplním obdélník texturou?** Nastavte `TexturePaint` jako aktuální barvu a zavolejte `document.fill(rectangle)`.

## Co je texturový dlaždicový vzor?
Texturový dlaždicový vzor opakuje malou bitmapu (dlaždici) přes větší oblast, což vám umožní **vyplnit tvar texturou** bez nutnosti kreslit každou dlaždici samostatně. Tento přístup je ideální pro pozadí, dekorativní výplně a texturovaný text v PostScriptu a funguje efektivně s libovolnou velikostí obrázku.

## Proč používat Aspose.Page pro Java?
Aspose.Page pro Java poskytuje engine bez závislostí, který generuje PostScript přímo z Java kódu, čímž eliminuje potřebu externích interpretů. Nabízí plnou kontrolu nad vektory, textem a bitmapovými texturami, podporuje více než 30 výstupních formátů a běží na jakémkoli operačním systému, který podporuje Java 8 nebo novější, což z něj činí univerzální volbu pro vývojáře.

## Předpoklady
- Funkční vývojové prostředí Java (JDK 8 nebo novější).  
- Základní znalost konceptů PostScriptu.  
- Knihovna Aspose.Page pro Java nainstalována – stáhněte ji **[download Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  

## Import balíčků
Importujte třídy, které budete potřebovat pro vytvoření PostScript dokumentu a práci s bitmapovými texturami. Importujte požadované Java a Aspose.Page třídy, které poskytují grafiku, manipulaci s obrázky a funkčnost PostScript dokumentu.

## Jak přidat texturový dlaždicový vzor v Java PostScriptu
Plný efekt dlaždicování můžete dosáhnout ve třech stručných krocích. Níže uvedená odpověď vám přesně řekne, co dělat, a následující sekce rozebírají jednotlivé kroky.

Načtěte svou bitmapu, vytvořte `TexturePaint` a aplikujte jej na tvary nebo text – to je vše, co potřebujete k vytvoření dlaždicové textury napříč libovolnou oblastí stránky.

### Krok 1: vytvořit PostScript dokument
Nejprve vytvořte objekt `Document`, který představuje výstupní soubor. Tento objekt je vstupním bodem pro všechny kreslicí operace.

`Document` je nejvyšší objekt Aspose.Page, který v paměti modeluje jeden PostScript soubor. Po vytvoření můžete přidávat stránky, nastavit velikost stránky a řídit výstupní možnosti.

### Krok 2: nastavit grafické prostředí
Přesuňte souřadnicový systém na pohodlný počátek a načtěte bitmapu, která bude sloužit jako dlaždice. Bitmapa je načtena do `BufferedImage`, kterou může Aspose.Page použít přímo.

### Krok 3: vytvořit texturový štětec
Definujte `TexturePaint`, který opakuje bitmapu přes oblast tvaru. `TexturePaint` je třída, která implementuje logiku dlaždicování; přijímá bitmapu a obdélník, který určuje velikost dlaždice. Upravit obdélník, pokud chcete, aby textura vypadala větší nebo menší.

### Krok 4: kreslit a vyplňovat tvary
Vytvořte obdélník (nebo jakýkoli jiný tvar) a zavolejte `document.fill(shape)`, zatímco je `TexturePaint` aktivní. Poté můžete volitelně obrysovat tvar, aby měl jasný kontur.

### Krok 5: přidat text s texturovaným vzorem
Můžete také aplikovat stejný `TexturePaint` na textové glyfy. To ukazuje **jak vyplnit texturou** znaky a zároveň je možné je obrysovat pro ostrý vzhled.

### Krok 6: uložit a zavřít
Nakonec zavřete stránku, zapište dokument na disk a uvolněte všechny prostředky. Výsledný soubor `.ps` obsahuje plně dlaždicovou texturu, kterou lze zobrazit v libovolném PostScript‑kompatibilním prohlížeči.

## Časté problémy a tipy
- **Chybějící soubor textury** – Ověřte, že cesta k `TestTexture.bmp` je správná a že soubor je čitelný procesem Java.  
- **Roztažená textura** – Pokud vypadá vzor deformovaně, ujistěte se, že obdélník `imageArea` odpovídá původním rozměrům bitmapy.  
- **Výkon** – Znovu použijte stejnou instanci `TexturePaint` pro více tvarů; tím se vyhnete zbytečným alokacím objektů a urychlíte vykreslování.  
- **Profesionální tip:** Použijte bitmapu s vysokým rozlišením pro dlaždici, aby textura zůstala ostrá při škálování vzoru.

## Často kladené otázky

**Q: Je Aspose.Page pro Java vhodný pro začátečníky?**  
A: Rozhodně. Knihovna poskytuje přehlednou dokumentaci a intuitivní API, což usnadňuje vývojářům všech úrovní zkušeností generovat obsah PostScriptu.

**Q: Mohu integrovat Aspose.Page pro Java do existujícího projektu?**  
A: Ano. Přidejte Maven/Gradle závislost, importujte požadované jmenné prostory a začněte používat API. Podrobné kroky integrace jsou k dispozici **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.

**Q: Kde mohu najít komunitní podporu?**  
A: Připojte se k **[Aspose.Page fóru](https://forum.aspose.com/c/page/39)**, kde můžete klást otázky, sdílet příklady a získat pomoc od inženýrů Aspose i dalších vývojářů.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete si stáhnout zkušební verzi **[Aspose trial download](https://releases.aspose.com/)** a vyzkoušet všechny funkce před zakoupením.

**Q: Jak získám dočasnou licenci pro testování?**  
A: Navštivte **[temporary license request](https://purchase.aspose.com/temporary-license/)** a požádejte o časově omezenou licenci, která odstraní omezení zkušební verze.

**Last Updated:** 2026-09-14  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```
```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```
```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Související tutoriály

- [Vytvořit texturový vzor v PostScriptu s Aspose.Page pro Java](/page/java/postscript-texture-patterns/)
- [Vytvořit radiální gradient v PostScriptu s Aspose.Page pro Java](/page/java/postscript-gradient-addition/)
- [Aspose.Page průvodce průhledností – Přidat průhlednost v Java PostScriptu](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}