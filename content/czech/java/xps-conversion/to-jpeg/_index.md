---
title: Převést XPS na JPEG v Javě
linktitle: Převést XPS na JPEG v Javě
second_title: Aspose.Page Java API
description: Naučte se, jak převést XPS na JPEG v Javě pomocí Aspose.Page. Komplexní průvodce s pokyny krok za krokem pro bezproblémovou integraci.
type: docs
weight: 11
url: /cs/java/xps-conversion/to-jpeg/
---
## Úvod
tomto tutoriálu prozkoumáme, jak převést soubory XPS (XML Paper Specification) na obrázky JPEG pomocí Aspose.Page for Java. Aspose.Page je výkonná Java knihovna, která umožňuje vývojářům bezproblémově pracovat s XPS a dalšími formáty dokumentů. Tento podrobný průvodce vám pomůže pochopit proces a implementovat jej do vašich aplikací Java.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Vývojové prostředí Java: Ujistěte se, že máte na svém počítači nastavené vývojové prostředí Java.
-  Aspose.Page for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Page for Java. Knihovnu najdete[tady](https://releases.aspose.com/page/java/).
- Ukázkový dokument XPS: Připravte si ukázkový dokument XPS, který chcete převést do formátu JPEG.
## Importujte balíčky
Začněte importováním potřebných balíčků do vaší třídy Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Krok 1: Inicializujte cesty a dokument XPS
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Inicializujte vstupní proud XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Krok 2: Nastavte možnosti JpegSaveOptions
```java
// Inicializujte objekt voleb s potřebnými parametry.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Krok 3: Vytvořte vykreslovací zařízení
```java
// Vytvořte vykreslovací zařízení pro formát PDF
ImageDevice device = new ImageDevice();
```
## Krok 4: Uložte XPS jako JPEG
```java
document.save(device, options);
```
## Krok 5: Iterujte a uložte stránky JPEG
```java
//Iterace přes oddíly dokumentů (pevné dokumenty, v podmínkách XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterujte stránky oddílů
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inicializujte výstupní proud obrazu
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Napište obrázek
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //zavřít proud
        imageStream.close();
    }
}
```
Tato série kroků efektivně převede váš dokument XPS na obrázky JPEG, každý uložený samostatně.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak převést XPS na JPEG v Javě pomocí Aspose.Page. Tento proces je neocenitelný pro vývojáře pracující s převodem dokumentů v aplikacích Java.
## Často kladené otázky

### Otázka: Je Aspose.Page vhodný pro komerční projekty?
 Odpověď: Ano, Aspose.Page je komerční produkt s dostupnými možnostmi licencování. Šek[tady](https://purchase.aspose.com/buy) pro detaily.
### Otázka: Mohu vyzkoušet Aspose.Page před nákupem?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Kde najdu dokumentaci Aspose.Page?
 Odpověď: Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Otázka: Jak mohu získat podporu pro Aspose.Page?
 A: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu.
### Otázka: Potřebuji pro testování dočasnou licenci?
 Odpověď: Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).