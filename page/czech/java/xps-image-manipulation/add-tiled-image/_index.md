---
date: 2025-12-28
description: Naučte se, jak v Javě pomocí Aspose.Page vytvořit XPS dokument a snadno
  přidat dlaždicový obrázek pomocí tohoto krok‑za‑krokem průvodce.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Jak vytvořit XPS dokument s dlaždicovým obrázkem v Javě
url: /cs/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS dokumentu a přidání dlaždicového obrázku v Javě

## Úvod
V moderním vývoji v Javě je schopnost **vytvořit XPS dokument** programově cennou dovedností, zejména když potřebujete dokument obohatit o grafiku, jako jsou dlaždicové obrázky. Aspose.Page pro Javu tento proces zjednodušuje a umožňuje vám soustředit se na vizuální design místo nízkoúrovňové manipulace se soubory. V tomto tutoriálu se naučíte, jak přesně vytvořit XPS dokument, **přidat dlaždicový obrázek** a uložit výsledek, vše s jasnými, krok‑za‑krokem příklady kódu.

## Rychlé odpovědi
- **Co dělá Aspose.Page?** Poskytuje vysoce‑úrovňové API pro generování a manipulaci s XPS dokumenty v Javě.  
- **Mohu dlaždicovat obrázek?** Ano – použijte `XpsImageBrush` s `XpsTileMode.Tile`.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo komerční licence.  
- **Jaká verze Javy je podporována?** Jakákoli JDK 8+ je kompatibilní.  
- **Jak dlouho trvá implementace?** Přibližně 10–15 minut pro základní scénář s dlaždicovým obrázkem.

## Co znamená „vytvořit XPS dokument“?
Soubor XPS (XML Paper Specification) je formát dokumentu s pevnou rozložením podobný PDF. Programové vytvoření XPS dokumentu vám umožní generovat tisknutelné, zařízení‑nezávislé soubory přímo z Java kódu.

## Proč přidávat dlaždicový obrázek?
Dlaždicování obrázku opakuje grafiku přes definovanou oblast, což je ideální pro pozadí, vodoznaky nebo vzorové výplně. Pomocí `XpsTileMode.Tile` v Aspose.Page můžete dosáhnout tohoto efektu jen několika řádky kódu.

## Předpoklady
Před tím, než se pustíte do práce, se ujistěte, že máte:

1. **Java Development Kit (JDK)** – nainstalovanou JDK 8 nebo novější.  
2. **Aspose.Page pro Javu** – stáhněte ze [stránky](https://releases.aspose.com/page/java/).  
3. **Zapisovatelný adresář** – kam bude uložen vygenerovaný XPS soubor.

## Import balíčků
Ve vašem Java projektu importujte potřebné třídy:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Průvodce krok za krokem

### Krok 1: Nastavení projektu
Přidejte JAR soubory Aspose.Page do classpath vašeho projektu a ověřte, že importy se kompilují bez chyb.

### Krok 2: Vytvoření XPS dokumentu
Instancujte nový objekt `XpsDocument`. Toto je hlavní kontejner, který bude obsahovat všechny stránky, cesty a zdroje.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Krok 3: Definice cesty k dlaždicovému obrázku
Umístěte obrázek, který chcete dlaždicovat (např. `R08LN_NN.jpg`) do adresáře uvedeného v `dataDir`. Obrázek bude použit jako vzor pro štětec.

### Krok 4: Přidání dlaždicového obrázku
Vytvořte obdélníkovou cestu a vyplňte ji pomocí `XpsImageBrush`. Nastavením režimu dlaždicování na `Tile` se obrázek opakuje po celém obdélníku.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Krok 5: Uložení dokumentu
Uložte XPS soubor na disk. Výstupní soubor bude obsahovat dlaždicový obrázek, který jste právě definovali.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Opakujte tyto kroky kdykoli potřebujete **přidat dlaždicový obrázek** na jiné stránky nebo tvary ve stejném XPS dokumentu.

## Časté problémy a řešení
| Problém | Řešení |
|---------|--------|
| Obrázek se nezobrazuje | Ověřte, že cesta k souboru (`dataDir + "R08LN_NN.jpg"`) je správná a obrázek je přístupný. |
| Vzor dlaždic se roztahuje | Upravit hodnoty `Rectangle2D` pro zdroj a cíl, aby se kontrolovala velikost dlaždice. |
| Průhlednost nemá žádný efekt | Ujistěte se, že průhlednost štětce je nastavena **po** konfiguraci režimu dlaždicování. |

## Často kladené otázky

### Je Aspose.Page kompatibilní se všemi verzemi Javy?
Aspose.Page je navržen tak, aby fungoval s různými verzemi Javy. Zkontrolujte kompatibilitu v dokumentaci [zde](https://reference.aspose.com/page/java/).

### Mohu používat Aspose.Page v komerčních projektech?
Ano, Aspose.Page nabízí komerční licence. Zakupte je [zde](https://purchase.aspose.com/buy).

### Je k dispozici bezplatná zkušební verze?
Ano, vyzkoušejte funkce Aspose.Page s bezplatnou zkušební verzí [zde](https://releases.aspose.com/).

### Kde najdu komunitní podporu a diskuse?
Zapojte se do komunity Aspose.Page na [fóru](https://forum.aspose.com/c/page/39).

### Jak získat dočasnou licenci pro Aspose.Page?
Získejte dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-28  
**Testováno s:** Aspose.Page pro Javu 24.12 (nejnovější)  
**Autor:** Aspose  

---