---
date: 2025-12-07
description: Tanulja meg, hogyan méretezzen téglalapot, transzformáljon alakzatot,
  és alkalmazzon affín transzformációt Java-ban az Aspose.Page használatával PostScript
  dokumentumok létrehozásához.
language: hu
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Hogyan méretezzen egy téglalapot és alkalmazzon transzformációkat az Aspose.Page
  segítségével
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Scale Rectangle and Apply Transformations with Aspose.Page

## Bevezetés
Üdvözöljük egy átfogó útmutatóban, amely bemutatja a **Aspose.Page for Java** hatékony funkcióinak kihasználását különféle oldaltranszformációk végrehajtásához. Ebben az oktatóanyagról megtanulja, hogyan **méretezzen téglalapot**, hogyan transzformáljon (fordítsa) alakzatokat, forgassa el objektumokat, és hogyan **alkalmazzon affín transzformációt** technikákat **PostScript document** létrehozása közben. Ezek a képességek lehetővé teszik, hogy gazdag, grafika‑intenzív Java alkalmazásokat építsen alacsony szintű renderelési kód nélkül.

## Gyors válaszok
- **Hogyan méretezhetek egy téglalapot Java-ban az Aspose.Page segítségével?** Használja a `document.scale()` metódust a forma rajzolása előtt.  
- **Mozgathatok (transzformálhatok) egy alakzatot anélkül, hogy más grafikákat befolyásolna?** Igen—mentse el a grafikai állapotot, hívja meg a `document.translate(x, y)`-t, rajzoljon, majd állítsa vissza az állapotot.  
- **Melyik osztály hoz létre PostScript fájlt?** `PsDocument` a `PsSaveOptions`-szel együtt.  
- **Szükségem van licencre a termelési használathoz?** Egy érvényes Aspose.Page licenc szükséges a kereskedelmi telepítésekhez.  
- **Melyik Java verzió támogatott?** Az Aspose.Page a Java 8-as és újabb verziókkal működik.

## Előfeltételek
Mielőtt belemerülnénk a lépésről‑lépésre útmutatóba, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:

- Alapvető Java programozási ismeretek.
- Az Aspose.Page for Java könyvtár telepítve van. Letöltheti a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalról.
- Java integrált fejlesztői környezet (IDE) beállítva a gépén.

## Csomagok importálása
A Java projektjében importálja a szükséges csomagokat az Aspose.Page for Java használatához:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Mi az a „how to scale rectangle” az Aspose.Page-ben?
A téglalap méretezése megváltoztatja annak méretét az X és Y tengelyek mentén, miközben megőrzi az alakját. Az Aspose.Page a `scale(float sx, float sy)` metódust biztosítja, amely **affín transzformációt** alkalmaz az aktuális grafikai állapotra. Ez a **how to scale rectangle** kulcsszó mögötti alapvető technika.

## Hogyan transzformáljunk (fordítsunk) alakzatot az Aspose.Page segítségével
A transzformáció (fordítás) egy alakzatot új helyre helyez anélkül, hogy megváltoztatná méreteit. Ez a **how to translate shape** lényege. A grafikai állapot mentésével, a `translate(dx, dy)` alkalmazásával, a rajzolással, majd az állapot visszaállításával a többi objektum érintetlen marad.

## Példa 1: Nincs transzformáció
Az első példa egy egyszerű téglalapot rajzol, anélkül, hogy bármilyen transzformációt alkalmazna. Ez alapvonalként szolgál a későbbi példákkal való összehasonlításhoz.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Példa 2: Transzformáció
Itt bemutatjuk a **how to translate shape**-t, a grafikai kontextus 250 egységgel jobbra mozgatásával, mielőtt a második téglalapot rajzolnánk.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Példa 3: Méretezés
Ez a példa megválaszolja az elsődleges kérdést: **how to scale rectangle**. A téglalapot az eredeti szélességének 50 %-ára és magasságának 75 %-ára zsugorítjuk.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Hogyan forgassuk el az alakzatot Java-ban (rotate shape java)
A forgatás egy másik gyakori affín művelet. Bár a forgatáshoz tartozó kódrészletek a rövidség kedvéért kimaradtak, a minta azonos: mentse el a grafikai állapotot, hívja meg a `document.rotate(angle)`-t, rajzolja meg az alakzatot, majd állítsa vissza. Ez a gyakorlatban bemutatja a **rotate shape java** és a **how to rotate rectangle** kifejezéseket.

## Miért használjuk az Aspose.Page-t ezekhez a transzformációkhoz?
- **Device‑independent**: Írjon egyszer, generáljon PostScript vagy XPS fájlt platform‑specifikus kód nélkül.  
- **Fine‑grained control**: A grafikai állapot közvetlen elérése lehetővé teszi a transzformáció, méretezés, nyírás és forgatás kombinálását.  
- **Performance**: Alacsony terhelésű API, amely alkalmas nagy dokumentumok kötegelt feldolgozására.  

## Gyakori felhasználási esetek
- Nyomtatható számlák generálása dinamikus vonalkódokkal és logókkal.  
- Műszaki diagramok létrehozása, ahol a pontos méretezés és pozicionálás szükséges.  
- Többoldalas jelentések automatikus előállítása PostScript formátumban.

## Következtetés
Ebben az oktatóanyagban különféle transzformációkat vizsgáltunk a Java oldalmanipulációban az Aspose.Page for Java segítségével, különös tekintettel a **how to scale rectangle**, **how to translate shape** és egyéb affín műveletekre. A példák követésével fejlesztheti Java alkalmazásait fejlett oldalmanipulációs képességekkel, és **create PostScript document** kimeneteket hozhat létre, amelyek megfelelnek a professzionális kiadási szabványoknak.

## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java-t más dokumentumformátumokhoz?
Az Aspose.Page elsősorban a PostScript és XPS formátumok oldalmanipulációjára összpontosít.

### Hol találok több példát és dokumentációt az Aspose.Page for Java-hoz?
Látogassa meg a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalt a részletes információkért.

### Van ingyenes próba a Aspose.Page for Java-hoz?
Igen, ingyenes próbát érhet el [itt](https://releases.aspose.com/).

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?
Ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

### Hol kaphatok közösségi támogatást vagy tehetek fel kérdéseket az Aspose.Page for Java-val kapcsolatban?
Látogassa meg az [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) oldalt a közösségi megbeszélésekhez.

## Gyakran Ismételt Kérdések

**Q: Mi a különbség a `translate` és a `scale` között?**  
A: A `translate` a koordináta‑rendszer origóját mozgatja, míg a `scale` a rajzolt objektumok méretét változtatja az X és/vagy Y tengelyek mentén.

**Q: Kombinálhatok több transzformációt egyetlen grafikai állapotban?**  
A: Igen—ha a rajzolás előtt sorban meghívja a `translate`, `scale`, `rotate` vagy `shear` metódusokat, kombinált affín transzformációt hoz létre.

**Q: Hogyan állíthatom vissza a transzformációkat egy alakzat rajzolása után?**  
A: Használja a `document.writeGraphicsRestore()`-t a korábban mentett grafikai állapot visszaállításához.

**Q: Lehetséges egy téglalapot a középpontja körül elforgatni?**  
A: Természetesen. A téglalapot transzformálja az origóba, alkalmazza a `rotate(angle)`-t, majd a rajzolás előtt visszahelyezi.

**Q: Támogatja az Aspose.Page az anti‑aliasing-et a simább grafikákhoz?**  
A: Igen—állítsa be a megfelelő renderelési beállításokat a `PsSaveOptions`‑ban az anti‑aliasing engedélyezéséhez.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}