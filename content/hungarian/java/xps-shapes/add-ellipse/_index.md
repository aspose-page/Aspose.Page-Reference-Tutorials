---
title: Adjon hozzá Radial Gradient Ellipse-t az Aspose.Page segítségével
linktitle: Adja hozzá az Ellipse-t a Java XPS-hez
second_title: Aspose.Page Java API
description: Tekintse meg a sugárirányú színátmenettel körvonalazott ellipszis hozzáadását a Java XPS-ben az Aspose.Page for Java segítségével, lépésről lépésre ismertető útmutatót. Fokozza a dokumentumkészítést könnyedén.
type: docs
weight: 10
url: /hu/java/xps-shapes/add-ellipse/
---
## Bevezetés
Üdvözöljük a Java XPS-ben ellipszis hozzáadásának lépésenkénti útmutatójában az Aspose.Page for Java használatával. Az Aspose.Page egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy könnyedén dolgozzanak XPS-dokumentumokkal. Ebben az oktatóanyagban végigvezetjük a radiális színátmenettel körvonalazott ellipszis létrehozásának és XPS-dokumentumként való mentésének folyamatán.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java Development Kit (JDK) telepítve a gépére.
-  Aspose.Page a Java könyvtárhoz letöltve. Megkaphatod[itt](https://releases.aspose.com/page/java/).
- Egy Ön által választott kódszerkesztő (Eclipse, IntelliJ stb.) Java kód írásához és végrehajtásához.
## Csomagok importálása
Győződjön meg arról, hogy a Java-projektbe importálta a szükséges csomagokat az Aspose.Page használatához. Adja hozzá a következő importálási utasításokat a Java-fájl tetejéhez:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## 1. lépés: Állítsa be a dokumentumkönyvtárat
Határozza meg a dokumentumkönyvtár elérési útját, ahová az XPS-dokumentum mentésre kerül:
```java
String dataDir = "Your Document Directory";
```
## 2. lépés: Hozzon létre XPS-dokumentumot
Inicializáljon egy új XPS-dokumentumot a következő kóddal:
```java
XpsDocument doc = new XpsDocument();
```
## 3. lépés: Adja meg a sugárirányú gradiens megállókat
Hozzon létre egy listát a gradiens megállóiról a radiális színátmenettel körvonalazott ellipszishez:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## 4. lépés: Út-geometria létrehozása
Határozzon meg egy radiális gradiens körvonalú ellipszist az útvonalgeometria segítségével:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## 5. lépés: Vászon és útvonal hozzáadása
Adjon hozzá egy új vásznat a dokumentumhoz, és fűzze hozzá az elérési utat a meghatározott geometriával:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## 6. lépés: Állítsa be az ütést és a színátmenetet
Konfigurálja az útvonal körvonalát radiális gradiens ecsettel:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## 7. lépés: Állítsa be az ütési vastagságot
Adja meg az útvonal löketvastagságát:
```java
path.setStrokeThickness(12f);
```
## 8. lépés: Mentse el a dokumentumot
Mentse el az eredményül kapott XPS-dokumentumot:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Gratulálunk! Sikeresen hozzáadott egy radiális színátmenetes körvonalas ellipszist a Java XPS-ben az Aspose.Page for Java használatával.
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan hozhat létre XPS-dokumentumot egy vizuálisan tetszetős, radiális színátmenettel húzott ellipszissel. Az Aspose.Page for Java leegyszerűsíti az XPS-dokumentumkezelést, és hatékony eszközkészletet biztosít a fejlesztőknek.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java oldalt más Java könyvtárakkal?
Igen, az Aspose.Page for Java zökkenőmentesen integrálható más Java könyvtárakkal.
### Az Aspose.Page alkalmas nagyméretű dokumentumfeldolgozásra?
Teljesen! Az Aspose.Page úgy lett kialakítva, hogy hatékonyan kezelje a nagyméretű dokumentumfeldolgozást.
### Hol találok további oktatóanyagokat és példákat az Aspose.Page for Java számára?
 Meglátogatni a[Aspose.Page a Java dokumentációhoz](https://reference.aspose.com/page/java/)átfogó oktatóanyagokért és példákért.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Vannak közösségi fórumok az Aspose.Page beszélgetésekhez?
 Igen, csatlakozz a[Aspose.Page közösségi fórum](https://forum.aspose.com/c/page/39) kapcsolatba léphet más fejlesztőkkel és segítséget kérhet.