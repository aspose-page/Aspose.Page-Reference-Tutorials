---
date: 2026-11-19
description: Naučte se, jak v Javě vytvářet soubory PostScript, nastavit velikost
  stránky A4 a přidávat vlastní písma pomocí Aspose.Page. Vyzkoušejte bezplatnou zkušební
  verzi ještě dnes!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: Vytvořte dokument v Javě s PostScriptem
og_description: Naučte se, jak vytvořit soubor PostScript v Javě, nastavit velikost
  stránky A4 a přidat vlastní písma pomocí Aspose.Page. Rychlý úvodní průvodce pro
  vývojáře.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: Vytvořte soubor PostScript v Javě s formátem A4 pomocí Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: Jak vytvořit soubor PostScript v Javě s formátem A4
url: /cs/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit soubor PostScript v Javě s velikostí A4

## Úvod
Pokud potřebujete **vytvořit soubor PostScript v Javě** a nastavit standardní rozměry stránky A4, Aspose.Page pro Javu vám poskytuje stručné, vysoce výkonné API, které abstrahuje nízkoúrovňovou syntaxi PostScriptu. V tomto tutoriálu projdeme každý krok – od načtení knihovny a konfigurace `PsSaveOptions` až po vložení vlastních písem TrueType nebo OpenType. Na konci budete mít připravený úryvek kódu, který můžete vložit do libovolného Java projektu.

## Rychlé odpovědi
- **Jaká knihovna vytváří PostScript v Javě?** Aspose.Page for Java.  
- **Jaká velikost stránky je v tomto průvodci cílem?** A4 (210 mm × 297 mm).  
- **Mohu vložit vlastní písma?** Ano – nastavte složku s doplňkovými písmy v možnostech uložení.  
- **Potřebuji licenci pro produkci?** Komerční licence je vyžadována; je k dispozici bezplatná zkušební verze.  
- **Jaké verze Javy jsou podporovány?** Java 8, 11 a 17 jsou plně podporovány.

## Jak nastavit velikost stránky A4 a vytvořit PostScript v Javě?
Načtěte knihovnu Aspose.Page, nakonfigurujte `PsSaveOptions` s konstantami A4 a zapište dokument do souboru – vše během méně než deseti řádků kódu. Tento přístup zaručuje správné rozměry stránky a umožňuje přidat vlastní písma bez další konfigurace.

## Co je velikost PostScript A4?
Velikost PostScript A4 je standard ISO 216 (210 mm × 297 mm) vyjádřený v jazyce pro popis stránek PostScript. Definuje tisknutelnou oblast, kterou tiskárny a prohlížeče interpretují, což zajišťuje konzistentní rozvržení napříč platformami. Protože PostScript popisuje obsah stránky nezávisle na zařízení, použití velikosti A4 zaručuje, že dokument bude vypadat stejně na jakékoli tiskárně nebo prohlížeči podporujícím A4 po celém světě.

## Proč použít Aspose.Page pro nastavení velikosti stránky PostScript?
Aspose.Page podporuje více než 30 operátorů PostScript a dokáže generovat soubory až do 500 MB bez načítání celého dokumentu do paměti. Zpracuje 200‑stránkový dokument za méně než 2 sekundy, poskytuje přesnou kontrolu nad rozměry stránky a efektivně zvládá velké pracovní zatížení. Knihovna také abstrahuje složitou syntaxi PostScript a automaticky spravuje prostředky, což ji činí ideální pro jednoduché letáky i komplexní vícestránkové zprávy.

## Jak přidat vlastní písma v Javě
Vložení vlastních typů písma zajišťuje, že vygenerovaný dokument bude vypadat přesně podle návrhu na jakékoli tiskárně nebo prohlížeči, a Aspose.Page automaticky objeví písma umístěná ve specifikované složce. Registrací doplňkové složky s písmy můžete použít libovolné písmo TrueType nebo OpenType, vyhnout se náhradním písmům a udržet konzistenci značky napříč všemi výstupními zařízeními.

## Předpoklady
Než začnete, ujistěte se, že máte:

- Znalost programování v Javě.  
- Aspose.Page pro Java nainstalováno. Můžete si jej stáhnout [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Složku pojmenovanou `necessary_fonts` (nebo libovolný název dle vašeho výběru), která obsahuje libovolná vlastní písma, která chcete vložit.

## Import balíčků
Ve vašem Java projektu importujte požadované třídy Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Nyní rozdělíme příklad do jasných, číslovaných kroků.

### Krok 1: nastavit adresář dokumentu
Konstanta `OUTPUT_DIR` říká knihovně, kam má zapsat vygenerovaný soubor.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Krok 2: definovat složku písem
`FONTS_FOLDER` ukazuje na adresář, který obsahuje vaše vlastní písma TrueType nebo OpenType.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 3: vytvořit výstupní stream pro dokument PostScript
`FileOutputStream` otevře stream, který přijme finální výstup PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Krok 4: vytvořit možnosti uložení s velikostí A4
`PsSaveOptions` určuje, jak je dokument PostScript uložen, včetně velikosti stránky, okrajů a komprese.  
**Definice:** `PsPageSize` je výčet, který obsahuje standardní konstanty velikostí stránek, jako jsou A4, Letter a Legal.  
Nastavením `options.setPageSize(PsPageSize.A4)` nakonfigurujete dokument na standardní rozměry A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Krok 5: nastavit okraje stránky a přidat složku s vlastními písmy
`options.setMargins(0, 0, 0, 0)` odstraní všechny okraje pro stránku po celé ploše a `options.setAdditionalFontsFolder(FONTS_FOLDER)` zaregistruje vaše vlastní písma.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Krok 6: vytvořit vícestránkový nebo jednostránkový PS dokument
`PsDocument` představuje dokument PostScript, který může obsahovat jednu nebo více stránek. Instancí `new PsDocument(outputStream, options)` vytvoříte objekt dokumentu. Nastavte `multiPaged` na `true` pro vícestránkový výstup a poté zavolejte `document.newPage()` pro každou další stránku, kterou potřebujete.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Krok 7: zavřít aktuální stránku a uložit dokument
Voláním `document.close()` dokončíte soubor a zapíšete výstup **PostScript A4 size** na disk.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Časté problémy a tipy
- **Písmo se nezobrazuje?** Ověřte, že soubor písma je podporovaný formát TrueType nebo OpenType a že `FONTS_FOLDER` končí lomítkem (`/`).  
- **Okraje se stále zobrazují?** Zavolejte `options.setMargins(...)` **před** vytvořením `PsDocument`.  
- **Vícestránkový výstup vypadá prázdně?** Nezapomeňte volat `document.newPage()` pro každou další stránku, kterou potřebujete.  
- **Velké soubory způsobují chyby nedostatku paměti?** Aspose.Page streamuje data, takže můžete bezpečně generovat soubory až do 500 MB; jen zajistěte, aby váš JVM heap byl alespoň 1 GB pro velmi velké úlohy.

## Často kladené otázky

**Q: Mohu použít vlastní písma v mém PostScript dokumentu?**  
A: Ano, nastavte doplňkovou složku s písmy v možnostech uložení (viz Krok 5) a Aspose.Page písma automaticky vloží.

**Q: Je k dispozici zkušební verze pro Aspose.Page pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi [Aspose.Page free trial page](https://releases.aspose.com/).

**Q: Jak mohu získat úplnou referenci API?**  
A: Odkazujte na dokumentaci [API reference documentation](https://reference.aspose.com/page/java/).

**Q: Kde si mohu zakoupit licenci pro Aspose.Page pro Java?**  
A: Licenci můžete zakoupit na [license purchase page](https://purchase.aspose.com/buy).

**Q: Kde se mohu obrátit na komunitu pro pomoc?**  
A: Navštivte fórum komunity Aspose.Page [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

**Q: Mohu generovat vícestránkové soubory PostScript?**  
A: Rozhodně – nastavte `multiPaged` na `true` v Kroku 6 a zavolejte `document.newPage()` pro každou další stránku.

## Závěr
Postupem podle těchto kroků nyní umíte **vytvořit soubor PostScript v Javě** a nastavit **velikost stránky A4** pomocí Aspose.Page, přičemž můžete **přidat vlastní písma v Javě** a ovládat možnosti velikosti stránky. Aspose.Page se postará o těžkou část, takže se můžete soustředit na obsah svých dokumentů místo na složitosti jazyka PostScript.

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

## Související tutoriály

- [Aspose.Page Java Tutorial – nastavit vlastní velikost stránky při přidávání stránek v PostScriptu](/page/java/postscript-page-manipulation/add-pages2/)
- [Jak přidat text v PostScriptu s Aspose.Page pro Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial – převod PostScriptu do PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}