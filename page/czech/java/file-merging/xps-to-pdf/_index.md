---
date: 2025-11-29
description: Naučte se, jak uložit XPS jako PDF v Javě s Aspose.Page Java. Postupujte
  podle našeho krok‑za‑krokem průvodce pro efektivní konverzi XPS na PDF a nastavení
  komprese PDF.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Převod XPS na PDF v Javě pomocí Aspose.Page Java
url: /cs/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XPS na PDF v Javě pomocí Aspose.Page Java

## Úvod
V tomto tutoriálu se naučíte **jak převést XPS na PDF v Javě pomocí Aspose.Page Java**, robustní knihovnu určenou pro konverzi dokumentů v Javě. Ať už potřebujete hromadně zpracovávat faktury, generovat tisknutelné zprávy nebo jednoduše migrovat staré XPS soubory, Aspose.Page Java vám práci učiní rychlou, spolehlivou a plně konfigurovatelnou.

## Rychlé odpovědi
- **Která knihovna provádí konverzi XPS na PDF?** Aspose.Page Java  
- **Jak dlouho trvá základní konverze?** Obvykle méně než sekunda pro jednostránkový XPS soubor.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze stačí pro hodnocení; licence je vyžadována pro produkci.  
- **Mohu řídit kompresi PDF?** Ano – použijte `PdfSaveOptions` k nastavení komprese obrázků a textu.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo novější (doporučeno JDK 11+).

## Co je Aspose.Page Java?
Aspose.Page Java je **vysoce výkonné API**, které umožňuje vývojářům programově vytvářet, upravovat a konvertovat XPS dokumenty. Podporuje vykreslování XPS do PDF, PNG, JPEG a dalších formátů a poskytuje jemnozrnné řízení výstupních nastavení, jako je **nastavení komprese PDF**.

## Proč použít Aspose.Page Java pro konverzi XPS na PDF?
- **Renderování bez závislostí** – žádné nativní knihovny ani externí nástroje.  
- **Přesné zachování rozvržení** – výstupní PDF odráží původní vzhled XPS.  
- **Plná kontrola nad výstupem PDF** – můžete upravit kvalitu obrázků, zvolit kompresní algoritmy a vybrat konkrétní stránky k vykreslení.  
- **Cross‑platform** – funguje na Windows, Linuxu a macOS s libovolným standardním JDK.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK) 8+** – nejnovější JDK se doporučuje pro výkon a bezpečnost.  
2. **Aspose.Page for Java knihovna** – stáhněte JAR z oficiální [Aspose.Page Java dokumentace](https://reference.aspose.com/page/java/).  
3. **IDE** (IntelliJ IDEA, Eclipse, VS Code) nebo jednoduchý textový editor plus nástroje pro sestavení z příkazové řádky (Maven/Gradle).  

## Import balíčků
Add the required imports to your Java class so you can work with XPS documents and PDF output.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Postupný průvodce

### Krok 1: Nastavte cestu ke složce dokumentu
Define the folder that contains your source XPS file and where the PDF will be saved.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Krok 2: Inicializujte výstupní proud PDF
Create a `FileOutputStream` that points to the destination PDF file.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Tip:** Použijte `try‑with‑resources` k automatickému uzavření proudu a zabránění únikům prostředků.

### Krok 3: Načtěte XPS dokument
Instantiate an `XpsDocument` object by loading the source XPS file.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 4: Inicializujte PDF Save Options (Nastavení komprese PDF)
Configure how the PDF should be compressed. This step lets you **set PDF compression** for images and text, which reduces file size without sacrificing quality.

Nastavte, jak má být PDF komprimováno. Tento krok vám umožní **nastavit kompresi PDF** pro obrázky a text, což snižuje velikost souboru bez ztráty kvality.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Proč je to důležité:** Úprava kvality JPEG a typů komprese může zmenšit 10 MB PDF na méně než 2 MB při zachování požadované vizuální věrnosti.

### Krok 5: Vytvořte renderovací zařízení pro formát PDF
`PdfDevice` streamuje vykreslené stránky do výstupního proudu PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Uložte dokument
Finally, render the XPS content to PDF using the configured options.

Nakonec vykreslete obsah XPS do PDF pomocí nakonfigurovaných možností.

```java
document.save(device, options);
```

> **Výsledek:** Po spuštění se `XPStoPDF.pdf` objeví ve složce `dataDir` a bude obsahovat převedené stránky s nastavením komprese, které jste zadali.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|----------|
| **`FileNotFoundException`** | Nesprávná cesta `dataDir` | Ověřte, že adresář existuje a že aplikace má oprávnění pro čtení/zápis. |
| **Prázdné stránky PDF** | Chybějící inicializace `PdfDevice` | Ujistěte se, že `PdfDevice` je vytvořen se stejným `FileOutputStream`, který se používá pro výstup. |
| **Velká velikost PDF** | Výchozí komprese je nízká | Zvyšte `setJpegQualityLevel` nebo přepněte na `PdfImageCompression.Jpeg` s nižší úrovní kvality. |
| **Zobrazí se jen některé stránky** | Filtr `setPageNumbers` vylučuje stránky | Upravte pole tak, aby zahrnovalo všechny požadované stránky, nebo odstraňte volání pro export všech stránek. |

## Často kladené otázky

**Q: Je Aspose.Page Java kompatibilní s různými verzemi Javy?**  
A: Ano, Aspose.Page Java podporuje Java 8 až Java 21, včetně distribucí Oracle i OpenJDK.

**Q: Mohu přizpůsobit nastavení komprese pro konvertovaný PDF?**  
A: Rozhodně. Použijte `PdfSaveOptions` k nastavení kvality JPEG, typu komprese obrázků a komprese textu, jak je ukázáno v kroku 4.

**Q: Kde mohu najít další podporu nebo diskuse komunity?**  
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro pomoc od komunity, ukázky kódu a tipy na řešení problémů.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page?**  
A: Ano, můžete si stáhnout plně funkční zkušební verzi ze [stránky ke stažení Aspose](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page?**  
A: Dočasnou licenci lze požádat [zde](https://purchase.aspose.com/temporary-license/).

## Závěr
Využitím **Aspose.Page Java** můžete snadno **uložit XPS jako PDF** a řídit každý aspekt výstupu, od výběru stránek po kompresi. Tento tutoriál pokrývá vše, co potřebujete k integraci konverze XPS na PDF do vašich Java aplikací, ať už vytváříte jednorázový nástroj nebo rozsáhlý pipeline pro zpracování dokumentů.

---

**Poslední aktualizace:** 2025-11-29  
**Testováno s:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}