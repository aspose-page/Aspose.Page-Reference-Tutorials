---
title: Přidat obdélník v Java XPS
linktitle: Přidat obdélník v Java XPS
second_title: Aspose.Page Java API
description: Naučte se přidávat obdélníky v Java XPS pomocí Aspose.Page. Postupujte podle našeho podrobného průvodce pro bezproblémovou manipulaci s dokumenty. #JavaXPS #AsposePage
weight: 11
url: /cs/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidat obdélník v Java XPS

## Úvod
Vítejte v tomto komplexním průvodci přidáváním obdélníků v Java XPS pomocí Aspose.Page! Ať už jste zkušený vývojář nebo s Java XPS teprve začínáte, tento tutoriál vás provede celým procesem s pokyny krok za krokem, což vám zajistí hluboké porozumění tématu.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programovacího jazyka Java.
-  Knihovna Aspose.Page nainstalována. Pokud ne, můžete si jej stáhnout z[Aspose.Page Java dokumentace](https://reference.aspose.com/page/java/).
- Funkční vývojové prostředí Java.
## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java. Ujistěte se, že knihovna Aspose.Page je správně přidána do vaší třídy. Zde je základní příklad:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Nyní rozdělme poskytnutý příklad do několika kroků pro přidání obdélníku v Java XPS.
## Krok 1: Nastavte adresář dokumentů
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
```
Nahraďte "Your Document Directory" cestou k požadovanému adresáři.
## Krok 2: Vytvořte nový dokument XPS
```java
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```
Tím se inicializuje nový dokument XPS.
## Krok 3: Přidejte jednobarevný tahaný obdélník CMYK
```java
// CMYK (modrý) jednobarevný vytažený obdélník vlevo dole
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Tento krok přidá vytažený obdélník s plnou barvou CMYK.
## Krok 4: Uložte výsledný dokument XPS
```java
// Uložte výsledný dokument XPS
doc.save(dataDir + "AddRectangle_out.xps");
```
Nakonec uložte upravený dokument XPS s přidaným obdélníkem.
Opakujte tyto kroky a upravte parametry podle potřeby, abyste dále přizpůsobili své obdélníky.
## Závěr
Gratulujeme! Úspěšně jste se naučili přidávat obdélníky v Java XPS pomocí Aspose.Page. Tento výukový program poskytuje pevný základ pro vaše úsilí o manipulaci s dokumenty XPS.
## Nejčastější dotazy
### Mohu přidat více obdélníků do jednoho dokumentu XPS?
Ano, můžete přidat tolik obdélníků, kolik potřebujete, opakováním kroků uvedených v tutoriálu.
### Jak mohu změnit barvu obdélníku?
 Upravte hodnoty barev v`createColor` způsob, jak dosáhnout požadované barvy.
### Je Aspose.Page vhodný pro zpracování složitých manipulací s dokumenty XPS?
Absolutně! Aspose.Page poskytuje robustní sadu funkcí pro zpracování různých úloh s dokumenty XPS.
### Kde najdu další příklady a podporu?
 Prozkoumat[Fórum Aspose.Page](https://forum.aspose.com/c/page/39)získat další příklady a požádat o pomoc komunitu.
### Mohu Aspose.Page před nákupem vyzkoušet?
 Ano, můžete prozkoumat a[zkušební verze zdarma](https://releases.aspose.com/) vyzkoušet možnosti Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
