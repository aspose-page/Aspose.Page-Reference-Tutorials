---
date: 2025-12-23
description: Jednoduše **převádějte XPS na PNG** v Javě pomocí Aspose.Page. Tento
  průvodce ukazuje, jak renderovat XPS do obrazových souborů spolehlivým a vývojářsky
  přívětivým řešením.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Převod XPS na PNG v Javě
url: /cs/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XPS na PNG v Javě

## Úvod
Ve dynamickém světě vývoje softwaru se často objevuje potřeba **převést XPS na PNG** (XML Paper Specification na Portable Network Graphics). K bezproblémovému provedení tohoto úkolu v Javě poskytuje Aspose.Page výkonné řešení. V tomto tutoriálu projdeme proces převodu XPS na PNG pomocí Aspose.Page pro Javu.

## Rychlé odpovědi
- **Jaká knihovna provádí převod?** Aspose.Page for Java  
- **Jaké formáty jsou zapojeny?** XPS (zdroj) → PNG (výstup)  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována komerční licence  
- **Mohu nastavit rozlišení obrázku?** Ano, pomocí `PngSaveOptions.setResolution()`  
- **Je možné vybrat konkrétní stránky?** Rozhodně – zadejte čísla stránek v objektu možností  

## Proč převádět XPS na PNG?
Vykreslování XPS do souborů obrázků je užitečné, když potřebujete zobrazit dokumenty na webu, vložit je do zpráv nebo generovat miniatury pro náhled. PNG nabízí bezztrátovou kompresi a širokou podporu v prohlížečích, což z něj činí ideální volbu pro vysoce kvalitní vizuální reprezentaci obsahu XPS.

## Předpoklady
Než se ponoříme do tutoriálu, ujistěte se, že máte nastaveny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte JDK nainstalovaný ve svém systému.  
2. Aspose.Page for Java: Stáhněte a nainstalujte knihovnu Aspose.Page. Odkaz ke stažení najdete [zde](https://releases.aspose.com/page/java/).  
3. Integrované vývojové prostředí (IDE): Vyberte si IDE kompatibilní s Javou, jako je IntelliJ IDEA nebo Eclipse.  

## Jak převést XPS na PNG v Javě
Níže je krok za krokem průvodce, který vysvětluje **jak převést XPS** dokumenty do PNG obrázků, včetně úryvků kódu, které můžete přímo zkopírovat do svého projektu.

### Import balíčků
Ve svém Java projektu importujte potřebné balíčky pro využití funkcí Aspose.Page. Přidejte následující importní příkazy na začátek svého Java souboru:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Krok 1: Nastavte adresář dokumentu
Definujte složku, která obsahuje váš zdrojový XPS soubor a kam budou uloženy PNG soubory.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Načtěte XPS dokument
Vytvořte instanci `XpsDocument`, která načte zdrojový XPS soubor.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 3: Inicializujte možnosti
Nakonfigurujte možnosti výstupu PNG. Zde můžete nastavit vyhlazování, rozlišení a určit, které stránky se mají vykreslit.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Krok 4: Vytvořte vykreslovací zařízení
Vytvořte `ImageDevice`, který bude uchovávat vykreslená data obrázku.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Krok 5: Uložte a iterujte
Vykreslete XPS dokument a poté zapište každý vygenerovaný PNG bajtový pole do souboru na disku.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Dodržením těchto kroků můžete snadno **vykreslit XPS do obrázkových** souborů ve formátu PNG pomocí Aspose.Page pro Javu.

## Závěr
Na závěr, Aspose.Page pro Javu zjednodušuje proces převodu XPS na PNG a poskytuje vývojářům spolehlivý a efektivní nástroj. Začleňte tuto knihovnu do svých Java projektů, abyste zefektivnili úlohy manipulace s dokumenty.

## Další často kladené otázky

**Q: Mohu převést jen vybrané stránky XPS souboru?**  
A: Rozhodně. Použijte metodu `setPageNumbers` v `PngSaveOptions` k určení stránek, které chcete vykreslit.

**Q: Jaké rozlišení obrázku se doporučuje pro vysoce kvalitní PNG?**  
A: Rozlišení 300 dpi je dobrá rovnováha mezi kvalitou a velikostí souboru, ale můžete jej upravit pomocí `options.setResolution()`.

**Q: Podporuje API vícevláknový převod pro velké dokumenty?**  
A: Ano, můžete spustit logiku převodu v paralelních vláknech, přičemž každé zpracovává jinou stránku nebo část dokumentu.

**Q: Jak zvládnout využití paměti při převodu velmi velkých XPS souborů?**  
A: Zpracovávejte stránky sekvenčně a po každém zápisu uvolněte `FileOutputStream`, jak je ukázáno ve vzorovém kódu.

**Q: Existuje způsob, jak přidat vlastní metadata do vygenerovaných PNG souborů?**  
A: Přestože `PngSaveOptions` přímo neexponuje pole metadat, můžete PNG po‑zpracovat pomocí standardních knihoven obrázků a vložit metadata.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}