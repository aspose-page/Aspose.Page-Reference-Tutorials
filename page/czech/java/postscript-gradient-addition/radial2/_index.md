---
date: 2026-02-13
description: Naučte se, jak vyplnit tvar gradientem a nakreslit kruh s gradientem
  v Java PostScript pomocí Aspose.Page. Průvodce krok za krokem s kódem a tipy.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Vyplnit tvar gradientem: Příklad radiálního Java PostScriptu'
url: /cs/java/postscript-gradient-addition/radial2/
weight: 13
---

.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vyplnit tvar gradientem: Java PostScript radiální příklad

## Úvod
V tomto tutoriálu se naučíte, jak **vyplnit tvar gradientem** vytvořením příkladu radiálního gradientu pro PostScript dokument pomocí Aspose.Page pro Java. Provedeme vás každým krokem – od nastavení projektu po vykreslení kruhu vyplněného hladkým radiálním gradientem – abyste mohli okamžitě přidat poutavou grafiku do svých Java aplikací.

## Rychlé odpovědi
- **Co tento tutoriál vytváří?** PostScript soubor (`.ps`) obsahující kruh vyplněný radiálním gradientem.  
- **Která knihovna je vyžadována?** Aspose.Page pro Java (nejnovější verze).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro funkční příklad.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence; pro vývoj stačí bezplatná zkušební verze.  
- **Mohu kód znovu použít pro PDF nebo SVG?** Ano – Aspose.Page podporuje více výstupních formátů s minimálními úpravami.

## Jak vyplnit tvar gradientem v PostScriptu
Než se ponoříme do kódu, objasníme, proč je důležité „vyplnit tvar gradientem“. Použití gradientů dodá vaší grafice profesionální, trojrozměrný vzhled bez potřeby rastrových obrázků. S Aspose.Page můžete aplikovat stejnou logiku gradientu na jakýkoli vektorový tvar – kruhy, obdélníky nebo vlastní cesty – ve všech podporovaných výstupních formátech (PostScript, PDF, SVG).

## Co je radiální gradient?
Radiální gradient přechází barvy od centrálního bodu směrem ven, čímž vytváří hladké, kruhové prolínání. Je ideální pro zvýraznění, pozadí tlačítek nebo jakýkoli vizuál, který potřebuje přirozený efekt „záře“.

## Proč použít Aspose.Page pro radiální gradienty?
- **Renderování nezávislé na zařízení** – funguje stejně na PostScriptu, PDF, SVG a dalších.  
- **Plná integrace s Java** – žádný nativní kód, jen čisté Java API.  
- **Výstup vysoké kvality** – podporuje anti‑aliasing a řízení barevného prostoru.

## Požadavky
Než se ponoříme dál, ujistěte se, že máte:

- Základní znalost programování v Javě.  
- Nainstalovaný JDK 8 nebo novější na vašem počítači.  
- Knihovna Aspose.Page pro Java (stáhněte z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat. Patří sem standardní typy grafiky AWT a API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Nastavení adresáře dokumentu
Definujte složku, kam bude uložen vygenerovaný PostScript soubor. Nahraďte zástupný text skutečnou cestou ve vašem systému.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Vytvoření výstupního proudu
Otevřete `FileOutputStream`, který ukazuje na cílový soubor `.ps`. Tento proud poskytuje binární data generovaná Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Krok 3: Vytvoření možností uložení
Vytvořte instanci `PsSaveOptions`. Můžete přizpůsobit velikost stránky, kompresi atd., ale výchozí hodnoty jsou pro tento příklad dostačující.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Vytvoření PS dokumentu
Vytvořte objekt `PsDocument`, předáním výstupního proudu a možností uložení. Příznak `false` říká Aspose.Page, aby automaticky neotevřel stránku (provedeme to ručně).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: Vytvoření kruhu
Nakreslíme kruh pomocí `Ellipse2D.Float`. Parametry jsou `(x, y, šířka, výška)`. Nastavením šířka = výška získáte dokonalý kruh.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Jak nakreslit kruh s gradientem
Nyní, když máme tvar, dalším krokem je **nakreslit kruh s gradientem**. Použitím `RadialGradientPaint` na kruh se operace vyplnění automaticky použije na gradient, který definujeme.

## Krok 6: Definice barev gradientu
Připravte dvě pole: jedno pro barvy, které se objeví v gradientu, a druhé pro odpovídající frakční pozice (0 = střed, 1 = okraj).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Krok 7: Vytvoření AffineTransform
`AffineTransform` mění měřítko a posouvá gradient tak, aby odpovídal našemu kruhu. Matice `(scaleX, 0, 0, scaleY, translateX, translateY)` vykoná požadovanou operaci.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Krok 8: Vytvoření RadialGradientPaint
Nyní vytvoříme objekt `RadialGradientPaint`. Přijímá středový bod, poloměr, ohniskový bod, frakce barev, pole barev, metodu cyklu, barevný prostor a transformaci, kterou jsme právě definovali.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Krok 9: Nastavení Paint a vyplnění kruhu
Aplikujte gradientový paint na dokument a vyplňte dříve definovaný kruh. Toto je jádro našeho **příkladu radiálního gradientu** a ukazuje, jak **vyplnit tvar gradientem**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Krok 10: Uzavření stránky a uložení dokumentu
Dokončete stránku, zapište obsah na disk a uzavřete proud. Váš PostScript soubor je nyní připraven k zobrazení v libovolném PS prohlížeči.

```java
document.closePage();
document.save();
```

Gratulujeme! Úspěšně jste vytvořili příklad radiálního gradientu v Java PostScriptu pomocí Aspose.Page. Nyní máte znovupoužitelný vzor pro **vyplnění tvaru gradientem**, který lze přizpůsobit dalším tvarům a výstupním formátům.

## Časté problémy a řešení
| Problém | Řešení |
|---------|----------|
| **FileNotFoundException** při otevírání výstupního proudu | Ověřte, že `dataDir` ukazuje na existující složku a máte oprávnění k zápisu. |
| Gradient vypadá plochý nebo chybí | Ujistěte se, že pole `fractions` má stejnou délku jako pole `colors` a že `AffineTransform` správně mění měřítko. |
| Barvy jsou převrácené | Prohoďte pořadí barev v poli `colors` nebo upravte souřadnice bodu `focus`. |

## Často kladené otázky

**Q: Kde mohu najít dokumentaci k Aspose.Page pro Java?**  
A: Kompletní reference API je k dispozici [zde](https://reference.aspose.com/page/java/).

**Q: Jak si mohu stáhnout Aspose.Page pro Java?**  
A: Stáhněte nejnovější JAR ze [stránky vydání](https://releases.aspose.com/page/java/).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano – stáhněte zkušební verzi [zde](https://releases.aspose.com/).

**Q: Mohu získat dočasnou licenci pro testování?**  
A: Samozřejmě, požádejte o ni na [stránce dočasné licence](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu získat komunitní podporu?**  
A: Připojte se k diskusi na [fóru Aspose.Page](https://forum.aspose.com/c/page/39).

## Závěr
V tomto průvodci jsme vytvořili kompletní **příklad radiálního gradientu** pro PostScript dokument pomocí Aspose.Page pro Java. Dodržením kroků nyní máte znovupoužitelný vzor pro **vyplnění tvaru gradientem**, který můžete přizpůsobit PDF, SVG nebo jakémukoli jinému formátu podporovanému Aspose.Page. Experimentujte s různými barvami, poloměry a tvary, abyste obohatili své Java grafické projekty.

---

**Poslední aktualizace:** 2026-02-13  
**Testováno s:** Aspose.Page pro Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}