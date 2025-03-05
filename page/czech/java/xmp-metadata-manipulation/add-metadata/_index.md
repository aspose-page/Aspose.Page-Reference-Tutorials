---
title: Přidejte metadata v XMP pomocí Java
linktitle: Přidejte metadata v XMP pomocí Java
second_title: Aspose.Page Java API
description: Prozkoumejte bezproblémovou integraci Aspose.Page for Java a zjistěte, jak bez námahy přidat metadata XMP do souborů EPS. Pozvedněte svou hru pro správu dokumentů ještě dnes!
type: docs
weight: 11
url: /cs/java/xmp-metadata-manipulation/add-metadata/
---
## Úvod
Chcete vylepšit metadata svého dokumentu přidáním informací XMP pomocí Javy? Už nehledejte! Tento podrobný průvodce vás provede procesem přidávání metadat do souboru EPS pomocí knihovny Aspose.Page for Java. Aspose.Page je výkonný nástroj, který zjednodušuje úlohy manipulace s dokumenty v aplikacích Java.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Page for Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
- Soubor EPS, který chcete upravit.
## Importujte balíčky
Nejprve naimportujte potřebné balíčky do svého programu Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Krok 1: Získejte metadata XMP
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, vytvoří se nový pomocí hodnot z komentářů metadat PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.getXmpMetadata();
```
Ujistěte se, že jste nahradili "Your Document Directory" skutečnou cestou, kde jsou uloženy vaše dokumenty.

## Krok 2: Načtěte hodnotu CreatorTool
```java
// Získejte hodnotu „CreatorTool“.
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Krok 3: Načtěte hodnotu CreateDate
```java
// Získejte hodnotu „CreateDate“.
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Krok 4: Načtení hodnoty názvu
```java
// Získejte hodnotu „Titul“.
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Krok 5: Načtení hodnoty formátu
```java
//Získejte hodnotu "formát".
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Krok 6: Načtení hodnoty tvůrce
```java
// Získejte hodnotu „tvůrce“.
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Krok 7: Načtení hodnoty MetadataDate
```java
// Získejte hodnotu "MetadataDate".
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Krok 8: Uložte dokument s novými metadaty XMP
```java
// Inicializujte výstupní proud souboru EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Uložte dokument s novými metadaty XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Nakonec nezapomeňte zavřít vstupní EPS stream:
```java
// Zavřete vstupní EPS stream
psStream.close();
```
Nyní jste úspěšně přidali metadata do svého souboru EPS pomocí Aspose.Page for Java!
## Závěr
V tomto tutoriálu jsme prozkoumali proces přidávání metadat XMP do souboru EPS pomocí knihovny Aspose.Page for Java. Tento výkonný nástroj vám umožňuje bezproblémově manipulovat s dokumenty a vylepšuje tak váš celkový zážitek ze správy dokumentů.
## Nejčastější dotazy
### Otázka: Je Aspose.Page for Java k použití zdarma?
 A: Aspose.Page for Java je komerční produkt. Jeho funkce můžete prozkoumat prostřednictvím bezplatné zkušební verze[tady](https://releases.aspose.com/).
### Otázka: Kde najdu dokumentaci k Aspose.Page for Java?
 Odpověď: Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Odpověď: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Jaké formáty souborů podporuje Aspose.Page for Java?
A: Aspose.Page for Java podporuje různé formáty, včetně EPS, PDF a XPS.
### Otázka: Mohu si zakoupit Aspose.Page pro Java?
 Odpověď: Ano, můžete si zakoupit Aspose.Page pro Javu[tady](https://purchase.aspose.com/buy).