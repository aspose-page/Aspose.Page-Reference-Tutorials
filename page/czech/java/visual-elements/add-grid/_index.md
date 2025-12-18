---
date: 2025-12-18
description: Naučte se, jak přidat mřížku a průhledný obdélník v Java XPS dokumentech
  pomocí Aspose.Page. Krok za krokem průvodce, jak efektivně uložit XPS dokument.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Jak přidat mřížku pomocí vizuálního štětce v Javě
url: /cs/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat mřížku pomocí Visual Brush v Javě

## Úvod
Pokud hledáte **jak přidat mřížku** do vašich v Javě generovaných XPS dokumentů, jste na správném místě. V tomto tutoriálu vás provedeme přidáním mřížky pomocí Visual Brush, vrstvením průhledného obdélníku a nakonec **uložením XPS dokumentu** pomocí Aspose.Page Java API. Na konci budete mít vylepšený vizuál, který lze znovu použít v reportech, fakturách nebo v jakékoli aplikaci pracující s dokumenty.

## Rychlé odpovědi
- **Co dělá Visual Brush?** Vykresluje definovanou oblast s opakovatelným vizuálním obsahem, ideální pro opakující se vzory jako jsou mřížky.  
- **Mohu změnit barvu mřížky?** Ano – upravte nastavení solid‑color štětce.  
- **Jak přidám průhledný obdélník nad mřížku?** Použijte `setOpacity` na cestu vyplněnou pevnou barvou.  
- **Jaká metoda ukládá soubor?** `doc.save(...)` zapíše XPS soubor na disk.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.

## Co je Visual Brush Grid?
Visual Brush vám umožní definovat malý vizuál (vzor mřížky) a poté jej dlaždicovat přes větší oblast. Tento přístup je paměťově úspornější než kreslení každé čáry zvlášť a poskytuje pixelově dokonalou opakovatelnost.

## Proč použít Aspose.Page pro tento úkol?
- **Cross‑platform** – Funguje na jakémkoli OS, který podporuje Javu.  
- **High‑fidelity rendering** – Přesná kontrola nad barvami, průhledností a dlaždicováním.  
- **No external dependencies** – Vše je řešeno prostřednictvím knihovny Aspose.Page.

## Požadavky
Než se pustíme dál, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Nainstalovanou knihovnu Aspose.Page – můžete si ji stáhnout z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Nainstalovaný JDK 8 nebo novější na vašem vývojovém počítači.

## Import balíčků
Nejprve importujte požadované třídy, aby kompilátor věděl, kde najít typy, které budeme používat:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Postupný průvodce

### Krok 1: Nastavte svůj projekt
Vytvořte novou instanci `XpsDocument` a nastavte složku, kam chcete uložit výstupní soubor.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Krok 2: Vytvořte magentovou vizuální štětec pro mřížku
Definujeme malý magentový tvar, který bude dlaždicován přes oblast mřížky.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Krok 3: Definujte geometrii pro štětec mřížky
Nastavte obdélníkovou oblast, která přijme dlaždicovaný vizuál.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Krok 4: Vytvořte nové plátno pro dokument
Přidejte plátno do dokumentu a umístěte jej tam, kde se má mřížka objevit.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Krok 5: Přidejte mřížku na plátno
Aplikujte vizuální štětec na geometrii, čímž povolíte dlaždicování.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Krok 6: Přidejte průhledný červený obdélník (sekundární prvek)
Zde demonstrujeme **přidání průhledného obdélníku** nad mřížku pro zvýraznění.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Krok 7: Uložte výsledný XPS dokument
Nakonec zapíšete dokument na disk – toto je krok **uložení XPS dokumentu**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Postupujte podle těchto kroků a získáte profesionálně vypadající mřížku s průhledným překryvem, vše generováno programově.

## Časté problémy a tipy
- **Nesprávná velikost dlaždice:** Ujistěte se, že `Rectangle2D` použitý pro štětec odpovídá zamýšlené velikosti opakování; jinak se vzor může roztáhnout.  
- **Průhlednost se neaplikovala:** Pamatujte, že `setOpacity` musíte zavolat na cestu, kterou chcete učinit průhlednou; neovlivní samotný štětec.  
- **Soubor se neuložil:** Ověřte, že `dataDir` ukazuje na existující složku a že má vaše aplikace oprávnění k zápisu.

## Často kladené otázky

**Q: Je Aspose.Page vhodný pro profesionální generování dokumentů?**  
A: Ano, Aspose.Page je robustní knihovna navržená pro tvorbu XPS a PDF dokumentů vysoké kvality v Javě.

**Q: Mohu pomocí Visual Brush upravit barvy mřížky?**  
A: Rozhodně! Změňte parametry `createColor` ve volání `setFill` štětce na libovolné hodnoty RGBA, které potřebujete.

**Q: Kde mohu najít další podporu pro Aspose.Page?**  
A: Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro komunitní pomoc a oficiální odpovědi.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page?**  
A: Ano, můžete získat [free trial](https://releases.aspose.com/) a vyzkoušet všechny funkce před zakoupením.

**Q: Jak mohu získat dočasnou licenci pro testování?**  
A: Získejte [temporary license](https://purchase.aspose.com/temporary-license/), která funguje pro vývoj a hodnocení.

---

**Poslední aktualizace:** 2025-12-18  
**Testováno s:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}