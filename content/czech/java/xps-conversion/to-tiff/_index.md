---
title: Převést XSP na TIFF v Javě
linktitle: Převést XSP na TIFF v Javě
second_title: Aspose.Page Java API
description: Převeďte XPS na TIFF bez námahy pomocí Aspose.Page pro Java. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci. Stáhnout teď!
type: docs
weight: 14
url: /cs/java/xps-conversion/to-tiff/
---
dnešní digitální době hraje konverze dokumentů zásadní roli v různých aplikacích. Pokud jste vývojář Java, který hledá robustní řešení pro převod XPS (XML Paper Specification) dokumentů do TIFF (Tagged Image File Format), Aspose.Page for Java je vaše oblíbená knihovna. V tomto podrobném průvodci vás provedeme celým procesem a zajistíme vám bezproblémové používání s podrobnými vysvětleními a úryvky kódu.
## Předpoklady
Než se pustíte do procesu převodu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Aspose.Page pro knihovnu Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
-  Platná licence pro Aspose.Page for Java. Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) nebo zakoupit plnou licenci[tady](https://purchase.aspose.com/buy).
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java. Ujistěte se, že máte do projektu přidánu knihovnu Aspose.Page for Java.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Krok 1: Nastavte adresář dokumentů
Definujte cestu k adresáři vašeho dokumentu, kde je umístěn vstupní soubor XPS.
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Načtěte dokument XPS
Načtěte dokument XPS pomocí knihovny Aspose.Page.
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Krok 3: Inicializujte TiffSaveOptions
Inicializujte objekt TiffSaveOptions s nezbytnými parametry, jako je režim vyhlazování, rozlišení a konkrétní čísla stránek.
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Krok 4: Vytvořte vykreslovací zařízení
Vytvořte vykreslovací zařízení pro formát TIFF pomocí třídy ImageDevice.
```java
ImageDevice device = new ImageDevice();
```
## Krok 5: Uložte dokument do TIFF
Uložte dokument XPS do formátu TIFF pomocí zadaných možností a vykreslovacího zařízení.
```java
document.save(device, options);
```
## Krok 6: Iterujte a uložte obrázky TIFF
Procházejte oddíly dokumentu a stránky, inicializujte výstupní proudy obrazu a ukládejte obrazy TIFF.
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 Gratulujeme! Úspěšně jste převedli XPS na TIFF v Javě pomocí Aspose.Page. Neváhejte a prozkoumejte další funkce a funkce knihovny v[dokumentace](https://reference.aspose.com/page/java/).
## Závěr
V tomto tutoriálu jsme probrali základní kroky pro převod XPS na TIFF v Javě pomocí Aspose.Page. Konverze dokumentů je nyní na dosah ruky, což vám umožní vylepšit vaše aplikace o všestrannou podporu formátů souborů.
## Často kladené otázky
### Mohu používat Aspose.Page pro Javu bez licence?
 I když můžete získat dočasnou licenci pro vyzkoušení, pro produkční použití je vyžadována platná licence. Získejte licenci[tady](https://purchase.aspose.com/buy).
### Existují nějaká omezení velikosti souborů XPS pro převod?
Aspose.Page for Java zpracovává dokumenty různých velikostí, ale je vhodné testovat s většími soubory ve vašem konkrétním prostředí.
### Jak mohu získat podporu nebo se ptát na Aspose.Page for Java?
 Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, knihovnu můžete prozkoumat pomocí bezplatné zkušební verze. Stáhnout to[tady](https://releases.aspose.com/).
### Jaké je doporučené rozlišení pro obrázky TIFF v tomto převodu?
Uvedený příklad používá rozlišení 300 DPI, ale můžete jej upravit podle svých konkrétních požadavků.