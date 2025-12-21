---
date: 2025-12-21
description: Naučte se, jak nastavit rozlišení při převodu XPS na BMP v Javě pomocí
  Aspose.Page. Tento průvodce konverzí obrázků v Javě zajišťuje vysokou kvalitu výsledků.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Jak nastavit rozlišení při převodu XPS na BMP v Javě
url: /cs/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XPS na BMP v Javě

## Úvod
Vítejte v tomto podrobném průvodci, jak **nastavit rozlišení** při převodu souborů XPS (XML Paper Specification) na formát BMP (Bitmap) v Javě pomocí Aspose.Page. Aspose.Page pro Javu je výkonná knihovna, která poskytuje komplexní funkce pro práci s dokumenty XPS. V tomto tutoriálu vás provedeme procesem snadného převodu souborů XPS na obrázky BMP.

## Rychlé odpovědi
- **Jakou knihovnu mám použít?** Aspose.Page pro Javu poskytuje nejkompletnější funkce pro převod XPS → BMP.  
- **Mohu ovládat kvalitu obrázku?** Ano – použijte `BmpSaveOptions` k nastavení rozlišení a režimu vyhlazování.  
- **Potřebuji převádět jen konkrétní stránky?** Rozhodně, `options.setPageNumbers()` vám umožní vybrat přesné stránky.  
- **Je to pravý převod obrázku v Javě?** API vykresluje stránky XPS přímo do bitmapových dat, takže nejsou potřeba žádné meziformáty.  
- **Jaká verze Javy je podporována?** Všechny moderní verze Javy (8 a novější) jsou kompatibilní.

## Jaký je účel nastavení rozlišení?
Rozlišení určuje počet bodů na palec (DPI) v generovaném BMP obrázku. Vyšší DPI poskytuje ostřejší obrázky, což je nezbytné pro tisk nebo detailní grafickou práci. Úprava rozlišení vám dává plnou kontrolu nad kvalitou výstupu vašeho **java convert xps** pracovního postupu.

## Proč použít Aspose.Page pro převod XPS → BMP?
- **Vysoká věrnost** – zachovává vektorovou kvalitu původního XPS.  
- **Detailní kontrola** – můžete nastavit DPI, vyhlazování a dokonce vybrat konkrétní stránky k převodu.  
- **Žádné externí závislosti** – čistá Java, nevyžaduje nativní knihovny.  
- **Škálovatelnost** – funguje pro jednostránkové dokumenty i pro velké vícestránkové soubory XPS.

## Předpoklady
Než se pustíte do procesu převodu, ujistěte se, že máte následující předpoklady:
- **Vývojové prostředí Java** – Java 8 nebo novější nainstalovaná na vašem počítači.  
- **Knihovna Aspose.Page pro Javu** – Stáhněte a zahrňte knihovnu Aspose.Page pro Javu do svého projektu. Knihovnu najdete [zde](https://releases.aspose.com/page/java/).  
- **Ukázkový soubor XPS** – Připravte ukázkový dokument XPS, který chcete převést na BMP.

## Import balíčků
Zahrňte potřebné balíčky Aspose.Page do svého Java kódu:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Jak nastavit rozlišení pro převod XPS na BMP
Níže je stručný, číslovaný průvodce, který ukazuje, kde a jak nastavit rozlišení, a také jak **převést konkrétní stránky**.

### Krok 1: Načtení dokumentu XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 2: Inicializace možností (rozlišení a výběr stránek)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Krok 3: Vytvoření vykreslovacího zařízení
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Krok 4: Uložení dokumentu pomocí možností
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Krok 5: Procházení vykreslených obrázků a zápis souborů
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

Opakujte tyto kroky pro jakoukoli další úpravu nebo modifikaci, kterou v procesu převodu můžete potřebovat.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Nízká kvalita výstupu BMP** | Ověřte, že `options.setResolution()` je nastaveno na hodnotu ≥ 300 DPI. |
| **Převádí se jen část dokumentu** | Ujistěte se, že `options.setPageNumbers()` zahrnuje všechny požadované indexy stránek. |
| **OutOfMemoryError u velkých souborů XPS** | Zpracovávejte dokument v menších částech nebo zvyšte velikost haldy JVM (`-Xmx`). |
| **Soubor nenalezen** | Zkontrolujte znovu cestu `dataDir` a zda vstupní soubor XPS existuje. |

## Často kladené otázky
### Q: Můžu přizpůsobit rozlišení BMP obrázků?
A: Ano, můžete upravit rozlišení změnou parametru `options.setResolution()` v kódu.

### Q: Je Aspose.Page kompatibilní s různými verzemi Javy?
A: Ano, Aspose.Page podporuje širokou škálu verzí Javy. Ujistěte se, že máte nainstalovanou kompatibilní verzi.

### Q: Jak mohu převést soubory XPS z konkrétního rozsahu stránek?
A: Použijte metodu `options.setPageNumbers()` k určení čísel stránek, které chcete převést.

### Q: Existují další výstupní formáty podporované Aspose.Page?
A: Ano, Aspose.Page podporuje různé výstupní formáty. Podívejte se do dokumentace pro úplný seznam.

### Q: Kde mohu najít další pomoc nebo podporu?
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

---

**Poslední aktualizace:** 2025-12-21  
**Testováno s:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}