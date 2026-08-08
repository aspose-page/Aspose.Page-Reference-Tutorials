---
date: 2026-05-20
description: Naučte se, jak přidat XMP metadata do souborů EPS pomocí Aspose.Page
  for Java. Podrobný návod krok za krokem, jak programově vložit jednoduché XMP vlastnosti.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Přidat jednoduché vlastnosti v XMP pomocí Javy
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Přidat XMP metadata do souborů EPS pomocí Javy
url: /cs/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání XMP metadat do EPS souborů pomocí Javy

## Úvod
V moderních grafických pipelinech vám možnost **přidat XMP metadata** do EPS souborů programově poskytuje plnou kontrolu nad tím, jak jsou vaše ilustrace popsány, vyhledávány a archivovány. S Aspose.Page pro Javu můžete číst, upravovat a zapisovat XMP pakety uvnitř EPS dokumentů, aniž byste opustili ekosystém Javy. V tomto tutoriálu vás provedeme přesnými kroky, jak přidat jednoduché XMP vlastnosti do EPS souboru, abyste mohli rychle a spolehlivě obohatit své grafiky o vlastní metadata.

## Rychlé odpovědi
- **Co znamená „přidat XMP metadata do EPS“?** Vložení XMP paketu (XML‑založených metadat) do EPS souboru.  
- **Která knihovna je vyžadována?** Aspose.Page pro Javu (ke stažení na stránkách Aspose).  
- **Potřebuji licenci pro testování?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Kolik řádků kódu?** Méně než 30 řádků Javy plus několik importů.  
- **Mohu přidat i jiné typy dat?** Ano – data, celá čísla, double, řetězce a dokonce i pole jsou podporovány.

## Jak přidat XMP metadata do EPS souborů pomocí Javy?
Načtěte EPS soubor pomocí `new PsDocument("input.eps")`, získejte nebo vytvořte jeho XMP paket, vložte požadované vlastnosti a poté dokument uložte zpět na disk – vše během méně než deseti řádků Javy. Tento přístup vám umožní vložit vyhledávatelná, standardy‑kompatibilní metadata bez ruční úpravy zdrojového EPS.

## Co jsou XMP metadata v EPS?
XMP metadata v EPS jsou XML paket, který žije uvnitř EPS souboru a ukládá informace jako autor, datum vytvoření a vlastní značky. Vložení tohoto paketu umožňuje následným nástrojům číst a reagovat na data bez potřeby samostatných souborů.

## Proč přidávat XMP metadata do EPS souborů?
Vložení XMP metadat dělá z EPS aktiv okamžitě vyhledávatelná, zajišťuje soulad ukládáním licenčních informací přímo do souboru, umožňuje automatizovaným pipeline rozhodovat na základě vložených značek a garantuje, že metadata cestují s grafikou napříč všemi platformami. Aspose.Page dokáže zpracovat soubory až do 500 MB, aniž by načítal celý dokument do paměti, což poskytuje vysoký výkon pro rozsáhlé úlohy.

## Předpoklady
Než začnete, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Knihovnu Aspose.Page pro Javu nainstalovanou. Můžete si ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  
- Ukázkový EPS soubor obsahující metadata. Pokud žádný nemáte, můžete použít poskytnutý soubor **`xmp3.eps`**.

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Importy zůstávají přesně stejné jako v původním příkladu:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Krok 1: Načtení EPS dokumentu a získání XMP metadat
Třída `PsDocument` představuje EPS soubor a poskytuje metody pro přístup k jeho obsahu a metadatům.  
Objekt `XmpMetadata` obsahuje XMP paket spojený s dokumentem.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Přidání vlastnosti Date
Třída `Date` představuje konkrétní okamžik v čase s milisekundovou přesností.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Krok 3: Přidání vlastnosti Integer
Třída `Integer` obaluje primitivní hodnotu `int` jako objekt.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Krok 4: Přidání vlastnosti Double
Třída `Double` obaluje primitivní hodnotu `double` jako objekt.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Krok 5: Přidání vlastnosti String
Třída `String` představuje sekvenci znaků.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Krok 6: Uložení aktualizovaného EPS souboru
Metoda `save` zapíše upravený dokument zpět na disk a zachová strukturu EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 7: Vyčištění prostředků
Vždy zavírejte streamy, aby nedocházelo k únikům souborových deskriptorů a aby byly všechny buffery vyprázdněny.

```java
// Close input EPS stream
psStream.close();
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Null XMP metadata** | EPS soubor neobsahoval XMP paket a knihovna nedokázala odvodit PS komentáře. | Ujistěte se, že zdrojový EPS obsahuje alespoň jeden PS komentář (např. `%%Creator`). Knihovna automaticky vygeneruje minimální XMP paket. |
| **Time zone mismatch** | Data se posunou při otevření v jiné aplikaci. | Před vytvořením objektu `Date` nastavte `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, jak je ukázáno v Kroku 2. |
| **License exception** | V runtime dojde k vyhození `LicenseException`. | Použijte platnou Aspose.Page licenci před použitím API, nebo spusťte v režimu zkušební verze pro evaluaci. |

## Často kladené otázky
**Q: Můžu použít Aspose.Page pro Javu s jinými programovacími jazyky?**  
A: Aspose.Page primárně podporuje Javu, ale ekvivalentní knihovny jsou dostupné pro .NET, C++ a Python.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Javu?**  
A: Ano, funkce Aspose.Page můžete vyzkoušet získáním bezplatné zkušební verze **[zde](https://releases.aspose.com/)**.

**Q: Kde najdu podrobnou dokumentaci pro Aspose.Page pro Javu?**  
A: Dokumentace je dostupná **[zde](https://reference.aspose.com/page/java/)**.

**Q: Jak získat dočasnou licenci pro Aspose.Page pro Javu?**  
A: Dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Kde mohu zakoupit Aspose.Page pro Javu?**  
A: Produkt můžete zakoupit **[zde](https://purchase.aspose.com/buy)**.

---

**Poslední aktualizace:** 2026-05-20  
**Testováno s:** Aspose.Page pro Javu 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak číst XMP metadata pomocí Javy – Aspose.Page průvodce](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp tutoriál – Přidání jmenného prostoru v XMP pomocí Javy](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Přidání položek pole v XMP metadata pomocí Javy](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}