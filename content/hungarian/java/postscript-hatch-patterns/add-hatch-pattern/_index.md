---
title: Adja hozzá a sraffozási mintát a Java PostScript-hez
linktitle: Adja hozzá a sraffozási mintát a Java PostScript-hez
second_title: Aspose.Page Java API
description: Ismerje meg, hogyan adhat lenyűgöző sraffozási mintákat a Java PostScript dokumentumokhoz az Aspose.Page használatával. Emelje fel vizuális tartalmát könnyedén.
type: docs
weight: 10
url: /hu/java/postscript-hatch-patterns/add-hatch-pattern/
---
## Bevezetés
Java programozás világában a vizuális elemek javítása általános követelmény a fejlesztők számára. Az egyik érdekes vizuális fejlesztés a sraffozási minták hozzáadása a PostScript dokumentumokhoz. Ez az oktatóanyag végigvezeti a sraffozási minták hozzáadásának folyamatán az Aspose.Page for Java használatával.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy beállította a következőket:
- Java fejlesztői környezet: Győződjön meg arról, hogy készen áll a Java fejlesztői környezetre.
-  Aspose.Page for Java Library: Töltse le és telepítse az Aspose.Page for Java könyvtárat. Megtalálhatja a szükséges fájlokat[itt](https://releases.aspose.com/page/java/).
## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java projektbe. Használja a következő kódrészletet:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 1. lépés: A kezdeti paraméterek beállítása
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Kimeneti adatfolyam létrehozása PostScript-dokumentumhoz
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Hozzon létre mentési beállításokat A4-es méretben
PsSaveOptions options = new PsSaveOptions();
// Hozzon létre új PS-dokumentumot az oldal megnyitásával
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## 2. lépés: Mentse el a grafikai állapotot és a fordítást
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## 3. lépés: Hozzon létre négyzetet minden mintához
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## 4. lépés: Állítsa be a tollat a Pattern Square Outline-hoz
```java
BasicStroke stroke = new BasicStroke(2);
```
## 5. lépés: Ismétlés a sraffozási mintákon keresztül
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (folytatás a megadott kóddal)
}
```
## 6. lépés: Állítsa vissza a grafikus állapotot
```java
document.writeGraphicsRestore();
```
## 7. lépés: Töltse ki a szöveget sraffozási mintával
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## 8. lépés: Vázolja fel a szöveget sraffozási mintával
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## 9. lépés: Zárja be és mentse a dokumentumot
```java
document.closePage();
document.save();
```
Kövesse ezeket a lépéseket, és sikeresen hozzáadhat sraffozási mintákat a Java PostScript dokumentumhoz az Aspose.Page használatával.
## Következtetés
A vizuális elemek, például a sraffozási minták beépítése jelentősen növelheti Java-alkalmazásainak vonzerejét. Az Aspose.Page for Java zökkenőmentessé teszi ezt a folyamatot, lehetővé téve, hogy vizuálisan lenyűgöző PostScript dokumentumokat készítsen könnyedén.
## GYIK
### Használhatom az Aspose.Page for Java oldalt más Java keretrendszerekkel?
Igen, az Aspose.Page for Java zökkenőmentesen integrálható különféle Java-keretrendszerekkel.
### Elérhető próbaverzió az Aspose.Page for Java számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 Ideiglenes jogosítványt szerezhet[itt](https://purchase.aspose.com/temporary-license/).
### Hol találok további oktatóanyagokat és támogatást az Aspose.Page for Java számára?
 Fedezze fel a[Aspose.Page a Java fórumhoz](https://forum.aspose.com/c/page/39) oktatóanyagokért és közösségi támogatásért.
### Létezik átfogó dokumentációs forrás az Aspose.Page for Java számára?
 Igen, nézze meg a dokumentációt[itt](https://reference.aspose.com/page/java/).