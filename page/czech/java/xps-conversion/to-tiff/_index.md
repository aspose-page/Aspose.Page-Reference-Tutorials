---
date: 2025-12-23
description: Převádějte XPS do TIFF snadno s Aspose.Page Java. Postupujte podle našeho
  krok‑za‑krokem průvodce pro bezproblémovou integraci pomocí Aspose.Page Java. Stáhněte
  si nyní!
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Převod XSP na TIFF v Javě pomocí Aspose.Page Java
url: /cs/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XSP na TIFF v Javě pomocí Aspose.Page Java

V dnešním rychle se vyvíjejícím softwarovém prostředí **aspose page java** usnadňuje a zpřehledňuje konverzi dokumentů v Javě. Ať už potřebujete **převést XPS na TIFF** pro archivaci, tisk nebo dávkové zpracování, tento tutoriál vás provede přesné kroky, vysvětlí „proč“ za každou akcí a poskytne praktické tipy, které můžete okamžitě použít.

## Rychlé odpovědi
- **Jaká knihovna provádí konverzi XPS‑to‑TIFF?** Aspose.Page Java.  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována platná licence Aspose.Page Java.  
- **Která verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Mohu převést více XPS souborů najednou?** Ano – můžete vytvořit smyčku pro dávkovou konverzi XPS kolem stejného kódu.  
- **Jaké rozlišení je nejlepší pro tiskové TIFFy?** 300 DPI je běžná volba, ale můžete jej upravit pomocí TiffSaveOptions.

## Co je Aspose.Page Java?
Aspose.Page Java je výkonné API, které umožňuje **java document conversion** z XPS (XML Paper Specification) do široké škály rastrových a vektorových formátů, včetně TIFF. Zpracovává složité rozvržení stránek, písma a grafiku, aniž by bylo potřeba Microsoft XPS Document Writer.

## Proč použít Aspose.Page Java pro konverzi XPS na TIFF?
- **Vysoká věrnost:** Zachovává vektorová data a vykreslování textu.  
- **Výkon:** Optimalizováno pro velké soubory a scénáře dávkové konverze XPS.  
- **Flexibilita:** Jemně ladí výstup pomocí `tiff save options`, jako je rozlišení, komprese a výběr stránek.  
- **Cross‑platform:** Funguje na jakémkoli OS, který podporuje Javu, což je ideální pro serverové zpracování.

## Předpoklady
Před tím, než se pustíte do procesu konverze, ujistěte se, že máte:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovnu Aspose.Page pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).  
- Platnou licenci pro Aspose.Page pro Java. Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/), nebo zakoupit plnou licenci [zde](https://purchase.aspose.com/buy).

## Import balíčků
Začněte importováním potřebných balíčků ve vašem Java projektu. Ujistěte se, že JAR Aspose.Page pro Java je přidán do cesty sestavení.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Krok 1: Nastavte adresář dokumentu
Definujte cestu ke složce, která obsahuje váš zdrojový XPS soubor.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Načtěte XPS dokument
Vytvořte instanci `XpsDocument`, která ukazuje na vstupní soubor.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## Krok 3: Inicializujte TiffSaveOptions
Nastavte **tiff save options**, které řídí kvalitu obrazu, rozlišení a které stránky exportovat.

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## Krok 4: Vytvořte vykreslovací zařízení
Instancujte `ImageDevice`, který vykreslí stránky do TIFF obrázků.

```java
ImageDevice device = new ImageDevice();
```

## Krok 5: Uložte dokument do TIFF
Vykreslete XPS dokument pomocí zařízení a dříve definovaných možností.

```java
document.save(device, options);
```

## Krok 6: Procházejte a uložte TIFF obrázky
Projděte vykreslené obrazové buffery a zapište každou stránku do samostatného TIFF souboru.

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Gratulujeme! Úspěšně jste **převáděli XPS na TIFF** v Javě pomocí **aspose page java**. Neváhejte prozkoumat další funkce a možnosti knihovny v [dokumentaci](https://reference.aspose.com/page/java/).

## Závěr
V tomto tutoriálu jsme pokryli vše, co potřebujete vědět k provedení **java document conversion** z XPS na TIFF, od nastavení prostředí po jemné ladění `tiff save options`. S Aspose.Page Java můžete také vytvořit **dávkové XPS konverze** pipeline, které automaticky zpracují desítky nebo stovky souborů.

## Často kladené otázky
### Můžu použít Aspose.Page pro Java bez licence?
I když můžete získat dočasnou licenci pro hodnocení, platná licence je vyžadována pro produkční použití. Získejte svou licenci [zde](https://purchase.aspose.com/buy).

### Existují nějaká omezení velikosti XPS souborů pro konverzi?
Aspose.Page pro Java zpracovává dokumenty různých velikostí, ale je vhodné testovat s většími soubory ve vašem konkrétním prostředí.

### Jak mohu získat podporu nebo položit otázky ohledně Aspose.Page pro Java?
Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuze.

### Je k dispozici bezplatná zkušební verze Aspose.Page pro Java?
Ano, můžete knihovnu vyzkoušet zdarma. Stáhněte ji [zde](https://releases.aspose.com/).

### Jaké je doporučené rozlišení pro TIFF obrázky v této konverzi?
Příklad používá rozlišení 300 DPI, ale můžete jej upravit podle vašich konkrétních požadavků.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.Page Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}