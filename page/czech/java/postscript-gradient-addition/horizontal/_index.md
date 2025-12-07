---
date: 2025-12-07
description: Naučte se, jak přidat vodorovný gradient v Java PostScript pomocí Linear
  Gradient Paint Java s Aspose.Page pro Java.
language: cs
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Přidat gradient v Java PostScript pomocí LinearGradientPaint.
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání gradientu v Java PostScript pomocí Linear Gradient Paint Java

## Úvod
V tomto komplexním tutoriálu se dozvíte, jak vytvořit krásný horizontální gradient v dokumentu PostScript pomocí **Linear Gradient Paint Java**. Aspose.Page pro Java usnadňuje práci s PostScript, PDF a dalšími vektorovými formáty a třída `LinearGradientPaint` vám poskytuje detailní kontrolu nad přechody barev. Na konci tohoto průvodce budete schopni vykreslovat gradienty na tvary **a** text, což vašim dokumentům dodá profesionální a poutavý vzhled.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java (podporuje Linear Gradient Paint Java).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní gradient.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Která verze JDK funguje?** Java 8 nebo novější.  
- **Mohu použít gradient jak na tvary, tak na text?** Ano – můžete vyplnit tvary a obrysnout nebo vyplnit text stejným gradientem.

## Předpoklady
Předtím, než se ponoříte do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovna Aspose.Page for Java. Můžete si ji stáhnout z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import balíčků
Začněte importováním potřebných balíčků ve vašem Java projektu. Tyto importy vám poskytují přístup k grafickým primitivům, manipulaci s gradienty a API Aspose.Page.

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

## Krok 1: Vytvoření obdélníku
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

## Krok 2: Vytvoření horizontálního Linear Gradient Paint
Zde vytvoříme objekt **Linear Gradient Paint Java**, který definuje horizontální přechod barev. `AffineTransform` škáluje gradient tak, aby odpovídal šířce a výšce obdélníku.

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

## Krok 3: Vyplnění obdélníku
Nyní vyplňte obdélník gradientem, který jsme právě definovali.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Krok 4: Vyplnění textu gradientem
Můžete také použít stejný gradient na text, čímž vytvoříte výrazný vizuální efekt.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Krok 5: Obrys textu gradientem
Nakonec obkreslete text pomocí gradientu jako barvy obrysu.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| Gradient se zdá natažený | Nesprávné škálování `AffineTransform` | Zajistěte, aby šířka a výška transformace odpovídaly rozměrům obdélníku (200 × 100 v příkladu). |
| Barvy vypadají vybledlé | Hodnoty alfa jsou nastaveny příliš nízko | Zvyšte komponentu alfa (čtvrtá hodnota v `new Color(r,g,b,alpha)`). |
| Text není viditelný | Barva (paint) není nastavena před kreslením textu | Zavolejte `document.setPaint(paint)` **před** jakýmkoli voláním `fillAndStrokeText` nebo `outlineText`. |

## Často kladené otázky
### Mohu používat Aspose.Page for Java v komerčních projektech?
Ano, Aspose.Page for Java lze používat v komerčních projektech. Pro podrobnosti o licencování navštivte [Aspose.Purchase](https://purchase.aspose.com/buy).

### Je k dispozici bezplatná zkušební verze?
Ano, můžete získat bezplatnou zkušební verzi Aspose.Page for Java [zde](https://releases.aspose.com/).

### Kde najdu další dokumentaci a podporu?
Navštivte [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) pro komplexní zdroje. Pro komunitní podporu se podívejte na [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### Jak mohu získat dočasnou licenci?
Dočasnou licenci můžete získat na [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Jaké jsou systémové požadavky pro Aspose.Page for Java?
Podívejte se do [dokumentace](https://reference.aspose.com/page/java/) pro podrobné systémové požadavky.

---

**Poslední aktualizace:** 2025-12-07  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}