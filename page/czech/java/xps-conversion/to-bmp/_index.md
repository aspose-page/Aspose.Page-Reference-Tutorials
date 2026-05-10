---
date: 2026-03-08
description: Naučte se, jak převést XPS na BMP v Javě a nastavit rozlišení BMP pomocí
  knihovny Aspose.Page pro konverzi obrázků v Javě. Tento průvodce zahrnuje výstup
  ve vysoké kvalitě a tipy šetřící paměť.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Převod XPS na BMP v Javě – Nastavte rozlišení pro výstup ve vysoké kvalitě
url: /cs/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XPS na BMP v Javě

## Úvod
Vítejte v tomto podrobném průvodci, jak **převést XPS na BMP** v Javě a nastavit rozlišení pro optimální kvalitu obrazu pomocí Aspose.Page. Ať už budujete tiskovou pipeline, generujete náhledy, nebo potřebujete grafiku ve vysokém rozlišení, řízení DPI vám dává flexibilitu splnit jakýkoli požadavek.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Page pro Java je nejkompletnější **java image conversion library** pro XPS → BMP.  
- **Mohu kontrolovat kvalitu obrazu?** Ano – použijte `BmpSaveOptions` k **nastavení rozlišení BMP** a režimu vyhlazování.  
- **Jak se vyhnout OutOfMemoryError Java při zpracování velkých XPS souborů?** Renderujte stránky po částech nebo zvětšete haldu JVM (`-Xmx`).  
- **Potřebuji převést jen konkrétní stránky?** Samozřejmě, `options.setPageNumbers()` vám umožní vybrat přesně požadované stránky.  
- **Jaké verze Javy jsou podporovány?** Všechny moderní verze Javy (8 a vyšší) fungují bez problémů.

## K čemu slouží nastavení rozlišení?
Rozlišení určuje počet bodů na palec (DPI) v generovaném BMP obrázku. Vyšší DPI poskytuje ostřejší obrázky, což je nezbytné pro tisk nebo detailní grafickou práci. Úprava rozlišení vám dává plnou kontrolu nad kvalitou výstupu vašeho **convert xps to bmp** workflow.

## Proč použít Aspose.Page pro převod XPS → BMP?
- **Vysoká věrnost** – zachovává vektorovou kvalitu původního XPS.  
- **Detailní kontrola** – můžete nastavit DPI, vyhlazování a dokonce vybrat konkrétní stránky k převodu.  
- **Žádné externí závislosti** – čistě Java, není potřeba nativních knihoven.  
- **Škálovatelnost** – funguje pro jednostránkové dokumenty i pro velké vícestránkové XPS soubory.  

## Požadavky
Před tím, než se ponoříte do procesu převodu, ujistěte se, že máte následující předpoklady:
- **Java Development Environment** – Java 8 nebo novější nainstalovaná na vašem počítači.  
- **Aspose.Page pro Java Library** – Stáhněte a zahrňte knihovnu Aspose.Page pro Java do svého projektu. Knihovnu najdete [zde](https://releases.aspose.com/page/java/).  
- **Ukázkový XPS soubor** – Připravte si ukázkový XPS dokument, který chcete převést na BMP.

## Import balíčků
Zahrňte potřebné Aspose.Page balíčky do svého Java kódu:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Jak nastavit rozlišení pro převod XPS na BMP
Níže je stručný, číslovaný návod, který ukazuje, kde a jak nastavit rozlišení, a také jak **převést konkrétní stránky**.

### Krok 1: Načtení XPS dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 2: Inicializace možností (rozlišení a výběr stránek)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Krok 3: Vytvoření renderovacího zařízení
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Krok 4: Uložení dokumentu s použitím možností
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Krok 5: Procházení vykreslených obrázků a zápis souborů
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Opakujte tyto kroky pro jakoukoli další úpravu nebo modifikaci, kterou v procesu převodu potřebujete.

## Jak se vyhnout OutOfMemoryError Java při převodu velkých XPS souborů
- **Zpracování po částech** – Příklad již renderuje dokument po částech (`device.getResult()`), což snižuje zatížení paměti.  
- **Zvětšení haldy JVM** – Použijte přepínač `-Xmx` (např. `-Xmx2g`) pro alokaci více paměti pro velké dokumenty.  
- **Uvolnění zdrojů** – Zavolejte `document.close()` po dokončení, aby se uvolnily nativní zdroje.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Nízká kvalita BMP výstupu** | Ověřte, že `options.setResolution()` je nastaveno na hodnotu ≥ 300 DPI. |
| **Převádí se jen část dokumentu** | Ujistěte se, že `options.setPageNumbers()` zahrnuje všechny požadované indexy stránek. |
| **OutOfMemoryError u velkých XPS souborů** | Zpracovávejte dokument v menších částech nebo zvětšete velikost haldy JVM (`-Xmx`). |
| **Soubor nenalezen** | Zkontrolujte cestu `dataDir` a ověřte, že vstupní XPS soubor existuje. |

## Často kladené otázky
### Q: Mohu přizpůsobit rozlišení BMP obrázků?
A: Ano, rozlišení můžete upravit změnou parametru `options.setResolution()` v kódu.

### Q: Je Aspose.Page kompatibilní s různými verzemi Javy?
A: Ano, Aspose.Page podporuje širokou škálu verzí Javy. Ujistěte se, že máte nainstalovanou kompatibilní verzi.

### Q: Jak mohu převést XPS soubory z konkrétního rozsahu stránek?
A: Použijte metodu `options.setPageNumbers()` a specifikujte čísla stránek, které chcete převést.

### Q: Existují i jiné výstupní formáty podporované Aspose.Page?
A: Ano, Aspose.Page podporuje různé výstupní formáty. Podívejte se do dokumentace pro kompletní seznam.

### Q: Kde mohu najít další pomoc nebo podporu?
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

---

**Poslední aktualizace:** 2026-03-08  
**Testováno s:** Aspose.Page pro Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}