---
date: 2025-12-23
description: Naučte se, jak převést XPS na PDF v Javě pomocí Aspose.Page. Tento průvodce
  ukazuje krok za krokem převod, jak renderovat PDF z XPS a nastavit čísla stránek
  PDF.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Jak převést XPS na PDF v Javě
url: /cs/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést XPS na PDF v Javě

## Jak převést XPS na PDF v Javě
V oblasti vývoje v Javě je **jak převést XPS na PDF** častou otázkou. Ať už budujete systém pro správu dokumentů nebo potřebujete generovat tisknutelné zprávy, spolehlivé převádění souborů XPS může být zásadní. Naštěstí Aspose.Page pro Java to usnadňuje a umožňuje **vytvořit PDF z XPS** pomocí několika řádků kódu.

## Rychlé odpovědi
- **Která knihovna provádí převod?** Aspose.Page for Java.
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní nastavení.
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkci.
- **Mohu převést jen vybrané stránky?** Ano – použijte možnost *specify PDF page numbers*.
- **Je převod bezztrátový?** Knihovna zachovává vektorovou grafiku a věrnost textu.

## Co je převod XPS na PDF?
XPS (XML Paper Specification) je formát dokumentu s pevnou rozložením od Microsoftu. Převodem na PDF můžete dokumenty sdílet, tisknout nebo archivovat pomocí univerzálně akceptovaného standardu PDF.

## Proč použít Aspose.Page pro Java k vytvoření PDF z XPS?
- **Vysoká věrnost** – zachovává vektorovou grafiku, písma a rozložení.
- **Detailní kontrola** – můžete nastavit kvalitu obrázků, kompresi a dokonce vybrat konkrétní stránky.
- **Žádné externí závislosti** – čistá Java, funguje na jakékoli platformě podporující JDK.

## Předpoklady
Předtím, než začnete, ujistěte se, že máte:

- **Java Development Kit (JDK)** – jakoukoli nedávnou verzi (doporučeno 8+).
- **Aspose.Page for Java** – stáhněte knihovnu z oficiální [dokumentace](https://reference.aspose.com/page/java/).
- XPS soubor, který chcete převést.

## Import balíčků
Ve vašem Java projektu importujte požadované balíčky pro práci s Aspose.Page pro Java. Tento krok je klíčový pro přístup k funkcím potřebným pro převod XPS na PDF.

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

### Krok 2: Inicializujte výstupní stream PDF
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
Vytvořte možnosti pro převod. Zde můžete **specify PDF page numbers**, upravit kvalitu obrázků a nastavit kompresi.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Krok 5: Vytvořte zařízení pro vykreslování PDF  
Nastavte zařízení pro vykreslování, které zapíše výstup PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Uložte dokument  
Nakonec uložte XPS dokument jako PDF pomocí nastavených možností a zařízení.

```java
document.save(device, options);
```

Opakujte tyto kroky a upravte cesty k souborům a možnosti podle vašeho konkrétního scénáře.

## Jak specifikovat čísla PDF stránek při převodu XPS
Pokud potřebujete jen podmnožinu stránek z původního XPS, naplňte pole `setPageNumbers` požadovanými indexy stránek (začínající od 1). To pomáhá snížit velikost souboru a dobu zpracování.

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že `dataDir` ukazuje na správnou složku a že název souboru XPS odpovídá.
- **LicenseException** – Pro produkční použití je vyžadována platná licence Aspose.Page; jinak knihovna běží v režimu hodnocení s vodoznakem.
- **Nízká kvalita obrázku** – Zvyšte `setJpegQualityLevel` nebo přepněte na bezztrátovou kompresi, pokud je to potřeba.

## Často kladené otázky
### Mohu převést XPS soubory s více stránkami pomocí Aspose.Page pro Java?
Ano, můžete **specify PDF page numbers** v `PdfSaveOptions` (viz Krok 4) a zahrnout tak libovolné stránky, které potřebujete.

### Kde mohu najít další podporu nebo diskutovat o dotazech souvisejících s Aspose.Page?
Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuze.

### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
Ano, můžete si funkce vyzkoušet pomocí [bezplatné zkušební verze](https://releases.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?
Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/) pro podrobnosti o dočasné licenci.

### Kde mohu zakoupit licenci Aspose.Page pro Java?
Licenci si můžete zakoupit [zde](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}