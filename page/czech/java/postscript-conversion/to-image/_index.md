---
date: 2026-02-10
description: Naučte se provádět konverzi obrázků v Javě ukládáním PS do PNG pomocí
  Aspose.Page. Podrobný návod krok za krokem, předpoklady, časté dotazy a ukázky kódu
  pro bezproblémovou konverzi PostScriptu na obrázek.
linktitle: Image Conversion Java – Convert PS to PNG with Aspose.Page
second_title: Aspose.Page Java API
title: Převod obrázků v Javě – Převod PS na PNG pomocí Aspose.Page
url: /cs/java/postscript-conversion/to-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod obrázků Java – Převod PS na PNG pomocí Aspose.Page

## Úvod
Pokud potřebujete **převést PS na PNG** rychle a spolehlivě, Aspose.Page for Java poskytuje jednoduché API, které se postará o těžkou práci. Tento tutoriál vám poskytne kompletní řešení **image conversion java** – od nastavení projektu až po generování vysoce kvalitních PNG obrázků z PostScript (.ps) souboru. Na konci pochopíte, proč je tento přístup ideální pro server‑side zpracování dokumentů, hromadné konverze nebo jakoukoli Java aplikaci pracující s grafickými soubory.

## Rychlé odpovědi
- **Jakou knihovnu potřebuji?** Aspose.Page for Java (nejnovější verze).  
- **Mohu převést více stránek?** Ano—každá stránka je uložena jako samostatný PNG soubor.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.  
- **Podporované formáty obrázků?** PNG, JPEG, BMP, GIF, TIFF (zde je ukázáno PNG).  
- **Typická doba implementace?** Přibližně 10‑15 minut pro základní konverzi.

## Co je konverze PS na PNG?
PostScript (PS) je jazyk pro popis stránky, který se používá převážně pro tisk. Převod PS souboru na PNG změní tento popis na rastrový obrázek, který lze zobrazit ve webových prohlížečích, vložit do dokumentů nebo dále zpracovat pomocí nástrojů pro úpravu obrázků.

## Proč použít Aspose.Page for Java?
- **Žádné externí závislosti** – čistá Java, žádné nativní binární soubory.  
- **Přesné vykreslování** – zachovává písma, vektory a barvy.  
- **Zpracování chyb** – volitelné potlačení drobných chyb, aby konverze probíhala plynule.  
- **Škálovatelné** – vhodné pro jednotlivé soubory i velké dávkové úlohy.

## Předpoklady
- **Knihovna Aspose.Page for Java** integrována do vašeho projektu. Stáhněte ji ze [stránky vydání](https://releases.aspose.com/page/java/).  
- **PostScript soubor** (`.ps`) umístěný v známém adresáři na vašem souborovém systému.  
- **Java 8+** nainstalována a nakonfigurována ve vašem vývojovém prostředí.

## Běžné případy použití pro Image Conversion Java
- Generování náhledových miniatur tiskových úloh pro webové portály.  
- Dávkové zpracování archivů PS souborů na PNG aktiva pro digitální publikování.  
- Převod PS reportů na PNG obrázky pro vložení do e‑mailových newsletterů.  
- Automatizace tvorby PNG aktiv pro mobilní aplikace, které nemohou přímo vykreslovat PostScript.

## Průvodce krok za krokem

### Krok 1: Importovat potřebné balíčky
Nejprve přidejte požadované třídy do vašeho Java zdrojového souboru, abyste mohli pracovat s proudy, Aspose EPS API a formáty obrázků.

```java
// Import necessary packages
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
import com.aspose.page.ImageFormat;
```

### Krok 2: Nastavit adresář dokumentu a zvolit formát obrázku
Definujte, kde se nachází váš zdrojový PS soubor, a uveďte, že chcete výstup ve formátu PNG.

```java
// Set the path to the documents directory
String dataDir = "Your Document Directory";
// Initialize image format
ImageFormat imageFormat = ImageFormat.PNG;
```

### Krok 3: Inicializovat vstupní stream PostScript
Otevřete stream pro soubor `.ps` a vytvořte instanci `PsDocument`, kterou Aspose vykreslí.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Krok 4: Nastavit možnosti konverze
Můžete Aspose sdělit, zda má potlačit nekritické chyby, které by jinak mohly konverzi přerušit.

```java
// Set conversion options
boolean suppressErrors = true;
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
```

### Krok 5: Vytvořit Image Device
`ImageDevice` funguje jako cíl, který sbírá rasterizované stránky.

```java
// Create ImageDevice
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Krok 6: Provedení konverze
Zavolejte metodu `save`, aby se PS dokument vykreslil do image device. Blok `try/finally` zajišťuje uzavření vstupního streamu.

```java
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Krok 7: Uložit vygenerované PNG soubory
Každá stránka je v zařízení uložena jako pole bajtů. Projděte je v cyklu, zapište každé pole do samostatného PNG souboru a pojmenujte soubory sekvenčně.

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

### Krok 8: Přezkoumat chyby (volitelné)
Pokud jste povolili potlačení chyb, můžete stále prohlédnout případná varování, která se během vykreslování objevila.

```java
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```

## Časté problémy a řešení
| Problém | Důvod | Oprava |
|-------|--------|-----|
| **Žádné výstupní soubory nebyly vytvořeny** | Nesprávná cesta `dataDir` nebo chybějící oprávnění k zápisu. | Ověřte, že adresář existuje a aplikace má právo zapisovat. |
| **Chybějící písma** | Písma použité v PS souboru nejsou pro Aspose dostupná. | Použijte `options.setAdditionalFontsFolders(...)` k nasměrování na vlastní složky s fonty. |
| **Částečné vykreslení stránky** | `suppressErrors` nastaveno na `false`, což způsobuje přerušení při drobných chybách. | Nechte `suppressErrors = true` nebo prozkoumejte `options.getExceptions()` pro podrobnosti. |

## Často kladené otázky

**Q: Mohu převést PS soubory, které obsahují drobné chyby?**  
A: Ano—nastavte příznak `suppressErrors` na `true` v `ImageSaveOptions`, aby konverze pokračovala i přes nekritické problémy.

**Q: Jak přidám podporu pro jiné formáty obrázků, např. JPEG?**  
A: Změňte `ImageFormat.PNG` na `ImageFormat.JPEG` (nebo jiný podporovaný enum) a upravte příponu souboru ve smyčce ukládání.

**Q: Je možné zadat vlastní velikost obrázku?**  
A: Můžete nakonfigurovat `ImageDevice` pomocí vlastností šířky a výšky před voláním `document.save(...)`.

**Q: Kde najdu podrobnější dokumentaci API?**  
A: Navštivte oficiální [dokumentaci](https://reference.aspose.com/page/java/) a [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu.

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Bezplatná zkušební licence funguje pro testování; pro produkční nasazení je vyžadována komerční licence.

## Závěr
Nyní máte kompletní, připravený recept pro **image conversion java**—konkrétně **ukládání PS jako PNG**—s využitím Aspose.Page. Dodržením výše uvedených kroků můžete integrovat vykreslování PostScriptu do jakékoli Java aplikace, ať už jde o webovou službu generující miniatury, dávkový procesor archivů nebo desktopový nástroj vizualizující tiskové úlohy.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}