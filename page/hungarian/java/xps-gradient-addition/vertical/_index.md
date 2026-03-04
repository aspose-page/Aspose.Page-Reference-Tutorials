---
date: 2025-12-25
description: Tanulja meg, hogyan adhat hozzá függőleges gradientet a Java XPS-ben
  az Aspose.Page használatával. Kövesse ezt a lépésről‑lépésre útmutatót, hogy növelje
  dokumentuma vizuális vonzerejét.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Hogyan adjon hozzá függőleges színátmenetet a Java XPS-ben
url: /hu/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adhatunk hozzá függőleges színátmenetet Java XPS-ben

## Bevezetés
Ebben az útmutatóban megtanulja, **hogyan adjon hozzá függőleges színátmenetet** XPS dokumentumokhoz Java használatával. A függőleges színátmenet drámaian javíthatja jelentései, számlái vagy bármely nyomtatható tartalma vizuális hatását. Lépésről lépésre végigvezetjük a projekt beállításától a végleges XPS fájl mentéséig, az erőteljes Aspose.Page for Java könyvtár segítségével.

## Gyors válaszok
- **Mit csinál a függőleges színátmenet?** Egyenletes színátmenetet hoz létre a forma tetejétől az aljáig.  
- **Melyik könyvtár szükséges?** Aspose.Page for Java (letölthető a hivatalos oldalról).  
- **Szükség van licencre?** Fejlesztéshez egy ingyenes próba verzió elegendő; termeléshez kereskedelmi licenc szükséges.  
- **Kompatibilis-e a Java 8+ verziókkal?** Igen, az API támogatja a Java 8 és újabb verziókat.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 perc alatt, ha a környezet már be van állítva.

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg róla, hogy a következőkkel rendelkezik:

- Működő Java fejlesztői környezet (JDK 8 vagy újabb).  
- Aspose.Page for Java könyvtár. Letöltheti [innen](https://releases.aspose.com/page/java/).  
- Alapvető Java programozási ismeretek.  

## Csomagok importálása
Kezdje a szükséges csomagok importálásával Java projektjéhez. Győön meg arról, hogy az Aspose.Page for Java könyvtár hozzá van adva a projekt osztályútvonalához.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## 1. lépés: A dokumentum inicializálása
Hozzon létre egy új XPS dokumentumot. Ez az objektum fogja tartalmazni a később hozzáadott rajzelemeket.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## 2. lépés: Útvonal létrehozása függőleges színátmenettel
Ezután definiáljon egy téglalap alakú útvonalat, és alkalmazzon rá függőleges lineáris színátmenetet. A színátmenet‑állomások határozzák meg a színeket és azok pozícióját a függőleges tengelyen.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## 3. lépés: A dokumentum mentése
Végül írja ki az XPS fájlt a lemezre. A keletkezett fájl tartalmazni fogja a függőleges színátmenettel kitöltött téglalapot.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Gratulálunk! Sikeresen megtanulta, **hogyan adjon hozzá függőleges színátmenetet** egy Java XPS dokumentumhoz az Aspose.Page segítségével.

## Miért használjunk függőleges színátmenetet?
- **Javított esztétika:** A színátmenetek mélységet és modern megjelenést kölcsönöznek a statikus alakzatoknak.  
- **Márka konzisztencia:** Zökkenőmentesen illessze a vállalati színeket az oldalakra.  
- **Könnyű testreszabás:** Színek vagy állomás‑pozíciók módosítása anélkül, hogy a grafikát újra kellene tervezni.

## Gyakori problémák és hibaelhárítás
- **A színátmenet nem látható:** Ellenőrizze, hogy a `LinearGradientBrush` kezdő‑ és végpontjai helyesen vannak beállítva függőleges tájolásra.  
- **A fájl nem mentődik:** Győződjön meg arról, hogy a `dataDir` egy írható mappára mutat, és rendelkezik a fájlírási jogosultságokkal.  
- **A könyvtár nem található:** Ellenőrizze, hogy az Aspose.Page JAR fájl szerepel-e a projekt build útvonalában.

## Gyakran feltett kérdések

**K: Használhatom az Aspose.Page for Java‑t kereskedelmi projektekben?**  
V: Igen, az Aspose.Page for Java kereskedelmi felhasználásra is elérhető. Megvásárolhatja [itt](https://purchase.aspose.com/buy).

**K: Van ingyenes próba verzió az Aspose.Page for Java‑hoz?**  
V: Igen, ingyenes próbát érhet el [itt](https://releases.aspose.com/).

**K: Hol találom az Aspose.Page for Java dokumentációját?**  
V: A dokumentáció elérhető [itt](https://reference.aspose.com/page/java/).

**K: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java‑hoz?**  
V: Ideiglenes licencet kaphat [itt](https://purchase.aspose.com/temporary-license/).

**K: Segítségre van szükségem vagy kérdésem van?**  
V: Látogasson el az Aspose.Page közösségi [fórumra](https://forum.aspose.com/c/page/39).

---

**Utolsó frissítés:** 2025-12-25  
**Tesztelt verzió:** Aspose.Page for Java 24.12 (a cikk írásakor legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}