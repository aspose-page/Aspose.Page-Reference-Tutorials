---
title: Přidejte položky pole v metadatech XMP pomocí Java
linktitle: Přidejte položky pole v metadatech XMP pomocí Java
second_title: Aspose.Page Java API
description: Vylepšete soubory EPS pomocí Aspose.Page pro Java. Naučte se snadno přidávat položky pole do metadat XMP. Nyní postupujte podle našeho podrobného průvodce!
weight: 10
url: /cs/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte položky pole v metadatech XMP pomocí Java

## Úvod
Vítejte v našem podrobném průvodci používáním Aspose.Page for Java k přidávání položek pole do metadat XMP. Aspose.Page je výkonná Java knihovna, která vám umožňuje manipulovat a pracovat s různými formáty dokumentů, včetně souborů EPS. V tomto tutoriálu se zaměříme na konkrétní úlohu přidávání položek pole do metadat XMP pomocí Javy.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
- Nainstalovaná knihovna Aspose.Page for Java.
- Základní znalost programování v Javě.
- Platný soubor EPS s existujícími metadaty XMP nebo komentáři k metadatům PS.
## Importujte balíčky
Chcete-li začít, musíte importovat potřebné balíčky pro práci s Aspose.Page. Na začátek souboru Java vložte následující řádky:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Krok 1: Získejte metadata XMP
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, získáme nový soubor vyplněný hodnotami z komentářů metadat PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.getXmpMetadata();
```
tomto kroku načteme existující metadata XMP ze souboru EPS. Pokud soubor EPS již neobsahuje metadata XMP, Aspose.Page vygeneruje nová a naplní je hodnotami z komentářů metadat PS.
## Krok 2: Přidejte položku pole „dc:title“.
```java
// Přidejte ještě jednu položku pole "dc:title".
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nyní přidáme novou položku pole do vlastnosti "dc:title" v metadatech XMP. Nahraďte "NewTitle" požadovaným názvem.
## Krok 3: Přidejte položku pole „dc:creator“.
```java
// Přidejte ještě jednu položku pole „dc:creator“.
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Podobně přidáme novou položku pole do vlastnosti „dc:creator“ v metadatech XMP. Nahraďte „NewCreator“ požadovanými informacemi o tvůrci.
## Krok 4: Inicializujte výstupní soubor EPS
```java
// Inicializujte výstupní proud souboru EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Připravte výstupní proud souboru EPS, kam bude uložen upravený dokument s aktualizovanými metadaty XMP.
## Krok 5: Uložte dokument se změněnými metadaty XMP
```java
//Uložte dokument se změněnými metadaty XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Uložte dokument s aktualizovanými metadaty XMP do výstupního souboru EPS.
## Závěr
Gratulujeme! Úspěšně jste se naučili přidávat položky pole do metadat XMP pomocí Aspose.Page for Java. Tato výkonná knihovna zjednodušuje proces manipulace se soubory EPS a poskytuje rozsáhlé funkce pro zpracování dokumentů.
## Často kladené otázky

### Mohu použít Aspose.Page for Java s jinými formáty dokumentů?
Ano, Aspose.Page podporuje různé formáty dokumentů, včetně EPS, PDF a XPS.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Page for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Jak si mohu zakoupit Aspose.Page pro Java?
 Produkt si můžete zakoupit[tady](https://purchase.aspose.com/buy).
### Jsou k dispozici dočasné licence pro Aspose.Page for Java?
 Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
