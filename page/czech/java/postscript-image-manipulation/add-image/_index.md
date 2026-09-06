---
date: 2026-08-23
description: Naučte se, jak použít aspose.page image manipulation java k vložení a
  otáčení obrázků v souborech PostScript s přehlednými příklady v Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Přidání obrázku v Java PostScript
og_description: Naučte se, jak použít aspose.page image manipulation java k vložení
  a otáčení obrázků v souborech PostScript, s podrobnými příklady kódu v Java.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Jak použít aspose.page image manipulation java k přidání obrázku
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Jak použít aspose.page image manipulation java k přidání obrázku
url: /cs/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít aspose.page image manipulation java k přidání obrázku

## Úvod

V tomto tutoriálu se naučíte, jak **použít aspose.page image manipulation java** k vytváření souborů PostScript, vkládání rastrových obrázků a aplikaci transformací posunu a otáčení. Na konci průvodce budete schopni generovat pixelově přesný výstup PostScript z Javy — ideální pro automatizované reportování, tiskové řetězce nebo jakýkoli pracovní postup, který vyžaduje přesné umístění obrázku v dokumentu PostScript.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java  
- **Mohu přidat více obrázků?** Ano – opakujte transformaci a kroky kreslení pro každý obrázek  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci  
- **Která verze Javy je podporována?** Java 8 a novější  
- **Je podpora otáčení obrázku?** Rozhodně – použijte `AffineTransform.rotate()`

## Co je aspose.page image manipulation java?

`aspose.page image manipulation java` je API Aspose.Page, které vám umožňuje programově vytvářet, upravovat a renderovat dokumenty PostScript z Java kódu, včetně úplné kontroly nad umístěním obrázku, měřítkem a otáčením. S tímto API se vyhnete nízkoúrovňové syntaxi PostScript a necháte knihovnu, aby interně zpracovávala konverzi formátu a vkládání.

## Proč použít aspose.page pro manipulaci s obrázky?

Aspose.Page poskytuje **více než 50 formátů obrázků** (včetně JPEG, PNG, BMP, TIFF) a může je vložit do PostScriptu, aniž by načítal celý dokument do paměti, což umožňuje zpracování souborů se stovkami stránek při zachování využití paměti pod 100 MB na typickém serveru. Vysoceúrovňové API abstrahuje složité příkazy PostScript, takže píšete stručný Java kód místo surových PS operátorů.

## Požadavky
- Java Development Kit (JDK) 8 nebo novější nainstalován.  
- Aspose.Page for Java knihovna – stáhněte ji **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Základní znalost syntaxe Javy a objektově orientovaného programování.

## Co je create postscript java?

Vytvoření souboru PostScript z Javy znamená programové generování dokumentu `.ps`, který popisuje rozvržení stránky, vektorovou grafiku a rastrové obrázky pomocí jazyka PostScript. Aspose.Page převádí vaše Java volání na platné PostScript instrukce, což vám umožňuje vytvářet soubory připravené k tisku bez samostatného interpretru PostScript.

## Jak přidat obrázek s posunem a otáčením krok za krokem

Nahrajte svůj obrázek, aplikujte `AffineTransform` a vykreslete jej na stránku. Následující kroky popisují přesné pořadí, které musíte dodržet.

### Krok 1: uložení grafického stavu

Uložení grafického stavu izoluje vaše transformace, takže je můžete později vrátit zpět. Toto je ekvivalentní operátoru `gsave` v čistém PostScriptu.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Krok 2: posun a transformace (posun a otočení obrázku)

Nejprve vytvořte `BufferedImage` ze zdrojového souboru, poté sestavte `AffineTransform`, který posune obrázek na požadované souřadnice a otočí jej kolem jeho středu. `AffineTransform.rotate` očekává úhel v radiánech, takže stupně převedete pomocí `Math.toRadians(degrees)`.

**AffineTransform** je třída v Javě, která představuje 2‑D afinní transformaci, jako je posun, otáčení, škálování nebo zkosení.  
**BufferedImage** je třída v Javě, která ukládá obrázek v paměti jako rastr pixelů.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Krok 3: přidání obrázku do dokumentu

Po nastavení transformace vykreslete obrázek na aktuální stránku. Knihovna automaticky převádí `BufferedImage` na vhodný PostScript image stream.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Krok 4: obnovení grafického stavu

Volání obnovy (`grestore`) vrátí grafický stav do podoby, v jaké byl před uložením, čímž zajistí, že následné kreslicí příkazy nebudou ovlivněny předchozí transformací.

```java
document.drawImage(image, transform, null);
```

### Krok 5: uzavření aktuální stránky a uložení

Dokončete stránku, uzavřete dokument a zapište výstupní soubor na disk.

```java
document.writeGraphicsRestore();
```

Můžete opakovat výše uvedenou sekvenci pro vložení dalších obrázků, přičemž každým krokem upravíte souřadnice posunu a úhel otáčení.

## Časté problémy a řešení
- **FileNotFoundException:** Ověřte, že `dataDir` končí oddělovačem souborů (`/` nebo `\\`) a že název souboru obrázku přesně odpovídá.  
- **ImageIO.read returns null:** Ujistěte se, že formát obrázku je mezi podporovanými (JPEG, PNG, BMP, GIF, TIFF).  
- **Incorrect rotation angle:** `AffineTransform.rotate` pracuje s radiány; použijte `Math.toRadians(degrees)` pro převod ze stupňů.  
- **Memory spikes on large pages:** Použijte `Document.save` s `saveOptions.setCompress(true)` ke snížení paměťové náročnosti.

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?**  
A: Základní knihovna je pouze pro Javu, ale Aspose poskytuje ekvivalentní API pro .NET, C++ a Python, každé přizpůsobené své platformě.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Dočasnou licenci můžete získat na **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde mohu najít komunitní podporu a diskuse související s Aspose.Page pro Java?**  
A: Navštivte **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** pro komunitní pomoc.

**Q: Existují další zdroje pro nákup Aspose.Page pro Java?**  
A: Knihovnu si můžete zakoupit na **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Závěr

Nyní máte kompletní, end‑to‑end příklad **aspose.page image manipulation java**, který vytváří soubor PostScript, posouvá a otáčí obrázek a výsledek ukládá. Prozkoumejte kompletní **[documentation](https://reference.aspose.com/page/java/)** a objevte pokročilé funkce jako vektorová grafika, vlastní velikosti stránek a vykreslování textu.

---

**Poslední aktualizace:** 2026-08-23  
**Testováno s:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

```java
document.closePage();
document.save();
```

## Související tutoriály

- [Jak převést PostScript na PDF pomocí Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Jak přidat gradient: Diagonální gradient v Java PostScript pomocí Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Jak přidat šachovnicový vzor v Java PostScript s Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}