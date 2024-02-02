---
title: Téglalap hozzáadása a Java XPS-ben
linktitle: Téglalap hozzáadása a Java XPS-ben
second_title: Aspose.Page Java API
description: Ismerje meg, hogyan adhat hozzá téglalapokat Java XPS-ben az Aspose.Page használatával. Kövesse lépésről lépésre útmutatónkat a zökkenőmentes dokumentumkezeléshez. #JavaXPS #AsposePage
type: docs
weight: 11
url: /hu/java/xps-shapes/add-rectangle/
---
## Bevezetés
Üdvözöljük ebben az átfogó útmutatóban a Java XPS-ben az Aspose.Page használatával téglalapok hozzáadásához! Akár tapasztalt fejlesztő, akár csak most kezdi a Java XPS-t, ez az oktatóanyag lépésről lépésre végigvezeti a folyamaton, így biztosítva a téma mélyreható megértését.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java programozási nyelv alapismerete.
-  Aspose.Page könyvtár telepítve. Ha nem, akkor letöltheti a[Aspose.Page Java dokumentáció](https://reference.aspose.com/page/java/).
- Működő Java fejlesztői környezet.
## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java projektbe. Győződjön meg arról, hogy az Aspose.Page könyvtár megfelelően van hozzáadva az osztályútvonalhoz. Íme egy alapvető példa:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Most bontsuk fel a példát több lépésre egy téglalap hozzáadásához a Java XPS-ben.
## 1. lépés: Állítsa be a dokumentumkönyvtárat
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
```
Cserélje ki a "Saját dokumentumkönyvtár" elemet a kívánt könyvtár elérési útjával.
## 2. lépés: Hozzon létre egy új XPS-dokumentumot
```java
// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
```
Ezzel inicializál egy új XPS-dokumentumot.
## 3. lépés: Adjon hozzá egy CMYK egyszínű körvonalas téglalapot
```java
// CMYK (kék) egyszínű, körvonalazott téglalap a bal alsó sarokban
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Ez a lépés egy körvonalozott téglalapot ad hozzá egyszínű CMYK színnel.
## 4. lépés: Mentse el az eredményül kapott XPS-dokumentumot
```java
// Mentse az eredményül kapott XPS-dokumentumot
doc.save(dataDir + "AddRectangle_out.xps");
```
Végül mentse el a módosított XPS-dokumentumot a hozzáadott téglalappal.
Ismételje meg ezeket a lépéseket, szükség szerint módosítva a paramétereket a téglalapok további testreszabásához.
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan adhat hozzá téglalapokat Java XPS-ben az Aspose.Page használatával. Ez az oktatóanyag szilárd alapot nyújt XPS-dokumentumkezelési törekvéseihez.
## GYIK
### Hozzáadhatok több téglalapot egyetlen XPS-dokumentumhoz?
Igen, tetszőleges számú téglalapot adhat hozzá az oktatóanyagban vázolt lépések megismétlésével.
### Hogyan tudom megváltoztatni a téglalap színét?
 Módosítsa a színértékeket a`createColor` módszer a kívánt szín elérésére.
### Az Aspose.Page alkalmas összetett XPS-dokumentummanipulációk kezelésére?
Teljesen! Az Aspose.Page robusztus szolgáltatáskészletet biztosít a különféle XPS-dokumentumfeladatok kezeléséhez.
### Hol találhatok további példákat és támogatást?
 Fedezze fel a[Aspose.Page fórum](https://forum.aspose.com/c/page/39)további példákért, és kérjen segítséget a közösségtől.
### Kipróbálhatom az Aspose.Page-t vásárlás előtt?
 Igen, felfedezheti a[ingyenes próbaverzió](https://releases.aspose.com/) hogy megtapasztalják az Aspose képességeit.Page.