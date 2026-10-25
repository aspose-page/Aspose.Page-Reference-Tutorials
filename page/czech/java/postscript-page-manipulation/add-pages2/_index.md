---
date: 2026-10-25
description: Naučte se, jak nastavit vlastní velikost stránky a přidávat stránky do
  Java PostScript dokumentů pomocí Aspose.Page. Postupujte podle našeho krok‑za‑krokem
  průvodce pro plynulou manipulaci s dokumenty.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Přidávání stránek v PostScriptu
og_description: Zjistěte, jak nastavit vlastní velikost stránky v PostScriptu pomocí
  Aspose.Page pro Java. Postupujte podle krok‑za‑krokem instrukcí pro přidání stránek,
  nastavení rozměrů a efektivní uložení dokumentu.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Nastavte vlastní velikost stránky v PostScriptu pomocí Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java tutoriál – nastavení vlastní velikosti stránky při přidávání
  stránek v PostScriptu
url: /cs/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – nastavení vlastní velikosti stránky při přidávání stránek v PostScriptu

## Úvod
V moderních Java aplikacích je často vyžadováno **set custom page size** pro výstup PostScript – ať už generujete faktury, vstupenky nebo vlastní grafiku. Tento tutoriál vám ukáže, jak nastavit vlastní velikost stránky pro každou stránku, přidat více stránek a vygenerovat soubor PostScript, který přesně odpovídá vašim požadavkům na rozvržení. Dostanete kompletní, spustitelný příklad, který můžete vložit do libovolného projektu Java 8+.

## Rychlé odpovědi
- **Can I set different page sizes for each page?** Ano—můžete otevírat stránky s vlastními rozměry pomocí `document.openPage(width, height)`.  
- **Do I need a license for production use?** Platná licence Aspose.Page je vyžadována pro nasazení mimo zkušební verzi.  
- **Which Java versions are supported?** Jaké verze Javy jsou podporovány? Knihovna funguje s Java 8 a novějšími.  
- **Is the API thread‑safe?** Je API thread‑safe? Instance dokumentu nejsou thread‑safe; vytvořte samostatný `PsDocument` pro každý vláken.  
- **How large can a PostScript file be?** Jak velký může být soubor PostScript? Aspose.Page efektivně zpracovává soubory o velikosti několika megabajtů; využití paměti roste s obsahem, nikoli s počtem stránek.  
- **Can I use the open page width/height overload?** Mohu použít přetížení open page width/height? Určitě—`openPage(double width, double height)` vám umožní zadat libovolné rozměry v bodech.  

## Požadavky
- Základní znalost programování v Javě.  
- Aspose.Page pro Java přidaný do vašeho projektu (Maven/Gradle nebo ruční JAR).  
- Vývojové prostředí Java (IDE, JDK 8+).  

## Import balíčků
Následující třídy jsou vyžadovány: `FileOutputStream` pro zápis souborů, `PsDocument` pro vytváření PostScript dokumentů a `PsSaveOptions` pro konfiguraci výstupních možností.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: vytvořit vícestránkový postscript dokument
`PsDocument` je hlavní třída představující PostScript dokument, který může obsahovat více stránek.

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

## Krok 2: přidat obsah na první stránku
Jakmile je dokument připraven, můžete na první stránku přidat libovolný obsah. Po dokončení stránku zavřete, aby se její obsah uzamkl.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Jak nastavit vlastní velikost stránky
Vlastní velikost stránky nastavíte voláním `document.openPage(width, height)` s požadovanými rozměry v bodech před vykreslením jakéhokoli obsahu. `openPage(width, height)` otevře novou stránku se zadanou šířkou a výškou, čímž získáte plnou kontrolu nad plátnem stránky. Pokud výchozí velikost stránky nevyhovuje, můžete při otevírání nové stránky **set custom page size**. To je užitečné pro účtenky, štítky nebo jakékoli nestandardní rozvržení.

## Krok 3: přidat druhou stránku s odlišnou velikostí
Níže otevřeme druhou stránku a explicitně zadáme vlastní šířku a výšku (v bodech). Toto demonstruje, jak nastavit vlastní velikost stránky pro jednotlivé stránky, což vám umožní pracovat s **different page sizes** v rámci jednoho dokumentu.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Krok 4: uložit dokument
Nakonec uložte změny uložením dokumentu. Všechny stránky — včetně těch s vlastními velikostmi — jsou zapsány do výstupního souboru.

```java
// Save the document
document.save();
```

Dodržením těchto kroků můžete bez problémů přidávat stránky a **set custom page size** v Java PostScript dokumentu pomocí Aspose.Page, což vám poskytne plnou kontrolu nad rozvržením každé stránky.

## Proč použít Aspose.Page pro nastavení vlastní velikosti stránky?
Aspose.Page poskytuje přesnou kontrolu nad rozměry stránky, umožňuje definovat libovolnou šířku a výšku v bodech, kombinovat více velikostí stránek v jednom dokumentu a efektivně streamovat obsah pro vysokovýkonnou generaci PostScriptu. To jej činí ideálním pro faktury, vstupenky a rozsáhlé dávkové zpracování, kde musí být využití paměti nízké.

Aspose.Page vám umožňuje definovat přesné rozměry stránky v bodech, kombinovat více velikostí v jednom souboru a efektivně streamovat obsah, což vám poskytuje přesnou kontrolu a vysoký výkon při generování PostScriptu.  
- **Precision:** Rozměry jsou definovány v bodech, takže máte přesnou kontrolu nad šířkou a výškou stránky.  
- **Flexibility:** Kombinujte **different page sizes** v jediném PostScript souboru.  
- **Performance:** Knihovna streamuje obsah přímo do výstupního souboru, zvládá soubory až do 500 MB při zachování využití haldy pod 100 MB, což je vhodné pro rozsáhlé scénáře **generate PostScript file**.  
- **Rich API:** Podporuje více než 30 grafických primitiv, 10 formátů obrázků a neomezený počet textových objektů na stránku — vše při respektování vlastních rozměrů, které nastavíte.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Rozměry stránky jsou zaměněny** | Pamatujte, že `openPage(width, height)` očekává nejprve šířku a pak výšku (obě v bodech). |
| **Obsah přesahuje stránku** | Použijte souřadnicový systém `PsGraphics` k umístění prvků v rámci vlastních hranic nebo škálujte svůj výkres. |
| **Chyby nedostatku paměti u obrovských dokumentů** | Povolte streamování zápisem přímo do `FileOutputStream` podle ukázky a vyhněte se načítání velkých obrázků do paměti najednou. |

## Často kladené otázky
### Mohu přidat stránky s různými velikostmi v jednom PostScript dokumentu?
Ano, jak je ukázáno v tomto tutoriálu, můžete do vícestránkového PostScript dokumentu přidávat stránky s různými velikostmi.

### Existují nějaká omezení počtu stránek, které mohu přidat?
Aspose.Page podporuje přidání prakticky neomezeného počtu stránek do dokumentu.

### Mohu na stránky přidat vlastní obsah, například obrázky nebo grafiku?
Určitě! Aspose.Page vám umožňuje přidávat širokou škálu obsahu, včetně textu, obrázků a dalších grafických prvků.

### Je Aspose.Page vhodný pro zpracování velkých dokumentů?
Ano, Aspose.Page je navržen tak, aby efektivně zvládal jak malé, tak velké dokumenty.

### Kde mohu najít další zdroje a podporu pro Aspose.Page?
Prozkoumejte [Aspose.Page documentation](https://reference.aspose.com/page/java/), nebo navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro komunitní podporu.

**Další otázky a odpovědi**

**Q:** *Jaké formáty obrázků jsou podporovány při kreslení na stránce PostScript?*  
**A:** Můžete přímo vložit obrázky PNG, JPEG, BMP a GIF pomocí kreslicího API.  

**Q:** *Jak změním výchozí DPI pro dokument?*  
**A:** Nastavte `PsSaveOptions.setResolution(int dpi)` před vytvořením `PsDocument`.  

**Q:** *Mohu šifrovat soubor PostScript pomocí hesla?*  
**A:** PostScript sám o sobě nepodporuje šifrování, ale můžete výstup zabalit do PDF a případně použít bezpečnostní nastavení.

**Poslední aktualizace:** 2026-10-25  
**Testováno s:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

## Související tutoriály

- [Jak nastavit velikost stránky A4 a vytvořit PostScript v Javě pomocí Aspose.Page](/page/java/document-creation/postscript/)
- [Jak převést PostScript na PDF pomocí Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Jak nakreslit obdélník v Java PostScript pomocí Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}