---
title: Adjon hozzá csempézett képet a Java XPS-ben
linktitle: Adjon hozzá csempézett képet a Java XPS-ben
second_title: Aspose.Page Java API
description: Fedezze fel a zökkenőmentes Java XPS dokumentumkezelést az Aspose.Page segítségével. Ennek a lépésről-lépésre szóló útmutatónak a segítségével megtanulhatja, hogyan adhat hozzá mozaikszerű képeket.
type: docs
weight: 11
url: /hu/java/xps-image-manipulation/add-tiled-image/
---
## Bevezetés
Java fejlesztés dinamikus világában egyre növekszik a hatékony dokumentumkezelés és -készítés iránti igény. Az Aspose.Page for Java hatékony eszközként jelenik meg, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak XPS-dokumentumokkal. Ez az oktatóanyag egy konkrét feladatra összpontosít – mozaikkép hozzáadása Java XPS dokumentumhoz.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Page for Java: Töltse le és telepítse az Aspose.Page for Java oldalt a[weboldal](https://releases.aspose.com/page/java/).
3. Saját dokumentumkönyvtár: Válasszon vagy hozzon létre egy könyvtárat, ahová menteni szeretné XPS-dokumentumát.
## Csomagok importálása
Java projektjében importálja a szükséges csomagokat az Aspose.Page funkciók használatához:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Most bontsuk le a mozaikkép Java XPS-dokumentumhoz való hozzáadásának folyamatát világos, kezelhető lépésekre.
## 1. lépés: Állítsa be projektjét
Kezdje a Java projekt beállításával, és győződjön meg arról, hogy az Aspose.Page for Java megfelelően integrálva van.
## 2. lépés: Hozzon létre XPS-dokumentumot
Inicializáljon egy új XPS-dokumentumot a következő kóddal:
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
```
## 3. lépés: Adja meg a csempézett kép elérési útját
Adja meg az XPS-dokumentumhoz hozzáadni kívánt csempézett kép elérési útját.
## 4. lépés: Adjon hozzá csempézett képet
Használja az alábbi kódrészletet egy csempézett kép hozzáadásához az XPS-dokumentumhoz:
```java
// Csempe kép
// ImageBrush kitöltött téglalap a jobb felső sarokban lent
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## 5. lépés: Mentse el a dokumentumot
Végül mentse az eredményül kapott XPS-dokumentumot az alábbi kóddal:
```java
// Mentse az eredményül kapott XPS-dokumentumot
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Ismételje meg ezeket a lépéseket, hogy az Aspose.Page segítségével könnyedén beépítsen egy mozaikképet a Java XPS dokumentumba.
## Következtetés
Az Aspose.Page for Java leegyszerűsíti az XPS-dokumentumok kezelésének folyamatát, és hatékony megoldást kínál a fejlesztőknek a dokumentumkezeléshez. Ennek a lépésről-lépésre szóló útmutatónak a követésével könnyedén hozzáadhat mozaikképet a Java XPS dokumentumhoz.

## GYIK
### Az Aspose.Page kompatibilis az összes Java-verzióval?
 Az Aspose.Page különféle Java-verziókkal való együttműködésre készült. Győződjön meg a kompatibilitásról a dokumentáció ellenőrzésével[itt](https://reference.aspose.com/page/java/).
### Használhatom az Aspose.Page-t kereskedelmi projektekhez?
Igen, az Aspose.Page kereskedelmi licenceket kínál. Vásárolja meg őket[itt](https://purchase.aspose.com/buy).
### Van ingyenes próbaverzió?
 Igen, fedezze fel az Aspose.Page funkcióit egy ingyenes próbaverzióval[itt](https://releases.aspose.com/).
### Hol találok közösségi támogatást és beszélgetéseket?
 Vegyen részt az Aspose.Page közösséggel a webhelyen[fórum](https://forum.aspose.com/c/page/39).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Page számára?
 Szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).