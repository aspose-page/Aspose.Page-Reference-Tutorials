---
title: Změňte hodnoty v XMP pomocí Java
linktitle: Změňte hodnoty v XMP pomocí Java
second_title: Aspose.Page Java API
description: Vylepšete dokumenty EPS pomocí Aspose.Page pro Java. Bez námahy upravujte metadata XMP pro přizpůsobený a profesionální obsah. #Vývoj Java
type: docs
weight: 17
url: /cs/java/xmp-metadata-manipulation/change-values/
---
## Úvod
V oblasti zpracování a manipulace s dokumenty vyniká Aspose.Page for Java jako výkonný nástroj. Tento tutoriál se ponoří do procesu změny hodnot XMP (Extensible Metadata Platform) v dokumentech EPS (Encapsulated PostScript) pomocí Java s knihovnou Aspose.Page. Podle poskytnutého podrobného průvodce se naučíte, jak snadno upravit metadata a zajistit, aby byly vaše dokumenty přizpůsobeny vašim konkrétním požadavkům.
## Předpoklady
Než se pustíme do tohoto tutoriálu, ujistěte se, že máte splněny následující předpoklady:
1. Vývojové prostředí Java: Ujistěte se, že máte na svém počítači funkční vývojové prostředí Java.
2.  Aspose.Page for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Page for Java. Potřebný balíček najdete[tady](https://releases.aspose.com/page/java/).
## Importujte balíčky
Začněte importem požadovaných balíčků do vašeho projektu Java. Tyto balíčky jsou životně důležité pro interakci a manipulaci s dokumenty EPS.
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
## Krok 1: Získejte metadata XMP
Načtěte metadata XMP z dokumentu EPS. Pokud soubor EPS neobsahuje metadata XMP, vytvoří se nový s hodnotami z komentářů metadat PS, jako jsou %%Creator, %%CreateDate a %%Title.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, vytvoří se nový s hodnotami z komentářů metadat PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 2: Změňte hodnotu "ModifyDate".
Upravte hodnotu "ModifyDate" v metadatech XMP tak, aby odrážela požadované datum.
```java
// Změňte hodnotu "ModifyDate".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Krok 3: Změňte hodnotu „Creator“.
Aktualizujte hodnotu "Creator" v metadatech XMP, abyste určili tvůrce dokumentu.
```java
// Změňte hodnotu „tvůrce“.
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Krok 4: Změňte hodnotu "Titul".
Upravte hodnotu "Title" v metadatech XMP, abyste nastavili vhodný název pro dokument.
```java
//Změňte hodnotu "title".
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Krok 5: Uložte dokument se změněnými metadaty XMP
Uložte dokument s aktualizovanými metadaty XMP do nového souboru EPS.
```java
// Inicializujte výstupní proud souboru EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Uložte dokument se změněnými metadaty XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Závěr
Gratulujeme! Úspěšně jste prošli procesem změny hodnot XMP v dokumentech EPS pomocí Aspose.Page for Java. Tento výukový program vás vybavil znalostmi pro úpravu metadat a zajistil, že vaše dokumenty budou hladce odpovídat vašim konkrétním požadavkům.
## Nejčastější dotazy
### Otázka: Jak mohu při úpravě hodnot XMP zvládnout úvahy o časovém pásmu?
 Využít`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` pro zajištění konzistence nastavení časového pásma.
### Otázka: Mohu změnit více hodnot XMP v jedné operaci?
 Ano, pomocí`put` metodou pro každou požadovanou hodnotu můžete upravit více hodnot XMP současně.
### Otázka: Kde najdu další dokumentaci k Aspose.Page for Java?
 Prozkoumejte komplexní dokumentaci[tady](https://reference.aspose.com/page/java/).
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).