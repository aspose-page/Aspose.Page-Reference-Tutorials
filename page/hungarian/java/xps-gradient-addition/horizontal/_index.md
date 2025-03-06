---
title: Vízszintes színátmenet hozzáadása a Java XPS-hez
linktitle: Vízszintes színátmenet hozzáadása a Java XPS-hez
second_title: Aspose.Page Java API
description: Ismerje meg, hogyan adhat lenyűgöző vízszintes színátmenetet XPS-dokumentumokhoz Java nyelven az Aspose.Page használatával. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
weight: 11
url: /hu/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vízszintes színátmenet hozzáadása a Java XPS-hez

## Bevezetés
Üdvözöljük ebben a lépésről-lépésre szóló útmutatóban, amely a Java XPS-ben vízszintes színátmenet hozzáadására vonatkozik az Aspose.Page for Java használatával. Az Aspose.Page for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak XPS (XML Paper Specification) dokumentumokkal.
Ebben az oktatóanyagban végigvezetjük egy Java-alkalmazás létrehozásának folyamatán, amellyel vízszintes színátmenetet adhatunk XPS-dokumentumhoz. Kövesse az alábbi lépéseket, hogy ezt könnyedén elérhesse.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1. Java fejlesztői környezet: Győződjön meg arról, hogy a Java telepítve van a rendszeren. Ha nem, töltse le és telepítse a Java legújabb verzióját innen[java.com](https://www.java.com).
2.  Aspose.Page for Java Library: rendelkeznie kell az Aspose.Page for Java könyvtárral. Letöltheti a[Aspose.Page a Java dokumentációhoz](https://reference.aspose.com/page/java/).
## Csomagok importálása
Kezdje a Java-alkalmazáshoz szükséges csomagok importálásával. Szerelje be az Aspose.Page for Java könyvtárat a projektbe. Ezt a következő kódsorok hozzáadásával teheti meg:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## 1. lépés: Inicializálja a dokumentumot
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
//Dokumentum inicializálása
XpsDocument doc = new XpsDocument();
```
## 2. lépés: Hozzon létre vízszintes színátmenetet
```java
// Vízszintes gradiens
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## 3. lépés: Útvonal hozzáadása színátmenettel
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## 4. lépés: Mentse el a dokumentumot
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Ismételje meg ezeket a lépéseket szükség szerint, és állítsa be a paramétereket az Ön egyedi igényei szerint.
## Következtetés
Gratulálunk! Sikeresen hozzáadott egy vízszintes színátmenetet egy XPS-dokumentumhoz az Aspose.Page for Java használatával. Ez az oktatóanyag átfogó útmutatót nyújtott azoknak a fejlesztőknek, akik Java-alkalmazásaikat gradiens effektusokkal szeretnék továbbfejleszteni.
## GYIK
### K: Alkalmazhatok több színátmenetet egyetlen XPS-dokumentumban?
Igen, összetett tervek létrehozásához több útvonalat is hozzáadhat különböző színátmenetekkel.
### K: Az Aspose.Page kompatibilis a legújabb Java verziókkal?
Az Aspose.Page for Java webhelyet rendszeresen frissítik, hogy biztosítsák a kompatibilitást a legújabb Java-kiadásokkal.
### K: Vannak más színátmenet-típusok az Aspose.Page oldalon?
Igen, a lineáris színátmenetek mellett az Aspose.Page támogatja a radiális színátmeneteket is a változatosabb hatások érdekében.
### K: Testreszabhatom a színátmenet megállók színét és helyzetét?
Teljesen! Az egyes színátmeneti megállók színeit és pozícióit teljes mértékben Ön irányíthatja.
### K: Létezik olyan közösségi fórum az Aspose.Page számára, ahol segítséget kérhetek?
 Igen, meglátogathatja a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) kapcsolatba lépni a közösséggel és segítséget kapni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
