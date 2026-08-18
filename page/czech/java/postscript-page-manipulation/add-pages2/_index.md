---
date: 2026-02-18
description: Naučte se, jak nastavit vlastní velikost stránky a přidávat stránky do
  Java PostScript dokumentů pomocí Aspose.Page. Postupujte podle našeho krok‑za‑krokem
  průvodce pro bezproblémovou manipulaci s dokumenty.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java tutoriál – nastavení vlastní velikosti stránky při přidávání
  stránek v PostScriptu
url: /cs/java/postscript-page-manipulation/add-pages2/
weight: 11
---

 ale můžete výstup zabalit do PDF a aplikovat bezpečnostní nastavení, pokud je to potřeba."

Horizontal rule "---" keep.

Last Updated etc.

Translate labels:

**Poslední aktualizace:** 2026-02-18  
**Testováno s:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

Now ensure formatting: bold markers remain.

Now produce final content with all shortcodes and placeholders.

Let's assemble.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java tutoriál – nastavení vlastní velikosti stránky při přidávání stránek v PostScriptu

## Úvod
V moderních Java aplikacích je často potřeba **nastavit vlastní velikost stránky** pro výstup PostScript – ať už generujete faktury, vstupenky nebo vlastní grafiku. V tomto tutoriálu se naučíte, jak **nastavit vlastní velikost stránky** pro každou stránku, přidávat více stránek a nakonec **vytvořit soubor PostScript**, který přesně odpovídá vašim požadavkům na rozvržení. Provedeme vás kódem krok za krokem, abyste techniku rychle mohli použít ve svých projektech.

## Rychlé odpovědi
- **Mohu nastavit různé velikosti stránek pro každou stránku?** Ano, můžete otevírat stránky s vlastními rozměry pomocí `document.openPage(width, height)`.  
- **Potřebuji licenci pro produkční použití?** Platná licence Aspose.Page je vyžadována pro nasazení mimo evaluační režim.  
- **Jaké verze Javy jsou podporovány?** Knihovna funguje s Javou 8 a novějšími.  
- **Je API thread‑safe?** Instance dokumentu nejsou thread‑safe; vytvořte samostatný `PsDocument` pro každý vlákno.  
- **Jak velký může být soubor PostScript?** Aspose.Page efektivně zpracovává soubory o velikosti několika megabajtů; využití paměti roste s obsahem, ne s počtem stránek.  
- **Mohu použít přetížení openPage s šířkou/výškou?** Rozhodně – `openPage(double width, double height)` vám umožní zadat libovolné rozměry v bodech.  

## Požadavky
- Základní znalost programování v Javě.  
- Aspose.Page pro Java přidaný do vašeho projektu (Maven/Gradle nebo ruční JAR).  
- Vývojové prostředí Java (IDE, JDK 8+).  

## Import balíčků
Pro začátek importujte potřebné třídy z knihovny Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Vytvoření vícestránkového PostScript dokumentu
Nejprve vytvořte nový `PsDocument` nakonfigurovaný pro více stránek. Tím se nastaví výstupní proud a knihovna bude vědět, že budeme pracovat s vícestránkovým souborem.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Krok 2: Přidání obsahu na první stránku
Jakmile je dokument připraven, můžete na první stránku přidat libovolný obsah. Po dokončení stránku zavřete, aby se její obsah uzamkl.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Jak nastavit vlastní velikost stránky
Pokud výchozí velikost stránky nevyhovuje, můžete **nastavit vlastní velikost stránky** při otevírání nové stránky. To je užitečné pro účtenky, štítky nebo jakékoli nestandardní rozvržení.

## Krok 3: Přidání druhé stránky s odlišnou velikostí
Níže otevřeme druhou stránku a explicitně zadáme vlastní šířku a výšku (v bodech). Tím ukážeme, jak nastavit vlastní velikost stránky pro jednotlivé stránky, což vám umožní pracovat s **různými velikostmi stránek** v rámci jednoho dokumentu.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Krok 4: Uložení dokumentu
Nakonec změny trvale uložíte pomocí uložení dokumentu. Všechny stránky – včetně těch s vlastními rozměry – jsou zapsány do výstupního souboru.

```java
// Save the document
document.save();
```

Dodržením těchto kroků můžete snadno přidávat stránky a **nastavit vlastní velikost stránky** v Java PostScript dokumentu pomocí Aspose.Page, což vám poskytne plnou kontrolu nad rozvržením každé stránky.

## Proč použít Aspose.Page pro nastavení vlastní velikosti stránky?
- **Přesnost:** Rozměry jsou definovány v bodech, takže získáte přesnou kontrolu nad šířkou a výškou stránky.  
- **Flexibilita:** Můžete kombinovat **různé velikosti stránek** v jednom souboru PostScript.  
- **Výkon:** Knihovna streamuje obsah přímo do výstupního souboru, což ji činí vhodnou pro rozsáhlé scénáře **generování souboru PostScript**.  
- **Bohaté API:** Podporuje kreslení grafiky, vkládání obrázků a přidávání textu – vše při zachování nastavených vlastních rozměrů.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Rozměry stránky jsou zaměněny** | Pamatujte, že `openPage(width, height)` očekává nejprve šířku a pak výšku (obě v bodech). |
| **Obsah přesahuje stránku** | Použijte souřadnicový systém `PsGraphics` k umístění prvků v rámci vlastních hranic nebo škálujte svůj výkres. |
| **Chyby nedostatku paměti u velkých dokumentů** | Povolením streamování zapisujte přímo do `FileOutputStream`, jak je ukázáno, a vyhněte se načítání velkých obrázků najednou do paměti. |

## Často kladené otázky
### Mohu přidat stránky s různými velikostmi v jednom PostScript dokumentu?
Ano, jak je ukázáno v tomto tutoriálu, můžete do vícestránkového PostScript dokumentu přidávat stránky s různými rozměry.

### Existují nějaká omezení počtu stránek, které mohu přidat?
Aspose.Page podporuje přidání prakticky neomezeného počtu stránek do dokumentu.

### Mohu na stránky přidat vlastní obsah, například obrázky nebo grafiku?
Rozhodně! Aspose.Page umožňuje přidávat širokou škálu obsahu, včetně textu, obrázků a dalších grafických prvků.

### Je Aspose.Page vhodný pro zpracování velkých dokumentů?
Ano, Aspose.Page je navrženo tak, aby efektivně zvládalo jak malé, tak i velké dokumenty.

### Kde najdu další zdroje a podporu pro Aspose.Page?
Prozkoumejte [Aspose.Page dokumentaci](https://reference.aspose.com/page/java/), nebo navštivte [Aspose.Page fórum](https://forum.aspose.com/c/page/39) pro komunitní podporu.

**Další otázky a odpovědi**

**Q:** *Jaké formáty obrázků jsou podporovány při kreslení na stránce PostScript?*  
**A:** Můžete přímo vkládat obrázky PNG, JPEG, BMP a GIF pomocí kreslicího API.  

**Q:** *Jak změním výchozí DPI dokumentu?*  
**A:** Nastavte `PsSaveOptions.setResolution(int dpi)` před vytvořením `PsDocument`.  

**Q:** *Mohu šifrovat soubor PostScript pomocí hesla?*  
**A:** PostScript sám o sobě šifrování nepodporuje, ale můžete výstup zabalit do PDF a aplikovat bezpečnostní nastavení, pokud je to potřeba.

---

**Poslední aktualizace:** 2026-02-18  
**Testováno s:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}