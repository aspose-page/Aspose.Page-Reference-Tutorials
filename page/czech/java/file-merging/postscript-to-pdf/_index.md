---
date: 2025-11-29
description: Bez námahy sloučte soubory PostScript do PDF v Javě s Aspose.Page. Komplexní
  tutoriál, časté dotazy a zdroje pro bezproblémovou konverzi dokumentů.
language: cs
linktitle: How to Merge PostScript Files to PDF in Java
second_title: Aspose.Page Java API
title: Jak sloučit soubory PostScript do PDF v Javě
url: /java/file-merging/postscript-to-pdf/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}  
{{< blocks/products/pf/main-container >}}  
{{< blocks/products/pf/tutorial-page-section >}}  

# Jak sloučit soubory PostScript do PDF v Javě  

## Úvod  
Sloučení souborů PostScript do jednoho PDF je častý požadavek, když potřebujete spojit zprávy, grafiku nebo výstup tiskárny do přenosného formátu. V tomto tutoriálu se naučíte **jak sloučit soubory PostScript** pomocí knihovny Aspose.Page pro Java, která převádí více `.ps` streamů na čistý, prohledávatelný PDF dokument. Provedeme vás každým krokem, od nastavení prostředí po práci s možnostmi konverze a řešení běžných chyb.  

## Rychlé odpovědi  
- **Jakou knihovnu mám použít?** Aspose.Page pro Java poskytuje dedikované API pro konverzi PostScript → PDF.  
- **Mohu převádět více souborů najednou?** Ano – stačí předat každý PostScript stream stejnému objektu `PsDocument` před uložením.  
- **Potřebuji licenci pro produkci?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro komerční použití.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší (doporučeno JDK 11).  
- **Kde najdu ukázkový kód?** Níže uvedené úryvky kódu jsou připravené ke spuštění.  

## Co je sloučení souborů PostScript?  
Sloučení souborů PostScript znamená vzít dva nebo více `.ps` dokumentů – každý popisuje obsah stránky v jazyce PostScript – a spojit je do jednoho PDF. Tento proces **převádí PostScript do PDF**, zachovává rozvržení, fonty a vektorovou grafiku a vytváří široce podporovaný výstupní formát.  

## Proč použít Aspose.Page pro Javu?  
- **Vysoká věrnost**: Konverze zachovává přesný vzhled původního PostScriptu.  
- **Žádné externí závislosti**: Není potřeba Ghostscript ani nativní binárky.  
- **Detailní kontrola**: Možnosti jako potlačení chyb a vlastní složky s fonty vám umožní přizpůsobit výstup.  

## Předpoklady  
Než začneme, ujistěte se, že máte:  

- **Aspose.Page pro Java** – stáhněte z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- **Java Development Kit (JDK)** – nainstalovaný JDK 8 nebo novější.  
- **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli editor, který preferujete.  

## Import balíčků  
Začněte importováním potřebných tříd, které nám umožní číst PostScript streamy a zapisovat PDF výstup.  

```java
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PdfSaveOptions;
import com.aspose.page.License;

import java.io.FileInputStream;
import java.io.FileOutputStream;
```  

## Krok 1: Import požadovaných balíčků (duplicitně pro přehlednost)  
Opakujeme základní importy, aby byl zdůrazněn hlavní soubor tříd používaných v procesu konverze.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.page.PsDocument;
import com.aspose.page.PdfSaveOptions;
```  

## Krok 2: Nastavte cesty k dokumentu a výstupu  
Definujte, kde se nachází váš zdrojový soubor PostScript a kam se má uložit výsledný PDF. Nahraďte `"Your Document Directory"` skutečnou cestou ke složce na vašem počítači.  

```java
String dataDir = "Your Document Directory";
FileOutputStream pdfStream = new FileOutputStream(dataDir + "PStoPDF.pdf");
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
```  

## Krok 3: Inicializujte objekt PsDocument  
Vytvořte instanci `PsDocument`, která načte vstupní stream PostScriptu. Tento objekt představuje celý dokument PostScript v paměti.  

```java
PsDocument document = new PsDocument(psStream);
```  

## Krok 4: Nastavte možnosti konverze  
Konfigurujte chování konverze. Povolení `suppressErrors` umožní procesu pokračovat i při drobných problémech ve zdroji. Můžete také nasměrovat engine na další složky s fonty, pokud váš PostScript používá vlastní fonty.  

```java
boolean suppressErrors = true;
PdfSaveOptions options = new PdfSaveOptions(suppressErrors);
// options.setAdditionalFontsFolders(new String[]{"FONTS_FOLDER"});
```  

## Krok 5: Inicializujte PdfDevice  
`PdfDevice` je výstupní cíl, který zapisuje PDF data do streamu, který jsme vytvořili dříve. Volitelně můžete specifikovat rozměry stránky nebo formáty obrázků, ale výchozí nastavení funguje ve většině scénářů.  

```java
com.aspose.eps.device.PdfDevice device = new com.aspose.eps.device.PdfDevice(pdfStream);
// Alternatively, specify size and image format if needed
// com.aspose.eps.device.PdfDevice device = new com.aspose.eps.device.PdfDevice(pdfStream, new Dimension(595, 842));
```  

## Krok 6: Uložte dokument do PDF  
Zavolejte metodu `save`, předáte zařízení a možnosti konverze. Blok `try/finally` zajišťuje, že streamy jsou uzavřeny i v případě výjimky.  

```java
try {
    document.save(device, options);
} finally {
    psStream.close();
    pdfStream.close();
}
```  

## Krok 7: Přezkoumejte chyby (pokud jsou)  
Když je `suppressErrors` nastaveno na `true`, API shromažďuje varování a chyby konverze. Projděte `options.getExceptions()` a zaznamenejte nebo zobrazte je pro ladění.  

```java
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```  

## Časté problémy a řešení  

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| **Chybějící fonty** | Font nebyl nalezen ve výchozí systémové cestě | Použijte `options.setAdditionalFontsFolders()` k nasměrování na váš vlastní adresář s fonty. |
| **Prázdné stránky** | Vstupní stream není nastaven na začátek | Ujistěte se, že `psStream` je čerstvý `FileInputStream` pro každý dokument. |
| **Konverze vyvolá `UnsupportedOperationException`** | Použití zastaralé verze Aspose.Page | Aktualizujte na nejnovější vydání Aspose.Page pro Java. |

## Často kladené otázky  

**Otázka: Mohu použít Aspose.Page pro Javu s jinými programovacími jazyky?**  
**Odpověď:** Ano, Aspose poskytuje ekvivalentní knihovny pro .NET, C++ a Python, což umožňuje workflow napříč jazyky.  

**Otázka: Kde najdu další dokumentaci a zdroje?**  
**Odpověď:** Navštivte [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) pro podrobné reference API, ukázkové kódy a osvědčené postupy.  

**Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Javu?**  
**Odpověď:** Rozhodně. Plně funkční zkušební verzi si můžete stáhnout na [Aspose free trial page](https://releases.aspose.com/).  

**Otázka: Jak mohu získat dočasnou licenci pro Aspose.Page pro Javu?**  
**Odpověď:** Dočasnou licenci můžete požádat na [temporary‑license page](https://purchase.aspose.com/temporary-license/).  

**Otázka: Kde mohu získat podporu nebo se spojit s komunitou Aspose?**  
**Odpověď:** Připojte se k diskusi na [Aspose.Page forum](https://forum.aspose.com/c/page/39), kde můžete klást otázky a sdílet zkušenosti.  

## Závěr  
V tomto průvodci jsme ukázali kompletní, připravený přístup k **sloučení souborů PostScript** a **konverzi PostScript do PDF** pomocí Aspose.Page pro Java. Dodržením krok‑za‑krokem instrukcí můžete tuto funkci integrovat do libovolné Java aplikace, ať už zpracováváte jedinou zprávu nebo hromadíte stovky souborů.  

---  

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}  

{{< /blocks/products/pf/main-container >}}  
{{< /blocks/products/pf/main-wrap-class >}}  

{{< blocks/products/products-backtop-button >