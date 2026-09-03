---
date: 2026-05-30
description: Naučte se, jak vytvořit XPS dokument v Javě pomocí Aspose.Page a snadno
  přidat dlaždicový obrázek pomocí tohoto krok‑za‑krokem průvodce. Jak rychle vytvářet
  XPS soubory.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Přidat dlaždicový obrázek do XPS v Javě
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Jak vytvořit XPS dokument s dlaždicovým obrázkem v Javě
url: /cs/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit XPS dokument s dlaždicovým obrázkem v Javě

## Úvod
Vytváření XPS dokumentů programově je základní dovedností pro vývojáře Javy, kteří potřebují tisknutelný, zařízení‑nezávislý výstup. **Jak vytvořit XPS** soubory efektivně odpovídá Aspose.Page pro Javu, který abstrahuje nízko‑úrovňové detaily XML Paper Specification a umožňuje soustředit se na vizuální návrh. V tomto průvodci uvidíte přesně, jak vytvořit XPS dokument, přidat dlaždicový obrázek jako pozadí nebo vzor a výsledek uložit – vše s úsporným, produkčně připraveným kódem.

## Rychlé odpovědi
- **Co dělá Aspose.Page?** Poskytuje vysokou úroveň API pro generování a manipulaci s XPS dokumenty v Javě.  
- **Mohu dlaždicovat obrázek?** Ano – použijte `XpsImageBrush` s `XpsTileMode.Tile`.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo komerční licence.  
- **Jaká verze Javy je podporována?** Jakákoli JDK 8+ je kompatibilní.  
- **Jak dlouho trvá implementace?** Přibližně 10–15 minut pro základní scénář s dlaždicovým obrázkem.

## Co je „vytvořit XPS dokument“?
`XpsDocument` je hlavní objekt Aspose.Page, který představuje jeden XPS soubor v paměti. Zahrnuje stránky, zdroje a metadata, což vám umožňuje sestavit dokument programově. Vytvořit XPS dokument znamená vytvořit instanci této třídy, přidat vizuální prvky a nakonec zavolat `save`, aby se soubor s pevně definovaným rozvržením zapsal na disk. Tento přístup eliminuje ruční práci s XML a zaručuje soulad s XML Paper Specification.

## Proč přidat dlaždicový obrázek?
Dlaždicování opakuje grafiku přes definovanou oblast, což je ideální pro pozadí, vodoznaky nebo vzorové výplně. Pomocí `XpsTileMode.Tile` se obrázek automaticky opakuje bez ručního duplikování, čímž šetří vývojový čas a zajišťuje konzistentní vykreslování na jakémkoli zařízení. Dlaždicové obrázky také udržují malou velikost souboru, protože stejný bitmapový zdroj je znovu používán místo opakovaného vkládání.

## Požadavky
1. **Java Development Kit (JDK)** – nainstalována JDK 8 nebo novější.  
2. **Aspose.Page for Java** – stáhněte ze [webu](https://releases.aspose.com/page/java/).  
3. **Zapisovatelný adresář** – kam bude vygenerovaný XPS soubor uložen.

## Import balíčků
Ve svém Java projektu importujte potřebné třídy:

`XpsDocument` je hlavní objekt představující XPS soubor.  
`XpsImageBrush` maluje tvary pomocí zdroje obrázku.  
`XpsTileMode` určuje, jak je obrázek dlaždicován.  
`Rectangle2D` popisuje obdélníkovou oblast pro umístění.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Průvodce krok za krokem

### Krok 1: Nastavte svůj projekt
Přidejte soubory Aspose.Page JAR do classpath vašeho projektu a ověřte, že importy se kompilují bez chyb.

### Krok 2: Vytvořte XPS dokument
`XpsDocument` je jádro kontejneru, který obsahuje stránky, cesty a zdroje. Vytvořte jej s požadovanou velikostí stránky a můžete začít přidávat grafické prvky.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Krok 3: Definujte cestu k dlaždicovému obrázku
Umístěte obrázek, který chcete dlaždicovat (např. `R08LN_NN.jpg`) do adresáře uvedeného v `dataDir`. Obrázek bude použit jako vzor pro štětec.

### Krok 4: Přidejte dlaždicový obrázek
Vytvořte obdélníkovou cestu a vyplňte ji pomocí `XpsImageBrush`. Nastavením režimu dlaždic na `Tile` se obrázek opakuje po celém obdélníku. Upravením zdrojových a cílových obdélníků můžete řídit velikost a umístění dlaždic.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Krok 5: Uložte dokument
Uložte XPS soubor na disk. Výstupní soubor bude obsahovat právě definovaný dlaždicový obrázek a lze jej otevřít v libovolném XPS prohlížeči.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Opakujte tyto kroky vždy, když potřebujete **přidat dlaždicový obrázek** na jiné stránky nebo tvary ve stejném XPS dokumentu.

## Časté problémy a řešení
| Problém | Řešení |
|---------|--------|
| Obrázek se nezobrazuje | Ověřte, že cesta k souboru (`dataDir + "R08LN_NN.jpg"`) je správná a obrázek je přístupný. |
| Vzor dlaždic se zdá roztažený | Upravte hodnoty `Rectangle2D` pro zdroj a cíl, aby se řídila velikost dlaždice. |
| Průhlednost nemá žádný efekt | Ujistěte se, že průhlednost štětce je nastavena **po** konfiguraci režimu dlaždic. |

## Často kladené otázky

**Q:** Je Aspose.Page kompatibilní se všemi verzemi Javy?  
**A:** Aspose.Page podporuje Javu 8 až Javu 21; úplnou matici kompatibility najdete [zde](https://reference.aspose.com/page/java/).

**Q:** Mohu používat Aspose.Page v komerčních projektech?  
**A:** Ano, pro produkční použití je vyžadována komerční licence. Možnosti nákupu jsou uvedeny [zde](https://purchase.aspose.com/buy).

**Q:** Je k dispozici bezplatná zkušební verze?  
**A:** Plně funkční bezplatná zkušební verze je ke stažení na stránce Aspose releases [zde](https://releases.aspose.com/).

**Q:** Kde mohu získat komunitní podporu?  
**A:** Připojte se k fóru komunity Aspose.Page na [forum](https://forum.aspose.com/c/page/39), kde můžete klást otázky a sdílet příklady.

**Q:** Jak získám dočasnou licenci pro hodnocení?  
**A:** Dočasné licence jsou poskytovány na vyžádání prostřednictvím portálu Aspose [zde](https://purchase.aspose.com/temporary-license/).

## Závěr
Nyní máte kompletní, produkčně připravený postup pro **jak vytvořit XPS** dokumenty s dlaždicovými obrázky pomocí Aspose.Page pro Javu. Využitím `XpsImageBrush` a `XpsTileMode.Tile` můžete generovat bohatou, opakovatelnou grafiku bez zvětšování velikosti souboru. Experimentujte s různými velikostmi dlaždic, úrovněmi průhlednosti a tvary, abyste vytvořili sofistikované rozvržení dokumentů. Dalším krokem je prozkoumat přidání vektorových tvarů nebo textových překryvů pro další vylepšení vašich XPS souborů.

---

**Poslední aktualizace:** 2026-05-30  
**Testováno s:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak přidat obrázek do Java XPS dokumentů – Jednoduchý průvodce s Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java – Přidání stránek do XPS tutoriál](/page/java/xps-page-manipulation/add-page/)
- [Převod XPS na PDF v Javě pomocí Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}