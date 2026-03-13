---
date: 2026-03-13
description: Naučte se, jak přidat gradient do XPS dokumentů v Javě pomocí Aspose.Page
  a jak přizpůsobit zastávky gradientu pro úchvatné horizontální efekty.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Jak přidat gradient – horizontální gradient v Java XPS
url: /cs/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat gradient – horizontální gradient v Java XPS

## Úvod
Vítejte v tomto krok‑za‑krokem průvodci, jak **přidat gradient** do XPS dokumentu pomocí Javy. V tomto tutoriálu se naučíte, jak přidat horizontální gradient, proč je důležitý pro vizuální dokonalost a jak **přizpůsobit gradientové zastávky** pro přesnou kontrolu barev. Aspose.Page pro Javu usnadňuje práci s dokumenty XPS (XML Paper Specification), což vám umožní soustředit se na design místo na nízkoúrovňové zpracování souborů.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Která verze Javy funguje?** Jakýkoli runtime Java 8+  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence  
- **Mohu změnit směr gradientu?** Ano – stačí upravit počáteční a koncové body lineárního štětce  
- **Je možné přidat více gradientů?** Rozhodně – opakujte kroky vytvoření cesty s různými štětci  

## Co je horizontální gradient v XPS?
Horizontální gradient je plynulý přechod barev zleva doprava přes tvar. V XPS je reprezentován lineárním gradientovým štětcem, který interpoluje mezi definovanými **gradientovými zastávkami**. Tento vizuální efekt se běžně používá pro bannery, tlačítka a výplně pozadí.

## Proč používat Aspose.Page pro Javu?
- **Kompletní podpora XPS** – vytvářejte, upravujte a renderujte bez nástrojů třetích stran.  
- **Jednoduché API** – objekty vysoké úrovně jako `XpsDocument`, `XpsPath` a `XpsGradientBrush` skrývají složitost XML.  
- **Výkon** – optimalizováno pro velké dokumenty a dávkové zpracování.  

## Předpoklady
Předtím, než začnete, ujistěte se, že máte:

1. **Vývojové prostředí Java** – Nainstalujte nejnovější JDK z [java.com](https://www.java.com).  
2. **Knihovna Aspose.Page pro Javu** – Stáhněte JAR z [dokumentace Aspose.Page pro Javu](https://reference.aspose.com/page/java/).  

## Import balíčků
Začněte importováním potřebných tříd. Tyto importy vám poskytují přístup k vytváření dokumentů, práci s gradienty a základní geometrii.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Krok 1: Inicializace XPS dokumentu
Vytvořte novou instanci `XpsDocument` a určete složku, kam chcete výsledek uložit.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Krok 2: Vytvoření horizontálního gradientu
Definujte seznam **gradientových zastávek**, které řídí barvu a pozici každého přechodového bodu. Níže uvedený příklad vytváří živý duhový gradient.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Jak přizpůsobit gradientové zastávky
- **Barva** – Použijte `doc.createColor(alpha, red, green, blue)` k nastavení libovolné ARGB hodnoty.  
- **Pozice** – Druhý argument (`float` mezi `0` a `1`) určuje, kde se zastávka objeví podél gradientové čáry. Úpravou těchto hodnot posunete barvy doleva nebo doprava.  

## Krok 3: Přidání cesty s gradientem
Vytvořte obdélníkovou cestu, případně aplikujte transformaci, a vyplňte ji lineárním gradientovým štětcem. Štětec používá dva body (`(10,0)` až `(228,0)`) k vytvoření horizontálního efektu. Protože Y‑souřadnice jsou identické, tento štětec funguje jako **horizontální gradientový štětec**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Tip:** Opakované používání stejného seznamu `stops` pro více cest může zlepšit výkon, ale nezapomeňte jej před přidáním nových zastávek `clear()`.

## Krok 4: Uložení dokumentu
Uložte soubor XPS na disk. Nyní jej můžete otevřít v libovolném prohlížeči XPS a vidět horizontální gradient v akci.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Jak použít více gradientů
Pokud chcete **použít více gradientů** ve stejném XPS dokumentu, jednoduše opakujte kroky „Vytvořit horizontální gradient“ a „Přidat cestu s gradientem“ pro každý nový tvar. Použijte nový seznam objektů `XpsGradientStop` (nebo vyčistěte existující seznam) a přiřaďte nový `LinearGradientBrush` s vlastními počátečními a koncovými body. Tento přístup vám umožní vrstvit gradienty, vytvářet složitá pozadí nebo zvýraznit různé UI prvky na jedné stránce.

## Proč je to důležité – Výhody horizontálního gradientového štětce
- **Vizuální hloubka:** Horizontální gradientový štětec přidává jemný trojrozměrný dojem bez dalších obrázků.  
- **Efektivita velikosti souboru:** Gradienty jsou uloženy jako vektorové definice, což udržuje soubor XPS lehký.  
- **Škálovatelnost:** Protože je gradient vektorový, škáluje se čistě na displejích s vysokým rozlišením.  

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|--------|-----|
| Gradient se zobrazuje jako plná barva | Nebyla přidána žádná gradientová zastávka nebo není nastaven štětec | Ujistěte se, že `path.setFill(...)` používá `LinearGradientBrush` a že jsou zastávky přidány pomocí `getGradientStops().addAll(stops)`. |
| Barvy vypadají mdlé | Nesprávná hodnota alfa (první parametr) | Použijte `255` pro plně neprůhledné barvy, pokud není požadována průhlednost. |
| Velikost cesty je špatná | Hodnoty transformační matice jsou nesprávné | Upravte parametry matice (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Často kladené otázky

**Q: Mohu použít více gradientů v jednom XPS dokumentu?**  
A: Ano, můžete přidat více cest, každou s vlastním gradientovým štětcem, a vytvořit tak složité vrstvené návrhy.

**Q: Je Aspose.Page kompatibilní s nejnovějšími verzemi Javy?**  
A: Aspose.Page pro Javu je pravidelně aktualizována a funguje s Java 8 a novějšími verzemi.

**Q: Existují v Aspose.Page i jiné typy gradientů?**  
A: Kromě lineárních gradientů Aspose.Page také podporuje radiální gradienty pro kruhové přechody barev.

**Q: Mohu přizpůsobit barvy a pozice gradientových zastávek?**  
A: Rozhodně! Máte plnou kontrolu nad ARGB barvou každé zastávky a její relativní pozicí (rozsah 0‑1).

**Q: Existuje komunitní fórum pro Aspose.Page, kde mohu získat pomoc?**  
A: Ano, můžete navštívit [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde se můžete spojit s komunitou a získat pomoc.

---

**Poslední aktualizace:** 2026-03-13  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}