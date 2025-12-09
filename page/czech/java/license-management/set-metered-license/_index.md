---
date: 2025-12-03
description: Naučte se, jak uložit EPS jako PNG pomocí Aspose.Page pro Javu při konfiguraci
  měřené licence. Krok za krokem průvodce s kompletním příkladem kódu.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Uložení EPS jako PNG pomocí Aspose.Page Java (měřená licence)
url: /cs/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení EPS jako PNG pomocí Aspose.Page Java (Měřená licence)

## Úvod
Pokud potřebujete **uložit EPS jako PNG** v Java aplikaci a chcete bezproblémový způsob správy licencí, jste na správném místě. Tento tutoriál vás provede nastavením měřené licence pro Aspose.Page, načtením souboru PostScript (EPS) a převodem na PNG obrázek – vše s jasnými, krok po kroku popsanými instrukcemi, které můžete ihned použít.

## Rychlé odpovědi
- **Co znamená „uložit EPS jako PNG“?** Převádí vektorový EPS soubor na rastrový PNG obrázek.  
- **Proč použít měřenou licenci?** Umožňuje platit jen za stránky, které zpracujete, což je ideální pro proměnlivé zatížení.  
- **Potřebuji internetové připojení?** Ne, měřené klíče jsou ověřovány lokálně.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší.  
- **Jak dlouho trvá nastavení?** Přibližně 10 minut pro základní implementaci.

## Co je „uložit EPS jako PNG“?
Uložení EPS jako PNG převádí škálovatelný dokument Encapsulated PostScript do široce podporovaného bitmapového formátu. PNG zachovává průhlednost a nabízí bezztrátovou kompresi, což jej činí ideálním pro webovou grafiku, miniatury a náhledy pro tisk.

## Proč použít Aspose.Page pro tento úkol?
- **Čisté Java API** – bez nativních závislostí.  
- **Vysoká věrnost** – vektorová grafika je renderována přesně.  
- **Měřená licence** – platíte jen za to, co převádíte.  
- **Podpora více výstupních formátů** – PNG, JPEG, TIFF atd.

## Požadavky
Před začátkem se ujistěte, že máte:

- Základní znalosti programování v Javě.  
- Knihovnu Aspose.Page nainstalovanou – stáhněte ji [zde](https://releases.aspose.com/page/java/).  
- Měřené veřejné a soukromé klíče, které můžete získat prostřednictvím svého Aspose účtu.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat. Zachovejte importní blok přesně tak, jak je uveden, aby se kód přeložil bez změn.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Krok 1: Inicializace dokumentu a formátu obrázku
Zde nastavíme měřené klíče a definujeme výstupní formát (PNG). Toto je základ pro operaci **uložit EPS jako PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Krok 2: Inicializace vstupního proudu PostScript
Otevřete EPS soubor, který chcete převést. Proud předává dokument do Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Kontrola licence dokumentu
Vždy ověřte, že měřená licence byla před zpracováním správně aplikována.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Krok 4: Inicializace možností a obrazového zařízení
Vytvořte objekt možností, který řídí nastavení převodu, a zařízení, které přijme vykreslený obrázek.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Krok 5: Uložení EPS souboru jako obrázku
Toto je hlavní volání **uložit EPS jako PNG**. Dokument je vykreslen do obrazového zařízení pomocí nastavených možností.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Krok 6: Získání a uložení bajtů obrázku
Extrahujte PNG bajty ze zařízení a zapište je do souboru na disku.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| **Licence není rozpoznána** | Klíče jsou nesprávné nebo jsou ve špatném pořadí. | Zkontrolujte řetězce veřejného/soukromého klíče a ujistěte se, že `setMeteredKey` je voláno před jakýmkoli zpracováním dokumentu. |
| **Výstupní soubor je prázdný** | `device.getImagesBytes()` vrátil `null`. | Ověřte, že EPS soubor je platný a že `ImageSaveOptions` není nastaven na plátno s nulovou velikostí. |
| **OutOfMemoryError u velkého EPS** | Renderování velkých vektorových souborů spotřebovává hodně paměti. | Zpracovávejte stránky po jedné nebo zvýšte velikost haldy JVM (`-Xmx2g`). |

## Často kladené otázky

**Q: Jak získám měřené veřejné a soukromé klíče?**  
A: Tyto klíče můžete získat prostřednictvím svého Aspose účtu.

**Q: Je knihovna Aspose.Page zdarma?**  
A: Aspose.Page nabízí jak bezplatnou zkušební verzi, tak placené verze. Navštivte [zde](https://releases.aspose.com/) pro bezplatnou zkušební verzi.

**Q: Mohu použít Aspose.Page pro komerční projekty?**  
A: Ano, Aspose.Page nabízí komerční licence. Můžete si je zakoupit [zde](https://purchase.aspose.com/buy).

**Q: Kde najdu další dokumentaci?**  
A: Odkazujte se na dokumentaci [zde](https://reference.aspose.com/page/java/).

**Q: Jak mohu získat dočasné licence?**  
A: Dočasné licence lze získat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2025-12-03  
**Testováno s:** Aspose.Page 24.12 for Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}