---
title: Oříznout soubory EPS v Javě – průvodce krok za krokem s Aspose.Page
linktitle: Oříznout soubor EPS v Javě
second_title: Aspose.Page Java API
description: Prozkoumejte podrobného průvodce oříznutím souborů EPS v Javě pomocí Aspose.Page. Vylepšete své dovednosti v manipulaci s dokumenty bez námahy.
type: docs
weight: 10
url: /cs/java/manipulation-eps/crop/
---
## Úvod
Chcete manipulovat se soubory EPS ve své aplikaci Java a přemýšlíte, jak je efektivně oříznout? Už nehledejte! V tomto komplexním průvodci vás provedeme procesem oříznutí souborů EPS krok za krokem pomocí výkonné knihovny Aspose.Page for Java.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
-  Knihovna Aspose.Page for Java: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page for Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
- Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu.
- Adresář dokumentů: Vytvořte vyhrazený adresář pro ukládání vstupních a výstupních souborů EPS.
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java. Níže uvedený fragment kódu ukazuje, jak importovat požadované balíčky:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```
Nyní si rozeberme každý krok výše uvedeného kódu pro jasnější pochopení.
## Krok 1: Nastavte složku Document Directory a Input Stream
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte vstupní proud pro soubor EPS
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
V tomto kroku nastavíme cestu k adresáři, kde jsou umístěny vaše soubory EPS, a vytvoříme vstupní proud pro cílový soubor EPS.
## Krok 2: Inicializujte objekt PsDocument
```java
// Inicializujte objekt PsDocument pomocí vstupního proudu
PsDocument doc = new PsDocument(inputEpsStream);
```
Zde inicializujeme objekt PsDocument pomocí vstupního proudu vytvořeného v předchozím kroku.
## Krok 3: Extrahujte počáteční vymezovací rámeček
```java
// Získejte počáteční ohraničovací rámeček obrázku EPS
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Získejte počáteční ohraničovací rámeček obrázku EPS, který pomáhá při definování parametrů oříznutí.
## Krok 4: Vytvořte výstupní proud
```java
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Vytvořte výstupní proud pro uložení oříznutého obrázku EPS.
## Krok 5: Definujte nový ohraničující rámeček a oříznutí
```java
// Vytvořte nový ohraničovací rámeček
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Ořízněte obrázek EPS a uložte jej do výstupního proudu
doc.cropEps(outputEpsStream, newBoundingBox);
```
Definujte nový ohraničovací rámeček se specifickými souřadnicemi a rozměry a poté pokračujte v odpovídajícím oříznutí obrázku EPS.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak oříznout soubory EPS v Javě pomocí Aspose.Page. Zahrňte tyto znalosti do svých projektů, abyste zlepšili své možnosti manipulace s dokumenty.
## Nejčastější dotazy
### Otázka: Je Aspose.Page kompatibilní s Java 8?
Odpověď: Ano, Aspose.Page je kompatibilní s Java 8 a vyššími verzemi.
### Otázka: Mohu používat Aspose.Page pro komerční účely?
 A: Ano, můžete. Podrobnosti o licencích naleznete na adrese[tady](https://purchase.aspose.com/buy).
### Otázka: Kde najdu další zdroje a podporu?
 A: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za diskusi a podporu.
### Otázka: Je k dispozici bezplatná zkušební verze?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Jak získám dočasnou licenci?
 A: Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).