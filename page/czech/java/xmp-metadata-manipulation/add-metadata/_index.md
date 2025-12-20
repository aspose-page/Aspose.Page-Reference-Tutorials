---
date: 2025-12-20
description: Naučte se, jak přidat XMP metadata do souborů EPS pomocí tutoriálu Aspose
  Page Java. Postupujte podle tohoto krok‑za‑krokem průvodce a zlepšete správu svých
  dokumentů.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java tutoriál – Přidání XMP metadat do souborů EPS
url: /cs/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidat metadata do XMP pomocí Javy

## Úvod
V tomto **aspose page java tutorial** se naučíte, jak vylepšit metadata svého dokumentu přidáním informací XMP pomocí Javy. Tento krok‑za‑krokem průvodce vás provede čtením existujícího souboru EPS, extrahováním jeho XMP metadat a uložením změn zpět na disk pomocí knihovny Aspose.Page pro Javu. Na konci tutoriálu budete mít solidní, znovupoužitelný vzor pro práci s XMP v jakémkoli EPS workflow.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java  
- **Mohu přidat XMP do libovolného souboru EPS?** Ano – API vytvoří nový XMP blok, pokud ještě neexistuje.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 a novější.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní aktualizaci metadat.

## Přehled tutoriálu Aspose Page Java
Tento tutoriál demonstruje základní kroky, které potřebujete k manipulaci s XMP metadaty v souborech EPS. Porozumění těmto krokům vám pomůže integrovat zpracování metadat do větších pipeline pro zpracování dokumentů, zlepšit vyhledatelnost a splnit průmyslové standardy pro správu digitálních aktiv.

## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.  
- Knihovna Aspose.Page pro Javu nainstalována. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).  
- Soubor EPS, který chcete upravit.

## Import balíčků
Nejprve importujte potřebné balíčky do svého Java programu:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Krok 1: Získat XMP metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Nahraďte `"Your Document Directory"` skutečnou cestou, kde jsou vaše dokumenty uloženy.

## Krok 2: Získat hodnotu CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Krok 3: Získat hodnotu CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Krok 4: Získat hodnotu Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Krok 5: Získat hodnotu Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Krok 6: Získat hodnotu Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Krok 7: Získat hodnotu MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Krok 8: Uložit dokument s novými XMP metadaty
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Nakonec nezapomeňte zavřít vstupní EPS stream:

```java
// Close input EPS stream
psStream.close();
```

Nyní jste úspěšně přidali metadata do svého EPS souboru pomocí Aspose.Page pro Javu!

## Závěr
V tomto **aspose page java tutorial** jsme prozkoumali, jak přidat XMP metadata do souboru EPS pomocí knihovny Aspose.Page pro Javu. Toto výkonné API vám umožňuje programově manipulovat s metadaty dokumentu, což vám pomáhá udržovat aktiva organizovaná a snadno vyhledatelná.

## Často kladené otázky

**Q: Je Aspose.Page pro Javu zdarma k použití?**  
A: Aspose.Page pro Javu je komerční produkt. Jeho funkce můžete vyzkoušet prostřednictvím bezplatné zkušební verze [zde](https://releases.aspose.com/).

**Q: Kde najdu dokumentaci pro Aspose.Page pro Javu?**  
A: Dokumentace je k dispozici [zde](https://reference.aspose.com/page/java/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Javu?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Jaké formáty souborů Aspose.Page pro Javu podporuje?**  
A: Aspose.Page pro Javu podporuje různé formáty, včetně EPS, PDF a XPS.

**Q: Mohu si zakoupit Aspose.Page pro Javu?**  
A: Ano, Aspose.Page pro Javu můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Jak zacházet s velkými EPS soubory při přidávání metadat?**  
A: Zpracovávejte soubor ve streamovacím režimu (jak je ukázáno), aby byl nízký odběr paměti, a streamy okamžitě uzavírejte.

**Q: Mohu upravit existující XMP pole místo jen jejich čtení?**  
A: Rozhodně – můžete použít `xmp.put(key, value)` k aktualizaci nebo přidání nových položek před uložením.

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}