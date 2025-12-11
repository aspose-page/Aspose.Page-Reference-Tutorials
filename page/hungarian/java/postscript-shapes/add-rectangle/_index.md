---
date: 2025-12-11
description: Tanulja meg, hogyan rajzoljon téglalap alakzatokat Java PostScriptben
  az Aspose.Page segítségével. Ez a lépésről‑lépésre útmutató bemutatja, hogyan állítsa
  be a festést, a téglalap színét Java-ban, és hogyan hozzon létre élénk grafikákat.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Hogyan rajzoljunk téglalapot Java PostScript-ben az Aspose.Page használatával
url: /hu/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan rajzoljunk téglalapot Java PostScript-ben az Aspose.Page segítségével

## Bevezetés
Ha **how to draw rectangle** alakzatokat kell létrehoznod egy Java PostScript fájlban, jó helyen jársz. Ebben az útmutatóban végigvezetünk az Aspose.Page for Java használatán, hogy színes téglalapokat adjunk hozzá, szabályozzuk a kitöltést és a körvonalat, és elmentsük az eredményt PostScript dokumentumként. Pontosan meg fogod látni, hogyan **how to set paint**, hogyan definiáljuk a téglalap geometriáját, és miért ideális ez a megközelítés nyomtatható grafikák programozott előállításához.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Page for Java  
- **Megváltoztathatom a téglalap színeit?** Igen – használd a `setPaint`-t bármely `java.awt.Color`-ral  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba verzió tesztelésre elegendő; a termeléshez licenc szükséges  
- **Milyen oldalméretet használ a példában?** A4 (alapértelmezett `PsSaveOptions`)  
- **Kompatibilis a kód a Java 8+-al?** Teljesen – standard AWT osztályokat használ  

## Előfeltételek
Mielőtt belemerülnél az útmutatóba, győződj meg róla, hogy a következő előfeltételek adottak:
- Alapvető Java programozási ismeretek.  
- Az Aspose.Page for Java könyvtár telepítve van. Ha nincs, töltsd le a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalról.  
- Java fejlesztői környezet beállítva a gépeden.

## Csomagok importálása
A Java projektedben kezdj el importálni a szükséges csomagokat:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hogyan rajzoljunk téglalapot Java PostScript-ben
Az alábbiakban a teljes munkafolyamatot láthatod, világos lépésekre bontva. Minden lépés rövid magyarázatot tartalmaz, majd az eredeti kódrészletet (változatlan).

### 1. lépés: Paint beállítása a téglalap kitöltéséhez  
**How to set paint** – az első téglalaphoz narancssárga kitöltőszínt választunk.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### 2. lépés: Paint beállítása a téglalap körvonalához  
**Set rectangle color java** – most a paint-et pirosra állítjuk, és meghatározunk egy vonalvastagságot.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### 3. lépés: Aktuális oldal bezárása és dokumentum mentése  
A rajzolás után bezárjuk az oldalt és elmentjük a fájlt.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Miért használjuk az Aspose.Page-et téglalap grafikákhoz?
- **Cross‑platform**: Szabványos PostScript-et generál, amely bármely nyomtatón működik.  
- **Fine‑grained control**: A kitöltőszíneket, körvonal színeket és vonalvastagságokat függetlenül állíthatod be.  
- **No external dependencies**: Csak a beépített AWT geometriai osztályokat használja.  

## Gyakori problémák és tippek
- **File path errors** – győződj meg róla, hogy a `dataDir` fájl elválasztóval (`/` vagy `\\`) végződik.  
- **License exceptions** – a próbaverzió vízjelet ad hozzá; a termeléshez teljes licenc szükséges.  
- **Color visibility** – egyes nyomtatók másként értelmezhetik az RGB értékeket; először egy egyszerű fekete téglalappal tesztelj.  

## Összegzés
Ebben az útmutatóban bemutattuk, hogyan **how to draw rectangle** alakzatokat hozunk létre egy Java PostScript dokumentumban, lefedtük, hogyan **how to set paint**, és megmutattuk, hogyan **set rectangle color java** használva az Aspose.Page-et. Nyugodtan kísérletezz különböző alakzatokkal, színekkel és vonalstílusokkal, hogy gazdag nyomtatható grafikákat hozz létre jelentésekhez, számlákhoz vagy egyedi nyomatokhoz.

## Gyakran feltett kérdések

### Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?
Az Aspose.Page elsősorban Java-t támogat, de hasonló könyvtárak elérhetők más nyelvekhez is.

### Elérhető próba verzió az Aspose.Page for Java-hoz?
Igen, felfedezheted az Aspose.Page for Java funkcióit a [free trial version](https://releases.aspose.com/).

### Hol találok további segítséget és megbeszéléseket?
Látogasd meg az [Aspose.Page forum](https://forum.aspose.com/c/page/39) közösséghez csatlakozni és segítséget kapni.

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?
Szerezz ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/).

### Hol vásárolhatok licencelt verziót az Aspose.Page for Java-hoz?
Vásárolj licencelt verziót [itt](https://purchase.aspose.com/buy).

**További kérdések és válaszok**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** Igen – egyszerűen módosítsd a `Rectangle2D.Float(x, y, width, height)` paramétereket a `fill` vagy `draw` hívása előtt.

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** Absolút. A téglalap rajzolása után használd a `document.drawString(...)`-t a kívánt betűtípussal és pozícióval.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** Igen, az API olyan metódusokat biztosít, mint a `drawEllipse` és a `drawPolygon` a különféle vektorgrafikákhoz.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}