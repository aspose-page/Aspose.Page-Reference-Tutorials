---
date: 2025-12-03
description: Prozkoumejte, jak uložit jako PostScript a oříznout tvary pomocí Aspose.Page
  pro Javu. Naučte se nastavit styl čáry a použít oblast oříznutí při ořezávání grafiky
  v Javě.
language: cs
linktitle: Save as PostScript – Clipping in Java Page Manipulation
second_title: Aspose.Page Java API
title: Uložit jako PostScript – Ořezávání v manipulaci s Java stránkami
url: /java/page-manipulation/clipping/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení jako PostScript – Ořezávání v Java Page Manipulation

## Úvod
Když potřebujete **uložit jako PostScript** při tvorbě složitých grafik, ořezávání se stává vaším nejmocnějším spojencem. V Java Page Manipulation s Aspose.Page umožňuje ořezávání definovat přesné oblasti, kde jsou vykreslovací operace viditelné, a poskytuje tak jemnou kontrolu nad konečným výstupem. Tento tutoriál vás provede **tím, jak ořezávat tvary**, **nastavit styl tahu** a **použít oblast ořezávání** pomocí knihovny Aspose.Page pro Java, abyste mohli s jistotou vytvářet vylepšené soubory PostScript.

## Rychlé odpovědi
- **Co znamená „uložit jako PostScript“?**  
  Vytvoří soubor .ps, který ukládá vektorovou grafiku v jazyce PostScript, ideální pro tisk a vykreslování ve vysokém rozlišení.  
- **Která knihovna provádí ořezávání v Javě?**  
  Aspose.Page pro Java poskytuje jednoduché API pro `java graphics clipping`.  
- **Potřebuji licenci pro spuštění ukázky?**  
  Dočasná licence stačí pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu změnit vzhled tahu?**  
  Ano – použijte `set stroke style` s `BasicStroke` a upravte šířku, vzor čáry i konce.  
- **Je kód kompatibilní s Java 8+?**  
  Rozhodně, ukázka běží na jakémkoli runtime Java 8 nebo novějším.

## Co je „uložit jako PostScript“ v Aspose.Page?
Uložení dokumentu jako PostScript převádí vaše vykreslovací příkazy do jazyka popisu stránek PostScript. Výsledný soubor `.ps` lze otevřít v tiskárnách, prohlížečích nebo převést do PDF bez ztráty kvality.

## Proč používat ořezávání v Java grafice?
Ořezávání vám umožňuje **použít oblast ořezávání** k omezení kreslení na konkrétní tvary – ideální pro vytváření masek, složitých rozvržení nebo zaměření pozornosti na určitou část stránky. Také pomáhá snížit velikost souboru tím, že se vyhnete zbytečným kreslicím příkazům mimo viditelnou oblast.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte:

- **Aspose.Page pro Java** – stáhněte ze [Aspose.Page documentation](https://reference.aspose.com/page/java/).  
- **Vývojové prostředí Java** – JDK 8 nebo novější, s vaším oblíbeným IDE (IntelliJ, Eclipse, atd.).  

## Import balíčků
Ve vašem Java projektu importujte potřebné třídy:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Tyto importy vám poskytují přístup k definicím tvarů, manipulaci s barvami, konfiguraci tahu a API Aspose.Page pro vytvoření PostScript dokumentu.

## Průvodce krok za krokem

### Krok 1: Nastavení dokumentu a výstupního proudu
Nejprve vytvořte `PsDocument` a nasměrujte jej na výstupní proud, kam bude zapsán **PostScript** soubor.

```java
String dataDir = "Your Document Directory";
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Clipping_outPS.ps");
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Tip:** Uchovávejte `dataDir` jako absolutní cestu nebo použijte `Paths.get(...)` pro platformně nezávislé cesty.

### Krok 2: Vytvoření tvarů a **jak ořezávat tvary**
Nyní definujeme geometrii, se kterou budeme pracovat – obdélník a kruh. Poté **použijeme oblast ořezávání** pomocí kruhu, aby byl vykreslen jen ten část obdélníku, která leží uvnitř kruhu.

```java
Shape rectangle = new Rectangle2D.Float(0, 0, 300, 200);
document.setPaint(Color.BLUE);
// Clipping by shape
document.writeGraphicsSave();
document.translate(100, 100);
Shape circle = new Ellipse2D.Float(50, 0, 200, 200);
document.clip(circle);
document.fill(rectangle);
document.writeGraphicsRestore();
```

Pár `writeGraphicsSave()` / `writeGraphicsRestore()` zachovává stav grafiky, čímž zajišťuje, že ořezávání ovlivní jen zamýšlené kreslicí příkazy.

### Krok 3: **Nastavit styl tahu** a vykreslit obrys
Po vyplnění oříznutého obdélníku demonstrujeme **java graphics clipping** tím, že nakreslíme okraj obdélníku s vlastním vzorem čáry.

```java
document.translate(100, 100);
BasicStroke stroke = new BasicStroke(2, BasicStroke.CAP_BUTT, BasicStroke.JOIN_MITER, 10.0f, new float[]{5.0f}, 0.0f);
document.setStroke(stroke);
document.draw(rectangle);
```

Zde `BasicStroke` definuje dvoupixelovou čáru s pětipixelovým přerušovaným segmentem, což ukazuje, jak **nastavit styl tahu** pro bohatší vizuální efekty.

### Krok 4: Uzavření stránky a **uložení jako PostScript**
Nakonec dokončete stránku a zapište výstupní soubor.

```java
document.closePage();
document.save();
```

Váš soubor `Clipping_outPS.ps` nyní obsahuje modrý obdélník oříznutý kruhovou oblastí, s přerušovaným obrysem – připravený k tisku nebo dalšímu převodu.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Soubor nenalezen** | Nesprávná cesta `dataDir` | Použijte absolutní cestu nebo `new File(dataDir).mkdirs()` před vytvořením proudu. |
| **Ořezávání se neaplikovalo** | Chybí `writeGraphicsSave()` / `writeGraphicsRestore()` | Zabalte kód ořezávání těmito voláními, aby se zachoval stav. |
| **Tah se zobrazuje jako plná čára** | Není nastaven pole čárek v `BasicStroke` | Ověřte, že je správně předáno pole vzoru (`new float[]{5.0f}`). |

## Často kladené otázky

### Je Aspose.Page kompatibilní s různými formáty dokumentů?
Ano, Aspose.Page podporuje různé formáty dokumentů a poskytuje všestrannost při zpracování dokumentů.

### Mohu používat Aspose.Page pro Java v komerčních projektech?
Rozhodně! Aspose.Page nabízí komerční licenci pro vývojáře, což umožňuje jeho použití jak v osobních, tak v komerčních projektech.

### Jak získám dočasnou licenci pro testovací účely?
Dočasnou licenci pro testování získáte [zde](https://purchase.aspose.com/temporary-license/).

### Kde najdu více příkladů a dokumentaci?
Prozkoumejte [dokumentaci](https://reference.aspose.com/page/java/) a [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde najdete spoustu zdrojů.

### Je k dispozici bezplatná zkušební verze?
Ano, bezplatnou zkušební verzi Aspose.Page získáte [zde](https://releases.aspose.com/).

**Další otázky a odpovědi**

**Q:** *Co konkrétně dělá „apply clipping region“ v renderovacím řetězci?*  
**A:** Říká grafickému enginu, aby ignoroval všechny kreslicí příkazy, které leží mimo definovaný tvar, čímž efektivně maskuje výstup.

**Q:** *Mohu kombinovat více ořezávacích tvarů?*  
**A:** Ano – zavolejte `document.clip()` vícekrát; každé volání protíná aktuální oblast ořezávání s novým tvarem.

**Q:** *Je možné změnit tvar ořezávání po vykreslení?*  
**A:** Pouze v rámci uloženého grafického stavu. Použijte `writeGraphicsSave()` před ořezáváním a `writeGraphicsRestore()` pro návrat.

## Závěr
Ovládnutím **uložení jako PostScript**, **jak ořezávat tvary**, **nastavení stylu tahu** a **použití oblasti ořezávání** získáte přesnou kontrolu nad vykreslováním Java grafiky s Aspose.Page. Experimentujte s různými geometriemi, vzory čar a barvami a odhalte plný potenciál tvorby vektorových dokumentů.

---

**Poslední aktualizace:** 2025-12-03  
**Testováno s:** Aspose.Page pro Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
