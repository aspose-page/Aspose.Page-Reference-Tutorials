---
date: 2026-02-18
description: Naučte se, jak kreslit obdélníkové tvary v Java PostScript pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce ukazuje, jak nastavit barvu výplně, nastavit barvu
  obdélníku v Javě a vytvořit živé grafiky, přičemž vysvětluje, jak efektivně kreslit
  obdélník.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Jak v Java PostScript nakreslit obdélník pomocí Aspose.Page
url: /cs/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nakreslit obdélník v Java PostScript pomocí Aspose.Page

## Úvod
Pokud potřebujete **how to draw rectangle** tvary uvnitř souboru Java PostScript, jste na správném místě. V tomto tutoriálu vás provedeme používáním Aspose.Page pro Java k přidání barevných obdélníků, řízení jejich výplně a obrysu a uložení výsledku jako dokumentu PostScript. Uvidíte přesně **how to set paint**, jak definovat geometrii obdélníku a proč je tento přístup ideální pro programové generování tisknutelných grafiky. Na konci průvodce také pochopíte širší kontext technik **draw rectangle java** a jak zapadají do workflow **java awt rectangle drawing**.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java  
- **Mohu změnit barvy obdélníku?** Ano – použijte `setPaint` s libovolnou `java.awt.Color`  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci  
- **Jaká velikost stránky je použita v příkladu?** A4 (default `PsSaveOptions`)  
- **Je kód kompatibilní s Java 8+?** Rozhodně – používá standardní třídy AWT  

## Co je “How to Draw Rectangle” v PostScriptu?
Kreslení obdélníku v dokumentu PostScript znamená definovat obdélníkovou oblast a buď ji vyplnit, obkreslit její konturu, nebo obojí. S Aspose.Page můžete toto provést pomocí známých tříd **java awt rectangle drawing**, což usnadňuje čitelnost a údržbu kódu.

## Proč použít Aspose.Page pro grafiku obdélníků?
- **Cross‑platform**: Generuje standardní PostScript, který funguje na jakémkoli tiskárně.  
- **Fine‑grained control**: Můžete nastavit barvy výplně, barvy obrysu a šířky čar nezávisle.  
- **No external dependencies**: Používá pouze vestavěné třídy geometrie AWT, takže nepotřebujete další grafické knihovny.  

## Předpoklady
Před tím, než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Java.  
- Knihovna Aspose.Page pro Java nainstalována. Pokud ne, stáhněte ji z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Vývojové prostředí Java nastavené na vašem počítači.

## Import balíčků
Ve vašem Java projektu začněte importováním potřebných balíčků. Tyto importy vám poskytují přístup ke třídám AWT `Color`, `BasicStroke` a `Rectangle2D`, stejně jako k základním třídám pro práci s dokumenty v Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Průvodce krok za krokem pro kreslení obdélníku v Java PostScript

### Krok 1: Nastavení barvy pro vyplnění obdélníku  
**How to set paint** – vybereme oranžovou barvu výplně pro první obdélník. Toto demonstruje schopnost **set rectangle color java**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Krok 2: Nastavení barvy pro obrys obdélníku  
**Set rectangle color java** – nyní změníme barvu na červenou a definujeme šířku obrysu. Tato část příkladu ukazuje, jak **draw rectangle java** s vlastní tloušťkou čáry.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Krok 3: Zavřít aktuální stránku a uložit dokument  
Po kreslení zavřeme stránku a uložíme soubor. Zavření stránky zajišťuje, že všechny kreslicí příkazy jsou vyprázdněny do PostScriptového proudu.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Běžné případy použití kreslení obdélníků
- **Invoice or receipt generation** – obdélníky slouží jako okraje nebo zvýrazňují sekce.  
- **Label creation** – kreslete barevné rámečky k oddělení informací o produktu.  
- **Simple charts** – použijte vyplněné obdélníky jako prvky sloupcových grafů.  
- **Custom printable forms** – kombinujte obdélníky s textem pro vytvoření polí formuláře.  

## Běžné problémy a tipy
- **File path errors** – ujistěte se, že `dataDir` končí souborovým oddělovačem (`/` nebo `\\`).  
- **License exceptions** – zkušební verze přidává vodoznak; získejte plnou licenci pro produkční použití.  
- **Color visibility** – některé tiskárny mohou interpretovat určité RGB hodnoty odlišně; nejprve otestujte jednoduchý černý obdélník.  
- **Memory usage** – pro velké dokumenty zvažte vyprázdnění proudu po každé stránce (`document.closePage()`).  

## Často kladené otázky

**Q:** *Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?*  
A: Aspose.Page primárně podporuje Java, ale podobné knihovny jsou k dispozici pro jiné jazyky.

**Q:** *Je k dispozici zkušební verze Aspose.Page pro Java?*  
A: Ano, můžete prozkoumat funkce Aspose.Page pro Java pomocí [free trial version](https://releases.aspose.com/).

**Q:** *Kde mohu najít další pomoc a diskuze?*  
A: Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39), kde můžete komunikovat s komunitou a získat pomoc.

**Q:** *Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?*  
A: Získejte dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

**Q:** *Kde mohu zakoupit licencovanou verzi Aspose.Page pro Java?*  
A: Kupte licencovanou verzi [zde](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Mohu měnit velikost obdélníku dynamicky?*  
A: Ano – jednoduše upravte parametry `Rectangle2D.Float(x, y, width, height)` před voláním `fill` nebo `draw`.

**Q:** *Je možné přidat text uvnitř obdélníku?*  
A: Rozhodně. Po nakreslení obdélníku použijte `document.drawString(...)` s požadovaným fontem a pozicí.

**Q:** *Podporuje Aspose.Page i jiné tvary, jako kruhy nebo mnohoúhelníky?*  
A: Ano, API poskytuje metody jako `drawEllipse` a `drawPolygon` pro různé vektorové grafiky.

## Závěr
V tomto průvodci jsme ukázali, jak **how to draw rectangle** tvary v Java PostScript dokumentu, pokryli **how to set paint** a ukázali, jak **set rectangle color java** pomocí Aspose.Page. Nyní máte pevný základ pro vytváření živých tisknutelných grafik, ať už vytváříte faktury, štítky nebo vlastní formuláře. Nebojte se experimentovat s různými barvami, styly čar a dalšími tvary AWT, abyste obohatili výstup.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}