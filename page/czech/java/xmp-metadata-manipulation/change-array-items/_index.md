---
date: 2025-12-20
description: Naučte se, jak měnit položky pole v XMP pomocí Aspose.Page pro Javu (aspose.page
  xmp java). Upravit metadata snadno s naším krok‑za‑krokem návodem a vylepšete své
  EPS dokumenty ještě dnes.
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
title: 'aspose.page xmp java - Změna položek pole v XMP pomocí Javy'
url: /cs/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp java: Změna položek pole v XMP pomocí Java

## Úvod
Vítejte v našem komplexním průvodci **změnou položek pole v XMP pomocí Aspose.Page pro Java**. Knihovna **aspose.page xmp java** vám dává plnou kontrolu nad XMP metadaty uvnitř EPS souborů, což usnadňuje přizpůsobení názvů, tvůrců a dalších vlastností. V tomto tutoriálu vás provedeme každým krokem potřebným k úpravě položek pole, abyste mohli své EPS dokumenty vylepšit a personalizovat s jistotou.

## Rychlé odpovědi
- **Co dělá aspose.page xmp java?** Umožňuje čtení a zápis XMP metadat v EPS souborech z Java.  
- **Potřebuji licenci pro vyzkoušení?** Ano, je k dispozici bezplatná zkušební verze, ale licence je vyžadována pro produkční použití.  
- **Která verze JDK je podporována?** Java 8 nebo novější.  
- **Mohu upravit i jiné pole metadat?** Ano – jakákoliv XMP vlastnost může být čtena nebo aktualizována.  
- **Je API thread‑safe?** Většina operací čtení/zápisu je bezpečná při použití na samostatných instancích dokumentu.

## Co je aspose.page xmp java?
`aspose.page xmp java` je součástí sady Aspose.Page pro Java, která se zaměřuje na práci s XMP (Extensible Metadata Platform). Abstrahuje nízkoúrovňovou strukturu XMP do jednoduchých Java objektů, což vám umožní pracovat s poli, bagy a strukturovanými vlastnostmi, aniž byste se museli zabývat surovým XML.

## Proč používat aspose.page xmp java pro EPS metadata?
- **Přesnost:** Přímé cílení na konkrétní položky XMP pole (např. title, creator).  
- **Automatizace:** Integrace aktualizací metadat do build pipeline nebo dávkových procesů.  
- **Kompatibilita:** Funguje s jakýmkoli EPS souborem, který dodržuje standard XMP.  

## Požadavky
- Java Development Kit (JDK) nainstalovaný na vašem systému.  
- Knihovna Aspose.Page pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).  

## Import balíčků
Abyste mohli začít, importujte potřebné třídy do svého Java projektu. Ujistěte se, že je Aspose.Page JAR přidán do classpath vašeho projektu.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Jak změnit položky pole pomocí aspose.page xmp java

### Krok 1: Získání XMP metadat
Nejprve načtěte XMP metadata ze svého EPS souboru. Pokud soubor postrádá XMP data, Aspose.Page vytvoří nový XMP blok naplněný z existujících PS komentářů (např. %%Creator, %%Title).

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Krok 2: Nastavení položky pole "dc:title"
Nyní nahraďte první prvek pole **dc:title** novým řetězcem názvu.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Krok 3: Nastavení položky pole "dc:creator"
Podobně aktualizujte první prvek pole **dc:creator**.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Krok 4: Inicializace výstupního EPS souborového streamu
Připravte stream pro výstupní EPS soubor, kam budou uložena upravená metadata.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

### Krok 5: Uložení dokumentu se změněnými XMP metadaty
Nakonec změny trvale uložte uložením dokumentu.

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Časté úskalí a tipy
- **Index mimo rozsah:** Ujistěte se, že zadaný index existuje; jinak Aspose vyhodí výjimku.  
- **Správa streamů:** Vždy uzavřete streamy v bloku `finally`, aby nedošlo k zamčení souboru.  
- **Aktivace licence:** Zapomenutí nastavení platné licence může vést k vodotisku ve výstupu v režimu zkušební verze.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak změnit položky pole v XMP pomocí **aspose.page xmp java**. Tento krok‑za‑krokem průvodce vás vybaví k programové úpravě EPS metadat, čímž otevírá dveře k automatizovaným pracovním postupům a bohatší správě obsahu.

## Další často kladené otázky
**Q: Mohu aktualizovat více položek pole v jednom volání?**  
A: Musíte volat `setArrayItem` pro každý index, který chcete upravit; neexistuje metoda pro hromadnou aktualizaci.  

**Q: Podporuje aspose.page xmp java vlastní jmenné prostory?**  
A: Ano, můžete pracovat s libovolným registrovaným XMP jmenným prostorem zadáním jeho úplného prefixu (např. `myNS:customProp`).  

**Q: Jak ověřím, že metadata byla správně aktualizována?**  
A: Znovu načtěte EPS soubor pomocí `PsDocument` a zavolejte `getXmpMetadata()` pro načtení hodnot zpět, nebo soubor prohlédněte v XMP prohlížeči.  

**Q: Je možné položku pole úplně odstranit?**  
A: Použijte `removeArrayItem(namespace, index)` k odstranění konkrétní položky z XMP pole.  

**Q: Ovlivní změny vizuální vzhled EPS?**  
A: Ne. XMP metadata jsou ne‑vizuální; nemění grafický obsah EPS souboru.  

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Page for Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}