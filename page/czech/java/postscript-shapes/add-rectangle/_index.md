---
title: Přizpůsobte Java PostScript - Přidání obdélníků pomocí Aspose.Page
linktitle: Přidat obdélník v Java PostScript
second_title: Aspose.Page Java API
description: Prozkoumejte podrobného průvodce přidáváním živých obdélníků do dokumentů Java PostScript pomocí Aspose.Page for Java. Vylepšete přizpůsobení dokumentu bez námahy!
weight: 11
url: /cs/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přizpůsobte Java PostScript - Přidání obdélníků pomocí Aspose.Page

## Úvod
Chcete vylepšit své dokumenty Java PostScript živými obdélníky? Už nehledejte! V tomto podrobném průvodci prozkoumáme, jak používat Aspose.Page pro Java k přidávání obdélníků do vašich PostScriptových dokumentů. Aspose.Page je výkonná knihovna, která poskytuje robustní funkce pro práci se soubory PostScript, takže je ideální volbou pro vývojáře, kteří chtějí manipulovat a přizpůsobovat své dokumenty.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Page for Java. Pokud ne, stáhněte si jej z[Aspose.Page pro dokumentaci Java](https://reference.aspose.com/page/java/).
- Vývojové prostředí Java nastavené na vašem počítači.
## Importujte balíčky
Ve svém projektu Java začněte importováním potřebných balíčků:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Kurz: Přidání obdélníků v Java PostScript
## Krok 1: Nastavte barvu pro obdélník výplně
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
// Sada barvy pro vyplnění obdélníku
document.setPaint(Color.ORANGE);        
// Vyplňte první obdélník
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Krok 2: Nastavte barvu pro obdélník tahu
```java
// Nastavit barvu pro hlazení obdélníku
document.setPaint(Color.RED);
// Nastavit zdvih
document.setStroke(new BasicStroke(3));
// Vytáhněte (obkreslete) druhý obdélník
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Krok 3: Zavřete aktuální stránku a uložte dokument
```java
// Zavřít aktuální stránku
document.closePage();
// Uložte dokument
document.save();
```
Gratulujeme! Pomocí Aspose.Page jste do dokumentu Java PostScript úspěšně přidali zářivé obdélníky.
## Závěr
V tomto tutoriálu jsme prozkoumali proces vylepšení vašich dokumentů Java PostScript pomocí obdélníků pomocí Aspose.Page for Java. Tato výkonná knihovna otevírá svět možností pro vývojáře, kteří chtějí snadno upravovat a manipulovat se svými dokumenty.
Bavte se experimentováním s různými tvary a barvami, aby byly vaše dokumenty vizuálně přitažlivé!
## Často kladené otázky

### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale podobné knihovny jsou dostupné i pro jiné jazyky.
### Je k dispozici zkušební verze Aspose.Page for Java?
 Ano, funkce Aspose.Page for Java můžete prozkoumat pomocí[zkušební verze zdarma](https://releases.aspose.com/).
### Kde najdu další pomoc a diskuze?
 Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) zapojit se do komunity a získat pomoc.
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde si mohu zakoupit licencovanou verzi Aspose.Page for Java?
 Kupte si licencovanou verzi[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
