---
title: Přidejte průhledný obrázek v Java PostScript
linktitle: Přidejte průhledný obrázek v Java PostScript
second_title: Aspose.Page Java API
description: Prozkoumejte bezproblémovou integraci průhledných obrázků do dokumentů Java PostScript s Aspose.Page for Java. Zvyšte své vizualizace dokumentů bez námahy.
type: docs
weight: 10
url: /cs/java/postscript-transparency/add-transparent-image/
---
## Úvod
Ve světě Java PostScriptu zvýšení vizuální přitažlivosti dokumentů často zahrnuje přidání průhledných obrázků. Tento tutoriál vás provede procesem začlenění průhledných obrázků do vašich dokumentů Java PostScript pomocí výkonné knihovny Aspose.Page for Java.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovanou nejnovější verzi JDK.
2.  Aspose.Page for Java: Stáhněte a nainstalujte knihovnu Aspose.Page for Java z[webová stránka](https://releases.aspose.com/page/java/).
3. Adresář dokumentů: Vytvořte v systému adresář, kam budete ukládat dokumenty Java PostScript.
4. Průsvitný obrazový soubor: Připravte průsvitný obrazový soubor (např. "mask1.png"), který použijete ve výukovém programu.
## Importujte balíčky
Do svého projektu Java naimportujte potřebné balíčky, abyste mohli využít funkcí poskytovaných Aspose.Page for Java. Zde je ukázkový fragment kódu:
```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Nastavte barvu pozadí
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
// Pro vizuální kontrast přidejte pod obrázky červený obdélník
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```
## Krok 2: Přeložte souřadnice
```java
// Přeložte na konkrétní pozici na stránce
document.writeGraphicsSave();
document.translate(20, 100);
```
## Krok 3: Vytvořte objekt obrázku
```java
// Vytvořte obrázek z průsvitného souboru obrázku
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```
## Krok 4: Přidejte neprůhledný obrázek
```java
// Přidejte obrázek do dokumentu jako neprůhledný obrázek RGB
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```
## Krok 5: Přidejte průhledný obrázek
```java
// Přidejte obrázek do dokumentu jako průhledný obrázek
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```
## Krok 6: Uložit a zavřít
```java
// Uložte a zavřete dokument
document.writeGraphicsRestore();
document.closePage();
document.save();
```
## Závěr
Gratulujeme! Úspěšně jste se naučili přidávat průhledné obrázky do dokumentů Java PostScript pomocí Aspose.Page for Java. Experimentujte s různými obrázky a pozicemi a vytvořte vizuálně úžasné dokumenty.
## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými knihovnami Java?
Ano, Aspose.Page for Java lze hladce integrovat s jinými knihovnami Java, aby se zlepšily možnosti zpracování dokumentů.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi Aspose.Page for Java z[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Dočasnou licenci můžete získat od[tento odkaz](https://purchase.aspose.com/temporary-license/).
### Existují nějaká fóra pro Aspose.Page pro podporu Java?
 Ano, navštivte[Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.
### Kde najdu dokumentaci k Aspose.Page for Java?
 Viz komplexní[dokumentace](https://reference.aspose.com/page/java/) pro podrobné informace o Aspose.Page for Java.