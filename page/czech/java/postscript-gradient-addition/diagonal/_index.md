---
date: 2026-09-04
description: Naučte se, jak přidat gradient v Java PostScript pomocí Aspose.Page Java,
  vytvářet diagonální barevné přechody pomocí LinearGradientPaint pro živé dokumenty.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Jak přidat gradient: diagonální gradient v Java PostScript pomocí Aspose.Page
  Java'
og_description: Naučte se, jak přidat gradient v Java PostScript pomocí Aspose.Page
  Java. Tento průvodce vám ukáže, jak vytvořit diagonální gradient pomocí LinearGradientPaint
  během několika kroků.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Jak přidat gradient v Java PostScript pomocí Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Jak přidat gradient: diagonální gradient v Java PostScript pomocí Aspose.Page
  Java'
url: /cs/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání diagonálního gradientu v Java PostScript pomocí Aspose.Page Java

## Úvod
Pokud chcete obohatit soubor PostScript o plynulý diagonální barevný přechod, **Aspose.Page Java** to dělá překvapivě snadno. V tomto tutoriálu se naučíte **jak přidat gradient** efekt krok za krokem pomocí třídy `LinearGradientPaint` z Java 2D. Na konci budete mít připravený úryvek k okamžitému spuštění, který vytvoří dokument PostScript s živým diagonálním gradientem, a pochopíte, proč je tento přístup udržovatelnější než ruční kódování čistých příkazů PostScript.

## Jak přidat gradient v Java PostScript
Přidání gradientu může znít jako úkol jen pro grafiku, ale s Aspose.Page získáte plnou kontrolu nad podkladovými příkazy PostScript při práci v čisté Javě. Tato sekce vysvětluje, proč tento přístup funguje a co získáte ve srovnání s ručním kódováním čistého PostScriptu.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java.  
- **Která třída vytváří gradient?** `LinearGradientPaint`.  
- **Mohu změnit barvy?** Ano – upravte pole `Color[]`.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Jak dlouho trvá implementace?** Přibližně 10 minut pro základní gradient.

## Co je Aspose.Page Java?
Aspose.Page Java je plnohodnotné API, které umožňuje vývojářům generovat, upravovat a převádět soubory PostScript a PDF bez jakéhokoli externího softwaru. Knihovna podporuje **více než 50 vstupních a výstupních formátů** a může zpracovávat dokumenty s **více než 500 stránkami**, přičemž spotřeba paměti zůstává pod 100 MB.

## Proč použít diagonální gradient?
Diagonální gradient přidává hloubku a vizuální zajímavost grafům, bannerům nebo jakémukoli grafickému prvku, který potřebuje moderní vzhled. Protože gradient běží od jednoho rohu k protilehlému, dobře funguje pro pozadí, vzhled tlačítek a dekorativní tvary, poskytuje profesionální vzhled bez dalších obrazových souborů.

## Požadavky
- Java Development Kit (JDK) 8 nebo vyšší.  
- IDE, například Eclipse, IntelliJ IDEA nebo VS Code.  
- **Aspose.Page for Java** knihovna – stáhněte nejnovější verzi z [oficiální stránky ke stažení](https://releases.aspose.com/page/java/).

## Import balíčků
The `java.awt` balíček poskytuje základní grafické třídy, zatímco balíček `com.aspose.page` vám dává přístup k API specifickým pro PostScript.

Třída `LinearGradientPaint` je mostem Aspose.Page k funkčnosti gradientů v Java 2D.  
`AffineTransform` umožňuje otáčení a škálování gradientu tak, aby byl diagonální.

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

## Krok 1: vytvořit výstupní stream pro dokument PostScript
Nejprve definujte složku, kam bude soubor uložen, a otevřete `FileOutputStream`. Tento stream přijímá vygenerovaná data PostScript.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Krok 2: vytvořit možnosti uložení s velikostí A4
`PsSaveOptions` vám umožňuje nastavit velikost stránky, rozlišení a další výstupní nastavení. Zde používáme výchozí velikost A4, která je 595 × 842 bodů při 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: vytvořit nový PS dokument
Třída `PsDocument` představuje dokument PostScript a poskytuje metody pro vytváření stránek a kreslení grafiky.  
Vytvořte instanci `PsDocument` pomocí výstupního streamu a možností uložení. Příznak `false` říká konstruktoru, aby automaticky neotevřel novou stránku – uděláme to později.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: vytvořit obdélník
Definujte obdélník, který bude obsahovat výplň gradientem. Pozice obdélníku (200, 100) a velikost (200 × 100) jsou zvoleny tak, aby byl gradient dobře viditelný.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Krok 5: vytvořit transformaci gradientu
`AffineTransform` nám umožňuje otáčet, škálovat a posouvat gradient tak, aby běžel diagonálně přes obdélník. Níže uvedená matematika vypočítá přeponu a podle toho upraví poměr škálování.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Krok 6: vytvořit diagonální lineární gradientový paint
`LinearGradientPaint` je hlavní třída, která generuje barevný přechod. Rozprostírá se od levého horního rohu obdélníku k pravému dolnímu, přičemž používá dříve definovanou transformaci. `MultipleGradientPaint.CycleMethod.NO_CYCLE` zajišťuje, že se gradient neopakuje.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Krok 7: nastavit paint a vyplnit obdélník
Aplikujte gradientový paint na dokument a vyplňte tvar obdélníku. Tento krok vykreslí diagonální barevný přechod na stránku PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Krok 8: zavřít aktuální stránku a uložit dokument
Na závěr zavřete stránku, vyprázdněte stream a uložte soubor. Výsledný soubor `DiagonalGradient_outPS.ps` lze otevřít v libovolném prohlížeči PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Časté problémy a tipy
- **Gradient vypadá plochý** – zkontrolujte úhel otáčení; otáčení o 45° vytvoří skutečný diagonál.  
- **Barvy vypadají vybledlé** – ujistěte se, že používáte `MultipleGradientPaint.ColorSpaceType.SRGB` pro přesné vykreslení barev.  
- **Chyba souboru nenalezen** – ověřte, že `dataDir` ukazuje na existující složku a že aplikace má oprávnění k zápisu.  
- **Velké dokumenty způsobují špičky v paměti** – použijte `PsSaveOptions.setCompress(true)` ke snížení paměťové náročnosti.

## Často kladené otázky

**Q: Můžu tuto knihovnu použít pro jiné grafické operace v Javě?**  
A: Ano, Aspose.Page for Java poskytuje kompletní sadu kreslicích primitiv, renderování textu a možnosti manipulace s obrázky.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page Java?**  
A: Rozhodně. Můžete si stáhnout plně funkční zkušební verzi ze [stránky bezplatné zkušební verze Aspose](https://releases.aspose.com/).

**Q: Kde najdu dokumentaci pro Aspose.Page Java?**  
A: Oficiální reference API je k dispozici na [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Jak mohu zakoupit licenci pro Aspose.Page Java?**  
A: Licence lze zakoupit přímo přes [portál nákupu Aspose](https://purchase.aspose.com/buy).

**Q: Potřebujete pomoc nebo máte otázky?**  
A: Navštivte komunitní [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde vám pomohou jak inženýři Aspose, tak ostatní vývojáři.

---

**Poslední aktualizace:** 2026-09-04  
**Testováno s:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit radiální gradient v PostScript pomocí Aspose.Page pro Java](/page/java/postscript-gradient-addition/)
- [Jak přidat gradient v Java PostScript pomocí Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Vytvořit PostScript gradient v Javě – Přidat vertikální gradient](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}