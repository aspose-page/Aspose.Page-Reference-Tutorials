---
title: Přidejte elipsu radiálního přechodu pomocí Aspose.Page
linktitle: Přidejte Ellipse do Java XPS
second_title: Aspose.Page Java API
description: Prozkoumejte podrobného průvodce přidáním elipsy s radiálním přechodem v Java XPS pomocí Aspose.Page for Java. Vylepšete svou tvorbu dokumentů bez námahy.
weight: 10
url: /cs/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte elipsu radiálního přechodu pomocí Aspose.Page

## Úvod
Vítejte v našem podrobném průvodci přidáním elipsy do Java XPS pomocí Aspose.Page for Java. Aspose.Page je výkonná Java knihovna, která umožňuje vývojářům bez námahy pracovat s dokumenty XPS. V tomto tutoriálu vás provedeme procesem vytvoření elipsy s radiálním přechodem a jejím uložením jako dokument XPS.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Aspose.Page pro knihovnu Java stažena. Můžeš to dostat[tady](https://releases.aspose.com/page/java/).
- Editor kódu dle vašeho výběru (Eclipse, IntelliJ atd.) pro psaní a spouštění kódu Java.
## Importujte balíčky
Ujistěte se, že máte do svého projektu Java importované potřebné balíčky, abyste mohli používat Aspose.Page. Na začátek svého souboru Java přidejte následující příkazy pro import:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Krok 1: Nastavte adresář dokumentů
Definujte cestu k adresáři vašeho dokumentu, kam bude dokument XPS uložen:
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Vytvořte dokument XPS
Inicializujte nový dokument XPS pomocí následujícího kódu:
```java
XpsDocument doc = new XpsDocument();
```
## Krok 3: Definujte zarážky radiálního přechodu
Vytvořte seznam zarážek přechodu pro elipsu taženou radiálním přechodem:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Krok 4: Vytvořte geometrii cesty
Definujte vytaženou elipsu s radiálním přechodem pomocí geometrie cesty:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Krok 5: Přidejte plátno a cestu
Přidejte do dokumentu nové plátno a připojte cestu s definovanou geometrií:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Krok 6: Nastavte Stroke a Gradient
Nakonfigurujte tah cesty pomocí štětce s radiálním přechodem:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Krok 7: Nastavte tloušťku tahu
Určete tloušťku tahu cesty:
```java
path.setStrokeThickness(12f);
```
## Krok 8: Uložte dokument
Uložte výsledný dokument XPS:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Gratulujeme! Úspěšně jste přidali vytaženou elipsu s radiálním přechodem v Java XPS pomocí Aspose.Page for Java.
## Závěr
V tomto tutoriálu jsme prozkoumali kroky k vytvoření dokumentu XPS s vizuálně přitažlivou elipsou s radiálním přechodem. Aspose.Page for Java zjednodušuje manipulaci s dokumenty XPS a poskytuje vývojářům výkonnou sadu nástrojů.
## Často kladené otázky
### Mohu používat Aspose.Page for Java s jinými knihovnami Java?
Ano, Aspose.Page for Java lze bez problémů integrovat s jinými knihovnami Java.
### Je Aspose.Page vhodný pro zpracování rozsáhlých dokumentů?
Absolutně! Aspose.Page je navržena tak, aby efektivně zvládla zpracování rozsáhlých dokumentů.
### Kde najdu další návody a příklady pro Aspose.Page pro Javu?
 Navštivte[Aspose.Page pro dokumentaci Java](https://reference.aspose.com/page/java/)pro komplexní návody a příklady.
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Existují komunitní fóra pro diskuse Aspose.Page?
 Ano, připojte se k[Aspose.Page komunitní fórum](https://forum.aspose.com/c/page/39) spojit se s ostatními vývojáři a získat pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
