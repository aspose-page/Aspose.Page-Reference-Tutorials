---
title: Průvodce pokročilými transformacemi s Aspose.Page
linktitle: Transformace v Java Page Manipulation
second_title: Aspose.Page Java API
description: Naučte se provádět pokročilé transformace stránek v Javě pomocí Aspose.Page for Java. Vylepšete své Java aplikace o výkonné možnosti manipulace.
weight: 11
url: /cs/java/page-manipulation/transformations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Průvodce pokročilými transformacemi s Aspose.Page

## Úvod
Vítejte v obsáhlém průvodci o využití výkonných funkcí Aspose.Page for Java k provádění transformací v Java Page Manipulation. Aspose.Page je všestranná knihovna Java, která umožňuje vývojářům efektivně pracovat s různými úkoly manipulace se stránkami.
## Předpoklady
Než se pustíme do podrobného průvodce, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Page for Java. Můžete si jej stáhnout z[Aspose.Page pro dokumentaci Java](https://reference.aspose.com/page/java/).
- Java Integrated Development Environment (IDE) nastavené na vašem počítači.
## Importujte balíčky
Ve svém projektu Java importujte potřebné balíčky, abyste mohli využívat Aspose.Page for Java:
```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Příklad 1: Žádné transformace
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
// Vytvořte nový dokument PS s otevřenou stránkou
PsDocument document = new PsDocument(outPsStream, options, false);
//Vytvořte obdélník
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Nastavte malování v grafickém stavu na horní úrovni
document.setPaint(Color.ORANGE);
// Vyplňte první obdélník bez jakýchkoli transformací.
document.fill(shape);
// Zavřít aktuální stránku
document.closePage();
// Uložte dokument
document.save();
```
## Příklad 2: Překlad
```java
// Uložte stav grafiky pro návrat zpět po transformaci
document.writeGraphicsSave();
// Posuňte aktuální grafický stav o 250 doprava
document.translate(250, 0);
// Nastavit malování v aktuálním stavu grafiky
document.setPaint(Color.BLUE);
// Vyplňte druhý obdélník translační transformací
document.fill(shape);
// Obnovte stav grafiky na předchozí (vyšší) úroveň
document.writeGraphicsRestore();
```
## Příklad 3: Měřítko
```java
// Uložte stav grafiky pro návrat zpět po transformaci
document.writeGraphicsSave();
// Měřítko aktuálního grafického stavu na 0,5 v ose X a 0,75 f na ose Y
document.scale(0.5f, 0.75f);
// Nastavit malování v aktuálním stavu grafiky
document.setPaint(Color.RED);
// Vyplňte třetí obdélník transformací měřítka
document.fill(shape);
// Obnovte stav grafiky na předchozí (vyšší) úroveň
document.writeGraphicsRestore();
```
Pokračujte ve vzoru s příklady pro rotaci, stříhání a komplexní transformaci podle poskytnutých úryvků kódu Java.
## Závěr
tomto tutoriálu jsme prozkoumali různé transformace v Java Page Manipulation pomocí Aspose.Page for Java. Podle těchto příkladů můžete vylepšit své aplikace Java o pokročilé možnosti manipulace se stránkami.
## FAQ
### Mohu použít Aspose.Page for Java pro jiné formáty dokumentů?
Aspose.Page se primárně zaměřuje na manipulaci se stránkami pro formáty PostScript a XPS.
### Kde najdu další příklady a dokumentaci pro Aspose.Page for Java?
 Navštivte[Aspose.Page pro dokumentaci Java](https://reference.aspose.com/page/java/) pro komplexní informace.
### Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde mohu hledat podporu komunity nebo se ptát na Aspose.Page for Java?
 Navštivte[Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pro komunitní diskuse.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
