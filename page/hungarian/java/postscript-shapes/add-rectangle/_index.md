---
date: 2026-02-18
description: Ismerje meg, hogyan lehet téglalap alakzatokat rajzolni Java PostScriptben
  az Aspose.Page segítségével. Ez a lépésről‑lépésre útmutató bemutatja, hogyan állítsa
  be a festést, a téglalap színét Java-ban, és hogyan hozzon létre élénk grafikákat,
  miközben hatékony téglalap-rajzolást magyaráz.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Hogyan rajzoljunk téglalapot Java PostScriptben az Aspose.Page használatával
url: /hu/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan rajzoljunk téglalapot Java PostScript-ben az Aspose.Page segítségével

## Bevezetés
Ha **how to draw rectangle** alakzatokat kell létrehoznia egy Java PostScript fájlban, jó helyen jár. Ebben az útmutatóban végigvezetjük, hogyan használja az Aspose.Page for Java-t színes téglalapok hozzáadásához, a kitöltés és körvonal vezérléséhez, és a végeredményt PostScript dokumentumként mentse el. Pontosan meg fogja látni, hogyan **how to set paint**, hogyan definiálja a téglalap geometriáját, és miért ideális ez a megközelítés nyomtatható grafikák programozott generálásához. A útmutató végére megérti a **draw rectangle java** technikák szélesebb kontextusát, és hogy ezek hogyan illeszkednek a **java awt rectangle drawing** munkafolyamatokba.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Módosíthatom a téglalap színeit?** Igen – használja a `setPaint`-et bármely `java.awt.Color`-ral  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba működik teszteléshez; licenc szükséges a termeléshez  
- **Melyik oldalméretet használja a példában?** A4 (alapértelmezett `PsSaveOptions`)  
- **Kompatibilis a kód a Java 8+ verzióval?** Teljesen – standard AWT osztályokat használ  

## Mi az a “How to Draw Rectangle” a PostScript-ben?
A téglalap rajzolása egy PostScript dokumentumban azt jelenti, hogy meghatároz egy téglalap alakú területet, és azt kitölti, körvonalazza, vagy mindkettőt. Az Aspose.Page segítségével ezt ismerős **java awt rectangle drawing** osztályokkal teheti meg, ami megkönnyíti a kód olvasását és karbantartását.

## Miért használjuk az Aspose.Page-t téglalap grafika készítéséhez?
- **Cross‑platform**: Standard PostScript-et generál, amely bármely nyomtatón működik.  
- **Fine‑grained control**: A kitöltő színeket, körvonal színeket és vonalvastagságokat függetlenül állíthatja be.  
- **No external dependencies**: Csak a beépített AWT geometriai osztályokat használja, így nincs szükség további grafikai könyvtárakra.  

## Előfeltételek
Mielőtt belemerülne az útmutatóba, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:
- Alapvető Java programozási ismeretek.  
- Telepítve van az Aspose.Page for Java könyvtár. Ha nincs, töltse le a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalról.  
- Java fejlesztői környezet beállítva a gépén.  

## Csomagok importálása
A Java projektjében kezdje a szükséges csomagok importálásával. Ezek az importok hozzáférést biztosítanak az AWT `Color`, `BasicStroke` és `Rectangle2D` osztályaihoz, valamint az Aspose.Page alapvető dokumentumkezelő osztályaihoz.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Lépésről‑lépésre útmutató a téglalap rajzolásához Java PostScript-ben

### 1. lépés: Paint beállítása a téglalap kitöltéséhez  
**How to set paint** – az első téglalaphoz narancssárga kitöltő színt választunk. Ez bemutatja a **set rectangle color java** képességet.

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

### 2. lépés: Paint beállítása a téglalap körvonalazásához  
**Set rectangle color java** – most a paint-et pirosra állítjuk, és meghatározunk egy vonalvastagságot. Ennek a példának ez a része megmutatja, hogyan **draw rectangle java** egy egyedi vonalvastagsággal.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### 3. lépés: Aktuális oldal bezárása és dokumentum mentése  
A rajzolás után bezárjuk az oldalt és elmentjük a fájlt. Az oldal bezárása biztosítja, hogy minden rajzolási parancs ki legyen írásra a PostScript adatfolyamba.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Általános felhasználási esetek a téglalap rajzolásához
- **Invoice or receipt generation** – a téglalapok határolóként vagy kiemelt szakaszként működnek.  
- **Label creation** – színes dobozok rajzolása a termékinformációk elválasztásához.  
- **Simple charts** – kitöltött téglalapok használata oszlopdiagram elemeként.  
- **Custom printable forms** – téglalapok és szöveg kombinálása űrlapmezők létrehozásához.  

## Gyakori problémák és tippek
- **File path errors** – győződjön meg róla, hogy a `dataDir` fájl elválasztóval (`/` vagy `\\`) végződik.  
- **License exceptions** – a próbaverzió vízjelet ad hozzá; szerezzen be teljes licencet a termelési használathoz.  
- **Color visibility** – egyes nyomtatók eltérően értelmezhetik az RGB értékeket; először teszteljen egy egyszerű fekete téglalappal.  
- **Memory usage** – nagy dokumentumok esetén fontolja meg a stream kiürítését minden oldal után (`document.closePage()`).  

## Gyakran Ismételt Kérdések

**Q:** *Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?*  
A: Az Aspose.Page elsősorban Java-t támogat, de hasonló könyvtárak elérhetők más nyelvekhez.  

**Q:** *Elérhető próba verzió az Aspose.Page for Java-hoz?*  
A: Igen, felfedezheti az Aspose.Page for Java funkcióit a [free trial version](https://releases.aspose.com/) segítségével.  

**Q:** *Hol találok további segítséget és megbeszéléseket?*  
A: Látogassa meg a [Aspose.Page fórumot](https://forum.aspose.com/c/page/39), hogy a közösséggel kapcsolatba léphessen és segítséget kapjon.  

**Q:** *Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?*  
A: Ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).  

**Q:** *Hol vásárolhatok licencelt verziót az Aspose.Page for Java-hoz?*  
A: Licencelt verziót vásárolhat [itt](https://purchase.aspose.com/buy).  

**Additional Q&A**

**Q:** *Módosíthatom dinamikusan a téglalap méretét?*  
A: Igen – egyszerűen módosítsa a `Rectangle2D.Float(x, y, width, height)` paramétereket a `fill` vagy `draw` hívása előtt.  

**Q:** *Lehetséges szöveget hozzáadni a téglalap belsejéhez?*  
A: Természetesen. A téglalap rajzolása után használja a `document.drawString(...)`-t a kívánt betűtípussal és pozícióval.  

**Q:** *Az Aspose.Page támogat más alakzatokat, például köröket vagy sokszögeket?*  
A: Igen, az API olyan metódusokat biztosít, mint a `drawEllipse` és a `drawPolygon` különféle vektorgrafikákhoz.  

## Összegzés
Ebben az útmutatóban bemutattuk, hogyan **how to draw rectangle** alakzatokat hozhatunk létre egy Java PostScript dokumentumban, lefedtük a **how to set paint** beállítását, és megmutattuk, hogyan **set rectangle color java** használható az Aspose.Page segítségével. Most már szilárd alapja van élénk nyomtatható grafikák létrehozásához, legyen szó számlákról, címkékről vagy egyedi űrlapokról. Nyugodtan kísérletezzen különböző színekkel, vonalstílusokkal és további AWT alakzatokkal a kimenet gazdagításához.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}