---
date: 2026-02-13
description: Naučte se, jak přidat gradient v Java PostScript pomocí Linear Gradient
  Paint Java s Aspose.Page pro Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Jak přidat gradient v Java PostScript pomocí lineárního Gradient Paint
url: /cs/java/postscript-gradient-addition/horizontal/
weight: 11
---

 with translation.

Check for any missed items: The "## Quick Answers" list items need translation. Ensure bullet dash and spacing same.

Also ensure code block placeholders remain unchanged.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat gradient v Java PostScript pomocí Linear Gradient Paint

## Úvod
V tomto komplexním tutoriálu objevíte **jak přidat gradient** do PostScript dokumentu pomocí Javy. Provedeme vás vytvořením krásného horizontálního gradientu s využitím **Linear Gradient Paint Java**, třídy, která vám poskytuje pixel‑dokonalou kontrolu nad přechody barev. S Aspose.Page for Java můžete vykreslovat gradienty jak na tvary **tak** i na text, čímž vašim dokumentům dodáte uhlazený, poutavý vzhled, který vyniká.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java (supports Linear Gradient Paint Java).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní gradient.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Která verze JDK funguje?** Java 8 nebo novější.  
- **Mohu použít gradient jak na tvary, tak na text?** Ano – můžete vyplnit tvary a obrysnout nebo vyplnit text stejným gradientem.

## Co je horizontální gradient a proč jej použít?
Horizontální gradient plynule míchá barvy zleva doprava přes tvar nebo text. Je ideální pro tvorbu moderních UI prvků, zvýrazněných nadpisů nebo jemných pozadí v reportech. Použití **Linear Gradient Paint Java** vám umožní definovat přesné počáteční a koncové barvy, průhlednost a měřítko, takže výsledek vypadá ostře na jakémkoli zařízení.

## Předpoklady
Než se ponoříte do kódu, ujistěte se, že máte následující:

- Nainstalovaný Java Development Kit (JDK) na vašem počítači.  
- Knihovnu Aspose.Page for Java. Můžete si ji stáhnout z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

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

## Krok 1: Vytvořit obdélník
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

## Krok 2: Vytvořit horizontální Linear Gradient Paint
Zde vytvoříme objekt **Linear Gradient Paint Java**, který definuje horizontální přechod barev. `AffineTransform` měří gradient tak, aby odpovídal šířce a výšce obdélníku.

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

## Krok 3: Vyplnit obdélník
Nyní vyplňte obdélník gradientem, který jsme právě definovali.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Krok 4: Vyplnit text gradientem
Můžete také použít stejný gradient na text, čímž vytvoříte výrazný vizuální efekt.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Krok 5: Obrysovat text gradientem
Nakonec obkreslete text pomocí gradientu jako barvy obrysu.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| Gradient se zdá natažený | Nesprávné škálování `AffineTransform` | Ujistěte se, že šířka a výška transformace odpovídají rozměrům obdélníku (200 × 100 v příkladu). |
| Barvy vypadají vybledlé | Hodnoty alfa jsou nastaveny příliš nízko | Zvyšte komponentu alfa (čtvrtá hodnota v `new Color(r,g,b,alpha)`). |
| Text není viditelný | Barva (paint) není nastavena před vykreslením textu | Zavolejte `document.setPaint(paint)` **před** jakýmkoli voláním `fillAndStrokeText` nebo `outlineText`. |

## Často kladené otázky
**Q:** Mohu použít Aspose.Page for Java v komerčních projektech?  
**A:** Ano, Aspose.Page for Java může být použita v komerčních projektech. Pro podrobnosti o licencování navštivte [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Je k dispozici bezplatná zkušební verze?  
**A:** Ano, můžete získat bezplatnou zkušební verzi Aspose.Page for Java [zde](https://releases.aspose.com/).

**Q:** Kde mohu najít další dokumentaci a podporu?  
**A:** Navštivte [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) pro komplexní zdroje. Pro komunitní podporu se podívejte na [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Jak mohu získat dočasnou licenci?  
**A:** Dočasnou licenci můžete získat na [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**Q:** Jaké jsou systémové požadavky pro Aspose.Page for Java?  
**A:** Podívejte se na [documentation](https://reference.aspose.com/page/java/) pro podrobné systémové požadavky.

---

**Poslední aktualizace:** 2026-02-13  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}