---
date: 2026-05-15
description: Prozkoumejte aspose.page xmp tutorial pro Java — naučte se, jak změnit
  položky pole v XMP metadata, aktualizovat názvy EPS, tvůrce a další během několika
  řádků kódu.
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: Změna položek pole v XMP pomocí Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page xmp průvodce: Změna položek pole v XMP pomocí Java'
url: /cs/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp tutoriál: Změna položek pole v XMP pomocí Java

## Úvod
Vítejte v našem komplexním **aspose.page xmp tutoriál**. V tomto průvodci vám krok za krokem ukážeme, jak změnit položky pole v XMP metadatech uvnitř EPS souborů pomocí Aspose.Page pro Java. Ať už potřebujete aktualizovat název dokumentu, seznam autorů nebo jakékoli jiné XMP pole, proces je jednoduchý, plně programovatelný a funguje s Java 8 +.

## Rychlé odpovědi
- **Co dělá aspose.page xmp java?** Čte a zapisuje XMP metadata v EPS souborech přímo z Javy.  
- **Potřebuji licenci pro vyzkoušení?** Ano—je k dispozici bezplatná 30‑denní zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Která verze JDK je podporována?** Java 8 nebo novější (včetně Java 11, 17 a 21).  
- **Mohu upravit jiné pole metadat?** Rozhodně – jakákoliv XMP vlastnost, včetně vlastních jmenných prostorů, může být čtena nebo aktualizována.  
- **Je API thread‑safe?** Většina operací čtení/zápisu je bezpečná, pokud každý vlákno pracuje se svou vlastní instancí `PsDocument`.

## Co je aspose.page xmp java?
`aspose.page xmp java` je komponenta Aspose.Page pro Java, která abstrahuje Extensible Metadata Platform (XMP) do snadno použitelných Java objektů. Umožňuje manipulovat s poli, bagy a strukturovanými vlastnostmi bez nutnosti pracovat s čistým XML. V praxi pracujete s vysoce‑úrovňovými metodami jako `setArrayItem` a `removeArrayItem` pro okamžitou úpravu metadat.

## Proč použít aspose.page xmp java pro EPS metadata?
Tuto knihovnu byste měli použít, když potřebujete přesnou, automatizovanou kontrolu EPS metadat ve velkém měřítku. Aspose.Page podporuje **30+ XMP schématických polí** a dokáže zpracovat soubory až do **500 MB** bez načítání celého dokumentu do paměti, což vám poskytuje jak rychlost, tak nízkou spotřebu paměti. API také zaručuje, že změny zachovají původní grafiku, takže vizuální vykreslování zůstane nedotčeno.

## Požadavky
- Java Development Kit (JDK) 8 nebo novější nainstalován.  
- Knihovna Aspose.Page pro Java. Stáhněte nejnovější JAR ze [zde](https://releases.aspose.com/page/java/).  
- Platný soubor licence Aspose (nebo zkušební licence) umístěný na classpath.

## Jak změnit položky pole pomocí aspose.page xmp java
Tato sekce demonstruje kompletní workflow: otevřete EPS soubor, získáte jeho XMP metadata objekt, upravíte konkrétní položky pole a nakonec zapíšete aktualizovaný dokument zpět na disk. Každý krok je ilustrován stručným Java kódem, což usnadňuje integraci do vašich aplikací.

### Krok 1: Získání XMP metadat
Zavolejte `document.getXmpMetadata()` pro získání XMP metadata objektu spojeného s EPS souborem.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### Krok 2: Nastavení položky pole "dc:title"
Použijte `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` pro nahrazení první položky názvu.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Krok 3: Nastavení položky pole "dc:creator"
Podobně, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` aktualizuje první položku tvůrce.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Krok 4: Inicializace výstupního EPS souborového proudu
Vytvořte `FileOutputStream` ukazující na cílový EPS soubor pro zápis aktualizovaného dokumentu.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Krok 5: Uložení dokumentu se změněnými XMP metadaty
Třída `PsDocument` představuje EPS dokument a poskytuje metodu `save` pro zápis změn do proudu.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## Časté úskalí a tipy
- **Index mimo rozsah:** Ověřte, že cílový index existuje; jinak Aspose vyhodí `ArrayIndexOutOfBoundsException`.  
- **Správa streamů:** Vždy uzavřete streamy v bloku `finally` nebo použijte try‑with‑resources, aby nedocházelo k zamykání souborů.  
- **Aktivace licence:** Zapomenutí aplikovat platnou licenci vede k EPS souboru s vodoznakem v režimu zkušební verze.  
- **Velké soubory:** Pro EPS soubory větší než 200 MB zvažte zvýšení velikosti haldy JVM (`-Xmx2g`), aby nedošlo k tlaku na paměť.

## Často kladené otázky

**Q: Mohu aktualizovat více položek pole v jednom volání?**  
A: Ne. Musíte zavolat `setArrayItem` pro každý index, který chcete upravit; API neposkytuje metodu pro hromadnou aktualizaci.

**Q: Podporuje aspose.page xmp java vlastní jmenné prostory?**  
A: Ano. Při volání `setArrayItem` nebo `removeArrayItem` uveďte celý prefix (např. `myNS:customProp`).

**Q: Jak mohu ověřit, že metadata byla správně aktualizována?**  
A: Znovu načtěte EPS pomocí `PsDocument`, zavolejte `getXmpMetadata()` a prohlédněte vrácené hodnoty, nebo otevřete soubor v XMP prohlížeči.

**Q: Je možné úplně odstranit položku pole?**  
A: Použijte `removeArrayItem(namespace, index)` k odstranění konkrétní položky z XMP pole.

**Q: Ovlivní změny vizuální vzhled EPS?**  
A: Ne. XMP metadata jsou uložena odděleně od grafického obsahu a nemění způsob, jakým se EPS vykresluje.

## Závěr
Nyní jste zvládli **aspose.page xmp tutoriál** pro Javu a můžete s jistotou měnit položky pole v EPS XMP metadatech. Tato schopnost umožňuje automatizované dokumentové pipeline, hromadné aktualizace metadat a lepší správu aktiv bez zásahu do vizuálních dat.

---

**Poslední aktualizace:** 2026-05-15  
**Testováno s:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Související tutoriály

- [Přidání položek pole do XMP metadat pomocí Javy](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp tutoriál – Změna pojmenované hodnoty v XMP pomocí Javy](/page/java/xmp-metadata-manipulation/change-named-value/)
- [Jak číst XMP metadata pomocí Javy – Průvodce Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}