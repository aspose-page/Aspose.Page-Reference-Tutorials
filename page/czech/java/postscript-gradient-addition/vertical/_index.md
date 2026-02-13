---
date: 2026-02-13
description: Naučte se, jak vytvořit gradient v PostScriptu v Javě pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce vám ukáže, jak snadno přidat vertikální gradient do
  vašich PostScript dokumentů.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Vytvořte PostScriptový gradient v Javě – Přidejte vertikální gradient
url: /cs/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PostScript gradientu v Javě – Přidání vertikálního gradientu

## Úvod
V tomto komplexním tutoriálu se naučíte, jak **create PostScript gradient in Java** pomocí Aspose.Page for Java. Přidání vertikálního gradientu může vaše dokumenty učinit živějšími a profesionálnějšími a s několika řádky kódu můžete dosáhnout úchvatných vizuálních efektů. Provedeme vás každým krokem, vysvětlíme, proč je každá část důležitá, a poskytneme praktické tipy, jak se vyhnout běžným úskalím. Na konci tohoto průvodce budete schopni generovat PostScript soubory se plynulými, poutavými vertikálními barevnými přechody.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Mohu přizpůsobit barvy?** Ano, lze použít libovolný `java.awt.Color`  
- **Je podpora rotace?** Ano, gradient můžete otočit pomocí `AffineTransform`  
- **Jaký výstupní formát je vytvořen?** Standardní PostScript (.ps) soubor  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována komerční licence  

## Proč přidat vertikální gradient do PostScript dokumentu?
Vertikální gradienty dodají vašim stránkám hloubku, aniž by zvětšily velikost souboru. Jsou ideální pro:

* Záhlaví nebo patičky zpráv, které potřebují jemné pozadí.  
* Zvýraznění sekcí v technických manuálech nebo white‑papers.  
* Poskytnutí moderního vzhledu pro grafy, diagramy nebo propagační letáky.

Protože je gradient definován ve vektorové formě, výstup zůstává ostrý při jakémkoli rozlišení.

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovna Aspose.Page for Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).

## Import balíčků
Ve vašem Java projektu importujte potřebné balíčky, abyste mohli začít:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Nyní si projdeme proces přidání vertikálního gradientu krok za krokem.

## Jak vytvořit PostScript gradient v Javě
Níže je podrobný návod, který přesně ukazuje, jak **create PostScript gradient in Java** pomocí Aspose.Page API.

### Krok 1: Nastavte adresář dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Vytvořte výstupní stream pro PostScript dokument
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Krok 3: Vytvořte možnosti uložení s velikostí A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: Vytvořte nový PS dokument
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: Vytvořte obdélník
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Krok 6: Nastavte barvy a frakce pro gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Krok 7: Vytvořte transformaci gradientu
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Krok 8: Vytvořte vertikální lineární gradientový paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Krok 9: Nastavte paint a vyplňte obdélník
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Krok 10: Zavřete aktuální stránku a uložte dokument
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gratulujeme! Úspěšně jste přidali vertikální gradient do vašeho Java PostScript dokumentu pomocí Aspose.Page for Java.

## Časté problémy a řešení
- **Gradient vypadá plochý:** Ujistěte se, že škálování `AffineTransform` odpovídá rozměrům obdélníku.  
- **Barvy vypadají vybledlé:** Ověřte, že používáte správný `ColorSpaceType` (SRGB) a že pole frakcí je seřazeno od 0.0 do 1.0.  
- **Soubor nebyl vygenerován:** Zkontrolujte, že výstupní adresář (`dataDir`) existuje a aplikace má oprávnění k zápisu.  

## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými Java knihovnami?
Ano, Aspose.Page for Java je navržena tak, aby spolupracovala bez problémů s ostatními Java knihovnami.

### Je k dispozici bezplatná zkušební verze Aspose.Page for Java?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Kde najdu další dokumentaci?
Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/page/java/).

### Jak mohu zakoupit Aspose.Page for Java?
Aspose.Page for Java můžete zakoupit [zde](https://purchase.aspose.com/buy).

### Existuje fórum pro diskuse o Aspose.Page?
Ano, můžete se připojit k komunitnímu fóru [zde](https://forum.aspose.com/c/page/39).

## Další často kladené otázky

**Q: Mohu vytvořit jiné směry gradientu (horizontální, diagonální)?**  
**A: Rozhodně. Upravit počáteční a koncové body v `LinearGradientPaint` a změnit úhel rotace v `AffineTransform`.**

**Q: Funguje to také s výstupem PDF?**  
**A: Stejná logika gradientu může být použita při ukládání do PDF pomocí `PdfSaveOptions` místo `PsSaveOptions`.**

**Q: Jak mohu dynamicky změnit velikost gradientu?**  
**A: Vypočítejte rozměry obdélníku za běhu a předávejte tyto hodnoty jak do `Rectangle2D`, tak do konstruktoru `AffineTransform`.**

---

**Poslední aktualizace:** 2026-02-13  
**Testováno s:** Aspose.Page for Java 24.11 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}