---
date: 2025-12-21
description: Naučte se, jak pomocí Aspose.Page upravit XMP v EPS dokumentech pomocí
  Javy. Rychle vylepšete metadata pomocí Aspose.Page pro Javu.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page upravit xmp – Změna hodnot v XMP pomocí Javy
url: /cs/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změna hodnot v XMP pomocí Javy

## Úvod
Pokud potřebujete **aspose.page modify xmp** data uvnitř souboru EPS, jste na správném místě. V tomto tutoriálu vás provedeme přesnými kroky potřebnými k načtení, aktualizaci a uložení hodnot XMP (Extensible Metadata Platform) pomocí knihovny Aspose.Page pro Javu. Na konci budete schopni přizpůsobit metadata dokumentu – jako je tvůrce, název a datum úpravy – tak, aby odpovídala požadavkům vašeho projektu.

## Rychlé odpovědi
- **Co dělá “aspose.page modify xmp”?** Umožňuje číst a zapisovat XMP metadata v EPS souborech pomocí Aspose.Page Java API.  
- **Která verze knihovny je vyžadována?** Jakákoli aktuální verze Aspose.Page pro Java (API je stabilní napříč verzemi).  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze stačí pro hodnocení; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu změnit více XMP polí najednou?** Ano – zavolejte `put` pro každé pole před uložením dokumentu.  
- **Je potřeba nastavení časové zóny?** Nastavení výchozí časové zóny (např. UTC) zajišťuje konzistentní hodnoty data.

## Co je XMP a proč jej upravovat?
XMP (Extensible Metadata Platform) je standardizovaný způsob, jak vložit bohatá metadata přímo do souborů jako EPS, PDF a obrázky. Aktualizace XMP vám umožní řídit, jak jsou dokumenty indexovány, zobrazovány a vyhledávány – což je klíčové pro branding, soulad s předpisy a automatizaci pracovních postupů.

## Proč použít Aspose.Page pro Javu?
- **Plnohodnotné API** – Není potřeba externí nástroje; vše je zpracováno v rámci procesu.  
- **Cross‑platform** – Funguje na jakémkoli OS, který podporuje Javu.  
- **Žádné nativní závislosti** – Čistá Java implementace usnadňuje nasazení.  
- **Robustní podpora** – Zpracovává existující XMP bloky i vytváří nové z PS komentářů, pokud chybí.

## Požadavky
Před zahájením tohoto tutoriálu se ujistěte, že máte splněny následující požadavky:
1. **Vývojové prostředí Java** – JDK (8 nebo novější) a IDE nebo nástroj pro sestavení dle vašeho výběru.  
2. **Knihovna Aspose.Page pro Java** – Stáhněte a nainstalujte knihovnu Aspose.Page pro Java. Potřebný balíček najdete [zde](https://releases.aspose.com/page/java/).

## Import balíčků
Začněte importováním potřebných balíčků do vašeho Java projektu. Tyto balíčky jsou nezbytné pro interakci a manipulaci s EPS dokumenty.

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

## Krok 1: Získání XMP metadat
Načtěte XMP metadata z EPS dokumentu. Pokud EPS soubor neobsahuje XMP metadata, vytvoří se nová s hodnotami z PS komentářů, jako jsou %%Creator, %%CreateDate a %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Změna hodnoty „ModifyDate“
Upravte hodnotu „ModifyDate“ v XMP metadatech tak, aby odrážela požadované datum.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Krok 3: Změna hodnoty „Creator“
Aktualizujte hodnotu „Creator“ v XMP metadatech, abyste určili tvůrce dokumentu.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Krok 4: Změna hodnoty „Title“
Upravte hodnotu „Title“ v XMP metadatech a nastavte vhodný název dokumentu.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Krok 5: Uložení dokumentu s upravenými XMP metadaty
Uložte dokument s aktualizovanými XMP metadaty do nového EPS souboru.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Časté problémy a řešení
- **Chybějící XMP blok** – API jej automaticky vytvoří z PS komentářů, ale můžete také ručně vytvořit `XmpMetadata`, pokud je potřeba.  
- **Neshody časových zón** – Vždy nastavte `TimeZone.setDefault` před vytvořením objektu `Date`, aby se předešlo neočekávaným posunům.  
- **Chyby přístupu k souborům** – Ověřte, že vstupní a výstupní cesty jsou správné a že má vaše aplikace oprávnění ke čtení/zápisu.

## Často kladené otázky

**Q: Jak mohu řešit časové zóny při úpravě XMP hodnot?**  
A: Využijte `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, aby byla zajištěna konzistence nastavení časové zóny.

**Q: Mohu změnit více XMP hodnot v jedné operaci?**  
A: Ano, použitím metody `put` pro každou požadovanou hodnotu můžete upravit více XMP hodnot najednou.

**Q: Kde najdu další dokumentaci k Aspose.Page pro Javu?**  
A: Prozkoumejte komplexní dokumentaci [zde](https://reference.aspose.com/page/java/).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page pro Javu?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro Aspose.Page pro Javu?**  
A: Dočasnou licenci získáte [zde](https://purchase.aspose.com/temporary-license/).

**Q: Ovlivňuje úprava XMP vizuální obsah EPS?**  
A: Ne. Změny XMP jsou pouze metadata a nemění grafické prvky EPS souboru.

**Q: Mohu programově načíst zpět aktualizované hodnoty pro ověření změny?**  
A: Rozhodně – stačí zavolat `xmp.get("dc:creator")` (nebo příslušný klíč) po uložení a před uzavřením dokumentu.

## Závěr
Gratulujeme! Úspěšně jste prošli procesem **aspose.page modify xmp** hodnot v EPS dokumentech pomocí Aspose.Page pro Javu. Tento tutoriál vás vybavil znalostmi pro úpravu metadat, což zajistí, že vaše dokumenty budou přesně odpovídat vašim specifickým požadavkům.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
