---
title: Aspose.Page Java szöveg manipuláció
linktitle: Szöveg hozzáadása a Java PostScript-ben
second_title: Aspose.Page Java API
description: Fedezze fel az Aspose.Page for Java erejét a PostScript-dokumentumokhoz való szöveg hozzáadásával kapcsolatos oktatóanyagunkban. Tanulja meg könnyedén használni a rendszer- és egyéni betűtípusokat.
type: docs
weight: 10
url: /hu/java/postscript-text-manipulation/add-text/
---
## Bevezetés
Üdvözöljük lépésenkénti útmutatónkban a Java PostScript nyelvű szöveg hozzáadásához az Aspose.Page for Java használatával. Az Aspose.Page for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy könnyedén kezeljék a PostScript dokumentumokat. Ebben az oktatóanyagban végigvezetjük a szöveg hozzáadásának, a rendszer- és egyéni betűtípusok használatának, a szöveg körvonalazásának, valamint a vonások beépítésének folyamatán a tetszetős eredmény érdekében.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java programozási alapismeretek.
-  Aspose.Page for Java könyvtár telepítve. Letöltheti a[Aspose.Page a Java letöltési oldalához](https://releases.aspose.com/page/java/).
-  A szükséges betűtípusok elérhetők a megadott mappában. További információkat találhat a[Aspose.Page a Java dokumentációhoz](https://reference.aspose.com/page/java/).
## Csomagok importálása
Java-projektjében importálja a szükséges Aspose.Page for Java csomagokat:
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
## 1. lépés: Állítsa be a dokumentumot
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Kimeneti adatfolyam létrehozása PostScript-dokumentumhoz
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Hozzon létre mentési beállításokat A4-es méretben
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// PS-fájlba írandó szöveg
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Hozzon létre új 1 oldalas PS-dokumentumot
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 2. lépés: Rendszer-betűtípus használata szöveg kitöltéséhez
```java
// Rendszer betűtípus használata szöveg kitöltésére
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Szöveg kitöltése alapértelmezett vagy már meghatározott színnel (fekete)
document.fillText(str, font, 50, 100);
// Töltse ki a szöveget kék színnel
document.fillText(str, font, 50, 150, Color.BLUE);
```
## 3. lépés: Egyéni betűtípus használata a szöveg kitöltéséhez
```java
// Egyéni betűtípus használata szöveg kitöltéséhez
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Szöveg kitöltése alapértelmezett vagy már meghatározott színnel (fekete)
document.fillText(str, drFont, 50, 200);
// Töltse ki a szöveget kék színnel
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## 4. lépés: Szöveg körvonalazása rendszer betűtípussal
```java
// Rendszerbetűtípus használata szöveg körvonalazásához
document.outlineText(str, font, 50, 300);
// Vázlatos szöveg kék-lila színű, 2 pontos szélességű tollal
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Töltse ki a szöveget narancssárga színnel, és húzza át kék színű, 2 pontos szélességű tollal
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## 5. lépés: Szöveg körvonalazása egyéni betűtípussal
```java
// Egyéni betűtípus használata szöveg körvonalazásához
document.outlineText(str, drFont, 50, 450);
// Vázlatos szöveg kék-lila színű, 2 pontos szélességű tollal
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Töltse ki a szöveget narancssárga színnel, és húzza át kék színű, 2 pontos szélességű tollal
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## 6. lépés: Mentse el a dokumentumot
```java
// Az aktuális oldal bezárása
document.closePage();
// Mentse el a dokumentumot
document.save();
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan lehet szöveget hozzáadni a Java PostScript nyelvhez az Aspose.Page for Java használatával. Kísérletezzen különböző betűtípusokkal, színekkel és körvonalazási lehetőségekkel, hogy tovább javítsa dokumentumát.
## Gyakran Ismételt Kérdések
### Használhatom saját egyéni betűtípusaimat az Aspose.Page for Java programmal?
 Igen, használhat egyéni betűtípusokat a betűtípus nevének és méretének megadásával`DrFont` osztály.
### Hogyan tudom megváltoztatni a szöveg színét?
 A kívánt színt a gombbal állíthatja be`Color` osztályban a szöveg kitöltésekor vagy felvázolásakor.
### Lehetséges több oldalt hozzáadni egy PostScript dokumentumhoz?
Teljesen! Több oldalt is létrehozhat a dokumentum létrehozási és mentési lépéseinek megismétlésével.
###  Mi a célja a`ExternalFontCache` class?
`ExternalFontCache` egyéni betűtípusok lekérésére szolgál, biztosítva, hogy elérhetőek legyenek a szövegkezeléshez.
### Alkalmazhatok különböző vonásokat a vázolt szövegre?
 Igen, testreszabhatja a körvonal szélességét és színét a gombbal`Stroke` osztály és`Color` osztály, ill.