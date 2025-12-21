---
date: 2025-12-21
description: Naučte se číst metadata XMP pomocí Javy s Aspose.Page. Tento krok‑za‑krokem
  průvodce vám ukáže, jak číst XMP formát dokumentu a extrahovat klíčové vlastnosti.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Jak číst metadata XMP v Javě – Průvodce Aspose.Page
url: /cs/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získání metadat z XMP pomocí Javy

## Jak číst metadata XMP pomocí Javy

Vítejte v našem podrobném tutoriálu, který ukazuje **jak číst XMP** metadata pomocí Javy a knihovny Aspose.Page. XMP (Extensible Metadata Platform) je široce přijatý standard pro vkládání bohatých metadat do dokumentů. Na konci tohoto průvodce budete schopni číst XMP formát dokumentu, získat informace o tvůrci, časová razítka, náhledy a další — což vám umožní vytvářet chytřejší řešení pro analýzu dokumentů.

## Rychlé odpovědi
- **Co znamená „jak číst xmp“?** Jedná se o programové získávání XMP metadat ze souborů.  
- **Která knihovna je vyžadována?** Aspose.Page for Java (k dispozici na stránce ke stažení Aspose).  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence; k dispozici je také bezplatná zkušební verze.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.  
- **Mohu číst XMP i z jiných formátů?** Ano, Aspose.Page dokáže zpracovávat EPS, PDF a několik typů obrázků, které obsahují XMP.

## Požadavky
Než se pustíte do kódu, ujistěte se, že máte:

- **Java Development Kit (JDK)** – Java 8+ nainstalovanou a nakonfigurovanou ve vašem systému.  
- **Aspose.Page for Java** – Stáhněte knihovnu z oficiální stránky [here](https://releases.aspose.com/page/java/).  
- EPS soubor, který obsahuje XMP metadata (např. `xmp1.eps`).  

## Import balíčků
Ve vašem Java projektu importujte potřebné balíčky:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Inicializace vstupního proudu EPS souboru
Nejprve nastavte cestu k adresáři s dokumenty a inicializujte vstupní proud EPS souboru.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Získání XMP metadat
Načtěte XMP metadata z EPS souboru. Pokud soubor XMP metadata neobsahuje, bude vytvořen nový soubor s hodnotami získanými z PS komentářů.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 3: Extrakce informace CreatorTool
Zkontrolujte a vytiskněte hodnotu „CreatorTool“ z XMP metadat.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Krok 4: Extrakce informace CreateDate
Zkontrolujte a vytiskněte hodnotu „CreateDate“ z XMP metadat.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Krok 5: Získání šířky náhledu
Pokud existují náhledy, extrahujte a vytiskněte šířku prvního náhledu.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Krok 6: Extrakce informace formátu
Zkontrolujte a vytiskněte hodnotu „format“ z XMP metadat.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Krok 7: Získání DocumentID
Zkontrolujte a vytiskněte hodnotu „DocumentID“ z XMP metadat.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Proč je to důležité
Čtení XMP metadat vám umožní programově zjistit původ, datum vytvoření a další zásadní atributy dokumentu, aniž byste jej museli otevírat v prohlížeči. To je zvláště užitečné při hromadném zpracování, systémech správy obsahu a digitálních pipelinech, kde metadata řídí indexaci a vyhledávání.

## Časté problémy a tipy
- **Chybějící XMP:** Některé EPS soubory nemusí obsahovat XMP. Volání `getXmpMetadata()` vytvoří minimální sadu na základě existujících PS komentářů, ale úplná metadata získáte jen v případě, že jsou skutečně vložena.  
- **Pole náhledů:** Klíč `xmp:Thumbnails` může obsahovat více položek. Příklad extrahuje jen první; pokud potřebujete všechny náhledy, projděte pole.  
- **Povědomí o jmenných prostorech:** XMP klíče používají jmenné prostory (např. `xmp:`, `dc:`). Ujistěte se, že odkazujete na přesný název klíče, jinak `containsKey` vrátí false.

## Často kladené otázky
### Mohu použít Aspose.Page for Java s jinými programovacími jazyky?
Ano, Aspose.Page podporuje více jazyků, včetně Javy, .NET a dalších. Podívejte se na [documentation](https://reference.aspose.com/page/java/) pro podrobnosti.

### Je k dispozici bezplatná zkušební verze Aspose.Page for Java?
Ano, bezplatnou zkušební verzi získáte [here](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.Page for Java?
Navštivte fórum [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro komunitní podporu.

### Jak získám dočasnou licenci pro Aspose.Page for Java?
Dočasnou licenci můžete získat [here](https://purchase.aspose.com/temporary-license/).

### Existují další zdroje pro Aspose.Page for Java?
Prozkoumejte kompletní [documentation](https://reference.aspose.com/page/java/) a stáhněte knihovnu [here](https://releases.aspose.com/page/java/).

## Další otázky
**Q: Funguje tento postup i s PDF soubory, které obsahují XMP?**  
A: Ano, Aspose.Page může číst XMP z PDF, EPS a několika formátů obrázků.

**Q: Mohu po načtení XMP metadata upravit?**  
A: Rozhodně. Objekt `XmpMetadata` je mutabilní; můžete přidávat, aktualizovat nebo odstraňovat klíče a poté dokument uložit.

**Q: Existuje způsob, jak extrahovat všechny obrázky náhledů, nejen jejich rozměry?**  
A: Můžete získat binární data z vlastnosti `xmpGImg:data` každého záznamu náhledu a zapsat je do souboru.

## Závěr
Nyní ovládáte **jak číst XMP** metadata pomocí Javy a Aspose.Page. Dodržením těchto kroků můžete extrahovat nástroje tvůrců, časová razítka, náhledy, informace o formátu a ID dokumentu — což vám poskytne úplný přehled o vložených metadatech vašich EPS souborů. Nebojte se experimentovat s dalšími XMP jmennými prostory a získávat tak ještě bohatší data pro své aplikace.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose