---
date: 2026-06-20
description: Naučte se, jak nastavit velikost stránky A4, vytvořit soubory PostScript
  v Javě a přidat vlastní písma pomocí Aspose.Page. Vyzkoušejte bezplatnou zkušební
  verzi ještě dnes!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Vytvořit dokument v Javě s PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Jak nastavit velikost stránky A4 a vytvořit PostScript v Javě s Aspose.Page
url: /cs/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit velikost stránky A4 a vytvořit PostScript v Javě s Aspose.Page

## Úvod
Pokud potřebujete **nastavit velikost stránky a4** při generování souborů PostScript z Javy, Aspose.Page poskytuje rychlé, spolehlivé API, které skrývá nízko‑úrovňové detaily. V tomto tutoriálu projdeme celý pracovní postup — vytvoření dokumentu PostScript, nastavení rozměrů stránky A4 a **přidání vlastních fontů**, pokud je to potřeba. Na konci budete mít připravený úryvek kódu, který můžete vložit do jakéhokoli Java projektu.

## Rychlé odpovědi
- **Jaká knihovna vytváří PostScript v Javě?** Aspose.Page for Java.  
- **Jakou velikost stránky tento průvodce cílí?** A4 (210 mm × 297 mm).  
- **Mohu vložit své vlastní fonty?** Ano — nastavte složku s doplňkovými fonty v možnostech uložení.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Jaké verze Javy jsou podporovány?** Java 8 a novější.

## Jak nastavit velikost stránky a4 a vytvořit postscript v Javě
Načtěte knihovnu Aspose.Page, nakonfigurujte `PsSaveOptions` s konstantami A4 a zapište dokument do souboru — vše během méně než deseti řádků kódu. Tento přímý přístup zaručuje správné rozměry stránky a umožňuje přidat vlastní fonty bez další konfigurace.

## Co je velikost postscript A4?
Velikost PostScript A4 je standard ISO 216 (210 mm × 297 mm) vyjádřený v jazyce pro popis stránky PostScript. Definuje tisknutelnou oblast, kterou tiskárny a prohlížeče interpretují, což zajišťuje konzistentní rozvržení napříč platformami. Protože PostScript popisuje obsah stránky nezávisle na zařízení, použití velikosti A4 zaručuje, že dokument bude vypadat stejně na jakékoli tiskárně nebo prohlížeči podporujícím A4 po celém světě.

## Proč použít Aspose.Page k nastavení velikosti stránky postscript?
Aspose.Page podporuje **více než 30 operátorů PostScript** a může generovat soubory až do **500 MB** bez načítání celého dokumentu do paměti. To vám poskytuje přesnou kontrolu nad rozměry stránky při efektivním zpracování velkých úloh. Knihovna také abstrahuje složitou syntaxi PostScript, automaticky spravuje zdroje a poskytuje vysoce výkonný streaming, což ji činí ideální jak pro jednoduché jednoprvkové letáky, tak pro komplexní vícestránkové zprávy.

## Jak přidat vlastní fonty v Javě
Vkládání vlastních typů písma zajišťuje, že vygenerovaný dokument vypadá přesně podle návrhu na jakékoli tiskárně nebo prohlížeči, a Aspose.Page automaticky objeví fonty umístěné ve specifikované složce. Registrací doplňkové složky s fonty můžete použít libovolný TrueType nebo OpenType font, vyhnout se náhradním substitucím a udržet konzistenci značky napříč všemi výstupními zařízeními.

## Požadavky
- Praktické znalosti programování v Javě.  
- Aspose.Page pro Java nainstalováno. Můžete jej stáhnout [zde](https://releases.aspose.com/page/java/).  
- Složka pojmenovaná `necessary_fonts` (nebo libovolný název dle vašeho výběru), která obsahuje všechny vlastní fonty, které chcete vložit.

## Import balíčků
Ve vašem Java projektu importujte požadované třídy Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Nyní rozdělíme příklad do jasných, číslovaných kroků.

### Krok 1: Nastavit adresář dokumentu
Konstanta `OUTPUT_DIR` říká knihovně, kam má zapsat vygenerovaný soubor.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Krok 2: Definovat složku s fonty
`FONTS_FOLDER` ukazuje na adresář, který obsahuje vaše vlastní TrueType nebo OpenType fonty.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 3: Vytvořit výstupní stream pro dokument PostScript
`FileOutputStream` otevře stream, který přijme finální výstup PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Krok 4: Vytvořit možnosti uložení s velikostí A4
`PsSaveOptions` vám umožňuje specifikovat cílovou velikost stránky.  
**Definice:** `PsPageSize` je výčet, který obsahuje standardní konstanty velikostí stránek, jako jsou A4, Letter a Legal.  
Nastavením `options.setPageSize(PsPageSize.A4)` nakonfigurujete dokument na standardní rozměry A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Krok 5: Nastavit okraje stránky a přidat složku s vlastními fonty
`options.setMargins(0, 0, 0, 0)` odstraní všechny okraje pro stránku s plným ořezem a `options.setAdditionalFontsFolder(FONTS_FOLDER)` zaregistruje vaše vlastní fonty.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Krok 6: Vytvořit vícestránkový nebo jednostránkový PS dokument
`PsDocument document = new PsDocument(outputStream, options)` vytváří dokument. `PsDocument` představuje dokument PostScript, který může obsahovat jednu nebo více stránek. Nastavte `multiPaged` na `true` pro vícestránkový výstup.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Krok 7: Zavřít aktuální stránku a uložit dokument
Voláním `document.close()` dokončíte soubor a zapíšete výstup **PostScript A4 size** na disk.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Časté problémy a tipy
- **Font se nezobrazuje?** Ověřte, že soubor fontu je podporovaný formát TrueType nebo OpenType a že `FONTS_FOLDER` končí lomítkem (`/`).  
- **Okraje se stále zobrazují?** Zavolejte `options.setMargins(...)` **před** vytvořením `PsDocument`.  
- **Vícestránkový výstup vypadá prázdně?** Nezapomeňte volat `document.newPage()` pro každou další stránku, kterou potřebujete.

## Často kladené otázky

**Q: Mohu použít vlastní fonty v mém PostScript dokumentu?**  
A: Ano, nastavte doplňkovou složku s fonty v možnostech uložení (viz Krok 5) a Aspose.Page fonty automaticky vloží.

**Q: Je k dispozici zkušební verze pro Aspose.Page pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak mohu získat úplnou referenci API?**  
A: Odkazujte na dokumentaci [zde](https://reference.aspose.com/page/java/).

**Q: Kde si mohu zakoupit licenci pro Aspose.Page pro Java?**  
A: Licenci můžete koupit [zde](https://purchase.aspose.com/buy).

**Q: Kde se mohu zeptat komunity na pomoc?**  
A: Navštivte fórum Aspose.Page [forum](https://forum.aspose.com/c/page/39).

**Q: Mohu generovat vícestránkové PostScript soubory?**  
A: Rozhodně — nastavte `multiPaged` na `true` v Kroku 6 a zavolejte `document.newPage()` pro každou další stránku.

## Závěr
Postupováním těmito kroky nyní víte **jak nastavit velikost stránky a4** a vytvořit **PostScript** soubory v Javě s Aspose.Page, přičemž můžete **přidat vlastní fonty java** a řídit možnosti velikosti stránky. Aspose.Page se postará o těžkou část, takže se můžete soustředit na obsah svých dokumentů.

---

**Poslední aktualizace:** 2026-06-20  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Aspose.Page Java Tutorial – set custom page size while Adding Pages in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [How to Add Text in PostScript with Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Convert PostScript to PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```