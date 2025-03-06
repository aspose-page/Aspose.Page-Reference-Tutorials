---
title: Přidejte šrafovací vzor v Java PostScript
linktitle: Přidejte šrafovací vzor v Java PostScript
second_title: Aspose.Page Java API
description: Naučte se přidávat podmanivé šrafovací vzory do dokumentů Java PostScript pomocí Aspose.Page. Zvyšte svůj vizuální obsah bez námahy.
weight: 10
url: /cs/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte šrafovací vzor v Java PostScript

## Úvod
Ve světě programování v jazyce Java je vylepšení vizuálních prvků běžným požadavkem pro vývojáře. Jedním ze zajímavých vizuálních vylepšení je přidání šrafovacích vzorů do PostScriptových dokumentů. Tento tutoriál vás provede procesem přidávání šrafovacích vzorů pomocí Aspose.Page pro Java.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující nastavení:
- Vývojové prostředí Java: Ujistěte se, že máte připravené vývojové prostředí Java.
-  Aspose.Page for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Page for Java. Můžete najít potřebné soubory[tady](https://releases.aspose.com/page/java/).
## Importujte balíčky
Chcete-li začít, importujte požadované balíčky do svého projektu Java. Použijte následující fragment kódu:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Nastavte počáteční parametry
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## Krok 2: Uložte stav grafiky a přeložte
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Krok 3: Vytvořte čtverec pro každý vzor
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Krok 4: Nastavte pero pro čtvercový obrys
```java
BasicStroke stroke = new BasicStroke(2);
```
## Krok 5: Iterujte přes šrafovací vzory
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (pokračujte zadaným kódem)
}
```
## Krok 6: Obnovte stav grafiky
```java
document.writeGraphicsRestore();
```
## Krok 7: Vyplňte text šrafovacím vzorem
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Krok 8: Obrys textu se šrafovacím vzorem
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Krok 9: Zavřete a uložte dokument
```java
document.closePage();
document.save();
```
Postupujte podle těchto kroků a pomocí Aspose.Page úspěšně přidáte šrafovací vzory do dokumentu Java PostScript.
## Závěr
Začlenění vizuálních prvků, jako jsou šrafovací vzory, může výrazně zvýšit přitažlivost vašich aplikací Java. Aspose.Page for Java činí tento proces bezproblémovým a umožňuje vám bez námahy vytvářet vizuálně ohromující PostScriptové dokumenty.
## Nejčastější dotazy
### Mohu používat Aspose.Page for Java s jinými frameworky Java?
Ano, Aspose.Page for Java je navržena tak, aby se hladce integrovala s různými frameworky Java.
### Je pro Aspose.Page k dispozici zkušební verze pro Javu?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu další návody a podporu pro Aspose.Page for Java?
 Prozkoumat[Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) za výukové programy a podporu komunity.
### Existuje komplexní dokumentační zdroj pro Aspose.Page for Java?
 Ano, podívejte se na dokumentaci[tady](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
