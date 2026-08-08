---
date: 2026-05-15
description: Naučte se, jak upravit metadata XMP a jak změnit hodnoty XMP v souborech
  EPS pomocí Aspose.Page for Java – jasný krok‑za‑krokem návod.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Změna pojmenované hodnoty v XMP pomocí Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: jak upravit XMP – Změna pojmenované hodnoty v XMP pomocí Java
url: /cs/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak upravit xmp – Změna pojmenované hodnoty v XMP pomocí Javy

V moderních pracovních postupech s dokumenty **Aspose.Page for Java** usnadňuje čtení, úpravu a zápis XMP metadat uvnitř EPS souborů. **Tento tutoriál ukazuje, jak upravit XMP** metadata v EPS dokumentech pomocí Aspose.Page API, takže můžete udržet informace o dokumentu přesné, prohledávatelné a v souladu s průmyslovými standardy. Ať už aktualizujete rozměry stránky, informace o autorovi nebo vlastní značky, níže uvedené kroky vás provedou procesem v Javě.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Změna pojmenované hodnoty XMP v EPS souboru pomocí Aspose.Page for Java.  
- **Jaká verze knihovny je vyžadována?** Jakákoli nedávná verze Aspose.Page for Java (API je stabilní již několik let).  
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná nebo plná licence; pro testování funguje bezplatná zkušební verze.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro vývojáře obeznámeného s Java I/O.  
- **Mohu to použít s jinými formáty souborů?** XMP API je také k dispozici pro PDF, SVG a další formáty podporované Aspose.Page.

## Co je XMP metadata?
XMP (Extensible Metadata Platform) je standardizovaný formát založený na XML pro vkládání bohatých metadat — jako je tvůrce, název a vlastní vlastnosti — přímo do souborů. V EPS dokumentech XMP existuje vedle tradičních PostScript komentářů, což umožňuje aplikacím číst a upravovat metadata bez změny vizuálního obsahu.

## Proč použít Aspose.Page pro Javu k úpravě XMP?
Aspose.Page vám poskytuje **plnou kontrolu nad více než 150 vlastnostmi XMP schématu** a funguje konzistentně napříč formáty EPS, PDF a SVG. Zpracovává soubory až do **500 MB** bez načítání celého dokumentu do paměti a obsahuje vestavěnou validaci, která zaručuje, že výsledný EPS zůstane v souladu se standardy. Není potřeba žádných externích XML parserů ani nativních knihoven.

## Úvod
Aspose.Page for Java je robustní knihovna, která usnadňuje manipulaci a zpracování EPS souborů. Pokud jde o práci s XMP metadaty v těchto souborech, Aspose.Page poskytuje vývojářům komplexní sadu funkcí. V tomto tutoriálu se zaměříme na změnu pojmenované hodnoty v XMP, nabízející jasný a stručný návod pro vývojáře, kteří chtějí rozšířit své schopnosti zpracování dokumentů.

## Požadavky
1. **Java vývojové prostředí** – JDK (8 nebo vyšší) a IDE nebo nástroj pro sestavení (Maven/Gradle).  
2. **Knihovna Aspose.Page for Java** – Stáhněte a integrujte knihovnu Aspose.Page for Java do svého projektu. Knihovnu a podrobnou dokumentaci najdete [zde](https://reference.aspose.com/page/java/).  
3. **Ukázkový EPS soubor** – Mějte připravený ukázkový EPS soubor pro experimentování. Pokud žádný nemáte, použijte poskytnutý příklad s názvem **"xmp4.eps."**

## Import balíčků
`import` příkazy přinášejí nezbytné třídy Aspose.Page do dosahu.

Třída `PsDocument` je jádrový objekt Aspose.Page, který představuje EPS dokument v paměti.  
Třída `XmpMetadata` poskytuje přístup k XMP paketu vloženému v EPS souboru.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Jak upravit XMP metadata?
Nahrajte EPS soubor, načtěte jeho XMP paket, upravte požadovanou vlastnost a uložte dokument — vše v několika jednoduchých řádcích. Tento přístup funguje pro jakoukoli pojmenovanou XMP hodnotu, ať už jde o standardní pole Dublin Core nebo vlastní jmenný prostor, který jste definovali.

## Krok 1: Inicializace vstupního proudu EPS souboru
`FileInputStream` otevře jen pro čtení proud k zdrojovému EPS souboru, což umožňuje Aspose.Page načíst dokument bez uzamčení souborového systému.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Krok 2: Inicializace PsDocument
`PsDocument` je hlavní objekt, který zapouzdřuje obsah EPS a poskytuje přístup k jeho metadatům, stránkám a zdrojům.

```java
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Získání XMP metadata
`XmpMetadata` představuje XMP paket uvnitř EPS souboru a nabízí metody pro čtení, úpravu nebo mazání jednotlivých vlastností.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 4: Nastavení nové hodnoty v XMP
`setProperty` nastaví hodnotu specifikované XMP vlastnosti v metadatovém paketu.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Krok 5: Inicializace výstupního proudu EPS souboru
`FileOutputStream` vytvoří zapisovatelný proud pro uložení upraveného EPS souboru.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Krok 6: Uložení dokumentu s upravenými XMP metadaty
`save` zapíše PsDocument v paměti, včetně aktualizovaného XMP, do výstupního proudu.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 7: Zavření vstupního proudu EPS
`close` uvolní souborový handle a uvolní prostředky spojené se vstupním proudem.

```java
// Close input EPS stream
psStream.close();
```

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že `dataDir` ukazuje na správnou složku a že `xmp4.eps` existuje.  
- **LicenseException** – Pokud vidíte chyby licence, ujistěte se, že je načten platný soubor licence Aspose.Page před vytvořením `PsDocument`.  
- **Metadata Not Updated** – Po uložení otevřete výsledný EPS v prohlížeči metadat (např. Adobe Bridge), abyste potvrdili, že se nová hodnota zobrazila.

## Často kladené otázky
**Otázka: Mohu použít Aspose.Page for Java s jinými programovacími jazyky?**  
Aspose.Page primárně podporuje Javu, ale Aspose nabízí ekvivalentní knihovny pro .NET, C++ a Python, které poskytují podobné možnosti manipulace s XMP.

**Otázka: Je k dispozici bezplatná zkušební verze Aspose.Page for Java?**  
Ano, můžete si vyzkoušet bezplatnou verzi Aspose.Page for Java [zde](https://releases.aspose.com/).

**Otázka: Kde mohu najít další podporu a diskuse o Aspose.Page for Java?**  
Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

**Otázka: Jak mohu získat dočasnou licenci pro Aspose.Page for Java?**  
Můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

**Otázka: Kde mohu zakoupit Aspose.Page for Java?**  
Pro nákup Aspose.Page for Java navštivte [stránku nákupu](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-05-15  
**Testováno s:** Aspose.Page for Java (latest release)  
**Autor:** Aspose

## Související tutoriály

- [Jak číst XMP metadata pomocí Javy – Průvodce Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Tutoriál Aspose Page Java – Přidání XMP metadat do EPS souborů](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page upravit xmp – Změna hodnot v XMP pomocí Javy](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}