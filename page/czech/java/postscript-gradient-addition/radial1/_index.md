---
title: Zvládnutí radiálních přechodů v Java PostScript s Aspose.Page
linktitle: Zvládnutí radiálních přechodů v Javě
second_title: Aspose.Page Java API
description: Naučte se přidávat úžasné radiální přechody v Java PostScript pomocí Aspose.Page for Java. Vylepšete své PostScriptové dokumenty pomocí tohoto podrobného průvodce.
weight: 12
url: /cs/java/postscript-gradient-addition/radial1/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí radiálních přechodů v Java PostScript s Aspose.Page

## Úvod
Vítejte v našem podrobném průvodci, jak přidat radiální gradient v Java PostScript pomocí Aspose.Page. V tomto tutoriálu vás provedeme procesem vytváření dokumentu PostScript s krásným radiálním přechodem. Aspose.Page for Java je výkonná knihovna, která umožňuje bezproblémovou práci se soubory PostScript.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Java.
-  Aspose.Page for Java: Stáhněte si a nainstalujte knihovnu Aspose.Page z[tady](https://releases.aspose.com/page/java/).
- Integrované vývojové prostředí (IDE): Vyberte si preferované Java IDE, jako je Eclipse nebo IntelliJ.
## Importujte balíčky
Začněte importem potřebných balíčků, abyste mohli začít s projektem Java PostScript:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Vytvořte obdélník
Začněme vytvořením obdélníku v našem PostScriptovém dokumentu:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
//Vytvořte obdélník
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```
## Krok 2: Definujte barvy a zlomky
Definujte pole barev a zlomků pro radiální přechod:
```java
// Vytvořte pole barev a zlomků pro přechod
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```
## Krok 3: Vytvořte radiální přechodovou barvu
Vytvořte radiální přechodovou barvu pro obdélník:
```java
// Vytvořte radiální gradientní barvu
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(300, 200), 100, new Point2D.Float(300, 200),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Krok 4: Nastavte Malování a Vyplňte obdélník
Nastavte barvu a vyplňte obdélník radiálním přechodem:
```java
// Nastavte barvu
document.setPaint(paint);
// Vyplňte obdélník
document.fill(rectangle);
```
## Krok 5: Zavřete a uložte
Nakonec zavřete aktuální stránku a uložte dokument:
```java
// Zavřít aktuální stránku
document.closePage();
// Uložte dokument
document.save();
```
Tím je dokončen proces přidání radiálního gradientu do vašeho dokumentu Java PostScript pomocí Aspose.Page.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vylepšit své PostScriptové dokumenty pomocí radiálních přechodů pomocí Aspose.Page for Java. Experimentujte s různými barvami a konfiguracemi a vytvořte úžasné vizuální efekty.
## Nejčastější dotazy
### Mohu používat Aspose.Page for Java v komerčních projektech?
 Ano, Aspose.Page pro Javu můžete používat v komerčních projektech. Podrobnosti o licencích naleznete na adrese[tady](https://purchase.aspose.com/buy).
### Kde najdu dokumentaci k Aspose.Page for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Je k dispozici bezplatná zkušební verze?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Potřebujete podporu komunity?
 Připojte se ke komunitě Aspose.Page[Fórum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
