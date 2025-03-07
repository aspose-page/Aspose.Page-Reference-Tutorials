---
title: Přidejte horizontální přechod v Java XPS
linktitle: Přidejte horizontální přechod v Java XPS
second_title: Aspose.Page Java API
description: Naučte se, jak přidat úžasný horizontální přechod do XPS dokumentů v Javě pomocí Aspose.Page. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
weight: 11
url: /cs/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte horizontální přechod v Java XPS

## Úvod
Vítejte v tomto podrobném průvodci přidáním horizontálního přechodu do Java XPS pomocí Aspose.Page for Java. Aspose.Page for Java je výkonná knihovna, která umožňuje vývojářům bezproblémově pracovat s dokumenty XPS (XML Paper Specification).
V tomto tutoriálu vás provedeme procesem vytváření aplikace Java pro přidání horizontálního přechodu do dokumentu XPS. Postupujte podle níže uvedených kroků, abyste toho dosáhli snadno.
## Předpoklady
Než začnete, ujistěte se, že máte splněny následující předpoklady:
1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou Javu. Pokud ne, stáhněte si a nainstalujte nejnovější verzi Javy z[java.com](https://www.java.com).
2.  Aspose.Page for Java Library: Musíte mít knihovnu Aspose.Page for Java. Můžete si jej stáhnout z[Aspose.Page pro dokumentaci Java](https://reference.aspose.com/page/java/).
## Importujte balíčky
Začněte importem potřebných balíčků pro vaši aplikaci Java. Zahrňte do svého projektu knihovnu Aspose.Page for Java. Můžete to udělat přidáním následujících řádků kódu:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Krok 1: Inicializujte dokument
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
//Inicializujte dokument
XpsDocument doc = new XpsDocument();
```
## Krok 2: Vytvořte vodorovný přechod
```java
// Horizontální přechod
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Krok 3: Přidejte cestu s přechodem
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Krok 4: Uložte dokument
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Opakujte tyto kroky podle potřeby a upravte parametry podle svých specifických požadavků.
## Závěr
Gratulujeme! Úspěšně jste přidali horizontální přechod do dokumentu XPS pomocí Aspose.Page for Java. Tento výukový program poskytuje komplexního průvodce pro vývojáře, kteří chtějí vylepšit své aplikace Java pomocí efektů přechodu.
## Nejčastější dotazy
### Otázka: Mohu použít více přechodů v jednom dokumentu XPS?
Ano, můžete přidat více cest s různými přechody a vytvořit tak složité návrhy.
### Otázka: Je Aspose.Page kompatibilní s nejnovějšími verzemi Java?
Aspose.Page for Java je pravidelně aktualizována, aby byla zajištěna kompatibilita s nejnovějšími verzemi Java.
### Otázka: Jsou v Aspose.Page k dispozici další typy přechodů?
Ano, kromě lineárních přechodů podporuje Aspose.Page i radiální přechody pro rozmanitější efekty.
### Otázka: Mohu přizpůsobit barvy a polohy zarážek přechodu?
Absolutně! Máte plnou kontrolu nad barvami a polohami každé zarážky přechodu.
### Otázka: Existuje komunitní fórum pro Aspose.Page, kde mohu hledat pomoc?
 Ano, můžete navštívit[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) spojit se s komunitou a získat pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
