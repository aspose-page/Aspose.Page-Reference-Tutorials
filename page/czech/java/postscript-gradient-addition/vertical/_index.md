---
title: Přidejte vertikální přechod v Java PostScript
linktitle: Přidejte vertikální přechod v Java PostScript
second_title: Aspose.Page Java API
description: Prozkoumejte podrobného průvodce přidáváním vertikálních přechodů v Java PostScript pomocí Aspose.Page for Java. Vylepšete své dokumenty bez námahy pomocí živých vizuálů.
weight: 14
url: /cs/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte vertikální přechod v Java PostScript

## Úvod
Vítejte v tomto podrobném průvodci přidáním vertikálního přechodu do jazyka Java PostScript pomocí Aspose.Page for Java. Pokud chcete vylepšit svůj dokument pomocí poutavých přechodů, je tento výukový program právě pro vás. Aspose.Page for Java poskytuje výkonné nástroje pro bezproblémovou manipulaci s PostScriptovými dokumenty.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Aspose.Page pro knihovnu Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
## Importujte balíčky
Ve svém projektu Java naimportujte potřebné balíčky, abyste mohli začít:
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
Nyní si rozdělme proces přidávání vertikálního přechodu v Java PostScript do několika kroků.
## Krok 1: Nastavte adresář dokumentů
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
```
## Krok 2: Vytvořte výstupní proud pro dokument PostScript
```java
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Krok 3: Vytvořte možnosti uložení s velikostí A4
```java
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
```
## Krok 4: Vytvořte nový dokument PS
```java
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 5: Vytvořte obdélník
```java
//Vytvořte obdélník
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Krok 6: Nastavte barvy a zlomky pro přechod
```java
// Vytvořte pole barev a zlomků pro přechod.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Krok 7: Vytvořte přechodovou transformaci
```java
// Vytvořte přechodovou transformaci. Složky měřítka v transformaci se musí rovnat šířce a výšce obdélníku.
// Komponenty překladu jsou posuny obdélníku.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Otočte přechod o 90 stupňů kolem počátku
transform.rotate(90 * (Math.PI / 180));
```
## Krok 8: Vytvořte barvu s vertikálním lineárním přechodem
```java
// Vytvořte vertikální lineární přechodovou barvu.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Krok 9: Nastavte Malování a Vyplňte obdélník
```java
// Nastavte barvu
document.setPaint(paint);
// Vyplňte obdélník
document.fill(rectangle);
```
## Krok 10: Zavřete aktuální stránku a uložte dokument
```java
// Zavřít aktuální stránku
document.closePage();
// Uložte dokument
document.save();
```
Gratulujeme! Úspěšně jste přidali vertikální přechod do dokumentu Java PostScript pomocí Aspose.Page for Java.
## Závěr
tomto tutoriálu jsme prozkoumali proces vylepšení vašich dokumentů pomocí živých vertikálních přechodů pomocí Aspose.Page pro Java. Nyní můžete své manipulace s dokumenty posunout na další úroveň začleněním úžasných vizuálů.
## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými knihovnami Java?
Ano, Aspose.Page for Java je navržena tak, aby bezproblémově spolupracovala s jinými knihovnami Java.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu další dokumentaci?
 K dispozici je podrobná dokumentace[tady](https://reference.aspose.com/page/java/).
### Jak si mohu zakoupit Aspose.Page pro Java?
 Můžete si zakoupit Aspose.Page pro Java[tady](https://purchase.aspose.com/buy).
### Existuje fórum pro diskuse na Aspose.Page?
 Ano, můžete se připojit ke komunitnímu fóru[tady](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
