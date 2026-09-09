---
date: 2026-09-09
description: Naučte se, jak vytvořit gradient v Java PostScript a přidat gradient
  do tvaru pomocí Aspose.Page. Postupujte podle tohoto krok‑za‑krokem průvodce s kódem
  a tipy.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Radiální gradient v Java PostScript s Aspose.Page
og_description: Naučte se, jak vytvořit gradient v Java PostScript a přidat gradient
  do tvaru pomocí Aspose.Page. Postupujte podle tohoto krok‑za‑krokem průvodce s kódem
  a tipy.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Jak vytvořit gradient v Java PostScript s radiálním výplní
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Jak vytvořit gradient v Java PostScript s radiálním výplní
url: /cs/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit gradient v Java PostScript s radiálním výplní

## Úvod
V tomto tutoriálu se naučíte **jak vytvořit gradient** grafiku v dokumentu PostScript pomocí Javy a Aspose.Page. Provedeme vás každým krokem—od nastavení projektu až po vykreslení kruhu vyplněného plynulým radiálním gradientem—abyste mohli **přidat gradient do tvarů** okamžitě a zvýšit vizuální kvalitu vašich Java aplikací.

## Rychlé odpovědi
- **Co tento tutoriál vytváří?** Soubor PostScript (`.ps`) obsahující kruh vyplněný radiálním gradientem.  
- **Která knihovna je vyžadována?** Aspose.Page pro Java (nejnovější verze).  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro funkční příklad.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence; pro vývoj stačí bezplatná zkušební verze.  
- **Mohu kód znovu použít pro PDF nebo SVG?** Ano—Aspose.Page podporuje více výstupních formátů s minimálními úpravami.

## Jak vyplnit tvar gradientem v PostScriptu
Můžete vyplnit tvar radiálním gradientem v PostScriptu vytvořením `PsDocument`, definováním `RadialGradientPaint`, aplikací na cílový tvar a nakonec uložením dokumentu. Tento stručný postup vám umožní vytvářet profesionálně vypadající vektorovou grafiku bez rastrových obrázků a stejný kód lze znovu použít pro výstup do PDF nebo SVG. Proces je jednoduchý a funguje konzistentně ve všech podporovaných formátech.

## Co je radiální gradient?
Radiální gradient přechází barvy od centrálního bodu směrem ven, čímž vytváří plynulé, kruhové přechody. Je ideální pro zvýraznění, pozadí tlačítek nebo jakýkoli vizuál, který potřebuje přirozený efekt „záře“. Vytvářením různých barevných zastávek a poloměru můžete simulovat osvětlení, hloubku a materiálové vlastnosti v čisté vektorové podobě.

## Proč použít Aspose.Page pro radiální gradienty?
Aspose.Page vám umožní generovat zařízení‑nezávislou vektorovou grafiku pomocí jediné Java API. Podporuje více než 50 vstupních a výstupních formátů—včetně PostScriptu, PDF a SVG—při zachování přesnosti barev a anti‑aliasingu pro výstup ve vysokém rozlišení. Knihovna také poskytuje snadno použitelné třídy pro gradienty, což činí implementaci složitých vizuálních efektů jednoduchou.

## Předpoklady
- Základní znalost programování v Javě.  
- Nainstalovaný JDK 8 nebo novější na vašem počítači.  
- Knihovna Aspose.Page pro Java (ke stažení z [Dokumentace Aspose.Page pro Java](https://reference.aspose.com/page/java/)).  

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

## Krok 1: nastavení adresáře dokumentu
Definujte složku, kam bude uložen vygenerovaný soubor PostScript. Nahraďte zástupný znak skutečnou cestou ve vašem systému.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: vytvoření výstupního proudu
FileOutputStream zapisuje surová data do souboru, což umožňuje uložení binárních dat. Otevření proudu zaměřeného na soubor `.ps` umožní Aspose.Page streamovat vygenerovaná data PostScript přímo na disk.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Krok 3: vytvoření možností uložení
PsSaveOptions konfiguruje, jak se soubor PostScript ukládá, včetně velikosti stránky a komprese. Můžete tato nastavení upravit, ale výchozí hodnoty jsou pro tento příklad dostačující.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: vytvoření PS dokumentu
PsDocument představuje dokument PostScript v paměti a poskytuje metody pro přidávání stránek a grafiky.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: vytvoření kruhu
`Ellipse2D.Float` popisuje tvar elipsy; když šířka = výška, stane se z ní dokonalý kruh. Tento objekt bude sloužit jako plátno pro naši výplň gradientem.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Jak nakreslit kruh s gradientem
Pro nakreslení kruhu s radiálním gradientem načtete `RadialGradientPaint` do grafického kontextu a poté vyplníte dříve definovanou elipsu. Tato jediná operace namaluje tvar plynulým přechodem barvy od středu směrem ven, čímž vytvoří vizuálně atraktivní efekt.

## Krok 6: definování barev gradientu
Připravte dva pole: jedno pro barvy, které se objeví v gradientu, a druhé pro odpovídající zlomkové pozice (0 = střed, 1 = okraj).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Krok 7: vytvoření AffineTransform
AffineTransform je matice, která může posouvat, otáčet, měnit měřítko nebo zkosit grafické objekty. Zde mění měřítko a posouvá gradient tak, aby přesně zapadl do kruhu.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Krok 8: vytvoření RadialGradientPaint
RadialGradientPaint vytváří radiální barevný gradient založený na středovém bodě, poloměru a barevných zastávkách.

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

## Krok 9: nastavení paint a vyplnění kruhu
Aplikujte gradient paint na dokument a vyplňte dříve definovaný kruh. Toto je jádro našeho **příkladu radiálního gradientu** a ukazuje, jak **vyplnit tvar gradientem**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Krok 10: uzavření stránky a uložení dokumentu
Dokončete stránku, zapište obsah na disk a uzavřete proud. Váš soubor PostScript je nyní připraven k zobrazení v libovolném PS prohlížeči.

```java
document.closePage();
document.save();
```

Gratulujeme! Úspěšně jste vytvořili příklad radiálního gradientu v Java PostScript pomocí Aspose.Page. Nyní máte znovupoužitelný vzor pro **vyplnění tvaru gradientem**, který lze přizpůsobit dalším tvarům a výstupním formátům.

## Časté problémy a řešení
| Problém | Řešení |
|---------|----------|
| **FileNotFoundException** při otevírání výstupního proudu | Ověřte, že `dataDir` ukazuje na existující složku a máte oprávnění k zápisu. |
| Gradient vypadá plochý nebo chybí | Ujistěte se, že pole `fractions` má stejnou délku jako pole `colors` a že `AffineTransform` správně mění měřítko. |
| Barvy se zobrazují obráceně | Prohoďte pořadí barev v poli `colors` nebo upravte souřadnice bodu `focus`. |

## Často kladené otázky

**Q: Kde mohu najít dokumentaci pro Aspose.Page pro Java?**  
A: Kompletní reference API je k dispozici v [Dokumentaci Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Q: Jak si mohu stáhnout Aspose.Page pro Java?**  
A: Stáhněte nejnovější JAR ze [stránky vydání](https://releases.aspose.com/page/java/).

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano—stáhněte zkušební verzi ze [stránky Aspose free trial download](https://releases.aspose.com/).

**Q: Mohu získat dočasnou licenci pro testování?**  
A: Určitě, požádejte o ni na [stránce dočasné licence](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu získat podporu komunity?**  
A: Připojte se k diskuzi na [fóru Aspose.Page](https://forum.aspose.com/c/page/39).

## Závěr
V tomto průvodci jsme vytvořili kompletní **příklad radiálního gradientu** pro dokument PostScript pomocí Aspose.Page pro Java. Dodržením kroků máte nyní znovupoužitelný vzor pro **vyplnění tvaru gradientem**, který můžete přizpůsobit PDF, SVG nebo jakémukoli jinému formátu podporovanému Aspose.Page. Experimentujte s různými barvami, poloměry a tvary, abyste obohatili své Java grafické projekty.

---

**Poslední aktualizace:** 2026-09-09  
**Testováno s:** Aspose.Page pro Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit PostScript Gradient v Javě – Přidat vertikální gradient](/page/java/postscript-gradient-addition/vertical/)
- [Vytvořit texturovaný vzor v PostScriptu s Aspose.Page pro Java](/page/java/postscript-texture-patterns/)
- [Tutoriál o průhlednosti Aspose.Page – Přidat průhlednost v Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}