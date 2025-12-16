---
date: 2025-12-14
description: Tanulja meg, hogyan állíthatja be a szöveg színét Java-ban az Aspose.Page
  for Java használatával, hogyan adhat szöveget a PostScript-hez, és hogyan alkalmazhat
  körvonalas szöveget a gazdag dokumentumstílushoz.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Szöveg színének beállítása Java-ban az Aspose.Page segítségével – Szövegmanipulációs
  útmutató
url: /hu/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Szöveg színének beállítása Java-ban az Aspose.Page használatával – Szövegmanipulációs útmutató

## Introduction
Üdvözöljük lépésről‑lépésre útmutatónkban, amely a **set text color java** témakörét mutatja be PostScript fájlokkal dolgozva az Aspose.Page for Java használatával. Az Aspose.Page for Java egy erőteljes könyvtár, amely lehetővé teszi a fejlesztők számára, hogy **generate postscript file** dokumentumokat hozzanak létre, betűtípusokat manipuláljanak, és a szöveget precízen formázzák. Ebben a tutorialban megtanulja, hogyan adjon szöveget, változtassa meg annak színét, állítsa be a méretet, és akár **apply stroke text** is alkalmazzon a kifinomult megjelenésért.

## Quick Answers
- **Melyik könyvtár teszi lehetővé a szöveg színének beállítását Java-ban?** Aspose.Page for Java.
- **Használhatok rendszer‑ és egyéni betűtípusokat?** Igen, mindkettő támogatott.
- **Hogyan változtathatom meg a szöveg méretét?** A betűméret megadásával a `Font` vagy `DrFont` létrehozásakor.
- **Lehetséges egyszerre körvonalazni és kitölteni a szöveget?** Természetesen – használja a `fillAndStrokeText`-et.
- **Milyen kimeneti formátumot állít elő ez a tutorial?** Egy PostScript (`.ps`) dokumentum.

## What is “set text color java”?
A szöveg színének beállítása Java-ban azt jelenti, hogy definiáljuk a `Color` objektumot, amelyet a renderelő motor (itt az Aspose.Page) használ a karakterek oldalra rajzolásakor. Ez a művelet elengedhetetlen a vizuálisan megkülönböztethető dokumentumok létrehozásához, különösen **postscript documents** programozott generálásakor.

## Why use Aspose.Page for Java?
- **Full control** a PostScript generálás felett anélkül, hogy natív PostScript interpreterre lenne szükség.
- **Support for both system and external fonts**, lehetővé téve bármilyen tipográfia beágyazását.
- **Easy API** a kitöltéshez, körvonalazáshoz és **fill and stroke text**, amely rugalmasságot biztosít a formázásban.
- **Cross‑platform** kompatibilitás – egyszer ír, bárhol fut, ahol Java fut.

## Prerequisites
Mielőtt belemerülne, győződjön meg róla, hogy rendelkezik:

- Alapvető Java programozási ismeretekkel.
- Telepített Aspose.Page for Java könyvtárral. Letöltheti a [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) oldalról.
- A szükséges betűtípusokkal a megadott mappában. További részletek a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalon találhatók.

## Import Packages
Java projektjében importálja a szükséges csomagokat az Aspose.Page for Java-hoz:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Step 1: Set Up the Document
Először létrehozunk egy új **PostScript document**-ot, és beállítjuk a kimeneti opciókat.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## How to Set Text Color Java Using System Font
Most bemutatjuk a **set text color java**-t egy rendszer‑által biztosított betűtípussal.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** A `fillText` metódus automatikusan a jelenlegi színt használja, ha nem ad meg `Color` argumentumot, amely alapértelmezés szerint feketére van állítva.

## Using Custom Font and Changing Text Size
Szintén **change text size**-t végezhet, és egy egyéni betűtípust használhat, amely a betűtípusok mappájában van tárolva.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
A szöveg körvonalazása éles szegélyt ad. Itt **apply stroke text**-et használunk egy `BasicStroke` segítségével.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Outlining Text with Custom Font
Ugyanez a technika működik egyéni betűtípusokkal is.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
Végül zárja be az oldalt, és írja a fájlt a lemezre.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | Győződjön meg róla, hogy a betűtípus fájl a `necessary_fonts` mappában van, és a mappa útvonalát helyesen adta hozzá a `options.setAdditionalFontsFolders` segítségével. |
| **Color not applied** | Ellenőrizze, hogy a `fillText` vagy `outlineText` megfelelő túlterhelését hívja, amely tartalmaz `Color` argumentumot. |
| **Stroke appears too thin** | Növelje a `BasicStroke` szélességét (pl. `new BasicStroke(3)`). |
| **Document not opening** | Erősítse meg, hogy a generált `.ps` fájl a megfelelő kiterjesztéssel van mentve, és hogy a megjelenítője támogatja a PostScript-et. |

## Frequently Asked Questions

**Q:** Használhatok saját egyéni betűtípusokat az Aspose.Page for Java-val?  
A: Igen, egyéni betűtípusokat használhat a betűtípus nevét és méretét a `DrFont` osztályban megadva.

**Q:** Hogyan változtathatom meg a szöveg színét?  
A: A kívánt színt a `Color` osztály segítségével állíthatja be a szöveg kitöltésekor vagy körvonalazásakor.

**Q:** Lehetséges több oldalt hozzáadni egy PostScript dokumentumhoz?  
A: Természetesen! Több oldalt hozhat létre a dokumentum létrehozási és mentési lépések megismétlésével.

**Q:** Mi a `ExternalFontCache` osztály célja?  
A: `ExternalFontCache` arra szolgál, hogy egyéni betűtípusokat töltsön be, biztosítva, hogy azok elérhetők legyenek a szövegmanipulációhoz.

**Q:** Alkalmazhatok különböző vonalakat a körvonalazott szövegre?  
A: Igen, a vonal szélességét és színét a `Stroke` osztály és a `Color` osztály segítségével testreszabhatja.

## Conclusion
Gratulálunk! Most már tudja, hogyan **set text color java**, hogyan változtassa meg a betűméreteket, **apply stroke text**, és hogyan **create postscript document** fájlokat használja az Aspose.Page for Java-val. Kísérletezzen különböző betűtípusokkal, színekkel és körvonalazási stílusokkal, hogy professzionális megjelenésű PostScript kimenetet hozzon létre.

**Legutóbb frissítve:** 2025-12-14  
**Tesztelve ezzel:** Aspose.Page for Java 23.12 (latest)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}