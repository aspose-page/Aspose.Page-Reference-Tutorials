---
date: 2026-01-02
description: Naučte se, jak přidat masku průhlednosti do XPS dokumentů pomocí Aspose.Page
  Java. Krok za krokem průvodce vytvořením obdélníku masky průhlednosti a zlepšením
  vizuální kvality.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Nastavení masky průhlednosti v Java XPS pomocí Aspose.Page Java
url: /cs/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení masky neprůhlednosti v Java XPS pomocí Aspose.Page Java

## Úvod
Vítejte v našem komplexním průvodci **aspose page java** maskami neprůhlednosti. V tomto tutoriálu se naučíte, jak vytvořit XPS dokument, přidat plátno a aplikovat masku neprůhlednosti na obdélník — vše pomocí výkonného Aspose.Page Java API. Na konci budete schopni přidávat obdélníky s maskou neprůhlednosti, které vašim XPS souborům dodají vyleštěný, poloprůhledný vzhled.

## Rychlé odpovědi
- **Co maska neprůhlednosti dělá?** Definuje různé úrovně průhlednosti pro tvar, což umožňuje zobrazit podkladový obsah.
- **Která knihovna je vyžadována?** Aspose.Page for Java (aspose page java).
- **Potřebuji licenci?** Dočasná licence stačí pro testování; pro produkci je vyžadována plná licence.
- **Kolik řádků kódu?** Přibližně 20 řádků Java plus několik inicializačních příkazů.
- **Mohu masku znovu použít na více tvarech?** Ano, můžete přiřadit stejný ImageBrush k několika cestám.

## Co je maska neprůhlednosti v XPS?
Maska neprůhlednosti je bitmapa nebo vektor, který řídí alfa (průhlednost) každého pixelu ve tvaru. Když je aplikována na obdélník, části obdélníku se stanou zcela neprůhlednými, částečně průhlednými nebo zcela průhlednými, čímž vznikají sofistikované vizuální efekty.

## Proč použít Aspose.Page Java pro masky neprůhlednosti?
- **Plnohodnotné .NET‑stylové API v Javě** — intuitivní objektový model.
- **Žádné externí závislosti** — funguje s čistou Javou.
- **Vysoká věrnost vykreslování** — masky se vykreslují přesně podle specifikace XPS.
- **Cross‑platform** — běží na Windows, Linuxu i macOS bez úprav.

## Požadavky
Než začnete, ujistěte se, že máte:
- Základní znalosti programování v Javě.  
- Nainstalovanou knihovnu Aspose.Page for Java. Můžete ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  
- Platnou licenci pro Aspose.Page. Pokud ji nemáte, získáte dočasnou licenci **[zde](https://purchase.aspose.com/temporary-license/)**.  
- Vývojové prostředí schopné kompilovat a spouštět Java aplikace (např. IntelliJ IDEA, Eclipse nebo VS Code).

## Import balíčků
Začněte importováním potřebných tříd z knihovny Aspose.Page. Tím zajistíte, že API bude dostupné ve vašem projektu.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Průvodce krok za krokem

### Krok 1: Vytvořte nový XPS dokument
Nejprve vytvořte čerstvý XPS dokument, který bude obsahovat veškerou naši grafiku.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Krok 2: Přidejte plátno
Plátno funguje jako kreslicí povrch uvnitř XPS stránky.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Krok 3: Přidejte obdélník a aplikujte plnou výplň
Zde vytvoříme cestu obdélníku a přiřadíme mu plnou červenou výplň. Tento obdélník později získá masku neprůhlednosti.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Krok 4: Přidejte masku neprůhlednosti pomocí ImageBrush
Načteme TIFF obrázek, definujeme zdrojové a cílové obdélníky a nastavíme štětec do režimu dlaždicování, aby se maska opakovala podle potřeby.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Krok 5: Uložte výsledný XPS dokument
Nakonec dokument uložíme na disk. Výstupní soubor bude obsahovat obdélník s aplikovanou maskou neprůhlednosti.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Postupujte podle těchto kroků pečlivě, abyste do svého Java XPS dokumentu pomocí Aspose.Page integrovali funkci **add opacity mask**.

## Časté problémy a řešení
- **Obrázek nebyl nalezen** — Ověřte, že `dataDir` ukazuje na správnou složku a že soubor `R08SY_NN.tif` existuje.
- **Maska vypadá jako plná** — Ujistěte se, že zdrojový obrázek skutečně obsahuje různé alfa hodnoty; plně neprůhledný obrázek průhlednost neukáže.
- **Režim dlaždicování není respektován** — Cílový obdélník musí být menší než zdrojový obdélník, aby bylo dlaždicování patrné.

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní se všemi Java vývojovými prostředími?**  
A: Ano, Aspose.Page je navrženo tak, aby bez problémů fungovalo s různými Java IDE a nástroji pro sestavování.

**Q: Mohu používat Aspose.Page bez licence?**  
A: Knihovnu můžete vyzkoušet s dočasnou licencí, ale pro produkční použití je vyžadována plná licence.

**Q: Existují nějaká omezení zkušební verze?**  
A: Zkušební verze může mít omezení velikosti nebo funkcí; podrobnosti najdete v oficiální dokumentaci.

**Q: Jak mohu získat podporu pro Aspose.Page?**  
A: Navštivte **[Aspose.Page fórum](https://forum.aspose.com/c/page/39)** pro komunitní pomoc nebo si zakupte licenci pro prémiovou podporu.

**Q: Nabízí Aspose.Page záruku vrácení peněz?**  
A: Informace o podmínkách vrácení najdete na **[stránce nákupu](https://purchase.aspose.com/buy)**.

---

**Poslední aktualizace:** 2026-01-02  
**Testováno s:** Aspose.Page Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}