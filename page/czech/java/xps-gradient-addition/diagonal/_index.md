---
date: 2026-05-25
description: Naučte se, jak přidat gradient do XPS dokumentů v Java pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce ukazuje, jak přidat Diagonal Gradient, použít Linear
  Gradient Brushes a vytvořit profesionální XPS soubory.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Přidat Diagonal Gradient v Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Jak přidat gradient: Diagonal Gradient v Java XPS'
url: /cs/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat gradient: Diagonální gradient v Java XPS

## Úvod
V moderním vývoji v Javě ovládání **jak přidat gradient** do XPS dokumentů dodá vašim zprávám vylepšený, poutavý vzhled, který vynikne. Tento tutoriál vás provede vytvořením XPS souboru od nuly, přidáním diagonálního gradientu a uložením výsledku – vše pomocí Aspose.Page pro Java. Pochopíte, proč jsou gradienty důležité, uvidíte přesné volání API a získáte praktické tipy, jak se vyhnout běžným úskalím.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Page for Java  
- **Která metoda přidává gradient?** `createLinearGradientBrush` s gradientovými zastávkami  
- **Potřebuji licenci?** Zkušební verze funguje pro vývoj; komerční licence je vyžadována pro produkci  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní diagonální gradient  
- **Mohu to použít s jinými Java frameworky?** Ano, API je framework‑agnostické  

## Co je diagonální gradient v XPS dokumentu?
Diagonální gradient je plynulý přechod barev, který běží od jednoho rohu tvaru k protilehlému rohu, čímž vytváří šikmý vizuální efekt. V XPS je tento efekt definován lineárním gradientovým štětcem obsahujícím uspořádané gradientové zastávky, které určují barvy a relativní pozice podél diagonální čáry.

## Proč přidat diagonální gradient pomocí Aspose.Page?
Aspose.Page poskytuje **100 % věrnost vykreslování** gradientů napříč více než 20 XPS prohlížeči a podporuje **30+ XPS funkcí** jako text, obrázky a vektorové tvary. API abstrahuje složitý XPS markup, takže se můžete soustředit na design a zároveň mít jistotu, že stejný soubor vypadá identicky na platformách Windows, macOS i Linux.

## Požadavky
- Základní znalosti programování v Java.  
- Nainstalovaný JDK na vašem počítači.  
- Knihovna Aspose.Page pro Java – stáhněte ji **[zde](https://releases.aspose.com/page/java/)**.  
- IDE jako IntelliJ IDEA nebo Eclipse.

## Import balíčků
Začněte importováním tříd, které budete potřebovat. Tyto importy vám umožní přístup k geometrii, práci s gradienty a tvorbě XPS dokumentu.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Krok 1: Nastavte svůj projekt
Vytvořte nový Java projekt ve svém preferovaném IDE a přidejte soubory Aspose.Page JAR do cesty sestavení projektu.

## Krok 2: Definujte adresář dokumentu
Určete, kde bude vygenerovaný XPS soubor uložen.

```java
String dataDir = "Your Document Directory";
```

## Krok 3: Vytvořte XPS dokument
`XpsDocument` je hlavní objekt, který představuje XPS soubor v paměti. Jeho vytvoření vám poskytne plátno pro přidání stránek, tvarů a štětců.

```java
XpsDocument doc = new XpsDocument();
```

## Krok 4: Přidejte cestu diagonálního gradientu
Vytvořte obdélníkovou cestu, která přijme gradient. Geometrie cesty používá jednoduchý příkaz move‑line‑close.  
XpsPath definuje vektorový tvar v XPS dokumentu, například obdélník nebo vlastní geometrii.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Krok 5: Definujte lineární gradientové zastávky
Nastavte barvy a jejich pozice. Každá zastávka určuje bod v gradientu, kde se objeví konkrétní barva.  
XpsGradientStop představuje jedinou barevnou zastávku v gradientu, specifikuje barvu a její offset.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Krok 6: Aplikujte lineární gradient na cestu
`XpsLinearGradientBrush` je typ štětce Aspose.Page pro lineární přechody barev. Přijímá dva body, které definují směr gradientu, a kolekci gradientových zastávek, které určují barvy podél této čáry.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Krok 7: Uložte dokument
Uložte XPS soubor na disk. Soubor bude obsahovat obdélník vyplněný diagonálním gradientem, který jste definovali.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Jak přidat gradient v Java XPS?
Načtěte `XpsDocument`, vytvořte `XpsLinearGradientBrush` se startovacím bodem `(0,0)` a koncovým bodem `(width,height)`, připojte gradientové zastávky, přiřaďte štětec vlastnosti `Fill` tvaru a nakonec zavolejte `save`. Tento stručný postup vám umožní vložit diagonální gradient během několika volání API, přičemž kód zůstane čistý a udržovatelný.

## Časté úskalí a tipy
- **Směr gradientu** – ujistěte se, že počáteční a koncové body štětce odpovídají požadované diagonále; jejich prohození otočí gradient.  
- **Přesnost barev** – Aspose používá ARGB; zahrňte alfa kanál, pokud potřebujete průhlednost.  
- **Cesta k souboru** – vždy používejte absolutní cestu nebo ověřte, že relativní cesta ukazuje na existující zapisovatelný adresář.

## Další časté dotazy

**Q: Jak mohu **how to add gradient** do existujícího XPS tvaru?**  
A: Vytvořte `XpsLinearGradientBrush`, definujte gradientové zastávky a přiřaďte jej vlastnosti `Fill` tvaru, jak je ukázáno v kroku 6.

**Q: Co **apply linear gradient** ve skutečnosti dělá pod kapotou?**  
A: Vytváří definici štětce v XPS balíčku, která odkazuje na počáteční/koncové body a kolekci gradientových zastávek, které prohlížeč vykreslí jako plynulý přechod barev.

**Q: Existuje rychlý způsob, jak **how to use aspose** pro další XPS funkce?**  
A: Ano, API Aspose.Page obsahuje metody pro přidávání obrázků, textu a vlastních tvarů – jednoduše prozkoumejte třídu `XpsDocument` pro další pomocníky.

**Q: Mohu **add gradient path** použít na ne‑obdélníkové tvary?**  
A: Rozhodně. Definujte libovolnou geometrii pomocí `createPathGeometry` a poté nastavte její `Fill` na gradientový štětec.

**Q: Ovlivňuje gradient velikost souboru výrazně?**  
A: Pouze mírně; definice gradientu jsou lehké XML položky v XPS balíčku.

---

**Poslední aktualizace:** 2026-05-25  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Přidání gradientu v Aspose Page XPS](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [Jak přidat obrázek do Java XPS dokumentů – jednoduchý průvodce s Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}