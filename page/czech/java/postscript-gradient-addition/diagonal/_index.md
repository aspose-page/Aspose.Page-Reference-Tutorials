---
date: 2025-12-07
description: Vylepšete své Java PostScript dokumenty pomocí diagonálních gradientů
  s Aspose.Page Java. Naučte se, jak přidat gradientové efekty pomocí LinearGradientPaint
  v Javě a snadno vytvořit živé barevné přechody.
language: cs
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Přidat úhlopříčný gradient v Java PostScript pomocí Aspose.Page Java
url: /java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání diagonálního gradientu v Java PostScript pomocí Aspose.Page Java

## Úvod
Pokud chcete obohatit soubor PostScript o plynulý diagonální barevný přechod, **Aspose.Page Java** to dělá překvapivě snadno. V tomto tutoriálu vás provedeme **tím, jak přidat gradient** krok za krokem pomocí třídy `LinearGradientPaint` z Java 2D. Na konci budete mít připravený úryvek kódu, který vytvoří PostScript dokument s živým diagonálním gradientem.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java.  
- **Která třída vytváří gradient?** `LinearGradientPaint`.  
- **Mohu změnit barvy?** Ano – upravte pole `Color[]`.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Jak dlouho trvá implementace?** Přibližně 10 minut pro základní gradient.

## Co je Aspose.Page Java?
Aspose.Page Java je výkonné API, které umožňuje vývojářům generovat, upravovat a konvertovat soubory PostScript a PDF bez potřeby jakéhokoli externího softwaru. Poskytuje kompletní grafické možnosti jazyka PostScript prostřednictvím čistého, objektově orientovaného rozhraní v Javě.

## Proč použít diagonální gradient?
Diagonální gradient přidává hloubku a vizuální zajímavost grafům, bannerům nebo jakémukoli grafickému prvku, který potřebuje moderní vzhled. Protože gradient běží od jednoho rohu k protilehlému, dobře funguje jako pozadí, skin tlačítka či dekorativní tvary.

## Požadavky
Než začnete, ujistěte se, že máte:

- Java Development Kit (JDK) 8 nebo vyšší.  
- IDE jako Eclipse, IntelliJ IDEA nebo VS Code.  
- **Aspose.Page for Java** knihovna – stáhněte nejnovější verzi z [oficiální stránky ke stažení](https://releases.aspose.com/page/java/).

## Import balíčků
Nejprve importujte třídy Java 2D a Aspose, které budete potřebovat. Tyto importy vám umožní přístup k definicím barev, geometrickým tvarům, malování gradientu a API pro PostScript dokument.

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

## Krok 1: Vytvoření výstupního proudu pro PostScript dokument
Začneme definováním složky, kam bude soubor uložen, a otevřením `FileOutputStream`. Tento proud přijme vygenerovaná data PostScriptu.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Krok 2: Vytvoření možností uložení s velikostí A4
`PsSaveOptions` vám umožňuje nastavit velikost stránky, rozlišení a další výstupní parametry. Zde použijeme výchozí velikost A4.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: Vytvoření nového PS dokumentu
Instancujte `PsDocument` pomocí výstupního proudu a možností uložení. Příznak `false` říká konstruktoru, aby automaticky neotevřel novou stránku – uděláme to později.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: Vytvoření obdélníku
Definujte obdélník, který bude vyplněn gradientem. Pozice obdélníku (200, 100) a rozměry (200 × 100) jsou zvoleny tak, aby byl gradient dobře viditelný.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Krok 5: Vytvoření transformace gradientu
`AffineTransform` nám umožňuje otáčet, škálovat a posouvat gradient tak, aby běžel diagonálně přes obdélník. Níže uvedený výpočet určuje přeponu a upravuje poměr škálování.

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

## Krok 6: Vytvoření diagonálního lineárního gradientu
Zde je jádro **tím, jak přidat gradient** – vytvoříme `LinearGradientPaint`, který sahá od levého horního rohu obdélníku k pravému dolnímu, s použitím dříve definované transformace. `MultipleGradientPaint.CycleMethod.NO_CYCLE` zajistí, že se gradient neopakuje.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Krok 7: Nastavení barvy a vyplnění obdélníku
Aplikujte gradientní barvu na dokument a vyplňte tvar obdélníku. Tento krok vykreslí diagonální barevný přechod na stránku PostScriptu.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Krok 8: Uzavření aktuální stránky a uložení dokumentu
Nakonec zavřete stránku, vyprázdněte proud a uložte soubor. Výsledný soubor `DiagonalGradient_outPS.ps` lze otevřít v libovolném prohlížeči PostScriptu.

```java
// Close current page and save the document
document.closePage();
document.save();
```

Po dokončení těchto osmi kroků jste úspěšně přidali diagonální gradient do PostScript dokumentu pomocí **Aspose.Page Java**. Klidně experimentujte s různými barvami, úhly a velikostmi obdélníku, abyste vytvořili vlastní vizuální efekty.

## Časté problémy a tipy
- **Gradient vypadá plochý** – zkontrolujte úhel otáčení; otočení o 45° vytvoří skutečnou diagonálu.  
- **Barvy vypadají vybledlé** – ujistěte se, že používáte `MultipleGradientPaint.ColorSpaceType.SRGB` pro přesné vykreslení barev.  
- **Chyba souboru nenalezen** – ověřte, že `dataDir` ukazuje na existující složku a aplikace má oprávnění k zápisu.

## Často kladené otázky

**Q: Mohu tuto knihovnu použít i pro jiné grafické operace v Javě?**  
A: Ano, Aspose.Page for Java poskytuje kompletní sadu kreslicích primitiv, renderování textu i možnosti práce s obrázky.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page Java?**  
A: Rozhodně. Plně funkční zkušební verzi si můžete stáhnout ze [stránky Aspose free trial](https://releases.aspose.com/).

**Q: Kde najdu dokumentaci k Aspose.Page Java?**  
A: Oficiální reference API je dostupná [zde](https://reference.aspose.com/page/java/).

**Q: Jak mohu zakoupit licenci pro Aspose.Page Java?**  
A: Licence lze zakoupit přímo přes [portál nákupu Aspose](https://purchase.aspose.com/buy).

**Q: Potřebujete pomoc nebo máte otázky?**  
A: Navštivte komunitní [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde vám pomohou jak inženýři Aspose, tak ostatní vývojáři.

**Poslední aktualizace:** 2025-12-07  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}