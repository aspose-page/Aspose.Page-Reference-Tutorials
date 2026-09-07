---
date: 2026-09-04
description: Naučte se, jak vytvořit vodorovný gradient java v souboru PostScript
  pomocí Linear Gradient Paint Java s Aspose.Page pro Java. Kód krok za krokem, běžné
  úskalí a často kladené otázky.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Vytvořte vodorovný gradient java v PostScriptu pomocí Aspose
og_description: Vytvořte vodorovný gradient java v PostScriptu s Linear Gradient Paint
  Java. Tento tutoriál Aspose.Page vám ukáže přesné kroky, předpoklady a tipy na řešení
  problémů během méně než 15 minut.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Vytvořte vodorovný gradient java v PostScriptu pomocí Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Vytvořte vodorovný gradient java v PostScriptu pomocí Aspose
url: /cs/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat horizontální gradient v Java PostScript pomocí Linear Gradient Paint

## Úvod
V tomto komplexním tutoriálu se naučíte **jak vytvořit horizontální gradient java** v dokumentu PostScript pomocí třídy **Linear Gradient Paint Java**, která je součástí Aspose.Page for Java. Provedeme vás každým krokem – od nastavení projektu po vykreslení gradientu na tvary i text – abyste během několika minut mohli vytvářet vyleštěnou grafiku připravenou k tisku. Ať už budujete reportingový engine, nástroj pro automatizaci designu nebo vlastní ovladač tiskárny, tento průvodce vám poskytne přesný kód, který potřebujete.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java (obsahuje Linear Gradient Paint Java).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní horizontální gradient.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Která verze JDK funguje?** Java 8 nebo novější.  
- **Mohu gradient použít jak na tvary, tak na text?** Ano – stejná instance `LinearGradientPaint` může vyplňovat tvary i být použita pro tahy nebo výplně textu.

## Co je horizontální gradient a proč jej použít?
Horizontální gradient míchá barvy od levého okraje objektu k pravému, čímž vytváří plynulý přechod, který přidává hloubku a vizuální zajímavost. Je ideální pro moderní UI komponenty, zvýrazněné nadpisy nebo jemné pozadí v PDF či PostScript reportech. Použití **Linear Gradient Paint Java** vám umožní přesně řídit počáteční a koncové barvy, průhlednost a měřítko, což zajišťuje ostrý výsledek na jakémkoli zařízení nebo tiskárně.

## Předpoklady
Předtím, než se ponoříte do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Aspose.Page for Java knihovnu. Můžete si ji stáhnout z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import balíčků
Začněte importováním potřebných balíčků ve vašem Java projektu. Tyto importy vám poskytují přístup k grafickým primitivům, manipulaci s gradienty a API Aspose.Page.

Třída `PsDocument` představuje dokument PostScript, na který můžete kreslit grafiku.  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: vytvořit obdélník
Nejprve nastavte výstupní stream, dokument a obdélník, který bude hostit gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Krok 2: vytvořit horizontální lineární gradient paint
`LinearGradientPaint` je hlavní třída definující lineární přechod barev.  
Třída `LinearGradientPaint` představuje objekt paint, který vykresluje gradient podél přímky; zadáte počáteční a koncové body, barevné zastávky a volitelný `AffineTransform` pro jeho škálování na váš tvar.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Krok 3: vyplnit obdélník
Nyní vyplňte obdélník gradientem, který jsme právě definovali.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Krok 4: vyplnit text gradientem
Můžete také použít stejný gradient na text, čímž vytvoříte výrazný vizuální efekt.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Krok 5: obrysnout text gradientem
Nakonec obryste text pomocí gradientu jako barvy tahu.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| Gradient se roztažený | Nesprávné škálování `AffineTransform` | Ujistěte se, že šířka a výška transformace odpovídají rozměrům obdélníku (200 × 100 v příkladu). |
| Barvy vypadají vybledlé | Hodnoty alfa jsou nastaveny příliš nízko | Zvyšte alfa komponentu (čtvrtá hodnota v `new Color(r,g,b,alpha)`). |
| Text není viditelný | Paint nebyl nastaven před vykreslením textu | Zavolejte `document.setPaint(paint)` **před** jakýmkoli voláním `fillAndStrokeText` nebo `outlineText`. |

## Často kladené otázky
**Q:** Mohu používat Aspose.Page for Java v komerčních projektech?  
**A:** Ano, Aspose.Page for Java lze použít v komerčních projektech. Pro podrobnosti o licencování navštivte stránku [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Je k dispozici bezplatná zkušební verze?  
**A:** Ano, můžete získat bezplatnou zkušební verzi Aspose.Page for Java na stránce [Aspose.Page for Java free trial](https://releases.aspose.com/).

**Q:** Kde najdu další dokumentaci a podporu?  
**A:** Navštivte [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) pro komplexní zdroje. Pro komunitní pomoc se podívejte na [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Jak získat dočasnou licenci?  
**A:** Dočasnou licenci můžete získat na stránce [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q:** Jaké jsou systémové požadavky pro Aspose.Page for Java?  
**A:** Podrobné systémové požadavky najdete v [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

---

**Poslední aktualizace:** 2026-09-04  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit PostScript Gradient v Java – Přidat vertikální gradient](/page/java/postscript-gradient-addition/vertical/)
- [Jak přidat gradient: Diagonální gradient v Java PostScript pomocí Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Vytvořit PostScript Gradient – Radiální gradient v Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}