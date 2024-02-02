---
title: Vízszintes színátmenet hozzáadása a Java PostScript-hez
linktitle: Vízszintes színátmenet hozzáadása a Java PostScript-hez
second_title: Aspose.Page Java API
description: Ismerje meg, hogyan adhat hozzá vízszintes színátmenetet a Java PostScript-ben az Aspose.Page for Java segítségével. Könnyedén készíthet lenyűgöző dokumentumokat.
type: docs
weight: 11
url: /hu/java/postscript-gradient-addition/horizontal/
---
## Bevezetés
Üdvözöljük ebben az átfogó oktatóanyagban, amely a Java PostScript vízszintes színátmenetek hozzáadására szolgál az Aspose.Page for Java segítségével. Az Aspose.Page egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PostScript- és más dokumentumformátumokkal dolgozzanak. Ebben az oktatóanyagban lépésről lépésre példák segítségével végigvezetjük Önt egy vízszintes színátmenettel rendelkező PostScript-dokumentum létrehozásának folyamatán.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java Development Kit (JDK) telepítve a gépére.
- Aspose.Page a Java könyvtárhoz. Letöltheti a[Aspose.Page Java dokumentáció](https://reference.aspose.com/page/java/).
## Csomagok importálása
Kezdje a szükséges csomagok importálásával a Java projektben. Ezek a csomagok kulcsfontosságúak az Aspose.Page használatához.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## 1. lépés: Hozzon létre egy téglalapot
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Kimeneti adatfolyam létrehozása PostScript-dokumentumhoz
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Hozzon létre mentési beállításokat A4-es méretben
PsSaveOptions options = new PsSaveOptions();
// Hozzon létre új PS-dokumentumot az oldal megnyitásával
PsDocument document = new PsDocument(outPsStream, options, false);
//Hozzon létre egy téglalapot
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## 2. lépés: Hozzon létre vízszintes lineáris színátmenetes festéket
```java
// Hozzon létre vízszintes lineáris gradiens festéket. A transzformáció skálaösszetevőinek meg kell egyeznie a téglalap szélességével és magasságával.
// A fordítási összetevők a téglalap eltolásai.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Állítsa be a festéket
document.setPaint(paint);
```
## 3. lépés: Töltse ki a téglalapot
```java
// Töltse ki a téglalapot
document.fill(rectangle);
```
## 4. lépés: Töltse ki a szöveget a színátmenettel
```java
// Töltse ki a szöveget a színátmenettel
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## 5. lépés: húzza át a szöveget a színátmenettel
```java
// Szöveg simítása a színátmenettel
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Következtetés
Gratulálunk! Sikeresen hozzáadott egy vízszintes színátmenetet a Java PostScript-ben az Aspose.Page for Java használatával. Ez az oktatóanyag egy részletes, lépésenkénti útmutatót tartalmaz, amely segít látványos PostScript-dokumentumok létrehozásában.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java-t kereskedelmi projektekben?
Igen, az Aspose.Page for Java használható kereskedelmi projektekben. Az engedélyezés részleteiért látogasson el a webhelyre[Aspose.Vásároljon](https://purchase.aspose.com/buy).
### Van ingyenes próbaverzió?
 Igen, hozzáférhet az Aspose.Page for Java ingyenes próbaverziójához[itt](https://releases.aspose.com/).
### Hol találok további dokumentumokat és támogatást?
 Meglátogatni a[Aspose.Page Java dokumentáció](https://reference.aspose.com/page/java/) átfogó forrásokért. Közösségi támogatásért tekintse meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39).
### Hogyan szerezhetek ideiglenes engedélyt?
 Ideiglenes jogosítványt szerezhet be[Aspose.Vásároljon](https://purchase.aspose.com/temporary-license/).
### Mik az Aspose.Page for Java rendszerkövetelményei?
 Utal[dokumentáció](https://reference.aspose.com/page/java/) részletes rendszerkövetelményekért.