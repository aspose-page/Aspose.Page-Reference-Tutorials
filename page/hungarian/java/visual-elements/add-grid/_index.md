---
date: 2025-12-18
description: Ismerje meg, hogyan adhat hozzá rácsot és átlátszó téglalapot Java XPS
  dokumentumokhoz az Aspose.Page segítségével. Lépésről lépésre útmutató az XPS dokumentum
  hatékony mentéséhez.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Hogyan adjon hozzá rácsot a Visual Brush használatával Java-ban
url: /hu/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá rácsot Visual Brush segítségével Java-ban

## Bevezetés
Ha **hogyan adjunk hozzá rácsot** elemeket a Java‑ban generált XPS dokumentumokhoz, jó helyen jársz. Ebben az útmutatóban végigvezetünk egy rács hozzáadásán Visual Brush‑szal, egy átlátszó téglalap rétegezésén, és végül a **XPS dokumentum mentésén** az Aspose.Page Java API használatával. A végére egy kifinomult vizuális elemet kapsz, amely újra felhasználható jelentésekben, számlákban vagy bármely dokumentum‑intenzív alkalmazásban.

## Gyors válaszok
- **Mit csinál a Visual Brush?** Egy meghatározott területet fest újrahasználható vizuális tartalommal, ami tökéletes ismétlődő mintákhoz, például rácsokhoz.  
- **Megváltoztathatom a rács színét?** Igen – módosítsd a brush szilárd‑szín beállításait.  
- **Hogyan adok hozzá egy átlátszó téglalapot a rács tetejére?** Használd a `setOpacity` metódust egy szilárd színnel kitöltött útvonalon.  
- **Melyik metódus menti a fájlt?** A `doc.save(...)` írja ki az XPS fájlt a lemezre.  
- **Szükség van licencre?** Ideiglenes vagy teljes licenc szükséges a termelési környezetben.

## Mi az a Visual Brush rács?
A Visual Brush lehetővé teszi, hogy egy kis vizuális elemet (a rácsmintát) definiálj, majd azt csempézd egy nagyobb területre. Ez a megközelítés memóriahatékonyabb, mint minden vonal külön-külön rajzolása, és pixel‑pontos ismétlődést biztosít.

## Miért használjuk az Aspose.Page‑t ehhez a feladathoz?
- **Cross‑platform** – Bármely, Java‑t támogató operációs rendszeren működik.  
- **Magas hűségű renderelés** – Precíz szín-, átlátszóság‑ és csempézés‑vezérlés.  
- **Nincs külső függőség** – Minden az Aspose.Page könyvtáron keresztül kezelhető.

## Előfeltételek
Mielőtt belevágnál, ellenőrizd, hogy a következők rendelkezésre állnak:

- Alapvető Java programozási ismeretek.  
- Telepített Aspose.Page könyvtár – letöltheted a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalról.  
- JDK 8 vagy újabb a fejlesztői gépeden.

## Csomagok importálása
Először importáld a szükséges osztályokat, hogy a fordító tudja, honnan vegye a használandó típusokat:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Lépés‑ről‑lépésre útmutató

### 1. lépés: Projekt beállítása
Hozz létre egy új `XpsDocument` példányt, és add meg azt a mappát, ahová a kimeneti fájlt menteni szeretnéd.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### 2. lépés: Magenta rács Visual Brush létrehozása
Definiálunk egy kis magenta alakzatot, amely a rácsterületre lesz csempészve.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### 3. lépés: Geometria definiálása a rács brush‑hoz
Állítsd be a téglalap alakú területet, amely a csempézett vizuális elemet fogja kapni.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### 4. lépés: Új vászon (Canvas) létrehozása a dokumentumhoz
Adj egy vásznát a dokumentumhoz, és helyezd el ott, ahol a rács megjelenik.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### 5. lépés: Rács hozzáadása a vászonhoz
Alkalmazd a visual brush‑t a geometriára, ezzel engedélyezve a csempézést.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### 6. lépés: Átlátszó piros téglalap hozzáadása (másodlagos funkció)
Itt bemutatjuk, hogyan **adjunk hozzá átlátszó téglalapot** a rács tetejére a hangsúlyozáshoz.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### 7. lépés: Az eredmény XPS dokumentum mentése
Végül írd ki a dokumentumot a lemezre – ez a **save XPS document** lépés.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Kövesd ezeket a lépéseket, és egy professzionális megjelenésű rácsot kapsz átlátszó átfedéssel, mindezt programozottan generálva.

## Gyakori problémák és tippek

- **Helytelen csempe méret:** Győződj meg róla, hogy a brush‑hoz használt `Rectangle2D` megegyezik a kívánt ismétlési mérettel; ellenkező esetben a minta nyúlhat.  
- **Az átlátszóság nem alkalmazódik:** Ne felejtsd el meghívni a `setOpacity` metódust azon az úton, amelyet átlátszóvá szeretnél tenni; ez nem érinti magát a brush‑t.  
- **A fájl nem mentődik:** Ellenőrizd, hogy a `dataDir` egy létező mappára mutat, és hogy az alkalmazásnak van írási joga.

## Gyakran ismételt kérdések

**Q: Az Aspose.Page alkalmas professzionális dokumentumgenerálásra?**  
A: Igen, az Aspose.Page egy robusztus könyvtár, amely magas minőségű XPS és PDF generálást biztosít Java‑ban.

**Q: Testreszabhatom a rács színeit Visual Brush‑szal?**  
A: Természetesen! Módosítsd a `createColor` paramétereit a brush `setFill` hívásában a kívánt RGBA értékekre.

**Q: Hol találok további támogatást az Aspose.Page‑hez?**  
A: Látogasd meg a [Aspose.Page forum](https://forum.aspose.com/c/page/39) közösségi segítségért és hivatalos válaszokért.

**Q: Van ingyenes próbaverziója az Aspose.Page‑nek?**  
A: Igen, a [free trial](https://releases.aspose.com/) segítségével felfedezheted az összes funkciót vásárlás előtt.

**Q: Hogyan szerezhetek ideiglenes licencet teszteléshez?**  
A: Szerezd be az [ideiglenes licencet](https://purchase.aspose.com/temporary-license/), amely fejlesztéshez és értékeléshez használható.

---

**Utoljára frissítve:** 2025-12-18  
**Tesztelt verzió:** Aspose.Page for Java 23.12 (legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}