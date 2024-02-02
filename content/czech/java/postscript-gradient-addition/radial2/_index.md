---
title: Radiální přechod Java PostScript s Aspose.Page
linktitle: Radiální přechod Java PostScript s Aspose.Page
second_title: Aspose.Page Java API
description: Prozkoumejte podrobného průvodce přidáním radiálního přechodu do jazyka Java PostScript pomocí Aspose.Page pro úžasnou grafiku ve vašich aplikacích Java.
type: docs
weight: 13
url: /cs/java/postscript-gradient-addition/radial2/
---
## Úvod
Vítejte v našem podrobném průvodci přidáním Radial Gradient 2 do Java PostScript pomocí Aspose.Page for Java. Tento výukový program vás provede procesem vytváření dokumentu PostScript s krásným radiálním přechodem, který vylepší vaše aplikace Java o vizuálně přitažlivou grafiku.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost programování v Javě.
- Na vašem počítači je nainstalována sada Java Development Kit (JDK).
-  Aspose.Page for Java knihovnu, kterou si můžete stáhnout z[Aspose.Page Java dokumentace](https://reference.aspose.com/page/java/).
## Importujte balíčky
Ve svém projektu Java importujte potřebné balíčky pro Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Nastavte adresář dokumentů
Definujte cestu k adresáři dokumentů:
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Vytvořte výstupní proud
Vytvořte výstupní proud pro dokument PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Krok 3: Vytvořte možnosti uložení
Vytvořte možnosti uložení s velikostí A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Krok 4: Vytvořte dokument PS
Vytvořte nový dokument PS s otevřenou stránkou:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 5: Vytvořte kruh
Definujte kruh pomocí třídy Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Krok 6: Definujte barvy přechodu
Vytvořte pole barev a zlomků pro radiální přechod:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Krok 7: Vytvořte AffineTransform
Vytvořte AffineTransform pro radiální gradient:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Krok 8: Vytvořte radiální přechodovou barvu
Vytvořte RadialGradientPaint se zadanými parametry:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Krok 9: Nastavte kruh malování a vyplnění
Nastavte barvu a vyplňte kruh radiálním přechodem:
```java
document.setPaint(paint);
document.fill(circle);
```
## Krok 10: Zavřete stránku a uložte dokument
Zavřete aktuální stránku a uložte dokument:
```java
document.closePage();
document.save();
```
Gratulujeme! Úspěšně jste přidali Radial Gradient 2 v Java PostScript pomocí Aspose.Page for Java.
## Závěr
V tomto tutoriálu jsme prozkoumali, jak vylepšit vaše Java aplikace pomocí radiálních přechodů v PostScriptových dokumentech. Aspose.Page for Java poskytuje výkonnou sadu nástrojů pro vytváření úžasné grafiky, která vám umožní posunout vaše projekty Java na další úroveň.
## Nejčastější dotazy
### Otázka: Kde najdu dokumentaci k Aspose.Page for Java?
 Odpověď: Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Otázka: Jak si mohu stáhnout Aspose.Page for Java?
 A: Můžete si jej stáhnout z[stránka vydání](https://releases.aspose.com/page/java/).
### Otázka: Je k dispozici bezplatná zkušební verze?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Mohu získat dočasnou licenci pro Aspose.Page for Java?
 Odpověď: Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu hledat podporu komunity a účastnit se diskuzí?
 A: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).