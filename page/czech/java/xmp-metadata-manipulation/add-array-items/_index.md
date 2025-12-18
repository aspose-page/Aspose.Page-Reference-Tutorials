---
date: 2025-12-18
description: Naučte se, jak přidávat metadata vložením položek pole do XMP metadat
  EPS souborů pomocí Aspose.Page pro Javu. Postupujte podle našeho krok‑za‑krokem
  průvodce.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Jak přidat metadata – přidat položky pole v XMP (Java)
url: /cs/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání položek pole do XMP metadat pomocí Javy

## Jak přidat metadata
Vítejte v našem podrobném průvodci, jak **přidat metadata** do souborů EPS pomocí Aspose.Page pro Javu. V tomto tutoriálu vás provedeme přidáváním položek pole do XMP metadat – běžná potřeba, když chcete obohatit informace o dokumentu, jako jsou názvy nebo autoři. Na konci pochopíte, proč je XMP cenné, jak s ním programově manipulovat a jak uložit aktualizovaný soubor EPS.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Page for Java  
- **Jaký formát souboru je cílem?** EPS (Encapsulated PostScript)  
- **Mohu přidat více titulů?** Ano, použijte `xmp.addArrayItem("dc:title", ...)` opakovaně  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována platná licence Aspose.Page  
- **Je kód kompatibilní s Java 8+?** Rozhodně, funguje se všemi moderními verzemi Javy  

## Předpoklady
Než se ponoříme do tutoriálu, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Page pro Javu nainstalována.  
- Základní znalost programování v Javě.  
- Platný soubor EPS s existujícími XMP metadaty nebo PS metadaty v komentářích.  

## Import balíčků
Abyste mohli začít, musíte importovat potřebné balíčky pro práci s Aspose.Page. Přidejte následující řádky na začátek vašeho Java souboru:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Získání XMP metadat
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
V tomto kroku získáme existující XMP metadata ze souboru EPS. Pokud soubor EPS již neobsahuje XMP metadata, Aspose.Page vygeneruje nová a naplní je hodnotami z PS metadatových komentářů.

## Krok 2: Přidání položky pole "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nyní přidáme novou položku pole do vlastnosti **dc:title** v XMP metadatech. Nahraďte `"NewTitle"` požadovaným názvem.

## Krok 3: Přidání položky pole "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Podobně přidáme novou položku pole do vlastnosti **dc:creator** v XMP metadatech. Nahraďte `"NewCreator"` požadovanými informacemi o autorovi.

## Krok 4: Inicializace výstupního proudu souboru EPS
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Připravte výstupní proud souboru EPS, kam bude upravený dokument s aktualizovanými XMP metadaty uložen.

## Krok 5: Uložení dokumentu se změněnými XMP metadaty
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Uložte dokument s aktualizovanými XMP metadaty do výstupního souboru EPS.

## Závěr
Gratulujeme! Úspěšně jste se naučili **přidávat metadata** vložením položek pole do XMP metadat pomocí Aspose.Page pro Javu. Tato výkonná knihovna zjednodušuje proces manipulace se soubory EPS a poskytuje rozsáhlou funkčnost pro zpracování dokumentů.

## Často kladené otázky

### Mohu použít Aspose.Page pro Javu s jinými formáty dokumentů?
Ano, Aspose.Page podporuje různé formáty dokumentů, včetně EPS, PDF a XPS.

### Je k dispozici bezplatná zkušební verze Aspose.Page pro Javu?
Ano, bezplatnou zkušební verzi můžete získat [zde](https://releases.aspose.com/).

### Kde najdu dokumentaci k Aspose.Page pro Javu?
Dokumentace je k dispozici [zde](https://reference.aspose.com/page/java/).

### Jak mohu zakoupit Aspose.Page pro Javu?
Produkt můžete zakoupit [zde](https://purchase.aspose.com/buy).

### Jsou k dispozici dočasné licence pro Aspose.Page pro Javu?
Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

## Další často kladené otázky

**Q: Mohu přidat více než jednu položku pole ke stejné vlastnosti?**  
A: Rozhodně. Zavolejte `xmp.addArrayItem` vícekrát pro stejnou vlastnost, abyste vytvořili seznam hodnot.

**Q: Funguje tento přístup s existujícími XMP schématy jinými než Dublin Core?**  
A: Ano, můžete přidávat položky pole do libovolné XMP vlastnosti, pokud je správně odkazován prostor názvů.

**Q: Jak mohu ověřit, že metadata byla přidána správně?**  
A: Otevřete výsledný soubor EPS v prohlížeči, který podporuje XMP (např. Adobe Bridge), nebo metadata extrahujte programově pomocí metod `XmpMetadata`.

---

**Poslední aktualizace:** 2025-12-18  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}