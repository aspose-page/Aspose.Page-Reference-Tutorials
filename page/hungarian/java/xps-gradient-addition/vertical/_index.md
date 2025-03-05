---
title: Függőleges színátmenet hozzáadása a Java XPS-ben
linktitle: Függőleges színátmenet hozzáadása a Java XPS-ben
second_title: Aspose.Page Java API
description: Ismerje meg, hogyan adhat hozzá függőleges színátmenetet Java XPS-dokumentumokhoz az Aspose.Page segítségével. Fokozza a vizuális vonzerőt erőfeszítés nélkül. Lépésről lépésre útmutató belül.
type: docs
weight: 12
url: /hu/java/xps-gradient-addition/vertical/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan adhat hozzá függőleges színátmenetet a Java XPS-hez az Aspose.Page for Java segítségével. Színátmenetek hozzáadása az XPS-dokumentumokhoz javíthatja a tartalom vizuális vonzerejét, vonzóbbá és esztétikusabbá téve azt.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Működő Java fejlesztői környezet.
-  Aspose.Page a Java könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/page/java/).
- Alapvető ismeretek a Java programozásról.
## Csomagok importálása
Kezdje a Java-projekthez szükséges csomagok importálásával. Győződjön meg arról, hogy az Aspose.Page for Java könyvtárat felvette a projektfüggőségek közé.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
        
// Importálja az Aspose.Page-t Java-hoz
```
## 1. lépés: Inicializálja a dokumentumot
Kezdje az XPS-dokumentum inicializálásával. Ez megteremti az alapot az olyan elemek hozzáadásához a dokumentumhoz, mint az útvonalak és színátmenetek.
```java
// Dokumentum inicializálása
XpsDocument doc = new XpsDocument();
```
## 2. lépés: Hozzon létre egy útvonalat függőleges színátmenettel
Most hozzunk létre egy útvonalat függőleges gradienssel. Ez magában foglalja az útvonal geometriájának meghatározását és a gradiens megállók megadását.
```java
// Hozzon létre egy útvonalat geometriával
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Függőleges gradiens megállók meghatározása
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Alkalmazza a függőleges gradienst az útvonalra
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## 3. lépés: Mentse el a dokumentumot
Végül mentse el az XPS-dokumentumot a hozzáadott függőleges színátmenettel a kívánt könyvtárba.
```java
// Mentse el a dokumentumot
doc.save(dataDir + "VerticalGradient.xps");
```
Gratulálunk! Sikeresen hozzáadott egy függőleges színátmenetet a Java XPS dokumentumhoz az Aspose.Page segítségével.
## Következtetés
Az XPS-dokumentumok színátmenetekkel történő javítása jelentősen javíthatja vizuális vonzerejüket. Az Aspose.Page for Java leegyszerűsíti ezt a folyamatot, és lehetővé teszi a lenyűgöző dokumentumok könnyű létrehozását.

### GYIK
### Használhatom az Aspose.Page for Java-t kereskedelmi projektekben?
 Igen, az Aspose.Page for Java kereskedelmi használatra elérhető. Megvásárolhatod[itt](https://purchase.aspose.com/buy).
### Létezik ingyenes próbaverzió az Aspose.Page for Java számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Page for Java dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/page/java/).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 Szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Segítségre van szüksége vagy kérdései vannak?
 Látogassa meg az Aspose.Page közösséget[fórum](https://forum.aspose.com/c/page/39).