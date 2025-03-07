---
title: Přidejte vzor dlaždic textury v jazyce Java PostScript
linktitle: Přidejte vzor dlaždic textury v jazyce Java PostScript
second_title: Aspose.Page Java API
description: Pomocí Aspose.Page for Java můžete do dokumentů PostScript bez námahy přidávat vzory dlaždic textury. Prozkoumejte našeho průvodce bezproblémovou integrací pro kreativní možnosti.
weight: 10
url: /cs/java/postscript-texture-patterns/add-texture-tiling-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte vzor dlaždic textury v jazyce Java PostScript

## Úvod
V oblasti vývoje Java je běžným požadavkem vytváření složitých vzorů a textur v PostScriptových dokumentech. Aspose.Page for Java se ukazuje jako cenný nástroj pro dosažení tohoto úkolu bez námahy. V tomto tutoriálu vás provedeme procesem přidání vzoru textury do dokumentu Java PostScript pomocí Aspose.Page.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programovacího jazyka Java.
- Znalost struktury dokumentu PostScript.
-  Nainstalovaná knihovna Aspose.Page for Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
## Importujte balíčky
Začněte importem potřebných balíčků pro váš projekt Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Vytvořte dokument PostScript
Začněte vytvořením nového dokumentu PostScript, zadáním výstupního proudu a možností uložení. Ujistěte se, že máte nakonfigurované potřebné cesty.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 2: Nastavení grafického prostředí
Nastavte grafické prostředí překladem počátku a vytvořením BufferedImage ze souboru obrázku textury.
```java
document.writeGraphicsSave();
document.translate(200, 100);
// Vytvořte objekt BufferedImage ze souboru obrázku
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## Krok 3: Vytvořte štětec na texturu
Definujte texturový štětec z obrázku a určete oblast, která má být pokryta texturou.
```java
// Vytvořte oblast obrázku s dvojnásobnou šířkou
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Vytvořte texturový štětec z obrázku
TexturePaint paint = new TexturePaint(image, imageArea);
```
## Krok 4: Nakreslete a vyplňte tvary
Vytvořte obdélník a vyplňte jej definovaným texturním štětcem. Navíc nakreslete a načrtněte tvar pro vizuální přitažlivost.
```java
// Vytvořte obdélník
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Nastavte tento štětec textury jako aktuální barvu
document.setPaint(paint);
// Vyplňte obdélník
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## Krok 5: Přidejte text se vzorem textury
Přidejte do dokumentu text a vyplňte/potáhněte jej vzorem textury. Přizpůsobte písmo, pozici a další parametry podle potřeby.
```java
// Vyplňte text vzorem textury
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Ohraničte text vzorkem textury
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Krok 6: Uložit a zavřít
Dokončete proces zavřením aktuální stránky, uložením dokumentu a zajištěním bezproblémového provedení.
```java
// Zavřít aktuální stránku
document.closePage();
// Uložte dokument
document.save();
```
## Závěr
Gratulujeme! Úspěšně jste přidali vzor dlaždic textury do dokumentu Java PostScript pomocí Aspose.Page for Java. Neváhejte a prozkoumejte další možnosti přizpůsobení a využijte plný potenciál této výkonné knihovny.

## FAQ
### Je Aspose.Page for Java vhodný pro začátečníky?
Absolutně! Aspose.Page for Java poskytuje komplexní dokumentaci, takže je přístupná pro vývojáře všech úrovní dovedností.
### Mohu integrovat Aspose.Page for Java do svého stávajícího projektu Java?
 Ano, Aspose.Page for Java můžete snadno integrovat do svého projektu podle poskytnuté dokumentace[tady](https://reference.aspose.com/page/java/).
### Kde mohu najít podporu nebo diskutovat o dotazech souvisejících s Aspose.Page?
 Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) zapojit se do komunity a vyhledat pomoc.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Návštěva[tento odkaz](https://purchase.aspose.com/temporary-license/) získat dočasnou licenci.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
