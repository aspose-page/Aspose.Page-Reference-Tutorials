---
date: 2026-05-25
description: Naučte se, jak číst XMP pomocí aspose.page v Javě. Tento krok‑za‑krokem
  průvodce ukazuje, jak extrahovat XMP metadata, creator info, timestamps, thumbnails
  a další.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Jak číst XMP metadata pomocí Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Čtení XMP pomocí Aspose.Page – Java průvodce
url: /cs/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získání metadat z XMP pomocí Javy

## Jak číst XMP pomocí Aspose.Page (Java)?

Načtěte EPS soubor pomocí `new Document("file.eps")` — třída `Document` představuje načtený soubor. Zavolejte `getXmpMetadata()`, která extrahuje XMP paket, a poté dotazujte vrácený objekt `XmpMetadata` — rozhraní podobné mapě pro XMP vlastnosti — abyste získali požadované klíče. To je vše, co je potřeba k načtení XMP pomocí Aspose.Page. API abstrahuje nízkoúrovňové parsování, takže získáte připravenou mapu vlastností během pouhých dvou řádků kódu.

Vítejte v našem podrobném tutoriálu, který ukazuje **jak číst XMP** metadata pomocí Javy a knihovny Aspose.Page. XMP (Extensible Metadata Platform) je široce přijímaný standard pro vkládání bohatých metadat do dokumentů. Na konci tohoto průvodce budete schopni číst XMP formátu dokumentu, získat informace o tvůrci, časová razítka, náhledy a další — což vám umožní vytvářet chytřejší řešení pro analýzu dokumentů.

## Rychlé odpovědi
- **Co znamená „číst XMP“?** Znamená to programově extrahovat XMP paket, který ukládá metadata uvnitř souboru.  
- **Která knihovna je vyžadována?** Aspose.Page pro Java (stáhněte z oficiální stránky [zde](https://releases.aspose.com/page/java/)).  
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná nebo plná licence; pro hodnocení funguje bezplatná zkušební verze.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.  
- **Mohu číst XMP z jiných formátů?** Ano – Aspose.Page extrahuje XMP z EPS, PDF, JPEG, PNG a více než 20 dalších formátů.

## Předpoklady
Než se ponoříte do kódu, ujistěte se, že máte:

- **Java Development Kit (JDK)** – Java 8+ nainstalovanou a nakonfigurovanou na vašem počítači.  
- **Aspose.Page pro Java** – Stáhněte knihovnu z oficiální stránky [zde](https://releases.aspose.com/page/java/).  
- EPS soubor, který obsahuje XMP metadata (např. `xmp1.eps`).  

## Import balíčků
Třída `XmpMetadata` se nachází v namespace `com.aspose.page.xmp`, zatímco třída `Document` je v `com.aspose.page`. Importujte obě, abyste mohli pracovat s EPS souborem a jeho metadaty.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Inicializace vstupního streamu EPS souboru
Začněte nastavením cesty k adresáři s dokumenty a inicializací vstupního streamu EPS souboru.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Získání XMP metadat
`XmpMetadata` je objekt Aspose.Page, který drží XMP paket extrahovaný z dokumentu. Získejte jej pomocí `document.getXmpMetadata()`. Pokud soubor XMP neobsahuje, API vytvoří minimální paket z existujících PostScript komentářů.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 3: Extrahování informace CreatorTool
Klíč `CreatorTool` leží v namespace `xmp` a zaznamenává aplikaci, která soubor vytvořila. Zkontrolujte jeho přítomnost a vytiskněte hodnotu.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Krok 4: Extrahování informace CreateDate
`CreateDate` ukládá časové razítko, kdy byl dokument původně vytvořen. Použijte stejný vzor `containsKey`/`get` pro jeho načtení.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Krok 5: Získání šířky náhledu
Pokud náhledy existují, pole `xmp:Thumbnails` obsahuje jeden nebo více záznamů. Každý záznam obsahuje `width`, `height` a binární data. Příklad získává šířku prvního náhledu.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Krok 6: Extrahování informace o formátu
Klíč `format` vám říká původní formát souboru (např. „application/postscript“). To je užitečné, když potřebujete logovat nebo ověřovat typy zdrojů.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Krok 7: Získání DocumentID
`DocumentID` je jedinečný identifikátor přiřazený aplikací tvůrce. Může být použit pro deduplikaci ve velkých knihovnách aktiv.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Proč je to důležité
Aspose.Page může číst XMP z **20+** formátů souborů a zpracovává dokumenty až do **500 MB** bez načítání celého souboru do paměti, což vám poskytuje rychlý, nízkonákladový přístup k zásadním metadatům. Tato schopnost je klíčová pro dávkové zpracování, systémy pro správu digitálních aktiv a jakékoli řešení, které spoléhá na prohledávatelné, strojově čitelné atributy dokumentů.

## Časté úskalí a tipy
- **Chybějící XMP:** Některé EPS soubory nemusí obsahovat XMP. Volání `getXmpMetadata()` vytvoří minimální sadu na základě existujících PS komentářů, ale plná metadata získáte jen v případě, že jsou vložena.  
- **Pole náhledů:** Klíč `xmp:Thumbnails` může obsahovat více záznamů. Příklad extrahuje jen první; pokud potřebujete všechny náhledy, projděte pole.  
- **Povědomí o jmenných prostorech:** XMP klíče používají jmenné prostory (např. `xmp:`, `dc:`). Ujistěte se, že odkazujete na přesný název klíče, jinak `containsKey` vrátí false.  

## Často kladené otázky
### Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?
Ano, Aspose.Page podporuje Java, .NET a několik dalších jazyků. Viz úplný seznam v [documentation](https://reference.aspose.com/page/java/).

### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Kde mohu najít podporu pro Aspose.Page pro Java?
Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro komunitní pomoc a oficiální podporu.

### Jak získat dočasnou licenci pro Aspose.Page pro Java?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Existují další zdroje pro Aspose.Page pro Java?
Prozkoumejte kompletní [dokumentaci](https://reference.aspose.com/page/java/) a stáhněte knihovnu [zde](https://releases.aspose.com/page/java/).

## Další FAQ
**Q: Funguje tento přístup s PDF soubory, které obsahují XMP?**  
A: Ano, Aspose.Page může číst XMP z PDF, EPS a několika formátů obrázků.

**Q: Mohu po načtení upravit XMP metadata?**  
A: Rozhodně. Objekt `XmpMetadata` je mutabilní; můžete přidávat, aktualizovat nebo odstraňovat klíče a poté dokument uložit.

**Q: Existuje způsob, jak extrahovat všechny obrázky náhledů, nejen rozměry?**  
A: Můžete získat binární data z vlastnosti `xmpGImg:data` každého záznamu náhledu a zapsat je do souboru.

## Závěr
Nyní ovládáte **jak číst XMP** metadata pomocí Javy a Aspose.Page. Dodržením těchto kroků můžete extrahovat nástroje tvůrců, časová razítka, náhledy, informace o formátu a ID dokumentů — což vám poskytne kompletní přehled o vložených metadatech vašich EPS souborů. Nebojte se experimentovat s dalšími XMP jmennými prostory a získávat tak ještě bohatší data pro své aplikace.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Související tutoriály

- [Aspose Page Java Tutorial – Přidání XMP metadat do EPS souborů](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Přidání jmenného prostoru v XMP pomocí Javy](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Změna pojmenované hodnoty v XMP pomocí Javy](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}