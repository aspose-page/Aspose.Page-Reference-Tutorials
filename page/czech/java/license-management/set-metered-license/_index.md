---
title: Snadná měřená integrace licencí s Aspose.Page Java
linktitle: Nastavte Metered License v Javě
second_title: Aspose.Page Java API
description: Prozkoumejte bezproblémovou integraci Aspose.Page s Javou. Nastavte měřené licence bez námahy a rozšiřte možnosti zpracování dokumentů.
type: docs
weight: 10
url: /cs/java/license-management/set-metered-license/
---
## Úvod
Vítejte v našem komplexním průvodci nastavením měřené licence v Javě pomocí Aspose.Page. Pokud chcete vylepšit své možnosti zpracování dokumentů a zajistit bezproblémovou integraci s Aspose.Page, jste na správném místě. V tomto tutoriálu vás provedeme celým procesem a rozdělíme každý krok na snadno stravitelné kousky.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
-  Knihovna Aspose.Page nainstalována. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/java/).
- Měřené veřejné a soukromé klíče, které můžete získat prostřednictvím svého účtu Aspose.
## Importujte balíčky
Začněme importem potřebných balíčků pro náš program Java. Ujistěte se, že máte knihovnu Aspose.Page integrovanou do vašeho projektu.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Krok 1: Inicializujte dokument a formát obrázku
Prvním krokem je nastavení dokumentu a definování požadovaného formátu obrázku.
```java
// nastavit měřené veřejné a soukromé klíče
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Přistupte k vlastnosti setMeteredKey a předejte veřejné a soukromé klíče jako parametry
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Krok 2: Inicializujte PostScript Input Stream
V tomto kroku inicializujeme vstupní proud PostScript pro zpracování.
```java
// Inicializujte vstupní proud PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Krok 3: Zkontrolujte licenci dokumentu
Než budete pokračovat, je důležité ověřit, zda je dokument řádně licencován.
```java
// Zkontrolujte, zda je dokument licencován
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Krok 4: Inicializujte možnosti a obrazové zařízení
Nyní inicializujeme možnosti a obrazové zařízení s výchozími parametry.
```java
// Inicializujte objekt voleb s výchozími parametry.
ImageSaveOptions options = new ImageSaveOptions();
// Inicializujte objekt ImageDevice s výchozími parametry.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Krok 5: Uložte soubor EPS jako obrázek
Uložte soubor EPS jako obrázek pomocí definovaných možností a zařízení.
```java
// Uložit soubor EPS jako obrázek
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Krok 6: Získejte a uložte bajty obrázku
Načtěte bajty obrázku a uložte je do souboru.
```java
// Získejte bajty obrázků. Pole jednoho bajtu pro jednu stránku. V našem případě máme jednu stránku.
byte[][] imagesBytes = device.getImagesBytes();
// Uložit bajty obrázku do souboru
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Závěr
Gratulujeme! Úspěšně jste nastavili měřenou licenci v Javě pomocí Aspose.Page. Tento výukový program poskytl průvodce krok za krokem, který zajistí hladký proces integrace.
## Nejčastější dotazy
### Otázka: Jak získám měřené veřejné a soukromé klíče?
Tyto klíče můžete získat prostřednictvím svého účtu Aspose.
### Otázka: Je knihovna Aspose.Page zdarma?
 Aspose.Page nabízí bezplatnou zkušební i placenou verzi. Návštěva[tady](https://releases.aspose.com/) na bezplatnou zkušební verzi.
### Otázka: Mohu použít Aspose.Page pro komerční projekty?
 Ano, Aspose.Page nabízí komerční licence. Můžete si je zakoupit[tady](https://purchase.aspose.com/buy).
### Otázka: Kde najdu další dokumentaci?
 Viz dokumentace[tady](https://reference.aspose.com/page/java/).
### Otázka: Jak mohu získat dočasné licence?
 Lze získat dočasné licence[tady](https://purchase.aspose.com/temporary-license/).