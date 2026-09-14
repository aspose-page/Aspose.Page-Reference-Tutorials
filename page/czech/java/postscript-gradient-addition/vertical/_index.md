---
date: 2026-09-14
description: Naučte se, jak vytvořit postscript gradient java s Aspose.Page. Tento
  krok‑za‑krokem průvodce vám ukáže, jak přidat vertikální gradient do souboru PostScript
  pomocí několika řádků Java kódu.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Přidat vertikální gradient do Java PostScript
og_description: Naučte se, jak vytvořit postscript gradient java s Aspose.Page. Tento
  krok‑za‑krokem průvodce vám ukáže, jak přidat vertikální gradient do souboru PostScript
  pomocí několika řádků Java kódu.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Vytvořit postscript gradient java – vertikální gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Vytvořit postscript gradient java – vertikální gradient
url: /cs/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření postscript gradientu v Javě – vertikální gradient

## Úvod
Aspose.Page for Java je knihovna, která umožňuje programově vytvářet a manipulovat se soubory PostScript a PDF. V tomto komplexním tutoriálu se naučíte, jak **create postscript gradient java** pomocí této knihovny. Přidání vertikálního gradientu může vaše dokumenty učinit živějšími a profesionálnějšími a s několika řádky kódu můžete dosáhnout úžasných vizuálních efektů. Provedeme vás každým krokem, vysvětlíme, proč je každý prvek důležitý, a poskytneme praktické tipy, jak se vyhnout běžným úskalím. Na konci tohoto průvodce budete schopni generovat soubory PostScript s plynulými, poutavými vertikálními barevnými přechody.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Mohu přizpůsobit barvy?** Ano, lze použít libovolný `java.awt.Color`  
- **Je rotace podporována?** Ano, můžete otočit gradient pomocí `AffineTransform`  
- **Jaký výstupní formát je vytvořen?** Standardní soubor PostScript (.ps)  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována komerční licence  

## Proč přidat vertikální gradient do dokumentu PostScript?
Přidání vertikálního gradientu dodá vašim stránkám hloubku, zlepší vizuální hierarchii a udrží velikost souboru nízkou, protože gradient je definován ve vektorové formě místo rastrových obrázků. Tato technika je ideální pro záhlaví zpráv, technické manuály nebo jakýkoli leták, který potřebuje moderní vzhled bez ztráty škálovatelnosti.

## Předpoklady
Před zahájením tutoriálu se ujistěte, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Aspose.Page for Java knihovna. Můžete si ji stáhnout ze [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Import balíčků
Ve vašem Java projektu importujte potřebné balíčky, abyste mohli začít:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Nyní si projdeme proces přidání vertikálního gradientu krok za krokem.

## Jak vytvořit postscript gradient v Javě
Načtěte své Java prostředí, vytvořte instanci `PsSaveOptions` a zavolejte `Document.save` – to je hlavní sekvence, která vytvoří soubor PostScript s vertikálním gradientem. API za vás provádí interpolaci barev, transformace souřadnic a vyprázdnění stránky, takže se musíte soustředit jen na definování obdélníku a parametrů gradientu.

### Krok 1: nastavení adresáře dokumentu
`File` objekty představují složku, kam bude výstup zapsán. Adresář musí existovat před otevřením proudu, jinak je vyvolána `IOException`.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: vytvoření výstupního proudu pro dokument PostScript
`FileOutputStream` zapisuje binární data PostScript na disk. Použití bloku `try‑with‑resources` zaručuje, že proud bude uzavřen i v případě výskytu výjimky.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Krok 3: vytvoření možností uložení s velikostí A4
`PsSaveOptions` vám umožňuje nastavit velikost stránky, DPI a zda vložit písma. Nastavením velikosti na A4 (595 × 842 bodů) odpovídá většině tisknutelných dokumentů.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: vytvoření nového PS dokumentu
`Document` je objekt nejvyšší úrovně, který v paměti představuje jeden soubor PostScript. Všechny kreslicí příkazy jsou vydávány vůči tomuto objektu.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: vytvoření obdélníku
`Rectangle2D.Double` definuje oblast, která bude vyplněna gradientem. Souřadnice obdélníku jsou vyjádřeny v bodech (1 bod = 1/72 palce).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Krok 6: nastavení barev a frakcí pro gradient
Pole `float[]` určuje pozici každé barevné zastávky (od 0,0 do 1,0). Objekt `Color` obsahuje skutečné RGB hodnoty. Můžete použít libovolný `java.awt.Color`, který chcete.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Krok 7: vytvoření transformace gradientu
`AffineTransform` mění měřítko a otáčí gradient. Pro čistý vertikální gradient potřebujete jen změnit měřítko osy Y; rotaci lze přidat později, pokud chcete.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Krok 8: vytvoření vertikálního lineárního gradientu
`LinearGradientPaint` spojuje obdélník, barevné zastávky a transformaci. Tento objekt je později předán grafickému kontextu.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Krok 9: nastavení barvy a vyplnění obdélníku
`Graphics2D.setPaint` aplikuje gradient a `fill` jej vykreslí uvnitř obdélníku, který jste dříve definovali.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Krok 10: uzavření aktuální stránky a uložení dokumentu
Volání `document.save` zapíše celý PostScript proud do výstupního souboru a uvolní všechny nativní zdroje.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gratulujeme! Úspěšně jste přidali vertikální gradient do vašeho Java PostScript dokumentu pomocí Aspose.Page for Java.

## Časté problémy a řešení
- **Gradient vypadá plochý:** Ujistěte se, že měřítko `AffineTransform` odpovídá rozměrům obdélníku.  
- **Barvy vypadají vybledlé:** Ověřte, že používáte správný `ColorSpaceType` (SRGB) a že pole frakcí je seřazeno od 0,0 do 1,0.  
- **Soubor nebyl vygenerován:** Zkontrolujte, že výstupní adresář (`dataDir`) existuje a aplikace má oprávnění k zápisu.  

## Často kladené otázky
**Q: Mohu používat Aspose.Page for Java s jinými Java knihovnami?**  
A: Ano, Aspose.Page for Java je navržena tak, aby bez problémů spolupracovala s dalšími Java knihovnami, jako jsou Apache Commons nebo Spring.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page for Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi [free trial download page](https://releases.aspose.com/).

**Q: Kde najdu další dokumentaci?**  
A: Podrobná dokumentace je k dispozici [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Jak mohu zakoupit Aspose.Page for Java?**  
A: Můžete zakoupit Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).

**Q: Existuje fórum pro diskuze o Aspose.Page?**  
A: Ano, můžete se připojit k komunitnímu fóru [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## Další často kladené otázky

**Q: Mohu vytvořit gradienty v jiných směrech (horizontální, diagonální)?**  
A: Rozhodně. Upravit počáteční a koncové body v `LinearGradientPaint` a změnit úhel rotace v `AffineTransform`.

**Q: Funguje to také s výstupem PDF?**  
A: Stejná logika gradientu může být použita při ukládání do PDF pomocí `PdfSaveOptions` místo `PsSaveOptions`.

**Q: Jak mohu dynamicky změnit velikost gradientu?**  
A: Vypočítejte rozměry obdélníku za běhu a předávejte tyto hodnoty jak do `Rectangle2D`, tak do konstruktoru `AffineTransform`.

---

**Last Updated:** 2026-09-14  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose

## Související tutoriály

- [Vytvořit radiální gradient v PostScriptu s Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Jak převést PostScript na PDF pomocí Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page Tutorial průhlednosti – Přidat průhlednost v Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}