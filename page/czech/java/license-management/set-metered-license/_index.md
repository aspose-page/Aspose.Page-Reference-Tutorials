---
date: 2026-09-24
description: Naučte se používat Aspose.Page k převodu EPS na PNG v Javě, nakonfigurujte
  licenci na měření a efektivně vytvořte soubor PNG pomocí Java kódu.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Nastavení licence na měření v Javě
og_description: Aspose.Page převod EPS na PNG v Javě s licencí na měření. Tento průvodce
  ukazuje krok za krokem, jak nakonfigurovat licencování, renderovat EPS a vytvořit
  soubor PNG pomocí Java kódu.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page převod EPS na PNG v Javě (licence na měření)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page převod EPS na PNG v Javě (licence na měření)
url: /cs/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page převod EPS na PNG v Javě (měřená licence)

## Úvod
Pokud potřebujete **uložit EPS jako PNG** v Java aplikaci a zároveň mít jednoduché licencování, jste na správném místě. Tento tutoriál vás provede nastavením **měřené licence** pro Aspose.Page, načtením souboru EPS (Encapsulated PostScript) a jeho konverzí na PNG obrázek. Na konci pochopíte, jak **efektivně renderovat EPS do PNG** a jak **zapsat PNG soubor v Javě** kódem, který spolehlivě funguje v produkci.

## Rychlé odpovědi
- **Co znamená „uložit EPS jako PNG“?** Převádí vektorový soubor EPS na rastrový PNG obrázek, zachovává průhlednost a bezztrátovou kompresi.  
- **Proč používat měřenou licenci?** Platíte jen za stránky, které zpracujete, což je ideální pro proměnlivé zatížení.  
- **Potřebuji internetové připojení?** Ne, měřené klíče jsou ověřovány lokálně na JVM.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší je plně podporována.  
- **Jak dlouho trvá nastavení?** Přibližně 10 minut pro základní implementaci.

## Co je „uložit EPS do PNG“?
Uložení EPS jako PNG převádí vektorový dokument Encapsulated PostScript do rastrového PNG obrázku, zachovává průhlednost a nabízí bezztrátovou kompresi. Tato transformace je užitečná, když potřebujete grafiku připravenou pro web, náhledy nebo tiskové ukázky, které lze zobrazit v libovolném prohlížeči bez nutnosti PostScript interpretru.

## Proč renderovat EPS do PNG pomocí Aspose.Page?
Aspose.Page poskytuje čistě Java API, které rasterizuje EPS soubory s vysokou věrností, podporuje více než 50 výstupních formátů a nabízí měřenou licenci, takže platíte jen za to, co převádíte. Knihovna dokáže zpracovat dokumenty se stovkami stránek, aniž by načítala celý soubor do paměti, a poskytuje rychlé, přesné vykreslování na jakékoli platformě podporující JVM.

## Předpoklady
- Základní zkušenosti s vývojem v Javě.  
- Knihovna Aspose.Page stažená z [stránky ke stažení Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Pár měřených veřejných a soukromých klíčů z vašeho Aspose účtu.  

## Import balíčků
`import` příkazy přinášejí potřebné třídy do rozsahu. Uchovejte tento blok přesně tak, jak je, aby se kód přeložil bez změn.

Třídy z `java.io` zpracovávají souborové proudy, zatímco třídy Aspose.Page spravují licencování, načítání dokumentu a vykreslování obrázku.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Jak uložit EPS jako PNG pomocí Aspose.Page Java
Níže je krok‑za‑krokem průvodce, který kombinuje licencování, načítání, renderování a zápis finálního PNG souboru.

### Přímá odpověď
Načtěte svůj EPS soubor, aplikujte měřenou licenci, nakonfigurujte `ImageSaveOptions` pro PNG, renderujte dokument do `ImageDevice` a nakonec zapište výsledné pole bajtů na disk. Tento postup dokončí **uložit EPS jako PNG** workflow během několika řádků Java kódu.

### Krok 1: inicializace dokumentu a formátu obrázku
Nejprve nastavte měřené klíče a definujte výstupní formát (PNG). Tím vytvoříte základ pro konverzi.

Třída `MeteredLicense` ukládá vaše veřejné a soukromé klíče, zatímco `ImageSaveOptions` říká Aspose.Page, aby vytvořila PNG výstup.

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

### Krok 2: inicializace vstupního proudu PostScript
Otevřete EPS soubor, který chcete převést. Proud předává dokumentu Aspose.Page data.

`FileInputStream` čte EPS soubor z disku, což umožňuje konstruktoru `Document` parsovat PostScript data.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Krok 3: kontrola licence dokumentu
Vždy ověřte, že měřená licence byla aplikována správně před zpracováním.

Metoda `isLicensed()` vrací `true` pouze tehdy, když jsou poskytnuté klíče platné, čímž zabraňuje neúmyslnému použití nelicencované knihovny.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Krok 4: inicializace možností a obrazového zařízení
Vytvořte objekt možností, který řídí nastavení konverze, a zařízení, které přijme vykreslený obrázek.

`ImageDevice` zachytí rasterizovaný výstup v paměti, zatímco `ImageSaveOptions` umožňuje doladit DPI, úroveň komprese a barevnou hloubku.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Krok 5: uložit EPS soubor jako obrázek
Toto je jádro volání **uložit EPS jako PNG**. Dokument je vykreslen do obrazového zařízení pomocí nastavených možností.

Metoda `document.save(device, options)` provádí rasterizaci v jediném kroku.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Krok 6: získat a uložit bajty obrázku
Extrahujte PNG bajty ze zařízení a zapište je do souboru na disku. Tento krok ukazuje, jak **zapsat PNG soubor v Javě** bezpečně.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` uloží obrázek bez dalších knihoven.

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
| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| **Licence není rozpoznána** | Klíče jsou nesprávné nebo je `setMeteredKey` voláno po zpracování dokumentu. | Zkontrolujte řetězce veřejného/soukromého klíče a ujistěte se, že `setMeteredKey` běží před jakýmkoli voláním Aspose.Page. |
| **Výstupní soubor je prázdný** | `device.getImagesBytes()` vrátil `null`, protože soubor EPS nelze parsovat. | Ověřte, že soubor EPS je platný a že `ImageSaveOptions` specifikuje nenulovou velikost plátna. |
| **OutOfMemoryError u velkých EPS** | Renderování velkých vektorových souborů spotřebovává hodně paměti haldy. | Zpracovávejte stránky po jedné nebo zvětšete haldu JVM (`-Xmx2g`). |

## Často kladené otázky

**Q: Jak získám měřené veřejné a soukromé klíče?**  
A: Přihlaste se do svého Aspose účtu, přejděte do sekce **Metered License** a zkopírujte vygenerované veřejné a soukromé klíče.

**Q: Je knihovna Aspose.Page zdarma?**  
A: Aspose.Page nabízí bezplatnou zkušební verzi s plnou funkčností; pro produkční použití je vyžadována placená licence. Stáhněte si zkušební verzi z [stránky ke stažení Aspose trial](https://releases.aspose.com/).

**Q: Mohu používat Aspose.Page pro komerční projekty?**  
A: Ano, komerční licence umožňuje nasazení v produkčních prostředích. Zakupte licenci na [stránce nákupu Aspose](https://purchase.aspose.com/buy).

**Q: Kde najdu další dokumentaci?**  
A: Kompletní reference API je k dispozici na [referenci Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Q: Jak získám dočasnou licenci pro hodnocení?**  
A: Dočasné licence jsou poskytovány přes portál Aspose na [stránce dočasné licence Aspose](https://purchase.aspose.com/temporary-license/).

**Q: Co když potřebuji převést vícestránkové EPS soubory?**  
A: Procházejte každou stránku pomocí `device.getImagesBytes()` a zapište každý pole bajtů do samostatného PNG souboru.

**Q: Můžu změnit kvalitu PNG nebo hloubku barev?**  
A: Ano, nakonfigurujte `ImageSaveOptions` (např. `options.setCompressionLevel(9)`) před voláním `document.save(...)`.

---

**Poslední aktualizace:** 2026-09-24  
**Testováno s:** Aspose.Page 24.12 pro Java (nejnovější)  
**Autor:** Aspose

## Související tutoriály

- [Jak nastavit licenci pro Aspose.Page Java API – Správa licencí](/page/java/license-management/)
- [Převod PS na PNG pomocí Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Změna velikosti EPS pomocí Aspose.Page – Manipulace s EPS v Javě](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}