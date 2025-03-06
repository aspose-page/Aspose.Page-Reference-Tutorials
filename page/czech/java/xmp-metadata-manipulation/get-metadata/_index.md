---
title: Získejte metadata z XMP pomocí Javy
linktitle: Získejte metadata z XMP pomocí Javy
second_title: Aspose.Page Java API
description: Odemkněte sílu Aspose.Page for Java a bez námahy extrahujte metadata XMP. Vylepšete analýzu dokumentů pomocí našeho podrobného průvodce!
weight: 18
url: /cs/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získejte metadata z XMP pomocí Javy

## Úvod
Vítejte v našem podrobném průvodci o využití Aspose.Page for Java k extrahování metadat ze souborů XMP. XMP (Extensible Metadata Platform) poskytuje standardizovaný způsob ukládání metadat do souborů. Tento tutoriál se zaměřuje na získávání základních informací z XMP pomocí Javy a nabízí pohled na detaily dokumentu.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovanou Javu.
-  Aspose.Page for Java: Stáhněte si a nainstalujte knihovnu Aspose.Page, kterou najdete[tady](https://releases.aspose.com/page/java/).
## Importujte balíčky
Do svého projektu Java naimportujte potřebné balíčky:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Krok 1: Inicializujte vstupní EPS File Stream
Začněte nastavením cesty k adresáři dokumentů a inicializací vstupního datového proudu souborů EPS.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Krok 2: Získejte metadata XMP
Načtěte metadata XMP ze souboru EPS. Pokud soubor postrádá metadata XMP, vygeneruje se nová s hodnotami z komentářů metadat PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 3: Extrahujte informace CreatorTool
Zkontrolujte a vytiskněte hodnotu "CreatorTool" z metadat XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Krok 4: Extrahujte informace CreateDate
Zkontrolujte a vytiskněte hodnotu "CreateDate" z metadat XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Krok 5: Načtěte šířku miniatury
Pokud existují miniatury, extrahujte a vytiskněte šířku první miniatury.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Krok 6: Extrahujte informace o formátu
Zkontrolujte a vytiskněte hodnotu „formát“ z metadat XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Krok 7: Získejte DocumentID
Zkontrolujte a vytiskněte hodnotu „DocumentID“ z metadat XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Závěr
Gratulujeme! Úspěšně jste se naučili extrahovat metadata XMP pomocí Aspose.Page for Java. Tato příručka poskytuje komplexní přehled procesu a zajišťuje, že můžete efektivně získat základní informace z vašich dokumentů.
## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
 Ano, Aspose.Page podporuje více jazyků, včetně Javy, .NET a dalších. Zkontrolovat[dokumentace](https://reference.aspose.com/page/java/) pro detaily.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu podporu pro Aspose.Page for Java?
 Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.
### Jak získám dočasnou licenci pro Aspose.Page for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Existují další zdroje pro Aspose.Page for Java?
 Prozkoumejte kompletní[dokumentace](https://reference.aspose.com/page/java/) a stáhněte si knihovnu[tady](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
