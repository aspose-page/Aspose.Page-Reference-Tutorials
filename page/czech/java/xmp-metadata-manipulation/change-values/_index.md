---
date: 2026-05-25
description: Naučte se, jak upravit xmp v EPS dokumentech pomocí Javy s Aspose.Page.
  Aktualizujte metadata rychle a spolehlivě.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Změna hodnot v XMP pomocí Javy
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: jak upravit xmp pomocí Aspose.Page – Změna hodnot v XMP pomocí Javy
url: /cs/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změna hodnot v XMP pomocí Javy

## Úvod
Pokud hledáte **jak upravit xmp** uvnitř souboru EPS pomocí Javy, jste na správném místě. Tento tutoriál vás provede každým krokem — čtením existujícího XMP bloku, aktualizací polí jako tvůrce, název a datum úpravy a nakonec uložením změn zpět do EPS dokumentu. Na konci budete mít znovupoužitelný úryvek, který zapadne do jakéhokoli automatizovaného pracovního postupu, a zajistí, že vaše soubory budou obsahovat správná metadata pro branding, soulad s předpisy nebo indexaci vyhledávači.

## Rychlé odpovědi
- **Co dělá “aspose.page modify xmp”?** Umožňuje číst a zapisovat metadata XMP v souborech EPS pomocí Aspose.Page Java API.  
- **Která verze knihovny je vyžadována?** Jakákoli aktuální verze Aspose.Page pro Java (API je stabilní napříč verzemi).  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze stačí pro vyhodnocení; pro produkční použití je vyžadována komerční licence.  
- **Mohu změnit více polí XMP najednou?** Ano – zavolejte `put` pro každé pole před uložením dokumentu.  
- **Je potřeba nastavení časové zóny?** Nastavení výchozí časové zóny (např. UTC) zajišťuje konzistentní hodnoty data.

## Co je XMP a proč jej upravovat?
XMP (Extensible Metadata Platform) je standardizovaný, XML‑založený formát pro vkládání bohatých metadat přímo do souborů, jako jsou EPS, PDF a obrázky. Aktualizací XMP můžete řídit, jak jsou dokumenty indexovány, zobrazovány a vyhledávány — což je klíčové pro konzistenci značky, soulad s předpisy a automatizované obsahové pipeline.

## Proč používat Aspose.Page pro Javu?
Aspose.Page poskytuje **plnohodnotné, čistě Java API**, které eliminuje potřebu externích nástrojů nebo nativních knihoven. Podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat soubory EPS až do **500 MB** bez načítání celého dokumentu do paměti, což umožňuje rychlou manipulaci s metadaty s nízkou spotřebou paměti na libovolném OS, který běží na Javě.

## Požadavky
Než se pustíme do tohoto tutoriálu, ujistěte se, že máte připravené následující požadavky:
1. **Java Development Environment** – JDK (8 nebo novější) a IDE nebo nástroj pro sestavení dle vašeho výběru.  
2. **Aspose.Page for Java Library** – Stáhněte a nainstalujte knihovnu Aspose.Page pro Java. Můžete najít potřebný balíček [zde](https://releases.aspose.com/page/java/).

## Import balíčků
Začněte importovat požadované balíčky do svého Java projektu. Tyto balíčky jsou nezbytné pro interakci s EPS dokumenty a jejich manipulaci.

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

## Jak upravit XMP v EPS pomocí Javy?
`Document` je třída Aspose.Page, která představuje soubor EPS a poskytuje přístup k jeho obsahu i metadatům. `XmpMetadata` představuje XMP blok připojený k dokumentu a umožňuje čtení a zápis polí metadat. `put` přidá nebo aktualizuje položku metadat v objektu XmpMetadata. `save` zapíše upravený dokument, včetně všech aktualizovaných XMP metadat, do souboru.

Načtěte EPS soubor pomocí `new Document("input.eps")`, získejte jeho objekt `XmpMetadata`, aktualizujte požadované klíče pomocí `put` a nakonec zavolejte `save`, aby se změny zapsaly do nového souboru. Tento stručný postup automaticky řeší chybějící XMP bloky, vytvoří jej z PostScript komentářů podle potřeby a zajistí časově zónově konzistentní data.

## Krok 1: Získání XMP metadat
Třída `XmpMetadata` představuje XMP blok připojený k EPS dokumentu. Když zavoláte `document.getXmpMetadata()`, API buď vrátí existující blok, nebo vytvoří nový z PS komentářů jako `%%Creator`, `%%CreateDate` a `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Změna hodnoty "ModifyDate"
Aktualizujte položku `"ModifyDate"` tak, aby odrážela nový čas úpravy. Použijte `java.util.Date` v kombinaci s `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, abyste zajistili, že uložená hodnota bude nezávislá na časové zóně.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Krok 3: Změna hodnoty "Creator"
Klíč `"Creator"` ukládá název aplikace nebo osoby, která vytvořila EPS soubor. Zavolejte `xmp.put("dc:creator", "Your Company Name")`, abyste nahradili existující hodnotu vlastním identifikátorem.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Krok 4: Změna hodnoty "Title"
Pole `"Title"` zobrazují mnohé systémy správy majetku. Nastavením pomocí `xmp.put("dc:title", "New Document Title")` zajistíte, že dokument bude správně zobrazen v katalozích a výsledcích vyhledávání.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Krok 5: Uložení dokumentu se změněnými XMP metadaty
Po všech úpravách zavolejte `document.save("output.eps")`. Knihovna zapíše aktualizovaný XMP blok zpět do EPS proudu a zachová původní grafický obsah beze změny.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Časté problémy a řešení
- **Chybějící XMP blok** – API automaticky vytvoří jeden z PS komentářů, ale v případě potřeby můžete také ručně vytvořit `XmpMetadata`.  
- **Neshody časových zón** – Vždy nastavte `TimeZone.setDefault` před vytvořením objektu `Date`, aby se předešlo neočekávaným posunům.  
- **Chyby přístupu k souborům** – Ujistěte se, že cesty vstupu a výstupu jsou správné a že má vaše aplikace oprávnění ke čtení/zápisu.

## Často kladené otázky

**Q: Jak mohu řešit časové zóny při úpravě hodnot XMP?**  
A: Využijte `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, aby byla zajištěna konzistence nastavení časové zóny.

**Q: Mohu změnit více XMP hodnot v jedné operaci?**  
A: Ano, použitím metody `put` pro každou požadovanou hodnotu můžete měnit více XMP hodnot současně.

**Q: Kde najdu další dokumentaci k Aspose.Page pro Javu?**  
A: Prozkoumejte podrobnou dokumentaci [zde](https://reference.aspose.com/page/java/).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page pro Javu?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro Aspose.Page pro Javu?**  
A: Dočasnou licenci získáte [zde](https://purchase.aspose.com/temporary-license/).

**Q: Ovlivňuje úprava XMP vizuální obsah EPS?**  
A: Ne. Změny XMP jsou pouze metadata a nemění grafické prvky EPS souboru.

**Q: Mohu programově přečíst zpět aktualizované hodnoty pro ověření změny?**  
A: Rozhodně — stačí zavolat `xmp.get("dc:creator")` (nebo příslušný klíč) po uložení a před uzavřením dokumentu.

## Závěr
Gratulujeme! Ovládli jste **jak upravit xmp** hodnoty v EPS dokumentech pomocí Aspose.Page pro Javu. Vložením přesných metadat tvůrce, názvu a data úpravy zajistíte, že vaše aktiva budou vyhledatelná, v souladu s předpisy a v souladu s vašimi standardy brandingu. Neváhejte tento vzor začlenit do dávkových zpracovatelských pipeline, CI/CD kroků nebo jakéhokoli automatizovaného workflow generování dokumentů.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## Související tutoriály

- [Aspose Page Java Tutoriál – Přidání XMP metadat do EPS souborů](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Jak číst XMP metadata pomocí Javy – Průvodce Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java – Změna položek pole v XMP pomocí Javy](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}