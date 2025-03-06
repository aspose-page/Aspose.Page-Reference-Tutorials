---
title: Přidejte vertikální přechod v Java XPS
linktitle: Přidejte vertikální přechod v Java XPS
second_title: Aspose.Page Java API
description: Naučte se, jak přidat vertikální přechod do dokumentů Java XPS pomocí Aspose.Page. Vylepšete vizuální přitažlivost bez námahy. Návod krok za krokem uvnitř.
weight: 12
url: /cs/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte vertikální přechod v Java XPS

## Úvod
tomto tutoriálu prozkoumáme, jak přidat vertikální přechod v Java XPS pomocí Aspose.Page pro Java. Přidáním přechodů do vašich dokumentů XPS můžete zvýšit vizuální přitažlivost vašeho obsahu, takže bude poutavější a esteticky příjemnější.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Funkční vývojové prostředí Java.
-  Aspose.Page pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/java/).
- Základní znalost programování v Javě.
## Importujte balíčky
Začněte importem potřebných balíčků pro váš projekt Java. Ujistěte se, že jste do závislostí projektu zahrnuli knihovnu Aspose.Page for Java.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page pro Java
```
## Krok 1: Inicializujte dokument
Začněte inicializací dokumentu XPS. Tím se nastaví základ pro přidávání prvků, jako jsou cesty a přechody, do dokumentu.
```java
// Inicializujte dokument
XpsDocument doc = new XpsDocument();
```
## Krok 2: Vytvořte cestu s vertikálním přechodem
Nyní vytvoříme cestu s vertikálním přechodem. To zahrnuje definování geometrie cesty a určení zarážek přechodu.
```java
// Vytvořte cestu s geometrií
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definujte vertikální zarážky gradientu
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Použijte svislý přechod na cestu
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Krok 3: Uložte dokument
Nakonec uložte dokument XPS s přidaným vertikálním přechodem do požadovaného adresáře.
```java
// Uložte dokument
doc.save(dataDir + "VerticalGradient.xps");
```
Gratulujeme! Úspěšně jste přidali vertikální přechod do dokumentu Java XPS pomocí Aspose.Page.
## Závěr
Vylepšení vašich dokumentů XPS pomocí přechodů může výrazně zlepšit jejich vizuální přitažlivost. Aspose.Page for Java tento proces zjednodušuje a umožňuje vám snadno vytvářet úžasné dokumenty.

### Nejčastější dotazy
### Mohu používat Aspose.Page for Java v komerčních projektech?
 Ano, Aspose.Page for Java je k dispozici pro komerční použití. Můžete si jej zakoupit[tady](https://purchase.aspose.com/buy).
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Page for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/page/java/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Potřebujete pomoc nebo máte otázky?
 Navštivte komunitu Aspose.Page[Fórum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
