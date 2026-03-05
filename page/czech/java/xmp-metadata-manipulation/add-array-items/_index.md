---
date: 2026-03-05
description: Naučte se, jak přidat položky pole dc:title do XMP metadat souborů EPS
  pomocí Aspose.Page pro Javu. Postupujte podle tohoto krok‑za‑krokem průvodce a dosáhnete
  rychlých výsledků.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Jak přidat položky pole dc:title v XMP metadatech pomocí Javy
url: /cs/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání položek pole do XMP metadat pomocí Javy

## Úvod
V tomto tutoriálu se dozvíte **jak přidat dc:title** (a další položky pole) do XMP metadat uvnitř souboru EPS pomocí Aspose.Page pro Javu. Aktualizace XMP metadat je užitečná, když potřebujete vložit vyhledávatelné informace—jako jsou názvy, autoři nebo klíčová slova—přímo do vašich grafických souborů. Provedeme vás každým krokem, vysvětlíme, proč je každý řádek důležitý, a ukážeme vám, jak změny ověřit.

## Rychlé odpovědi
- **Co představuje “dc:title”?** Jedná se o vlastnost názvu Dublin Core uloženou jako XMP pole.  
- **Proč upravovat XMP metadata?** Umožňuje lepší správu aktiv, vyhledatelnost a soulad se standardy.  
- **Potřebuji existující XMP blok?** Ne—Aspose.Page jej vygeneruje z PS komentářů, pokud chybí.  
- **Jaká verze knihovny je vyžadována?** Jakákoli aktuální verze Aspose.Page pro Javu (testováno s nejnovější verzí 2026).  
- **Mohu přidat další vlastnosti pole?** Ano—použijte stejnou metodu `addArrayItem` pro vlastnosti jako `dc:creator`.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte:

- Knihovnu Aspose.Page pro Javu nainstalovanou (přidejte JAR do classpath vašeho projektu).  
- Základní zkušenosti s vývojem v Javě (doporučeno JDK 8+).  
- Soubor EPS, který již obsahuje XMP metadata nebo alespoň PS metadata komentáře (např. `%%Title`, `%%Creator`).  

## Import balíčků
Pro začátek importujte třídy potřebné pro čtení, manipulaci a ukládání souborů EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Načtení EPS dokumentu a získání XMP metadat
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Zde otevřeme soubor EPS a požádáme Aspose.Page o jeho XMP blok. Pokud soubor XMP neobsahuje, knihovna jej automaticky vytvoří pomocí existujících PS komentářů, čímž zajistí, že vždy máte kontejner pro metadata, se kterým můžete pracovat.

## Krok 2: Přidání nové položky pole **dc:title**
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Tento řádek ukazuje **jak přidat dc:title**. Nahraďte `"NewTitle"` skutečným názvem, který chcete vložit. Metoda přidá hodnotu do existujícího pole názvů a zachová všechny předchozí názvy.

## Krok 3: Přidání nové položky pole **dc:creator**
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Podobně můžete rozšířit vlastnost `dc:creator`. Lze uložit více autorů; každé volání přidá další položku.

## Krok 4: Příprava výstupního proudu
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Vytvoříme proud pro upravený soubor EPS. Použití jiného názvu souboru (`xmp3_changed.eps`) ponechá originální soubor nedotčený.

## Krok 5: Uložení dokumentu s aktualizovanými XMP metadaty
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Volání `save` zapíše data EPS spolu s aktualizovaným XMP blokem. Blok `finally` zajišťuje uvolnění souborového handle i v případě výskytu výjimky.

## Proč je to důležité
Vložení přesných hodnot `dc:title` a `dc:creator` zlepšuje:

- **Vyhledatelnost** v systémech pro správu digitálních aktiv (DAM).  
- **Soulad** s publikovacími standardy, které vyžadují metadata.  
- **Spolupráci**, protože týmoví kolegové mohou rychle identifikovat obsah souboru bez otevření EPS.

## Časté úskalí a tipy
- **Úskalí:** Nepřímé přepsání existujících položek pole.  
  **Tip:** Použijte `xmp.getArrayItems("dc:title")` k prozkoumání aktuálních hodnot před přidáním nových.  
- **Úskalí:** Zapomenutí uzavřít proudy, což vede k zamknutí souborů.  
  **Tip:** Vždy obalte I/O do try‑with‑resources nebo použijte blok `finally`, jak je ukázáno.  
- **Tip:** Můžete řetězit více volání `addArrayItem` pro přidání několika názvů nebo autorů najednou.

## Často kladené otázky

### Mohu používat Aspose.Page pro Javu s jinými formáty dokumentů?
Ano, Aspose.Page podporuje různé formáty dokumentů, včetně EPS, PDF a XPS.

### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Javu?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Kde najdu dokumentaci pro Aspose.Page pro Javu?
Dokumentace je dostupná [zde](https://reference.aspose.com/page/java/).

### Jak mohu zakoupit Aspose.Page pro Javu?
Produkt můžete zakoupit [zde](https://purchase.aspose.com/buy).

### Jsou k dispozici dočasné licence pro Aspose.Page pro Javu?
Ano, dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-03-05  
**Testováno s:** Aspose.Page pro Javu (nejnovější verze 2026)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}