---
date: 2026-03-05
description: Naučte se, jak přidat mřížku pomocí Visual Brush v Javě s Aspose.Page.
  Postupujte podle krok‑za‑krokem průvodce a snadno vylepšete vizuální podobu dokumentu.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Jak přidat mřížku pomocí vizuálního štětce v Javě
url: /cs/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat mřížku pomocí Visual Brush v Javě

## Introduction
Pokud hledáte **jak přidat mřížku** do dokumentů generovaných v Javě, funkce Visual Brush od Aspose.Page to dělá překvapivě jednoduše. V tomto tutoriálu vás provede každým krokem, vysvětlí, proč je Visual Brush ideální pro vzory mřížky, a ukáže vám kompletní, spustitelný příklad.

## Quick Answers
- **What is a Visual Brush?** Opakovatelný vizuální prvek, který může být dlaždicován nebo roztahován tak, aby vyplnil oblast.  
- **Why use a grid?** Mřížky pomáhají strukturovat rozvržení, vytvářet pozadí nebo zvýrazňovat sekce v XPS dokumentech.  
- **Prerequisites?** Java JDK, Aspose.Page for Java a základní znalost grafiky v Javě.  
- **How long does implementation take?** Přibližně 10‑15 minut po nastavení knihovny.  
- **Can I customize colors?** Ano – barvy výplně, průhlednost a velikost dlaždice můžete řídit přímo v kódu.

## Why Use Visual Brush to Add a Grid?
Visual Brush vám umožní definovat malý vizuální prvek („dlaždici“) jednou a poté jej opakovat napříč libovolným tvarem. Tento přístup je paměťově úsporný a udržuje kód přehledný, zejména když potřebujete stejný vzor aplikovat na více pláten.

## Prerequisites
Než se pustíme do kódu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.  
- Nainstalovanou knihovnu Aspose.Page. Můžete ji stáhnout z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Nainstalovaný Java Development Kit (JDK) na vašem počítači.

## Import Packages
Ujistěte se, že máte v projektu Java importovány potřebné balíčky:
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

### Step 1: Set Up Your Project
Nejprve vytvořte instanci `XpsDocument` a nastavte složku, kam bude výstup uložen.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create Magenta Grid Visual Brush
Vytvoříme malý magenta dlaždici, která bude opakována. Geometrie cesty definuje tvar dlaždice.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for Magenta Grid Visual Brush
Zde popisujeme oblast, která obdrží dlaždicový štětec.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create New Canvas
Do dokumentu se přidá nový plátno a aplikujeme transformační posun, aby se mřížka objevila na požadovaném místě.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add Grid to Canvas
Nyní svázeme visual brush s geometrií a nastavíme režim dlaždicování.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add Red Transparent Rectangle
Pro demonstraci vrstvení překryjeme mřížku poloprůhledným červeným obdélníkem.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save Resultant XPS Document
Nakonec zapíšeme soubor XPS na disk.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Postupujte podle těchto kroků a úspěšně přidáte vizuálně atraktivní mřížku pomocí Visual Brush ve vaší Java aplikaci s Aspose.Page.

## Common Use Cases
- **Report backgrounds:** Přidejte jemné mřížkové vzory do finančních nebo technických zpráv pro lepší čitelnost.  
- **Design templates:** Vytvořte opakovaně použitelné šablony stránek, kde se stejná mřížka opakuje napříč více stránkami.  
- **Highlight sections:** Překryjte barevné mřížky, aby upoutaly pozornost na konkrétní oblasti dokumentu.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Grid appears stretched** | Ověřte, že `TileMode` je nastaven na `XpsTileMode.Tile` a že zdrojové i cílové obdélníky mají stejnou velikost. |
| **Colors look off** | Ujistěte se, že používáte správné RGBA hodnoty při vytváření solid color brush (`createColor(alpha, red, green, blue)`). |
| **Document not saved** | Zkontrolujte, že `dataDir` ukazuje na existující zapisovatelnou složku a že máte potřebná oprávnění k souborovému systému. |

## Conclusion
Gratulujeme! Naučili jste se **jak přidat mřížku** pomocí Visual Brush od Aspose.Page v Javě. Tato technika vám poskytuje detailní kontrolu nad vykreslováním vzorů a zároveň udržuje váš kód čistý a snadno udržovatelný.

## Frequently Asked Questions
### Is Aspose.Page suitable for professional document generation?
Ano, Aspose.Page je robustní knihovna navržená pro profesionální generování dokumentů v Javě.

### Can I customize the grid colors using Visual Brush?
Rozhodně! Visual Brush vám umožní malovat různými barvami, což poskytuje flexibilitu při přizpůsobení.

### Where can I find additional support for Aspose.Page?
Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuze.

### Is there a free trial available for Aspose.Page?
Ano, můžete získat [free trial](https://releases.aspose.com/) a prozkoumat funkce Aspose.Page.

### How can I obtain a temporary license for Aspose.Page?
Získejte [temporary license](https://purchase.aspose.com/temporary-license/) pro testovací účely.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose  

---