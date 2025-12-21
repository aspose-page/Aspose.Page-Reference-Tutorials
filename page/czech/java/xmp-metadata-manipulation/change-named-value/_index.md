---
date: 2025-12-21
description: aspose page xmp tutorial – Naučte se, jak upravit metadata XMP v souborech
  EPS pomocí Aspose.Page pro Javu v přehledném, krok‑za‑krokem průvodci.
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: aspose page xmp tutorial – Změna pojmenované hodnoty v XMP pomocí Java
url: /cs/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose page xmp tutorial – Změna pojmenované hodnoty v XMP pomocí Javy

V moderních pracovních postupech s dokumenty **Aspose.Page for Java** usnadňuje čtení, úpravu a zápis XMP metadat uvnitř souborů EPS. Tento **aspose page xmp tutorial** vás provede změnou pojmenované hodnoty v XMP paketu, takže můžete udržet metadata dokumentu přesná a prohledávatelná. Ať už aktualizujete rozměry stránky, informace o autorovi nebo vlastní značky, níže uvedené kroky ukazují přesně, jak to provést v Javě.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Změna pojmenované XMP hodnoty v souboru EPS pomocí Aspose.Page for Java.  
- **Která verze knihovny je požadována?** Jakákoli nedávná verze Aspose.Page for Java (API je stabilní již několik let).  
- **Potřebuji licenci?** Pro produkci je vyžadována dočasná nebo plná licence; pro testování funguje bezplatná zkušební verze.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro vývojáře obeznámeného s Java I/O.  
- **Mohu to použít s jinými formáty souborů?** XMP API je také k dispozici pro PDF, SVG a další formáty podporované Aspose.Page.

## Co jsou XMP metadata?
XMP (Extensible Metadata Platform) je standardizovaný formát pro vkládání bohatých metadat—jako je tvůrce, název a vlastní vlastnosti—přímo do souborů. V dokumentech EPS existuje XMP vedle tradičních PostScript komentářů, což umožňuje aplikacím číst a upravovat metadata, aniž by měnily vizuální obsah.

## Proč používat Aspose.Page for Java pro úpravu XMP?
- **Plná kontrola** – Přístup k jakékoli XMP vlastnosti, včetně vlastních struktur, bez nutnosti parsování surového XML.  
- **Konzistence napříč formáty** – Stejné API funguje pro EPS, PDF a SVG, což zjednodušuje údržbu kódu.  
- **Žádné externí závislosti** – Čistá Java knihovna, není potřeba nativní kód ani další parsery.  
- **Robustní zpracování chyb** – Vestavěná validace zajišťuje, že výsledný EPS zůstává v souladu se standardy.

## Úvod
Aspose.Page for Java je robustní Java knihovna, která usnadňuje manipulaci a zpracování souborů EPS. Pokud jde o práci s XMP metadaty v těchto souborech, Aspose.Page poskytuje vývojářům komplexní sadu funkcí. V tomto tutoriálu se zaměříme na změnu pojmenované hodnoty v XMP a nabídneme jasný a stručný návod pro vývojáře, kteří chtějí rozšířit své schopnosti zpracování dokumentů.

## Předpoklady
Před zahájením tutoriálu se ujistěte, že máte následující předpoklady:

1. **Java vývojové prostředí** – Ujistěte se, že máte na svém počítači nastavené Java vývojové prostředí.  
2. **Aspose.Page for Java knihovna** – Stáhněte a integrujte knihovnu Aspose.Page for Java do svého projektu. Knihovnu a podrobnou dokumentaci najdete [zde](https://reference.aspose.com/page/java/).  
3. **Ukázkový EPS soubor** – Mějte připravený ukázkový EPS soubor pro experimentování. Pokud žádný nemáte, můžete použít poskytnutý ukázkový soubor s názvem **"xmp4.eps."**

## Import balíčků
Pro zahájení procesu importujte potřebné balíčky ve svém Java kódu. Tyto balíčky jsou nezbytné pro interakci s Aspose.Page for Java. Přidejte následující řádky na začátek svého Java souboru:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

Nyní rozdělíme proces změny pojmenované hodnoty v XMP pomocí Aspose.Page for Java do několika kroků:

## Krok 1: Inicializace vstupního EPS souborového proudu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Krok 2: Inicializace PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Získání XMP metadat
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 4: Nastavení nové hodnoty v XMP
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Krok 5: Inicializace výstupního EPS souborového proudu
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Krok 6: Uložení dokumentu s upravenými XMP metadaty
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 7: Uzavření vstupního EPS proudu
```java
// Close input EPS stream
psStream.close();
```

Tento krok‑za‑krokem návod zajišťuje systematický přístup ke změně pojmenované hodnoty v XMP pomocí Aspose.Page for Java. Dodržením těchto kroků můžete tuto funkci bez problémů integrovat do svých Java aplikací.

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že `dataDir` ukazuje na správnou složku a že `xmp4.eps` existuje.  
- **LicenseException** – Pokud vidíte chyby licence, ujistěte se, že je načten platný soubor licence Aspose.Page před vytvořením `PsDocument`.  
- **Metadata Not Updated** – Po uložení otevřete výsledný EPS v prohlížeči metadat (např. Adobe Bridge), abyste potvrdili, že se nová hodnota zobrazila.

## Závěr
Na závěr, Aspose.Page for Java zjednodušuje proces práce s XMP metadaty v EPS souborech. Tento tutoriál vás vybavil znalostmi pro efektivní změnu pojmenované hodnoty v XMP, čímž rozšiřuje vaše schopnosti zpracování dokumentů.

## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale Aspose poskytuje podobné knihovny pro různé programovací jazyky.

### Je k dispozici bezplatná zkušební verze pro Aspose.Page for Java?
Ano, můžete si vyzkoušet bezplatnou zkušební verzi Aspose.Page for Java [zde](https://releases.aspose.com/).

### Kde najdu další podporu a diskuse o Aspose.Page for Java?
Navštivte [Aspose.Page fórum](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Kde mohu zakoupit Aspose.Page for Java?
Pro nákup Aspose.Page for Java navštivte [stránku nákupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.Page for Java (latest release)  
**Autor:** Aspose