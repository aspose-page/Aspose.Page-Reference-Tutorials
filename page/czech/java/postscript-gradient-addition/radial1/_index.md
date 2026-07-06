---
date: 2026-02-13
description: Naučte se, jak vytvořit PostScript gradient s radiálním gradientem barevných
  zastávek pomocí Aspose.Page pro Javu. Tento krok‑za‑krokem průvodce vám ukáže, jak
  přidat gradient barevných zastávek do vašich dokumentů.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Vytvoření PostScript gradientu – radiální gradient v Javě
url: /cs/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat radiální gradient v Java PostScript pomocí Aspose.Page

## Úvod
Pokud jste někdy potřebovali **vytvořit PostScript gradient** s plynulým, poutavým přechodem barev, naučit se přidat radiální gradient je ideální výchozí bod. V tomto tutoriálu vás provedeme všemi kroky potřebnými k vygenerování souboru PostScript, který obsahuje krásný radiální gradient, pomocí knihovny **Aspose.Page for Java**. Na konci pochopíte API, uvidíte kompletní spustitelný příklad a budete vědět, jak upravit barvy, pozice a poloměry tak, aby vyhovovaly jakémukoli designu.

## Rychlé odpovědi
- **Jaká knihovna vytváří radiální gradienty v PostScriptu?** Aspose.Page for Java.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.  
- **Potřebuji licenci pro spuštění kódu?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.  
- **Mohu změnit tvar gradientu?** Ano – upravte poloměr a středový bod v konstruktoru `RadialGradientPaint`.

## Jak vytvořit PostScript gradient s radiálním výplní
Níže najdete stručný, krok‑za‑krokem průvodce, který přesně ukazuje, jak **vytvořit PostScript gradient** pomocí radiální výplně. Každý krok obsahuje krátké vysvětlení následované původním blokem kódu (nezměněným).

## Co je radiální gradient?
Radiální gradient maluje barvy, které vyzařují z centrálního bodu směrem ven, postupně se míchají k okrajům. Na rozdíl od lineárních gradientů přechod barev následuje kruhový (nebo eliptický) vzor, což je ideální pro zvýraznění, světelné efekty nebo jemné pozadí.

## Proč použít Aspose.Page pro radiální gradienty?
- **Plná kontrola nad výstupem PostScript** – není třeba ručně psát nízkoúrovňové PS příkazy.  
- **Cross‑platform** – funguje na libovolném OS, které podporuje Javu.  
- **Bohaté řízení barev** – podporuje více barevných zastávek, různé barevné prostory a metody cyklu.  
- **Připraveno k integraci** – kombinujte s dalšími funkcemi Aspose.Page, jako jsou text, obrázky a vektorové tvary.

## Předpoklady
Než se pustíme do kódu, ujistěte se, že máte připraveno následující:

- **Java Development Kit (JDK) 8+** – ověřte pomocí `java -version`.  
- **Aspose.Page for Java** – stáhněte nejnovější JAR z oficiální [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE dle vašeho výběru** – Eclipse, IntelliJ IDEA nebo VS Code s rozšířeními pro Javu.  
- **Zapisovatelná složka** – kam se uloží vygenerovaný soubor `.ps`.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat. Balíček `java.awt` poskytuje objekty pro gradientní malování, zatímco `com.aspose.eps` obsahuje třídy pro práci s dokumenty PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Průvodce krok za krokem

### Krok 1: Vytvořte obdélník a otevřete PS dokument
Začneme vytvořením výstupního proudu, nastavením velikosti stránky (standardně A4) a definováním obdélníku, který bude hostit gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Tip:** Upravit souřadnice obdélníku (`200, 100, 200, 200`) tak, aby se gradient umístil kamkoli na stránce.

### Krok 2: Definujte barvy a frakce
Radiální gradient se skládá z *barevných zastávek* (barvy) a *frakcí* (relativní pozice těchto zastávek). Zde vytvoříme pole šesti barev a jejich odpovídajících frakcí.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Proč je to důležité:** Úpravou `fractions` řídíte, jak rychle barvy přecházejí, což umožňuje jemné i dramatické efekty.

### Přidání barevných zastávek do vašeho radiálního výplně
Když potřebujete **add color stops gradient**, jsou klíčová pole `colors` a `fractions`. Klidně je přeuspořádejte, přidejte nebo odeberte položky podle vašich vizuálních požadavků.

### Krok 3: Vytvořte objekt RadialGradientPaint
Nyní sestavíme objekt `RadialGradientPaint`. Konstruktor přijímá středový bod gradientu, poloměr, ohniskový bod, frakce, barvy, metodu cyklu, barevný prostor a volitelnou transformaci.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Poznámka:** `transform` může být `null`, pokud nepotřebujete další škálování nebo otáčení. Klidně experimentujte s `AffineTransform` pro zkosené gradienty.

### Krok 4: Nastavte Paint a vyplňte obdélník
S připraveným paintem řekneme `PsDocument`, aby jej použil, a následně vyplníme dříve definovaný obdélník.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

V tomto okamžiku obsahuje stránka PostScriptu obdélník hladce vyplněný radiálním gradientem, který jsme nakonfigurovali.

### Krok 5: Zavřete a uložte dokument
Nakonec zavřeme aktuální stránku a zapíšeme soubor na disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Otevřete `RadialGradient1_outPS.ps` v libovolném prohlížeči PostScriptu (např. Ghostscript) a uvidíte gradient vykreslený přesně podle definice.

## Časté problémy a řešení
| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Gradient se zobrazuje jako jednolitá barva | Pole `fractions` nezačíná na `0.0f` ani nekončí na `1.0f` | Ujistěte se, že první frakce je `0.0f` a poslední `1.0f`. |
| Barvy vypadají vybledle | Použit nesprávný `ColorSpaceType` | Přepněte na `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` pro živější výstup. |
| Soubor se nevyprodukuje | Cesta `FileOutputStream` je neplatná nebo není zapisovatelná | Ověřte, že `dataDir` existuje a aplikace má právo zápisu. |

## Často kladené otázky

**Q: Mohu použít Aspose.Page for Java v komerčních projektech?**  
A: Ano. Pro produkční použití je vyžadována komerční licence. Zakoupit ji můžete na [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Kde najdu oficiální referenci API?**  
A: Kompletní dokumentace je dostupná [zde](https://reference.aspose.com/page/java/).

**Q: Je k dispozici bezplatná zkušební verze pro testování?**  
A: Rozhodně. Stáhněte si zkušební verzi z [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro hodnocení?**  
A: Dočasnou licenci můžete požádat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu získat komunitní podporu?**  
A: Připojte se k fóru komunity Aspose.Page na [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Závěr
Nyní víte, **jak přidat radiální gradient** do Java PostScript dokumentu pomocí Aspose.Page. Úpravou velikosti obdélníku, barevných zastávek a poloměru gradientu můžete vytvořit nespočet vizuálních efektů – od jemných pozadí po výrazné světelné grafiky. Klidně experimentujte s různými hodnotami `AffineTransform` pro otáčení nebo zkosení gradientu a kombinujte tuto techniku s textem a obrázky pro bohatší PDF nebo EPS výstupy.

---

**Poslední aktualizace:** 2026-02-13  
**Testováno s:** Aspose.Page for Java latest (as of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}