---
date: 2026-01-28
description: Naučte se, jak vytvářet postscriptové dokumenty A4 v Javě pomocí Aspose.Page,
  přidávat vlastní písma v Javě a nastavit velikost stránky postscriptu. Vyzkoušejte
  bezplatnou zkušební verzi ještě dnes!
linktitle: Create Document in Java with PostScript
second_title: Aspose.Page Java API
title: Jak vytvořit PostScript A4 v Javě s Aspose.Page
url: /cs/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PostScript A4 v Javě s Aspose.Page

## Úvod
Pokud potřebujete **vytvářet soubory postscript a4 java** přímo z Javy, Aspose.Page to dělá rychle a spolehlivě. V tomto tutoriálu projdeme celý proces – jak vytvořit PostScript, nastavit velikost stránky PostScript na A4 a **přidat vlastní fonty**, pokud je to potřeba. Na konci budete mít připravený úryvek kódu, který můžete vložit do libovolného Java projektu.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Page for Java.  
- **Na jakou velikost stránky se tento průvodce zaměřuje?** A4 (na výšku).  
- **Mohu použít vlastní fonty?** Ano – přidejte vlastní fonty pomocí složky s dodatečnými fonty.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Jaká verze Javy je podporována?** Java 8 a novější.

## Jak vytvořit postscript a4 java
Tato sekce znovu uvádí hlavní cíl a poskytuje stručnou definici, aby vyhledávače mohly okamžitě zobrazit odpověď.

## Co je **postscript a4 size**?
PostScript A4 size označuje stránku formátovanou podle rozměrů ISO 216 A4 (210 mm × 297 mm) pomocí jazyka pro popis stránek PostScript. Jedná se o standardní velikost stránky pro mnoho obchodních dokumentů po celém světě.

## Proč použít Aspose.Page k **nastavení velikosti stránky postscript**?
Aspose.Page abstrahuje nízkoúrovňové příkazy PostScript, což vám umožní soustředit se na rozvržení dokumentu místo na složitosti jazyka. Získáte:
- Přesnou kontrolu nad rozměry stránky (včetně A4).  
- Snadnou integraci vlastních fontů bez manipulace se systémovými cestami k fontům.  
- Podporu jak pro jednostránkové, tak vícestránkové výstupy.

## Jak přidat vlastní fonty v Javě
Vložení vlastních typů písma zajišťuje, že vygenerovaný dokument vypadá přesně tak, jak má, na jakémkoli tiskárně nebo prohlížeči.

## Požadavky
- Základní znalost programování v Javě.  
- Aspose.Page pro Java nainstalováno. Můžete jej stáhnout [zde](https://releases.aspose.com/page/java/).  
- Složka pojmenovaná `necessary_fonts` (nebo libovolný název dle vašeho výběru), která obsahuje všechny vlastní fonty, které chcete vložit.

## Import balíčků
Ve vašem Java projektu importujte požadované třídy Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Krok 1: Nastavte adresář dokumentu
Nahraďte `"Your Document Directory"` absolutní cestou, kde chcete, aby se vygenerované soubory nacházely.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Definujte složku s fonty
Uložte všechny **vlastní fonty**, které chcete použít, do této složky. Aspose.Page je automaticky načte, když později nastavíte složku s dodatečnými fonty.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Krok 3: Vytvořte výstupní stream pro PostScript dokument
Tento stream ukazuje na soubor, který bude obsahovat finální výstup **PostScript A4 size**.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Krok 4: Vytvořte možnosti uložení s velikostí A4
Zde **nastavujeme velikost stránky PostScript** na A4 (na výšku). Pokud potřebujete jinou orientaci, stačí změnit konstantu.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Krok 5: Nastavte okraje stránky a přidejte složku s vlastními fonty
Odstraníme všechny okraje (nula) pro stránku po celé ploše a řekneme Aspose.Page, kde najde **vlastní fonty**, které jste dříve přidali.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Krok 6: Vytvořte vícestránkový nebo jednostránkový PS dokument
Nastavte `multiPaged` na `true`, pokud potřebujete více než jednu stránku; jinak se vytvoří jednostránkový dokument.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

### Krok 7: Zavřete aktuální stránku a uložte dokument
Tyto volání dokončí dokument, zavřou aktivní stránku a zapíšou soubor **PostScript A4 size** na disk.

```java
document.closePage();
document.save();
```

## Časté problémy a tipy
- **Font se nezobrazuje?** Ověřte, že soubor fontu je ve podporovaném formátu TrueType nebo OpenType a že cesta v `FONTS_FOLDER` končí lomítkem (`/`).  
- **Okraje se stále zobrazují?** Ujistěte se, že voláte `options.setMargins(...)` **před** vytvořením `PsDocument`.  
- **Vícestránkový výstup vypadá prázdně?** Nezapomeňte volat `document.newPage()` pro každou další stránku, kterou chcete přidat.

## Často kladené otázky

**Q: Mohu použít vlastní fonty v mém PostScript dokumentu?**  
A: Ano, můžete. Ujistěte se, že v možnostech uložení nastavíte složku s dodatečnými fonty (viz Krok 5).

**Q: Je k dispozici zkušební verze Aspose.Page pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak mohu získat přístup k úplné referenci API?**  
A: Odkazujte na dokumentaci [zde](https://reference.aspose.com/page/java/).

**Q: Kde si mohu zakoupit licenci pro Aspose.Page pro Java?**  
A: Licenci můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Existuje komunitní fórum pro diskuse o Aspose.Page?**  
A: Ano, připojte se ke komunitnímu [fóru](https://forum.aspose.com/c/page/39) pro podporu a tipy na osvědčené postupy.

**Q: Mohu generovat vícestránkové PostScript soubory?**  
A: Rozhodně – nastavte `multiPaged` na `true` v Kroku 6 a volajte `document.newPage()` pro každou další stránku.

## Závěr
Po provedení těchto kroků nyní víte, **jak vytvořit soubory postscript a4 java** s Aspose.Page, a zároveň můžete **přidat vlastní fonty v Javě** a řídit možnosti **nastavení velikosti stránky postscript**. Aspose.Page se postará o těžkou práci, takže se můžete soustředit na obsah svých dokumentů.

---

**Poslední aktualizace:** 2026-01-28  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}