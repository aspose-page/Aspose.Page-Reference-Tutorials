---
date: 2025-12-11
description: Naučte se, jak kreslit obdélníkové tvary v Java PostScript pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce ukazuje, jak nastavit barvu, nastavit barvu obdélníku
  v Javě a vytvořit živou grafiku.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Jak nakreslit obdélník v Java PostScript s Aspose.Page
url: /cs/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nakreslit obdélník v Java PostScript pomocí Aspose.Page

## Úvod
Pokud potřebujete **jak nakreslit obdélník** ve Java PostScript souboru, jste na správném místě. V tomto tutoriálu vás provedeme používáním Aspose.Page pro Java k přidání barevných obdélníků, řízení jejich výplně a obrysu a uložení výsledku jako PostScript dokumentu. Uvidíte přesně **jak nastavit paint**, jak definovat geometrii obdélníku a proč je tento přístup ideální pro programové generování tisknutelné grafiky.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java  
- **Mohu změnit barvy obdélníků?** Ano – použijte `setPaint` s libovolnou `java.awt.Color`  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci  
- **Jaká velikost stránky je v příkladu použita?** A4 (výchozí `PsSaveOptions`)  
- **Je kód kompatibilní s Java 8+?** Rozhodně – používá standardní třídy AWT  

## Požadavky
Než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.  
- Nainstalovanou knihovnu Aspose.Page for Java. Pokud ji nemáte, stáhněte ji z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Nastavené vývojové prostředí Javy na vašem počítači.

## Import balíčků
Ve vašem Java projektu začněte importováním potřebných balíčků:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak nakreslit obdélník v Java PostScript
Níže je kompletní pracovní postup rozdělený do přehledných kroků. Každý krok obsahuje krátké vysvětlení následované původním blokem kódu (beze změny).

### Krok 1: Nastavit paint pro vyplnění obdélníku  
**Jak nastavit paint** – vybereme oranžovou barvu výplně pro první obdélník.

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

### Krok 2: Nastavit paint pro obrys obdélníku  
**Nastavit barvu obdélníku java** – nyní změníme paint na červenou a definujeme šířku tahu.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Krok 3: Zavřít aktuální stránku a uložit dokument  
Po nakreslení zavřeme stránku a soubor uložíme.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Proč použít Aspose.Page pro grafiku obdélníků?
- **Cross‑platform**: Generuje standardní PostScript, který funguje na jakémkoli tiskárně.  
- **Fine‑grained control**: Můžete nezávisle nastavit barvy výplně, barvy obrysu a šířky čar.  
- **No external dependencies**: Používá pouze vestavěné třídy geometrie AWT.  

## Časté problémy a tipy
- **File path errors** – ujistěte se, že `dataDir` končí oddělovačem souborů (`/` nebo `\\`).  
- **License exceptions** – zkušební verze přidává vodoznak; pro produkční použití získejte plnou licenci.  
- **Color visibility** – některé tiskárny mohou interpretovat určité RGB hodnoty odlišně; nejprve otestujte jednoduchý černý obdélník.

## Závěr
V tomto průvodci jsme ukázali **jak nakreslit obdélník** ve Java PostScript dokumentu, pokryli **jak nastavit paint** a ukázali, jak **nastavit barvu obdélníku java** pomocí Aspose.Page. Klidně experimentujte s různými tvary, barvami a styly čar a vytvořte bohatou tisknutelnou grafiku pro zprávy, faktury nebo vlastní výtisky.

## Často kladené otázky

### Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale podobné knihovny jsou k dispozici i pro jiné jazyky.

### Je k dispozici zkušební verze Aspose.Page pro Java?
Ano, můžete si vyzkoušet funkce Aspose.Page pro Java pomocí [free trial version](https://releases.aspose.com/).

### Kde mohu najít další pomoc a diskuse?
Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39), kde můžete komunikovat s komunitou a získat podporu.

### Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?
Získejte dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Kde mohu zakoupit licencovanou verzi Aspose.Page pro Java?
Kupte licencovanou verzi [zde](https://purchase.aspose.com/buy).

**Další Q&A**

**Q:** *Mohu dynamicky měnit velikost obdélníku?*  
**A:** Ano – stačí upravit parametry `Rectangle2D.Float(x, y, width, height)` před voláním `fill` nebo `draw`.

**Q:** *Je možné přidat text uvnitř obdélníku?*  
**A:** Rozhodně. Po nakreslení obdélníku použijte `document.drawString(...)` s požadovaným fontem a pozicí.

**Q:** *Podporuje Aspose.Page i jiné tvary, jako kruhy nebo mnohoúhelníky?*  
**A:** Ano, API poskytuje metody jako `drawEllipse` a `drawPolygon` pro různé vektorové grafiky.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}