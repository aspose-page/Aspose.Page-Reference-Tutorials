---
date: 2025-12-11
description: Naučte se, jak nastavit vlastní velikost stránky a přidávat stránky do
  Java PostScript dokumentů pomocí Aspose.Page. Postupujte podle našeho průvodce krok
  za krokem pro bezproblémovou manipulaci s dokumenty.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java Tutorial – nastavení vlastní velikosti stránky při přidávání
  stránek v PostScriptu
url: /cs/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – nastavení vlastní velikosti stránky při přidávání stránek do PostScriptu

## Úvod
V moderních Java aplikacích je **nastavení vlastní velikosti stránky** pro výstup PostScript často vyžadováno – ať už generujete faktury, vstupenky nebo vlastní grafiku. Aspose.Page pro Java tuto úlohu usnadňuje. V tomto tutoriálu se naučíte, jak přidávat stránky a nastavit vlastní velikosti stránek v dokumentu PostScript, krok za krokem, abyste vždy získali přesně požadované rozložení.

## Rychlé odpovědi
- **Mohu nastavit různé velikosti stránek pro každou stránku?** Ano, můžete otevírat stránky s vlastními rozměry pomocí `document.openPage(width, height)`.  
- **Potřebuji licenci pro produkční použití?** Platná licence Aspose.Page je vyžadována pro nasazení mimo evaluační verzi.  
- **Jaké verze Javy jsou podporovány?** Knihovna funguje s Java 8 a novějšími.  
- **Je API thread‑safe?** Instance dokumentu nejsou thread‑safe; vytvořte samostatný `PsDocument` pro každý vlákno.  
- **Jak velký může být soubor PostScript?** Aspose.Page efektivně zpracovává soubory o velikosti několika megabajtů; spotřeba paměti roste s obsahem, ne s počtem stránek.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Aspose.Page pro Java přidaný do vašeho projektu (Maven/Gradle nebo ručně JAR).  
- Vývojové prostředí Java (IDE, JDK 8+).  

## Import balíčků
Na začátek importujte potřebné třídy z knihovny Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Vytvoření vícestránkového dokumentu PostScript
Nejprve vytvořte nový `PsDocument` nakonfigurovaný pro více stránek. Tím se nastaví výstupní stream a knihovna ví, že budeme pracovat s více‑stránkovým souborem.

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
Jakmile je dokument připraven, můžete na první stránku přidat libovolný obsah. Po dokončení stránku uzavřete, aby se její obsah uzamkl.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Jak nastavit vlastní velikost stránky
Pokud výchozí velikost stránky nevyhovuje, můžete **nastavit vlastní velikost stránky** při otevírání nové stránky. To je užitečné pro účtenky, štítky nebo jakékoli nestandardní rozložení.

## Krok 3: Přidání druhé stránky s odlišnou velikostí
Níže otevřeme druhou stránku a explicitně zadáme vlastní šířku a výšku (v bodech). Tento příklad ukazuje, jak nastavit vlastní velikost stránky pro jednotlivé stránky.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Krok 4: Uložení dokumentu
Nakonec změny uložíte pomocí uložení dokumentu. Všechny stránky – včetně těch s vlastními velikostmi – jsou zapsány do výstupního souboru.

```java
// Save the document
document.save();
```

Podle těchto kroků můžete snadno přidávat stránky a **nastavovat vlastní velikosti stránek** v Java dokumentu PostScript pomocí Aspose.Page, což vám dává plnou kontrolu nad rozložením každé stránky.

## Závěr
Aspose.Page pro Java poskytuje robustní, vývojářsky přívětivé API pro práci s dokumenty PostScript. Nyní víte, jak přidávat více stránek, aplikovat vlastní rozměry a výsledek uložit – což vám umožní generovat přesně formátovaný výstup pro jakékoli Java‑založené řešení.

## Často kladené otázky
### Mohu přidávat stránky různých velikostí v jednom dokumentu PostScript?
Ano, jak je ukázáno v tomto tutoriálu, můžete do více‑stránkového dokumentu PostScript přidávat stránky s různými velikostmi.  
### Existují nějaká omezení počtu stránek, které mohu přidat?
Aspose.Page podporuje přidání prakticky neomezeného počtu stránek do dokumentu.  
### Mohu na stránky přidávat vlastní obsah, například obrázky nebo grafiku?
Rozhodně! Aspose.Page umožňuje přidávat širokou škálu obsahu, včetně textu, obrázků a dalších grafických prvků.  
### Je Aspose.Page vhodný pro práci s velkými dokumenty?
Ano, Aspose.Page je navržen tak, aby efektivně zvládal jak malé, tak i velké dokumenty.  
### Kde najdu další zdroje a podporu pro Aspose.Page?
Prozkoumejte [Aspose.Page dokumentaci](https://reference.aspose.com/page/java/), nebo navštivte [Aspose.Page fórum](https://forum.aspose.com/c/page/39) pro komunitní podporu.  

**Další otázky a odpovědi**

**Q:** *Jaké formáty obrázků jsou podporovány při kreslení na stránku PostScript?*  
**A:** Můžete přímo vkládat PNG, JPEG, BMP a GIF obrázky pomocí kreslicího API.  

**Q:** *Jak změním výchozí DPI pro dokument?*  
**A:** Nastavte `PsSaveOptions.setResolution(int dpi)` před vytvořením `PsDocument`.  

**Q:** *Mohu šifrovat soubor PostScript pomocí hesla?*  
**A:** PostScript sám o sobě šifrování nepodporuje, ale můžete výstup zabalit do PDF a aplikovat bezpečnostní nastavení, pokud je to potřeba.

---

**Poslední aktualizace:** 2025-12-11  
**Testováno s:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
