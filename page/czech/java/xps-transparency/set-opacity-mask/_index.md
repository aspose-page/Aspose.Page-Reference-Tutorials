---
date: 2026-04-30
description: Naučte se, jak vytvořit XPS dokument v Javě a přidat masku průhlednosti
  pomocí Aspose.Page Java. Průvodce krok za krokem s ukázkami kódu.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Nastavit masku neprůhlednosti v Java XPS
second_title: Aspose.Page Java API
title: Vytvoření XPS dokumentu v Javě – nastavení masky průhlednosti pomocí Aspose.Page
url: /cs/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení masky neprůhlednosti v Java XPS pomocí Aspose.Page Java

## Úvod
V tomto tutoriálu **vytvoříte soubory XPS dokumentu v Javě** a naučíte se, jak použít masku neprůhlednosti, která vašim grafikám dodá upravený, poloprůhledný vzhled. Provedeme vás celým procesem – od inicializace XPS dokumentu, přidání plátna, nakreslení obdélníku až po připojení masky neprůhlednosti založené na obrázku – pomocí intuitivního Aspose.Page Java API. Na konci budete schopni programově generovat profesionální XPS soubory a masku znovu použít na libovolný tvar.

## Rychlé odpovědi
- **Co dělá maska neprůhlednosti?** Definuje různé úrovně průhlednosti pro tvar, což umožňuje zobrazit podkladový obsah.  
- **Která knihovna je vyžadována?** Aspose.Page pro Java (aspose page java).  
- **Potřebuji licenci?** Dočasná licence funguje pro testování; plná licence je vyžadována pro produkci.  
- **Kolik řádků kódu?** Přibližně 20 řádků Java plus několik nastavených příkazů.  
- **Mohu masku znovu použít na více tvarů?** Ano, můžete přiřadit stejný `ImageBrush` k několika cestám.

## Co je maska neprůhlednosti v XPS?
Maska neprůhlednosti je bitmapa nebo vektor, který řídí alfa (průhlednost) každého pixelu ve tvaru. Když je aplikována na obdélník, části obdélníku se stanou zcela neprůhlednými, částečně průhlednými nebo zcela průhlednými, čímž vznikají sofistikované vizuální efekty bez dalších vrstev kreslení.

## Proč použít Aspose.Page Java k **vytvoření XPS dokumentu java**?
- **Pure Java API** – Žádné nativní závislosti, takže stejný kód běží na Windows, Linuxu nebo macOS.  
- **Full XPS spec compliance** – Masky se vykreslují přesně podle definice XPS standardu.  
- **Object‑oriented design** – Podobné .NET, což usnadňuje přechod, pokud jste používali Aspose v jiných jazycích.  
- **High performance** – Optimalizováno pro velké dokumenty a dávkové zpracování.

## Běžné případy použití
- **Watermarking** – Aplikujte poloprůhledné logo napříč stránkami.  
- **Dynamic theming** – Změňte vizuální styl UI prvků v generovaných reportech.  
- **Print‑ready previews** – Zobrazte, jak bude návrh vypadat s různou průhledností před odesláním do tiskárny.

## Požadavky
Než začnete, ujistěte se, že máte:
- Základní znalost programování v Javě.  
- Knihovna Aspose.Page pro Java nainstalována. Můžete ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  
- Platná licence pro Aspose.Page. Pokud ji nemáte, získáte dočasnou licenci **[zde](https://purchase.aspose.com/temporary-license/)**.  
- Vývojové prostředí schopné kompilovat a spouštět Java aplikace (např. IntelliJ IDEA, Eclipse nebo VS Code).

## Import balíčků
Začněte importováním potřebných tříd z knihovny Aspose.Page. Tím zajistíte, že API bude ve vašem projektu k dispozici.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Průvodce krok za krokem

### Krok 1: Vytvořit nový XPS dokument
Nejprve vytvořte novou instanci XPS dokumentu, který bude obsahovat veškerou naši grafiku.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Krok 2: Přidat plátno
Plátno funguje jako kreslicí plocha uvnitř XPS stránky.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Krok 3: Přidat obdélník a použít plnou výplň
Zde vytvoříme cestu obdélníku a přiřadíme mu plnou červenou výplň. Tento obdélník později obdrží masku neprůhlednosti.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Krok 4: Přidat masku neprůhlednosti pomocí ImageBrush
Načteme TIFF obrázek, definujeme zdrojové a cílové obdélníky a nastavíme štětec do režimu dlaždicování, aby se maska v případě potřeby opakovala.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Krok 5: Uložit výsledný XPS dokument
Nakonec dokument uložíme na disk. Výstupní soubor bude obsahovat obdélník s aplikovanou maskou neprůhlednosti.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Postupujte podle těchto kroků pečlivě, abyste do svého Java XPS dokumentu pomocí Aspose.Page začlenili funkci **add opacity mask**.

## Časté problémy a řešení
- **Image not found** – Ověřte, že `dataDir` ukazuje na správnou složku a že soubor `R08SY_NN.tif` existuje.  
- **Mask appears solid** – Ujistěte se, že zdrojový obrázek skutečně obsahuje různé alfa hodnoty; plně neprůhledný obrázek nezobrazí průhlednost.  
- **Tile mode not respected** – Cílový obdélník musí být menší než zdrojový obdélník, aby bylo dlaždicování patrné.

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní se všemi vývojovými prostředími Java?**  
A: Ano, Aspose.Page je navrženo tak, aby bez problémů fungovalo s různými Java IDE a nástroji pro sestavování.

**Q: Mohu používat Aspose.Page bez licence?**  
A: I když můžete knihovnu vyzkoušet s dočasnou licencí, pro produkční použití je vyžadována plná licence.

**Q: Existují nějaká omezení zkušební verze?**  
A: Zkušební verze může mít omezení velikosti nebo funkcí; podrobnosti najdete v oficiální dokumentaci.

**Q: Jak mohu získat podporu pro Aspose.Page?**  
A: Navštivte **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pro komunitní pomoc nebo si zakupte licenci pro prémiovou podporu.

**Q: Existuje záruka vrácení peněz pro Aspose.Page?**  
A: Viz **[stránka nákupu](https://purchase.aspose.com/buy)** pro informace o podmínkách vrácení peněz.

**Poslední aktualizace:** 2026-04-30  
**Testováno s:** Aspose.Page Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}