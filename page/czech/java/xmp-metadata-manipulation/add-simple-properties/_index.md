---
title: Přidejte jednoduché vlastnosti v XMP pomocí Java
linktitle: Přidejte jednoduché vlastnosti v XMP pomocí Java
second_title: Aspose.Page Java API
description: Odemkněte potenciál Aspose.Page pro Java pomocí našeho průvodce přidáváním vlastností do metadat XMP v souborech EPS. Zvyšte úroveň zpracování dokumentů bez námahy!
type: docs
weight: 14
url: /cs/java/xmp-metadata-manipulation/add-simple-properties/
---
## Úvod
neustále se vyvíjejícím prostředí zpracování dokumentů je efektivní správa metadat zásadní. Aspose.Page for Java umožňuje vývojářům bezproblémově manipulovat s daty Extensible Metadata Platform (XMP). V tomto tutoriálu prozkoumáme proces přidávání jednoduchých vlastností do XMP pomocí Javy a poskytneme vám komplexního průvodce krok za krokem.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Page for Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
- Ukázkový soubor EPS obsahující metadata. Pokud žádný nemáte, použijte dodaný soubor „xmp3.eps“.
## Importujte balíčky
Ujistěte se, že importujete potřebné balíčky pro nastartování vašeho projektu:
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
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, získáme nový soubor vyplněný hodnotami z komentářů metadat PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 2: Přidejte vlastnost Date
```java
// Přidejte hodnotu vlastnosti data "xmp:Date1".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Krok 3: Přidejte vlastnost celé číslo
```java
// Přidejte celočíselnou hodnotu "xmp:Intg1".
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Krok 4: Přidejte dvojitou vlastnost
```java
// Přidejte hodnotu double vlastnosti "xmp:Double1".
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Krok 5: Přidejte vlastnost řetězce
```java
// Přidejte hodnotu vlastnosti řetězce "xmp:String1".
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Krok 6: Uložte dokument
```java
// Inicializujte výstupní proud souboru EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Uložte dokument se změněnými metadaty XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Krok 7: Zavřete streamy
```java
// Zavřete vstupní EPS stream
psStream.close();
```
## Závěr
Aspose.Page for Java zjednodušuje proces manipulace s metadaty XMP v souborech EPS. Podle tohoto podrobného průvodce můžete bez námahy přidat jednoduché vlastnosti pro vylepšení metadat vašeho dokumentu.
## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale jsou k dispozici verze pro jiné jazyky, jako je .NET.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, můžete prozkoumat funkce Aspose.Page získáním bezplatné zkušební verze[tady](https://releases.aspose.com/).
### Kde najdu podrobnou dokumentaci k Aspose.Page for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Lze získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde mohu zakoupit Aspose.Page pro Java?
 Produkt si můžete zakoupit[tady](https://purchase.aspose.com/buy).