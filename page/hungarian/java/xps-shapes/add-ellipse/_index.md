---
date: 2026-04-24
description: Tanulja meg, hogyan hozhat létre XPS dokumentumot Java‑ban radiális gradient
  ellipszissel. Ez a lépésről‑lépésre útmutató bemutatja, hogyan állíthatja be a vonalvastagságot
  és definiálhatja az útvonalgeometriát az Aspose.Page használatával.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Ellipszis hozzáadása Java XPS‑ben
second_title: Aspose.Page Java API
title: XPS-dokumentum létrehozása Java-ban – Radiális gradient ellipszis hozzáadása
url: /hu/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radial Gradient Ellipse hozzáadása az Aspose.Page segítségével

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **create XPS document Java** egy gyönyörű, radiális gradienttel körvonalazott ellipszist használva az Aspose.Page for Java segítségével. Az Aspose.Page egy robusztus könyvtár, amely elrejti az alacsony szintű XPS részleteket, lehetővé téve, hogy a tervezésre koncentráljon a fájlformátum bonyolultsága helyett. A útmutató végére egy kész XPS fájlt kap, amelyet beágyazhat jelentésekbe, számlákba vagy bármilyen dokumentum‑generálási munkafolyamatba.

## Gyors válaszok
- **Mi a kimenete ennek a kódnak?** Egy egyoldalas XPS fájl, amely egy több színű radiális gradienttel körvonalazott ellipszist tartalmaz.  
- **Melyik elsődleges API-t használja?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, stb.).  
- **Szükségem van licencre a minta futtatásához?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc a termeléshez kötelező.  
- **Melyek a beállított kulcsfontosságú tulajdonságok?** Körvonal ecset (radiális gradient), spread method, gradient stopok és körvonal vastagság.  
- **Módosíthatom az ellipszis méretét?** Igen – módosítsa az útvonal geometria karakterláncát vagy a gradient ecset koordinátáit.

## Mi az a “create XPS document Java”?
Az XPS dokumentum Java‑ban történő létrehozása azt jelenti, hogy programozottan generálunk egy XML Paper Specification (XPS) fájlt – egy rögzített elrendezésű dokumentumformátumot, amely a PDF‑hez hasonló – közvetlenül Java kódból. Az Aspose.Page egy magas szintű objektummodellt (`XpsDocument`, `XpsCanvas`, stb.) biztosít, amely elrejti az XML markup‑ot, így a folyamat olyan egyszerű, mint a szokásos Java objektumok kezelése.

## Miért használjunk radiális gradient ellipszist?
A radiális gradient háromdimenziós hatást kölcsönöz, tökéletes vizuális kiemelésekhez, logókhoz vagy díszítő elemekhez a jelentésekben. A szilárd színű körvonalhoz képest a gradient mélységet ad anélkül, hogy jelentősen növelné a fájlméretet, és az XPS formátum megőrzi a vektor minőséget bármilyen méretezésnél.

## Előfeltételek
- Java Development Kit (JDK) telepítve a gépén.  
- Aspose.Page for Java könyvtár letöltve. Letöltheti [itt](https://releases.aspose.com/page/java/).  
- A választott kódszerkesztő (Eclipse, IntelliJ, stb.) a Java kód írásához és futtatásához.

## Csomagok importálása
Győződjön meg róla, hogy a szükséges csomagok importálva vannak a Java projektjében az Aspose.Page használatához. Adja hozzá a következő import nyilatkozatokat a Java fájl tetejéhez:

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

## 1. lépés: Dokumentum könyvtár beállítása
Határozza meg az útvonalat a dokumentum könyvtárához, ahol az XPS dokumentum mentésre kerül:

```java
String dataDir = "Your Document Directory";
```

## 2. lépés: XPS dokumentum létrehozása
Inicializáljon egy új XPS dokumentumot a következő kóddal:

```java
XpsDocument doc = new XpsDocument();
```

## 3. lépés: Radiális gradient stopok meghatározása
Hozzon létre egy listát a gradient stopokból a radiális gradienttel körvonalazott ellipszishoz:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## 4. lépés: Útvonal geometria létrehozása
Definiáljon egy radiális gradienttel körvonalazott ellipszist útvonal geometria segítségével:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## 5. lépés: Vászon és útvonal hozzáadása
Adjon hozzá egy új vászont a dokumentumhoz, és fűzze hozzá az útvonalat a meghatározott geometriával:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## 6. lépés: Körvonal és gradient beállítása
Konfigurálja az útvonal körvonalát egy radiális gradient ecsettel:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## 7. lépés: Körvonal vastagságának beállítása
Adja meg a **set stroke thickness** értékét az útvonalhoz:

```java
path.setStrokeThickness(12f);
```

## 8. lépés: Dokumentum mentése
Mentse el a létrehozott XPS dokumentumot:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Gratulálunk! Sikeresen hozzáadott egy radiális gradienttel körvonalazott ellipszist, miközben **create XPS document Java**-t készített az Aspose.Page segítségével.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Ellipszis laposnak tűnik** | Az `XpsSpreadMethod.Pad` használata a `Reflect` helyett | Módosítsa a spread metódust `XpsSpreadMethod.Reflect`-re, ahogy a 6. lépésben látható. |
| **Nincs kimeneti fájl** | `dataDir` egy nem létező mappára mutat | Győződjön meg róla, hogy a könyvtár létezik, vagy használjon abszolút elérési utat. |
| **A gradient színek hibásak** | A gradient stopok helytelen sorrendje | Ellenőrizze, hogy az `offset` értékek (0 → 1) monoton növekednek. |
| **Fordítási hibák** | Az Aspose.Page JAR fájlok hiányoznak az osztályúton | Adja hozzá az `aspose-page-xx.jar`-t a projekt függőségeihez. |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Page for Java-t más Java könyvtárakkal?**  
A: Igen, az Aspose.Page for Java zökkenőmentesen integrálható más Java könyvtárakkal.

**Q: Az Aspose.Page alkalmas nagy‑léptékű dokumentumfeldolgozásra?**  
A: Teljes mértékben! Az Aspose.Page-et úgy tervezték, hogy hatékonyan kezelje a nagy‑léptékű dokumentumfeldolgozást.

**Q: Hol találok további útmutatókat és példákat az Aspose.Page for Java-hoz?**  
A: Látogasson el az [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalra, ahol átfogó útmutatókat és példákat talál.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Ideiglenes licencet kaphat [itt](https://purchase.aspose.com/temporary-license/).

**Q: Vannak közösségi fórumok az Aspose.Page megbeszélésekhez?**  
A: Igen, csatlakozzon az [Aspose.Page community forum](https://forum.aspose.com/c/page/39) közösséghez, hogy más fejlesztőkkel beszélgessen és segítséget kapjon.

---

**Utoljára frissítve:** 2026-04-24  
**Tesztelve:** Aspose.Page for Java 24.11 (legújabb a kiadás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}