---
title: Převést XPS na PNG v Javě
linktitle: Převést XPS na PNG v Javě
second_title: Aspose.Page Java API
description: Převeďte bez námahy XPS na PNG v Javě pomocí Aspose.Page. Zjednodušte úlohy dokumentů pomocí tohoto spolehlivého a vývojářského řešení.
type: docs
weight: 13
url: /cs/java/xps-conversion/to-png/
---
## Úvod
V dynamickém světě vývoje softwaru často vyvstává potřeba převádět dokumenty XPS (XML Paper Specification) na obrázky PNG (Portable Network Graphics). Pro bezproblémové splnění tohoto úkolu v Javě poskytuje Aspose.Page výkonné řešení. V tomto tutoriálu projdeme procesem převodu XPS na PNG pomocí Aspose.Page for Java.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte nastaveny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Page for Java: Stáhněte a nainstalujte knihovnu Aspose.Page. Odkaz ke stažení najdete[tady](https://releases.aspose.com/page/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si IDE kompatibilní s Java, jako je IntelliJ IDEA nebo Eclipse.
## Importujte balíčky
Do svého projektu Java importujte potřebné balíčky, abyste mohli využívat funkce Aspose.Page. Na začátek souboru Java přidejte následující příkazy pro import:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Krok 1: Nastavte adresář dokumentů
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
```
## Krok 2: Načtěte dokument XPS
```java
// Načíst dokument XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Krok 3: Inicializujte možnosti
```java
// Inicializujte objekt voleb s potřebnými parametry.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Krok 4: Vytvořte vykreslovací zařízení
```java
// Vytvořte vykreslovací zařízení pro formát PDF
ImageDevice device = new ImageDevice();
```
## Krok 5: Uložte a iterujte
```java
// Uložte dokument XPS do PNG pomocí možností a zařízení
document.save(device, options);
//Iterace přes oddíly dokumentů (pevné dokumenty, v podmínkách XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterujte stránky oddílů
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inicializujte výstupní proud obrazu
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Napište obrázek
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Zavřete stream
        imageStream.close();
    }
}
```
Podle těchto kroků můžete bez námahy převést dokumenty XPS na obrázky PNG pomocí Aspose.Page for Java.
## Závěr
Na závěr, Aspose.Page for Java zjednodušuje proces převodu XPS na PNG a poskytuje vývojářům spolehlivý a účinný nástroj. Zahrňte tuto knihovnu do svých projektů Java, abyste zjednodušili úlohy manipulace s dokumenty.
## Nejčastější dotazy
### Mohu používat Aspose.Page for Java v komerčních projektech?
 Ano, Aspose.Page je komerční produkt. Můžete najít informace o licencích[tady](https://purchase.aspose.com/buy).
### Je k dispozici bezplatná zkušební verze?
 Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Page for Java?
 K dispozici je obsáhlá dokumentace[tady](https://reference.aspose.com/page/java/).
### Jak získám dočasnou licenci pro testovací účely?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Existují komunitní fóra pro diskuse Aspose.Page?
 Ano, navštivte komunitní fóra[tady](https://forum.aspose.com/c/page/39).