---
date: 2026-02-13
description: Tanulja meg, hogyan töltsön ki alakzatot színátmenettel, és hogyan rajzoljon
  kört színátmenettel Java PostScriptben az Aspose.Page használatával. Lépésről‑lépésre
  útmutató kóddal és tippekkel.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Alakzat kitöltése színátmenettel: Java PostScript radiális példa'
url: /hu/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fill Shape with Gradient: Java PostScript Radiális Példa

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan **fill shape with gradient** egy radiális színátmenet példájának létrehozásával egy PostScript dokumentumhoz az Aspose.Page for Java használatával. Lépésről lépésre végigvezetjük a folyamaton – a projekt beállításától egy sima radiális színátmenettel kitöltött kör megjelenítéséig – hogy azonnal szemrevaló grafikákat adhasson Java alkalmazásaihoz.

## Gyors válaszok
- **What does this tutorial create?** Egy PostScript fájlt (`.ps`) tartalmaz, amely egy radiális színátmenettel kitöltött kört tartalmaz.  
- **Which library is required?** Aspose.Page for Java (legújabb verzió).  
- **How long does implementation take?** Körülbelül 10‑15 perc a működő példa elkészítéséhez.  
- **Do I need a license?** Ideiglenes vagy teljes licenc szükséges a termelési használathoz; a ingyenes próba verzió fejlesztéshez megfelelő.  
- **Can I reuse the code for PDF or SVG?** Igen – az Aspose.Page több kimeneti formátumot támogat minimális módosítással.

## Hogyan töltsünk ki alakzatot színátmenettel PostScript-ben
Mielőtt a kódba merülnénk, tisztázzuk, miért fontos a “fill shape with gradient”. A színátmenetek professzionális, háromdimenziós hatást kölcsönöznek a grafikáknak raszteres képek nélkül. Az Aspose.Page segítségével ugyanazt a színátmenet logikát alkalmazhatja bármely vektor alakzatra – körökre, téglalapokra vagy egyedi útvonalakra – az összes támogatott kimeneti formátumban (PostScript, PDF, SVG).

## Mi az a radiális színátmenet?
A radiális színátmenet a színeket a középpontból kifelé változtatja, sima, kör alakú keveréket hozva létre. Ideális kiemelésekhez, gombháttérhez vagy bármilyen vizuális elemhez, amely természetes „ragyogás” hatást igényel.

## Miért használjuk az Aspose.Page-et radiális színátmenetekhez?
- **Device‑independent rendering** – ugyanúgy működik PostScript, PDF, SVG és más formátumokon.  
- **Full Java integration** – nincs natív kód, csak tiszta Java API-k.  
- **High‑quality output** – támogatja az anti‑aliasinget és a színtér vezérlést.

## Előfeltételek
- Alapvető ismeretek a Java programozásban.  
- JDK 8 vagy újabb telepítve a gépén.  
- Aspose.Page for Java könyvtár (letölthető a [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) oldalról).  

## Csomagok importálása
Először importáljuk a szükséges osztályokat. Ezek közé tartoznak a szabványos AWT grafikai típusok és az Aspose.Page API.

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

## 1. lépés: Dokumentum könyvtár beállítása
Határozza meg azt a mappát, ahová a generált PostScript fájl mentésre kerül. Cserélje le a helyőrzőt a rendszerén lévő valós útvonalra.

```java
String dataDir = "Your Document Directory";
```

## 2. lépés: Kimeneti adatfolyam létrehozása
Nyisson egy `FileOutputStream`-et, amely a cél `.ps` fájlra mutat. Ez az adatfolyam táplálja az Aspose.Page által generált bináris adatokat.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 3. lépés: Mentési beállítások létrehozása
Példányosítsa a `PsSaveOptions` osztályt. Testreszabhatja az oldal méretét, tömörítést stb., de az alapértelmezések megfelelőek ebben a példában.

```java
PsSaveOptions options = new PsSaveOptions();
```

## 4. lépés: PS dokumentum létrehozása
Hozza létre a `PsDocument` objektumot, átadva a kimeneti adatfolyamot és a mentési beállításokat. A `false` jelző azt mondja az Aspose.Page-nek, hogy ne nyisson meg automatikusan oldalt (mi manuálisan fogjuk megtenni).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 5. lépés: Kör létrehozása
A `Ellipse2D.Float` segítségével rajzolunk egy kört. A paraméterek `(x, y, width, height)`. A `width = height` beállítás tökéletes kört eredményez.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Hogyan rajzoljunk kört színátmenettel
Miután megvan az alakzat, a következő lépés a **draw circle with gradient**. A `RadialGradientPaint` alkalmazásával a körre, a kitöltési művelet automatikusan a definiált színátmenetet használja.

## 6. lépés: Színátmenet színek meghatározása
Készítsen két tömböt: egyet a színátmenetben megjelenő színeknek, egyet pedig a megfelelő tört pozícióknak (0 = középpont, 1 = szél).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 7. lépés: AffineTransform létrehozása
Az `AffineTransform` méretez és eltolja a színátmenetet, hogy illeszkedjen a körhöz. A `(scaleX, 0, 0, scaleY, translateX, translateY)` mátrix elvégzi a feladatot.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 8. lépés: Radiális színátmenet festék létrehozása
Most felépítjük a `RadialGradientPaint` objektumot. Ez a középpontot, a sugárt, a fókuszpontot, a színarányokat, a színtömböt, a ciklusmetódust, a színtér-típust és a most definiált transzformációt veszi át.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## 9. lépés: Festék beállítása és kör kitöltése
Alkalmazza a színátmenet festéket a dokumentumra, és töltse ki a korábban definiált kört. Ez a **radial gradient example** magja, és bemutatja, hogyan **fill shape with gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## 10. lépés: Oldal lezárása és dokumentum mentése
Fejezze be az oldalt, írja a tartalmat a lemezre, és zárja le az adatfolyamot. A PostScript fájl most már készen áll a megtekintésre bármely PS megjelenítővel.

```java
document.closePage();
document.save();
```

Gratulálunk! Sikeresen létrehozott egy radiális színátmenet példát Java PostScript-ben az Aspose.Page használatával. Most már van egy újrahasználható minta a **fill shape with gradient**-hez, amely más alakzatokra és kimeneti formátumokra is adaptálható.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|---------|----------|
| **FileNotFoundException** when opening the output stream | Ellenőrizze, hogy a `dataDir` egy létező mappára mutat, és van írási jogosultsága. |
| Gradient looks flat or missing | Győződjön meg róla, hogy a `fractions` tömb hossza megegyezik a `colors` tömb hosszával, és az `AffineTransform` helyesen méretez. |
| Colors appear inverted | Cserélje fel a színek sorrendjét a `colors` tömbben, vagy módosítsa a `focus` pont koordinátáit. |

## Gyakran Ismételt Kérdések

**Q: Hol találhatom meg az Aspose.Page for Java dokumentációját?**  
A: A teljes API referencia elérhető [here](https://reference.aspose.com/page/java/).

**Q: Hogyan tölthetem le az Aspose.Page for Java-t?**  
A: Szerezze be a legújabb JAR-t a [releases page](https://releases.aspose.com/page/java/) oldalról.

**Q: Elérhető ingyenes próba verzió?**  
A: Igen – töltse le a próba verziót [here](https://releases.aspose.com/).

**Q: Kaphatok ideiglenes licencet teszteléshez?**  
A: Természetesen, kérjen egyet a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalról.

**Q: Hol kaphatok közösségi támogatást?**  
A: Csatlakozzon a beszélgetéshez az [Aspose.Page forum](https://forum.aspose.com/c/page/39) oldalon.

## Következtetés
Ebben az útmutatóban egy teljes **radial gradient example**-t építettünk egy PostScript dokumentumhoz az Aspose.Page for Java használatával. A lépések követésével most már van egy újrahasználható minta a **fill shape with gradient**-hez, amelyet PDF, SVG vagy bármely más, az Aspose.Page által támogatott formátumra adaptálhat. Kísérletezzen különböző színekkel, sugarakkal és alakzatokkal, hogy gazdagítsa Java grafikai projektjeit.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}