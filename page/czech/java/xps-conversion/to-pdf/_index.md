---
date: 2026-03-13
description: Naučte se, jak provést konverzi Aspose Page z XPS do PDF v Javě. Tento
  krok‑za‑krokem průvodce ukazuje, jak renderovat PDF z XPS, nastavit čísla stránek
  PDF a optimalizovat výstup.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Aspose Page Conversion – Jak převést XPS do PDF v Javě
url: /cs/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Page Conversion – Jak převést XPS na PDF v Javě

Převod souborů XPS do PDF je běžná potřeba, když potřebujete univerzálně zobrazitelný formát dokumentu. V tomto tutoriálu objevíte **aspose page conversion** v akci, pomocí Aspose.Page pro Java k **renderování PDF z XPS** pomocí několika řádků kódu. Ať už budujete systém pro správu dokumentů, generujete tisknutelné zprávy nebo archivujete soubory, tento průvodce vás provede celým procesem, od požadavků po řešení problémů.

## Rychlé odpovědi
- **Jaká knihovna provádí konverzi?** Aspose.Page for Java.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní nastavení.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkci.  
- **Mohu převést jen vybrané stránky?** Ano – použijte možnost *specify PDF page numbers*.  
- **Je konverze bezztrátová?** Knihovna zachovává vektorovou grafiku a věrnost textu.  

## Co je Aspose Page Conversion z XPS do PDF?
Aspose Page conversion převádí dokumenty XPS (XML Paper Specification) — formát s pevně daným rozvržením od Microsoftu — do PDF, de‑facto standardu pro sdílení a tisk. Konverze zachovává rozvržení, písma a vektorovou grafiku, což zajišťuje, že výsledné PDF vypadá přesně jako původní XPS.

## Proč použít Aspose.Page pro Java k renderování PDF z XPS?
- **Vysoká věrnost** – zachovává vektorovou grafiku, písma a rozvržení.  
- **Detailní kontrola** – můžete nastavit kvalitu obrázků, kompresi a dokonce vybrat konkrétní stránky.  
- **Žádné externí závislosti** – čistá Java, funguje na jakékoli platformě podporující JDK.  
- **Vestavěný výběr stránek** – snadno **specify PDF page numbers** pro snížení velikosti souboru.

## Požadavky
- **Java Development Kit (JDK)** – libovolná aktuální verze (doporučeno 8+).  
- **Aspose.Page for Java** – stáhněte knihovnu z oficiální [dokumentace](https://reference.aspose.com/page/java/).  
- XPS soubor, který chcete převést.

## Import balíčků
Ve vašem Java projektu importujte potřebné balíčky pro práci s Aspose.Page for Java. Tento krok je klíčový pro přístup k funkcím potřebným pro převod XPS na PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Průvodce krok za krokem

### Krok 1: Nastavte adresář dokumentu
Definujte cestu k složce, která obsahuje váš zdrojový soubor XPS.

```java
String dataDir = "Your Document Directory";
```

### Krok 2: Inicializujte výstupní proud PDF
Vytvořte `FileOutputStream`, který přijme vygenerovaný PDF.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Krok 3: Načtěte XPS dokument
Načtěte soubor XPS pomocí Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 4: Inicializujte možnosti uložení PDF  
Vytvořte možnosti pro konverzi. Zde můžete **specify PDF page numbers**, upravit kvalitu obrázků a nastavit kompresi.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Krok 5: Vytvořte zařízení pro renderování PDF  
Nastavte renderovací zařízení, které zapíše výstup PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Uložte dokument  
Nakonec uložte XPS dokument jako PDF pomocí nastavených možností a zařízení.

```java
document.save(device, options);
```

Opakujte tyto kroky a upravte cesty k souborům a možnosti podle vašeho konkrétního scénáře.

## Jak specifikovat čísla PDF stránek při konverzi XPS
Pokud potřebujete jen podmnožinu stránek z původního XPS, naplňte pole `setPageNumbers` požadovanými indexy stránek (počínaje 1). To pomáhá snížit velikost souboru a dobu zpracování.

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že `dataDir` ukazuje na správný adresář a že název XPS souboru odpovídá.  
- **LicenseException** – Pro produkční použití je vyžadována platná licence Aspose.Page; jinak knihovna běží v evaluačním režimu s vodoznakem.  
- **Nízká kvalita obrázku** – Zvyšte `setJpegQualityLevel` nebo přepněte na bezztrátovou kompresi, pokud je to potřeba.

## Často kladené otázky
### Můžu převést XPS soubory s více stránkami pomocí Aspose.Page pro Java?
Ano, můžete **specify PDF page numbers** v `PdfSaveOptions` (viz Krok 4) a zahrnout libovolné stránky, které potřebujete.

### Kde najdu další podporu nebo mohu diskutovat o dotazech souvisejících s Aspose.Page?
Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
Ano, můžete si vyzkoušet funkce pomocí [bezplatné zkušební verze](https://releases.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?
Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/) pro podrobnosti o dočasné licenci.

### Kde mohu zakoupit licenci Aspose.Page pro Java?
Licenci si můžete zakoupit [zde](https://purchase.aspose.com/buy).

**Poslední aktualizace:** 2026-03-13  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}