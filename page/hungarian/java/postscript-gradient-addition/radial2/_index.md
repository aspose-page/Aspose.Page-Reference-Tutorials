---
title: Java PostScript Radial Gradient az Aspose.Page-vel
linktitle: Java PostScript Radial Gradient az Aspose.Page-vel
second_title: Aspose.Page Java API
description: Tekintse meg a lépésenkénti útmutatót a Radial Gradient hozzáadásához a Java PostScriptben az Aspose.Page használatával, hogy lenyűgöző grafikákat készítsen Java-alkalmazásaiban.
weight: 13
url: /hu/java/postscript-gradient-addition/radial2/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript Radial Gradient az Aspose.Page-vel

## Bevezetés
Üdvözöljük lépésenkénti útmutatónkban a Radial Gradient 2 hozzáadásával kapcsolatban a Java PostScriptben az Aspose.Page for Java használatával. Ez az oktatóanyag végigvezeti Önt egy gyönyörű sugárirányú színátmenettel rendelkező PostScript-dokumentum létrehozásának folyamatán, amely a Java-alkalmazásokat tetszetős grafikával bővíti.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java programozási ismeretek.
- Java Development Kit (JDK) telepítése a gépen.
-  Aspose.Page a Java könyvtárhoz, amelyet letölthet a[Aspose.Page Java dokumentáció](https://reference.aspose.com/page/java/).
## Csomagok importálása
Java-projektjében importálja az Aspose.Page szükséges csomagjait:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 1. lépés: Állítsa be a dokumentumkönyvtárat
Határozza meg a dokumentumkönyvtár elérési útját:
```java
String dataDir = "Your Document Directory";
```
## 2. lépés: Hozzon létre kimeneti adatfolyamot
Hozzon létre egy kimeneti adatfolyamot a PostScript dokumentumhoz:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## 3. lépés: Hozzon létre mentési beállításokat
Hozzon létre mentési beállításokat A4-es méretben:
```java
PsSaveOptions options = new PsSaveOptions();
```
## 4. lépés: Hozzon létre PS-dokumentumot
Hozzon létre egy új PS-dokumentumot a megnyitott oldallal:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 5. lépés: Hozzon létre egy kört
Határozzon meg egy kört az Ellipse2D.Float osztály segítségével:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## 6. lépés: Határozza meg a színátmenet színeit
Hozzon létre szín- és törttömböket a radiális gradienshez:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## 7. lépés: Az AffineTransform létrehozása
Hozzon létre egy AffineTransformot a radiális gradienshez:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## 8. lépés: Hozzon létre Radial Gradient Paint
Hozzon létre egy RadialGradientPaint-et a megadott paraméterekkel:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## 9. lépés: Állítsa be a festék és a kitöltő kört
Állítsa be a festéket, és töltse ki a kört radiális gradienssel:
```java
document.setPaint(paint);
document.fill(circle);
```
## 10. lépés: Zárja be az oldalt és mentse a dokumentumot
Az aktuális oldal bezárása és a dokumentum mentése:
```java
document.closePage();
document.save();
```
Gratulálunk! Sikeresen hozzáadta a Radial Gradient 2-t a Java PostScript-hez az Aspose.Page for Java segítségével.
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan javíthatja a Java-alkalmazásokat a PostScript-dokumentumok radiális színátmeneteivel. Az Aspose.Page for Java hatékony eszközkészletet kínál lenyűgöző grafikák létrehozásához, lehetővé téve, hogy Java-projektjeit a következő szintre emelje.
## GYIK
### K: Hol találom az Aspose.Page for Java dokumentációját?
 V: A dokumentáció elérhető[itt](https://reference.aspose.com/page/java/).
### K: Hogyan tölthetem le az Aspose.Page-t Java számára?
 V: Letöltheti a[kiadások oldala](https://releases.aspose.com/page/java/).
### K: Van ingyenes próbaverzió?
 V: Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### K: Kaphatok ideiglenes licencet az Aspose.Page for Java számára?
 V: Igen, beszerezhet ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol kérhetek közösségi támogatást, és hol vehetek részt vitákban?
 V: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
