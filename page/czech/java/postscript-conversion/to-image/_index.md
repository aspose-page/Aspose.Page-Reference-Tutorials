---
date: 2025-12-04
description: Naučte se, jak převést PS na PNG v Javě pomocí Aspose.Page. Podrobný
  návod krok za krokem, předpoklady, časté dotazy a ukázky kódu pro bezproblémovou
  konverzi PostScriptu na obrázek.
linktitle: How to Convert PS to PNG in Java Using Aspose.Page
second_title: Aspose.Page Java API
title: Jak převést PS na PNG v Javě pomocí Aspose.Page
url: /cs/java/postscript-conversion/to-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést PS na PNG v Javě pomocí Aspose.Page

## Úvod
Pokud potřebujete **převést PS na PNG** rychle a spolehlivě, Aspose.Page pro Javu poskytuje jednoduché API, které se postará o těžkou část. V tomto tutoriálu projdeme celý proces – od nastavení projektu až po generování vysoce kvalitních PNG obrázků z PostScript (.ps) souboru. Na konci pochopíte, proč je tento přístup ideální pro server‑side zpracování dokumentů, hromadné konverze nebo jakoukoli Java aplikaci pracující s grafickými soubory.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page pro Javu (nejnovější verze).  
- **Mohu převádět více stránek?** Ano – každá stránka se uloží jako samostatný PNG soubor.  
- **Potřebuji licenci?** Pro hodnocení stačí bezplatná zkušební licence; licence je vyžadována pro produkci.  
- **Podporované formáty obrázků?** PNG, JPEG, BMP, GIF, TIFF (zde je ukázáno PNG).  
- **Typický čas implementace?** Přibližně 10‑15 minut pro základní konverzi.

## Co je konverze PS na PNG?
PostScript (PS) je jazyk pro popis stránek, který se používá převážně pro tisk. Převod PS souboru na PNG změní tento popis na rastrový obrázek, který lze zobrazit ve webových prohlížečích, vložit do dokumentů nebo dále zpracovávat pomocí nástrojů pro úpravu obrázků.

## Proč použít Aspose.Page pro Javu?
- **Žádné externí závislosti** – čistá Java, žádné nativní binárky.  
- **Přesné vykreslování** – zachovává písma, vektory i barvy.  
- **Zpracování chyb** – volitelné potlačení menších chyb, aby konverze probíhala plynule.  
- **Škálovatelnost** – vhodné pro jednotlivé soubory i velké dávkové úlohy.

## Předpoklady
Než začnete, ujistěte se, že máte:

- **Knihovnu Aspose.Page pro Javu** integrovanou ve vašem projektu. Stáhněte ji ze [stránky vydání](https://releases.aspose.com/page/java/).  
- **PostScript soubor** (`.ps`) umístěný v známém adresáři na vašem souborovém systému.  
- **Java 8+** nainstalovanou a nakonfigurovanou ve vašem vývojovém prostředí.

## Průvodce krok za krokem

### Krok 1: Import potřebných balíčků
Nejprve načtěte požadované třídy do svého Java zdrojového souboru, abyste mohli pracovat se streamy, Aspose EPS API a formáty obrázků.

```java
// Import necessary packages
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
import com.aspose.page.ImageFormat;
```

### Krok 2: Nastavte adresář dokumentu a zvolte formát obrázku
Definujte, kde se nachází váš zdrojový PS soubor, a specifikujte, že chcete výstup ve formátu PNG.

```java
// Set the path to the documents directory
String dataDir = "Your Document Directory";
// Initialize image format
ImageFormat imageFormat = ImageFormat.PNG;
```

### Krok 3: Inicializujte vstupní stream PostScriptu
Otevřete stream pro soubor `.ps` a vytvořte instanci `PsDocument`, kterou Aspose vykreslí.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Krok 4: Nastavte možnosti konverze
Můžete Aspose říci, zda má potlačit nekritické chyby, které by jinak mohly konverzi přerušit.

```java
// Set conversion options
boolean suppressErrors = true;
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
```

### Krok 5: Vytvořte Image Device
`ImageDevice` funguje jako cíl, který sbírá rasterizované stránky.

```java
// Create ImageDevice
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Krok 6: Proveďte konverzi
Zavolejte metodu `save`, aby se PS dokument vykreslil do image device. Blok `try/finally` zaručuje, že vstupní stream bude uzavřen.

```java
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Krok 7: Uložte vygenerované PNG soubory
Každá stránka je uložena jako pole bajtů uvnitř zařízení. Projděte je v cyklu, zapište každé pole do samostatného PNG souboru a pojmenujte soubory sekvenčně.

```java
byte[][] imagesBytes = device.getImagesBytes();
int i = 0;
for (byte [] imageBytes : imagesBytes) {
    String imagePath = dataDir + "PSToImage" + i + "." + imageFormat.toString().toLowerCase();
    FileOutputStream fs = new FileOutputStream(imagePath);
    try {
        fs.write(imageBytes, 0, imageBytes.length);
    } catch (IOException ex) {
        System.out.println(ex.getMessage());
    } finally {
        fs.close();
    }
    i++;
}
```

### Krok 8: Prohlédněte si chyby (volitelné)
Pokud jste povolili potlačení chyb, můžete i tak zkontrolovat varování, která se během vykreslování objevila.

```java
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Nevygenerovány žádné soubory** | Nesprávná cesta `dataDir` nebo chybějící oprávnění k zápisu. | Ověřte, že adresář existuje a aplikace má právo zapisovat. |
| **Chybějící písma** | Písma použité v PS souboru nejsou dostupná pro Aspose. | Použijte `options.setAdditionalFontsFolders(...)` a nasměrujte na vlastní složky s fonty. |
| **Částečné vykreslení stránky** | `suppressErrors` nastaveno na `false`, což způsobí přerušení při menších chybách. | Nechte `suppressErrors = true` nebo prozkoumejte `options.getExceptions()` pro podrobnosti. |

## Často kladené otázky

**Q: Mohu převádět PS soubory, které obsahují drobné chyby?**  
A: Ano – nastavte příznak `suppressErrors` na `true` v `ImageSaveOptions`, aby konverze pokračovala i při nekritických problémech.

**Q: Jak přidám podporu pro jiné formáty obrázků, například JPEG?**  
A: Změňte `ImageFormat.PNG` na `ImageFormat.JPEG` (nebo jiný podporovaný enum) a upravte příponu souboru v ukládacím cyklu.

**Q: Je možné specifikovat vlastní velikost obrázku?**  
A: Ano, můžete nakonfigurovat `ImageDevice` pomocí vlastností šířky a výšky před voláním `document.save(...)`.

**Q: Kde najdu podrobnější dokumentaci API?**  
A: Navštivte oficiální [dokumentaci](https://reference.aspose.com/page/java/) a fórum [Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu.

**Q: Potřebuji licenci pro vývojové sestavy?**  
A: Bezplatná evaluační licence stačí pro testování; pro produkční nasazení je vyžadována komerční licence.

## Závěr
Nyní máte kompletní, připravený recept na **převod PS na PNG** v Javě pomocí Aspose.Page. Dodržením výše uvedených kroků můžete integrovat vykreslování PostScriptu do jakékoli Java aplikace – ať už jde o webovou službu generující náhledy, dávkový procesor archivů nebo desktopový nástroj vizualizující tiskové úlohy.

---

**Poslední aktualizace:** 2025-12-04  
**Testováno s:** Aspose.Page pro Javu 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}