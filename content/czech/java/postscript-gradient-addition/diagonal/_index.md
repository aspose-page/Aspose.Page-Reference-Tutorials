---
title: Přidejte diagonální přechod v Java PostScript
linktitle: Přidejte diagonální přechod v Java PostScript
second_title: Aspose.Page Java API
description: Vylepšete své dokumenty Java PostScript pomocí diagonálních přechodů pomocí Aspose.Page for Java. Postupujte podle našeho podrobného průvodce a bez námahy přidejte zářivé barevné přechody.
type: docs
weight: 10
url: /cs/java/postscript-gradient-addition/diagonal/
---
## Úvod
Vítejte v našem podrobném průvodci přidáním diagonálního přechodu do jazyka Java PostScript pomocí Aspose.Page for Java. V tomto tutoriálu vás provedeme celým procesem a rozdělíme každý příklad do několika kroků. Jako zkušený autor SEO zajistím, že obsah bude nejen informativní, ale také optimalizovaný pro vyhledávače, takže vývojáři a nadšenci budou snadno sledovat.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
- Integrované vývojové prostředí (IDE) jako Eclipse nebo IntelliJ.
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
## Krok 1: Vytvořte výstupní proud pro dokument PostScript
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## Krok 2: Vytvořte možnosti uložení s velikostí A4
```java
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
```
## Krok 3: Vytvořte nový dokument PS
```java
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 4: Vytvořte obdélník
```java
//Vytvořte obdélník
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Krok 5: Vytvořte přechodovou transformaci
```java
//Vytvořte přechodovou transformaci. Složky měřítka se musí rovnat šířce a výšce obdélníku.
// Komponenty překladu jsou posuny obdélníku.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Otočte přechod, poté škálujte a překládejte pro viditelný barevný přechod
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```
## Krok 6: Vytvořte barvu s diagonálním lineárním přechodem
```java
// Vytvořte diagonální lineární přechodovou barvu
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## Krok 7: Nastavte Malování a Vyplňte obdélník
```java
// Nastavte barvu a vyplňte obdélník
document.setPaint(paint);
document.fill(rectangle);
```
## Krok 8: Zavřete aktuální stránku a uložte dokument
```java
// Zavřete aktuální stránku a uložte dokument
document.closePage();
document.save();
```
Pomocí těchto kroků úspěšně přidáte diagonální přechod v Java PostScript pomocí Aspose.Page for Java.
## Závěr
Gratulujeme! Naučili jste se, jak vylepšit své dokumenty Java PostScript pomocí diagonálních přechodů pomocí Aspose.Page for Java. Experimentujte s různými parametry, abyste dosáhli jedinečných vizuálních efektů.
## Často kladené otázky
### Otázka: Mohu tuto knihovnu použít pro jiné grafické operace v Javě?
Odpověď: Ano, Aspose.Page for Java poskytuje řadu funkcí pro práci s PostScriptem a dalšími grafickými prvky.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Kde najdu dokumentaci k Aspose.Page for Java?
 Odpověď: Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Otázka: Jak si mohu zakoupit licenci pro Aspose.Page for Java?
 A: Můžete si koupit licenci[tady](https://purchase.aspose.com/buy).
### Otázka: Potřebujete pomoc nebo máte otázky?
 A: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).