---
title: Změňte velikost souborů EPS v Javě pomocí Aspose.Page
linktitle: Změňte velikost souboru EPS v Javě
second_title: Aspose.Page Java API
description: Naučte se, jak bez námahy měnit velikost souborů EPS v Javě pomocí Aspose.Page for Java. Postupujte podle našeho komplexního průvodce, kde najdete podrobné pokyny.
weight: 11
url: /cs/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změňte velikost souborů EPS v Javě pomocí Aspose.Page

## Úvod
Vítejte v našem podrobném průvodci změnou velikosti souborů EPS v Javě pomocí výkonné knihovny Aspose.Page. Pokud jste někdy potřebovali upravit rozměry svých EPS obrázků programově, jste na správném místě. V tomto tutoriálu prozkoumáme různé možnosti změny velikosti, včetně bodů, palců, milimetrů a procent, což vám poskytne flexibilitu, kterou potřebujete pro své specifické požadavky.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Aspose.Page pro knihovnu Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
- Základní znalost programování v Javě.
## Importujte balíčky
Ve svém projektu Java se ujistěte, že máte potřebné importy pro použití funkcí Aspose.Page. Zde je příklad:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Nyní si tutoriál rozdělíme do několika kroků pro každou možnost změny velikosti:
## Změňte velikost EPS pomocí bodů
### Krok 1: Nastavte vstupní proud
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Krok 2: Inicializujte objekt PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Krok 3: Extrahujte aktuální velikost obrázku EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Krok 4: Vytvořte výstupní proud
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Krok 5: Změňte velikost a uložte v bodech
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Změna velikosti EPS pomocí palců
Postupujte podobně jako v příkladu 1, nahraďte "body" "palce" a podle toho upravte novou velikost.
## Změňte velikost EPS pomocí milimetrů
Postupujte podobně jako v příkladu 1, nahraďte "Body" "Milimetry" a podle toho upravte novou velikost.
## Změňte velikost EPS pomocí procent
Postupujte podobně jako v příkladu 1, nahraďte "Body" "Procenta" a podle toho upravte novou velikost.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak změnit velikost souborů EPS v Javě pomocí Aspose.Page. Tato příručka vám poskytuje všestranné možnosti a zajišťuje, že si proces změny velikosti můžete přizpůsobit tak, aby vyhovoval vašim konkrétním potřebám.

## Nejčastější dotazy
### Mohu tuto knihovnu použít pro jiné formáty obrázků?
Ne, Aspose.Page je speciálně navržen pro práci se soubory PostScript a EPS.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu další pomoc a diskuze?
 Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity.
### Jak mohu získat dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Existují nějaké příklady projektů?
 Ano, zkontrolujte dokumentaci[tady](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
