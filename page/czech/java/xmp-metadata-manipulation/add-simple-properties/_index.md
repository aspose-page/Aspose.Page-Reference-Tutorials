---
date: 2025-12-20
description: Naučte se, jak vytvořit XMP metadata EPS v souborech EPS pomocí Aspose.Page
  pro Javu. Krok za krokem průvodce, jak programově přidat jednoduché XMP vlastnosti.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Jak vytvořit XMP metadata EPS v Javě
url: /cs/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání jednoduchých vlastností do XMP pomocí Javy

## Úvod
V moderních pracovních postupech s dokumenty vám možnost **create XMP metadata EPS** souborů programově poskytuje plnou kontrolu nad tím, jak jsou vaše grafiky popsány, vyhledávány a archivovány. S Aspose.Page for Java můžete číst, upravovat a zapisovat XMP pakety uvnitř EPS dokumentů, aniž byste opustili ekosystém Javy. V tomto tutoriálu vás provedeme přesnými kroky, jak přidat jednoduché XMP vlastnosti do EPS souboru, abyste mohli rychle a spolehlivě obohatit své grafiky o vlastní metadata.

## Rychlé odpovědi
- **Co znamená „create xmp metadata eps“?** Přidání XMP paketu (metadata založených na XML) do souboru EPS.  
- **Která knihovna je vyžadována?** Aspose.Page for Java (ke stažení na stránkách Aspose).  
- **Potřebuji licenci pro testování?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Kolik řádků kódu?** Méně než 30 řádků Javy plus několik importů.  
- **Mohu přidat jiné typy dat?** Ano – datumy, celá čísla, double, řetězce a dokonce i pole jsou podporovány.

## Co je create xmp metadata eps?
XMP (Extensible Metadata Platform) je standard pro vkládání bohatých metadat do souborů. Když **create XMP metadata EPS**, vložíte XML paket do dokumentu EPS (Encapsulated PostScript), což umožní následným aplikacím číst autora, datum vytvoření, vlastní značky a další informace.

## Proč přidávat XMP metadata do souborů EPS?
- **Vyhledatelnost:** Umožňuje automatické indexování systémů DAM.  
- **Soulad:** Ukládá právní nebo licenční informace přímo do souboru.  
- **Automatizace:** Umožňuje následným pipeline rozhodovat na základě vložených dat.  
- **Přenositelnost:** Metadata cestují se souborem EPS, což zajišťuje konzistenci napříč platformami.

## Požadavky
- Základní znalost programování v Javě.  
- Knihovna Aspose.Page for Java nainstalována. Můžete ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  
- Ukázkový soubor EPS obsahující metadata. Pokud žádný nemáte, můžete použít poskytnutý soubor **`xmp3.eps`**.

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Importy zůstávají přesně stejné jako v originálním příkladu:

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

## Krok 1: Načtení dokumentu EPS a získání XMP metadat
Otevřeme soubor EPS, vytvoříme instanci `PsDocument` a získáme (nebo vytvoříme) XMP paket.

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
Přidání data je tak jednoduché, jako vytvořit objekt `Date` a vložit jej do XMP mapy.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Krok 3: Přidání vlastnosti Integer
Můžete uložit číselné identifikátory nebo čísla verzí pomocí celočíselné hodnoty.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Krok 4: Přidání vlastnosti Double
Čísla s plovoucí desetinnou čárkou jsou užitečná pro měření nebo hodnocení.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Krok 5: Přidání vlastnosti String
Vlastní textové značky (např. kódy projektů) jsou ukládány jako řetězce.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Krok 6: Uložení aktualizovaného souboru EPS
Po přidání všech vlastností zapíšeme dokument zpět na disk.

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
Vždy zavřete vstupní stream, aby nedocházelo k únikům souborových popisovačů.

```java
// Close input EPS stream
psStream.close();
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|---------|-------|--------|
| **Null XMP metadata** | Soubor EPS neobsahoval XMP paket a knihovna nedokázala odvodit PS komentáře. | Ujistěte se, že zdrojový EPS obsahuje alespoň jeden PS komentář (např. `%%Creator`). Knihovna automaticky vygeneruje minimální XMP paket. |
| **Time zone mismatch** | Data se při otevření v jiné aplikaci posunou. | Nastavte `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` před vytvořením objektu `Date`, jak je ukázáno v kroku 2. |
| **License exception** | V runtime dojde k vyhození `LicenseException`. | Použijte platnou licenci Aspose.Page před použitím API, nebo spusťte v režimu zkušební verze pro hodnocení. |

## Závěr
Po absolvování těchto kroků nyní víte, jak **create XMP metadata EPS** soubory pomocí Aspose.Page for Java. Přidání jednoduchých vlastností, jako jsou datumy, celá čísla, double a řetězce, je přímočaré a výsledné EPS soubory nesou bohatá, vyhledávatelná metadata, která prospívají jakémukoli následnému workflow.

## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale jsou k dispozici verze i pro jiné jazyky, například .NET.

### Je k dispozici bezplatná zkušební verze pro Aspose.Page for Java?
Ano, můžete prozkoumat funkce Aspose.Page získáním bezplatné zkušební verze [zde](https://releases.aspose.com/).

### Kde najdu podrobnou dokumentaci pro Aspose.Page for Java?
Dokumentace je k dispozici [zde](https://reference.aspose.com/page/java/).

### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
Dočasnou licenci lze získat [zde](https://purchase.aspose.com/temporary-license/).

### Kde mohu zakoupit Aspose.Page for Java?
Produkt můžete zakoupit [zde](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2025-12-20  
**Testováno s:** Aspose.Page for Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}