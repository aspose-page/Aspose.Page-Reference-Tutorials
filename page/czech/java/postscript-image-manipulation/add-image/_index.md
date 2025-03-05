---
title: Přidat obrázek v Java PostScript
linktitle: Přidat obrázek v Java PostScript
second_title: Aspose.Page Java API
description: Prozkoumejte bezproblémovou integraci Aspose.Page Java v tomto tutoriálu o přidávání obrázků do PostScriptových dokumentů. Zvyšte své možnosti manipulace s dokumenty.
type: docs
weight: 10
url: /cs/java/postscript-image-manipulation/add-image/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak přidat obrázky do dokumentu Java PostScript pomocí knihovny Aspose.Page for Java. Aspose.Page je výkonná knihovna, která poskytuje různé funkce pro práci se soubory PostScript a umožňuje vývojářům bezproblémově manipulovat a vylepšovat jejich dokumenty.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Page pro knihovnu Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
- Základní znalost programování v Javě.
## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java. Jako referenci použijte následující fragment kódu:
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Zápis grafiky Uložit
První krok zahrnuje zápis grafiky do dokumentu. To zajišťuje, že jakékoli transformace nebo úpravy provedené později lze v případě potřeby vrátit zpět.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## Krok 2: Přeložte a transformujte
Dále přeložte dokument a ze souboru obrázku vytvořte objekt BufferedImage. Pomocí AffineTransform použijte řadu transformací, jako je změna měřítka a rotace.
```java
document.translate(100, 100);
// Vytvořte objekt BufferedImage ze souboru obrázku
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Vytvořte transformaci obrazu
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## Krok 3: Přidejte obrázek do dokumentu
Nyní přidejte transformovaný obrázek do dokumentu.
```java
document.drawImage(image, transform, null);
```
## Krok 4: Napište Graphics Restore
Po přidání obrázku napište obnovu grafiky, abyste dokončili provedené změny.
```java
document.writeGraphicsRestore();
```
## Krok 5: Zavřete aktuální stránku a uložte
Zavřete aktuální stránku a uložte dokument.
```java
document.closePage();
document.save();
```
Opakujte tyto kroky pro přidání více obrázků nebo přizpůsobení transformací podle vašich požadavků.
## Závěr
 Gratulujeme! Úspěšně jste se naučili přidávat obrázky do dokumentu Java PostScript pomocí Aspose.Page for Java. Prozkoumat[dokumentace](https://reference.aspose.com/page/java/) pro pokročilejší vlastnosti a funkce.
## Nejčastější dotazy
### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale jsou dostupné i verze pro jiné programovací jazyky.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu podporu komunity a diskuse týkající se Aspose.Page for Java?
 Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.
### Existují nějaké další zdroje pro nákup Aspose.Page for Java?
 Knihovnu si můžete koupit[tady](https://purchase.aspose.com/buy).