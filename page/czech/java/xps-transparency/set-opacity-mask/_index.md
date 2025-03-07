---
title: Nastavte masku krytí v Java XPS
linktitle: Nastavte masku krytí v Java XPS
second_title: Aspose.Page Java API
description: Objevte sílu nastavení masky krytí v Java XPS s Aspose.Page. Postupujte podle našeho podrobného průvodce pro vizuálně vylepšené dokumenty.
weight: 11
url: /cs/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavte masku krytí v Java XPS

## Úvod
Vítejte v našem komplexním průvodci nastavením masky krytí v Java XPS pomocí Aspose.Page. V tomto tutoriálu vás provedeme procesem vytvoření dokumentu XPS, přidání plátna a použití masky krytí na obdélník pomocí výkonných funkcí Aspose.Page for Java.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Page for Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).
-  Platná licence pro Aspose.Page. Pokud ji nemáte, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
- Vývojové prostředí nastavené pro spouštění aplikací Java.
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java. Ujistěte se, že máte správně integrovanou knihovnu Aspose.Page. Níže je úryvek, který vás provede:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Nyní si ukázkový kód rozdělíme do několika kroků:
## Krok 1: Vytvořte nový dokument XPS
```java
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```
## Krok 2: Přidejte plátno
```java
// Nové plátno
XpsCanvas canvas = doc.addCanvas();
```
## Krok 3: Přidejte obdélník s maskou krytí
```java
// Obdélník vlevo uprostřed s neprůhledností maskovanou ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Krok 4: Pomocí ImageBrush nastavte masku krytí
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Krok 5: Uložte výsledný dokument XPS
```java
// Uložte výsledný dokument XPS
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Pečlivě postupujte podle těchto kroků, abyste začlenili masky krytí do dokumentu Java XPS pomocí Aspose.Page.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak nastavit masky krytí v Java XPS pomocí Aspose.Page. Tato funkce dodává vašim dokumentům vrstvu vizuální bohatosti, díky čemuž jsou poutavější a dynamičtější.
## Nejčastější dotazy
### Je Aspose.Page kompatibilní se všemi vývojovými prostředími Java?
Ano, Aspose.Page je navržena tak, aby bezproblémově spolupracovala s různými vývojovými prostředími Java.
### Mohu používat Aspose.Page bez licence?
když můžete Aspose.Page používat bez licence, doporučujeme si ji pořídit pro plný rozsah funkcí a podpory.
### Existují nějaká omezení zkušební verze?
Zkušební verze může mít některá omezení funkcí. Podrobnosti je vhodné zkontrolovat v dokumentaci.
### Jak mohu získat podporu pro Aspose.Page?
 Můžete navštívit[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) pro podporu komunity nebo zakoupení licence pro prémiovou asistenci.
### Existuje pro Aspose.Page záruka vrácení peněz?
 Odkazovat na[nákupní stránku](https://purchase.aspose.com/buy) informace o zásadách vrácení peněz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
