---
title: Méretezze át az EPS-fájlokat Java nyelven az Aspose.Page segítségével
linktitle: EPS fájl átméretezése Java nyelven
second_title: Aspose.Page Java API
description: Az Aspose.Page for Java segítségével megtudhatja, hogyan lehet könnyedén átméretezni az EPS-fájlokat Java nyelven. Kövesse átfogó útmutatónkat a lépésenkénti utasításokért.
weight: 11
url: /hu/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Méretezze át az EPS-fájlokat Java nyelven az Aspose.Page segítségével

## Bevezetés
Üdvözöljük lépésenkénti útmutatónkban az EPS-fájlok Java nyelven történő átméretezéséről a hatékony Aspose.Page könyvtár használatával. Ha valaha is programozottan kellett módosítania az EPS-képek méretét, akkor jó helyen jár. Ebben az oktatóanyagban különféle átméretezési lehetőségeket vizsgálunk meg, beleértve a pontokat, hüvelykeket, millimétereket és százalékokat, így biztosítva az Ön egyedi igényeihez szükséges rugalmasságot.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következőkkel:
- Java Development Kit (JDK) telepítve a gépére.
-  Aspose.Page a Java könyvtárhoz. Letöltheti[itt](https://releases.aspose.com/page/java/).
- Alapvető ismeretek a Java programozásról.
## Csomagok importálása
Java-projektjében győződjön meg arról, hogy rendelkezik az Aspose.Page funkciók használatához szükséges importokkal. Íme egy példa:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Most bontsuk le az oktatóanyagot több lépésre az egyes átméretezési lehetőségekhez:
## Méretezze át az EPS-t pontok segítségével
### 1. lépés: Állítsa be a bemeneti adatfolyamot
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### 2. lépés: Inicializálja a PsDocument objektumot
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### 3. lépés: Bontsa ki az EPS-kép jelenlegi méretét
```java
Dimension oldSize = doc.extractEpsSize();
```
### 4. lépés: Hozzon létre egy kimeneti adatfolyamot
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### 5. lépés: Méretezze át és mentse pontokban
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Méretezze át az EPS-t hüvelyk használatával
Kövesse az 1. példához hasonló lépéseket, cserélje ki a „Ponts” szót „Inch”-re, és ennek megfelelően állítsa be az új méretet.
## Méretezze át az EPS-t milliméterekkel
Kövesse az 1. példához hasonló lépéseket, cserélje ki a „pontok” szót „milliméterre”, és ennek megfelelően állítsa be az új méretet.
## Méretezze át az EPS-t a százalékok használatával
Kövesse az 1. példához hasonló lépéseket, cserélje ki a „pontok” szót „százalékra”, és ennek megfelelően állítsa be az új méretet.
## Következtetés
Gratulálunk! Sikeresen megtanulta az EPS-fájlok átméretezését Java nyelven az Aspose.Page használatával. Ez az útmutató sokoldalú lehetőségeket kínál, amelyek biztosítják, hogy az átméretezési folyamatot az Ön egyedi igényeihez igazíthassa.

## GYIK
### Használhatom ezt a könyvtárat más képformátumokhoz?
Nem, az Aspose.Page kifejezetten PostScript- és EPS-fájlok kezelésére készült.
### Létezik ingyenes próbaverzió az Aspose.Page for Java számára?
Igen, felfedezheti az ingyenes próbaverziót[itt](https://releases.aspose.com/).
### Hol találhatok további segítséget és beszélgetéseket?
 Meglátogatni a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásért.
### Hogyan szerezhetek ideiglenes engedélyt?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Vannak példaprojektek?
 Igen, ellenőrizze a dokumentációt[itt](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
