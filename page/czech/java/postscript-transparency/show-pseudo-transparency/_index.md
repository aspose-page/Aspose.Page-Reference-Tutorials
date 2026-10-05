---
date: 2026-10-04
description: Naučte se, jak vytvořit pseudo průhlednost v Javě pomocí Aspose.Page.
  Postupujte podle našeho průvodce krok za krokem a přidejte živé grafiky do souborů
  PostScript.
keywords:
- create pseudo transparency java
- Aspose.Page Java
- PostScript pseudo transparency
lastmod: 2026-10-04
linktitle: Zobrazit pseudo průhlednost v Java PostScript
og_description: Vytvořte pseudo průhlednost v Javě pomocí Aspose.Page pro generování
  živých grafických souborů PostScript. Tento průvodce vás během několika minut provede
  nastavením, kódem a řešením problémů.
og_image_alt: Aspose.Page Java tutorial showing pseudo transparency in PostScript
og_title: Návod na vytvoření pseudo průhlednosti v Javě s Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to create pseudo transparency java using Aspose.Page. Follow
    our step‑by‑step guide to add vibrant graphics in PostScript files.
  headline: How to create pseudo transparency java with Aspose.Page
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java is available for commercial use. You can purchase
      a license **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: Yes, you can get a free trial **[download free trial](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Detailed documentation is available **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.
    question: Where can I find additional documentation?
  - answer: You can obtain a temporary license **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for testing purposes?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.
    question: Need help or want to discuss Aspose.Page?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- pseudo transparency
- Aspose.Page
- Java PostScript
title: Jak vytvořit pseudo průhlednost v Javě pomocí Aspose.Page
url: /cs/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript pseudo-průhlednost s Aspose.Page

## Úvod
V tomto komplexním tutoriálu **vytvoříte pseudo‑průhlednou java** grafiku pomocí Aspose.Page pro Java. Provedeme vás vším – od instalace knihovny po nakreslení dvou překrývajících se obdélníků, které simulují průhlednost v souboru PostScript. Na konci budete vědět, proč je pseudo‑průhlednost důležitá, jak ji implementovat a jak upravit barvy a gradienty pro vlastní návrhy.

## Rychlé odpovědi
- **Co znamená pseudo‑průhlednost?** Simuluje průhlednost mícháním poloprůhledných gradientů.
- **Která knihovna je vyžadována?** Aspose.Page pro Java.
- **Potřebuji licenci pro spuštění příkladu?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je potřeba komerční licence.
- **Jaké IDE mohu použít?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, VS Code), které podporuje Java 8+.
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Co je pseudo‑průhlednost v Java PostScript?
Pseudo‑průhlednost je technika, která používá poloprůhledné výplně gradientů k vytvoření vizuálního dojmu průhledných objektů. Protože tradiční PostScript nepodporuje skutečné alfa kanály, Aspose.Page tuto funkci emuluje vrstvením průhledných tvarů. Úpravou hodnot opacity gradientu můžete simulovat různé stupně průhlednosti bez nutnosti nativní podpory alfa kanálu.

## Proč použít Aspose.Page pro pseudo‑průhlednost?
Aspose.Page podporuje **více než 30 výstupních formátů** (včetně EPS, PDF, SVG a PNG) a dokáže vykreslovat dokumenty s několika stovkami stránek, aniž by načítala celý soubor do paměti. Jeho multiplatformní Java API vám poskytuje detailní kontrolu nad barvami, opacity a směrem gradientu, což zajišťuje konzistentní výsledky na jakémkoli tiskárně nebo prohlížeči.

## Předpoklady
- Základní znalost Javy.  
- Znalost konceptů PostScriptu.  
- Knihovna Aspose.Page pro Java nainstalována. Pokud jste ji ještě ne stáhli, získáte ji **[download Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  
- Java IDE nebo nástroj pro sestavení (Maven/Gradle) připravený.

## Import balíčků
Následující importy vám poskytují přístup k barvám, gradientům a objektu PostScript dokumentu.

Třída `PsDocument` je nejvyšší objekt Aspose.Page, který představuje soubor PostScript v paměti.  

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

## Krok 1: vytvořit ps dokument
Nejprve vytvoříme výstupní stream a inicializujeme nový `PsDocument`. Tento objekt funguje jako plátno pro všechny následné kreslicí operace.

Konstruktor `PsDocument` přijímá `OutputStream` a `PageSize`, aby definoval kreslicí plochu.  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: definovat obdélník s neprůhlednou výplní gradientu
Nakreslíme první obdélník pomocí zcela neprůhledného gradientu. Ten bude sloužit jako pozadí pro naši pseudo‑průhlednou vrstvu.

Třída `LinearGradientBrush` poskytuje způsob, jak vyplnit tvary lineárními barevnými gradienty.  
Třída `LinearGradientBrush` vytváří štětec gradientu; její parametry `Color` přijímají hodnoty RGBA, kde čtvrtá hodnota (alfa) řídí opacity.  

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Krok 3: definovat obdélník s průhlednou výplní gradientu
Dále umístíme druhý obdélník, který používá gradient s alfa hodnotami. To vytváří efekt **pseudo‑průhlednosti**, když se překrývá s prvním tvarem.

Konstruktor `Color` vytváří barvu s červenou, zelenou, modrou a alfa složkou.  
Konstruktor `Color` `new Color(r, g, b, a)` vám umožňuje zadat alfa kanál (0‑255), kde nižší hodnoty zvyšují průhlednost.  

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Krok 4: uzavřít stránku a uložit dokument
Nakonec uzavřeme aktuální stránku a zapíšeme soubor PostScript na disk.

Metoda `save` zapíše obsah dokumentu do poskytnutého výstupního streamu.  
Volání `psDocument.save(outputStream)` dokončí soubor a vyprázdní všechny kreslicí příkazy do podkladového streamu.  

```java
document.closePage();
document.save();
```

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že `dataDir` ukazuje na existující složku a že má vaše aplikace oprávnění k zápisu.  
- **Incorrect colors** – Ujistěte se, že používáte konstruktor `Color(int r, int g, int b, int a)` pro průhledné barvy; čtvrtý parametr je alfa (0‑255).  
- **Gradient not visible** – Zkontrolujte, že parametry `AffineTransform` správně mapují gradient na rozměry obdélníku.

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro Java v komerčních projektech?**  
A: Ano, Aspose.Page pro Java je k dispozici pro komerční použití. Můžete zakoupit licenci **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete získat bezplatnou zkušební verzi **[download free trial](https://releases.aspose.com/)**.

**Q: Kde najdu další dokumentaci?**  
A: Podrobná dokumentace je k dispozici **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.

**Q: Jak mohu získat dočasnou licenci pro testovací účely?**  
A: Můžete získat dočasnou licenci **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.

**Q: Potřebujete pomoc nebo chcete diskutovat o Aspose.Page?**  
A: Navštivte **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.

---

**Poslední aktualizace:** 2026-10-04  
**Testováno s:** Aspose.Page pro Java 24.12 (nejnovější)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit radiální gradient v PostScriptu s Aspose.Page pro Java](/page/java/postscript-gradient-addition/)
- [Vytvořit texturovaný vzor v PostScriptu s Aspose.Page pro Java](/page/java/postscript-texture-patterns/)
- [Jak převést PostScript na PDF pomocí Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}