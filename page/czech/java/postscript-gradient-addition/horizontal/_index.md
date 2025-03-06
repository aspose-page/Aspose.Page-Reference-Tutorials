---
title: Přidejte horizontální přechod v Java PostScript
linktitle: Přidejte horizontální přechod v Java PostScript
second_title: Aspose.Page Java API
description: Naučte se, jak přidat vodorovný přechod v Java PostScript s Aspose.Page for Java. Vytvářejte vizuálně úžasné dokumenty bez námahy.
weight: 11
url: /cs/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte horizontální přechod v Java PostScript

## Úvod
Vítejte v tomto obsáhlém tutoriálu o přidání horizontálního přechodu do jazyka Java PostScript pomocí Aspose.Page for Java. Aspose.Page je výkonná Java knihovna, která umožňuje vývojářům pracovat s PostScriptem a dalšími formáty dokumentů. V tomto tutoriálu vás provedeme procesem vytváření PostScriptového dokumentu s horizontálním přechodem pomocí příkladů krok za krokem.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
- Aspose.Page pro knihovnu Java. Můžete si jej stáhnout z[Aspose.Page Java dokumentace](https://reference.aspose.com/page/java/).
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java. Tyto balíčky jsou klíčové pro práci s Aspose.Page.
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
## Krok 1: Vytvořte obdélník
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
//Vytvořte obdélník
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Krok 2: Vytvořte horizontální lineární přechodovou barvu
```java
// Vytvořte horizontální lineární přechodovou barvu. Složky měřítka v transformaci se musí rovnat šířce a výšce obdélníku.
// Komponenty překladu jsou posuny obdélníku.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Nastavte barvu
document.setPaint(paint);
```
## Krok 3: Vyplňte obdélník
```java
// Vyplňte obdélník
document.fill(rectangle);
```
## Krok 4: Vyplňte text přechodem
```java
// Vyplňte text přechodem
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Krok 5: Vytáhněte text pomocí přechodu
```java
// Přetáhněte text s přechodem
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Závěr
Gratulujeme! Úspěšně jste přidali horizontální přechod v Java PostScript pomocí Aspose.Page for Java. Tento kurz vám poskytl podrobného průvodce krok za krokem, který vám pomůže vytvořit vizuálně přitažlivé dokumenty PostScript.
## Často kladené otázky
### Mohu používat Aspose.Page for Java v komerčních projektech?
Ano, Aspose.Page for Java lze použít v komerčních projektech. Podrobnosti o licencích naleznete na adrese[Aspose.Purchase](https://purchase.aspose.com/buy).
### Je k dispozici bezplatná zkušební verze?
 Ano, máte přístup k bezplatné zkušební verzi Aspose.Page for Java[tady](https://releases.aspose.com/).
### Kde najdu další dokumentaci a podporu?
 Navštivte[Aspose.Page Java dokumentace](https://reference.aspose.com/page/java/) pro komplexní zdroje. Pro podporu komunity zkontrolujte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).
### Jak mohu získat dočasnou licenci?
 Dočasnou licenci můžete získat od[Aspose.Purchase](https://purchase.aspose.com/temporary-license/).
### Jaké jsou systémové požadavky pro Aspose.Page for Java?
 Odkazovat na[dokumentace](https://reference.aspose.com/page/java/) pro podrobné systémové požadavky.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
