---
title: Změňte položky pole v XMP pomocí Java
linktitle: Změňte položky pole v XMP pomocí Java
second_title: Aspose.Page Java API
description: Naučte se, jak změnit položky pole v XMP pomocí Aspose.Page for Java. Upravte metadata bez námahy pomocí našeho podrobného průvodce. Vylepšete své dokumenty EPS nyní!
weight: 15
url: /cs/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změňte položky pole v XMP pomocí Java

## Úvod
Vítejte v našem komplexním průvodci změnou položek pole v XMP pomocí Aspose.Page pro Java! Aspose.Page je výkonná Java knihovna, která vám umožňuje bezproblémově pracovat s metadaty XMP v souborech EPS. V tomto tutoriálu vás provedeme procesem úpravy položek pole v metadatech XMP, což vám pomůže vylepšit a přizpůsobit vaše dokumenty EPS.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Knihovna Aspose.Page pro Javu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/java/).
## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do vašeho projektu Java. Ujistěte se, že máte v projektu zahrnutou knihovnu Aspose.Page.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## Krok 1: Získejte metadata XMP
Nejprve načtěte metadata XMP ze souboru EPS. Pokud soubor EPS ještě neobsahuje metadata XMP, vytvoří se nový s hodnotami z komentářů k metadatům PS, jako je %%Creator, %%CreateDate, %%Title atd.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, bude nový soubor vyplněn hodnotami z komentářů metadat PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 2: Nastavte položku pole "dc:title".
Nyní nastavíme položku pole "dc:title" na index 0 s novou hodnotou.
```java
// Nastavte položku pole "dc:title" na index 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Krok 3: Nastavte položku pole „dc:creator“.
Podobně nastavte položku pole "dc:creator" na index 0 s novou hodnotou tvůrce.
```java
// Nastavte položku pole "dc:creator" na index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Krok 4: Inicializujte výstupní soubor EPS
Připravte výstupní proud souboru EPS, kam bude uložen upravený dokument.
```java
// Inicializujte výstupní proud souboru EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Krok 5: Uložte dokument se změněnými metadaty XMP
Uložte dokument s aktualizovanými metadaty XMP.
```java
//Uložte dokument se změněnými metadaty XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak změnit položky pole v XMP pomocí Aspose.Page for Java. Tento výukový program poskytuje podrobné pokyny, které zajišťují, že můžete své dokumenty EPS bez námahy vylepšit přizpůsobenými metadaty.

## Nejčastější dotazy
### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page je primárně navržen pro Javu, ale Aspose poskytuje podobné knihovny pro jiné jazyky.
### Kde najdu podrobnou dokumentaci k Aspose.Page for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde si mohu zakoupit plnou verzi Aspose.Page for Java?
 Můžete si koupit plnou verzi[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
